# Download-Folder-Organizer
A simple Python automation script that organizes files in a download folder into separate categories based on their file extensions.  Instead of manually sorting downloaded files, this script scans the folder and moves each file into the appropriate category folder.
Features
📂 Automatically scans a download directory
🖼️ Organizes images
🎬 Organizes videos
🎵 Organizes music files
📦 Organizes compressed/archive files
📄 Organizes documents
⚙️ Organizes setup/installer files
💻 Organizes programming files
🎨 Organizes design files
📁 Places unrecognized file types into others
⚡ Uses Python's built-in os and shutil modules
🛠️ Technologies Used
Python 3
os
shutil
📦 Requirements

No external Python packages are required.

The project uses Python's built-in libraries:

import os
import shutil
🚀 Installation

Clone the repository:

git clone https://github.com/your-username/download-folder-organizer.git
cd download-folder-organizer
⚙️ Configuration

Before running the script, update the download folder path:

os.chdir("E:\downloads")

Replace it with the location of your own Downloads folder.

For example:

os.chdir(r"C:\Users\YourName\Downloads")

Tip: Using a raw string (r"...") is recommended for Windows paths.

📁 Supported Categories

The script currently supports the following extensions:

Category	Extensions
🖼️ Images	.jpg, .png, .jpeg, .gif
🎬 Videos	.mp4, .mkv
🎵 Music	.mp3, .wav
📦 Archives	.zip, .tgz, .rar, .tar
📄 Documents	.pdf, .docx, .csv, .xlsx, .pptx, .doc, .ppt, .xls
⚙️ Setup	.msi, .exe
💻 Programs	.py, .c, .cpp, .php, .C, .CPP
🎨 Design	.xd, .psd

These categories and extensions are defined in the script's extentions dictionary.

▶️ Usage

Run the script:

python "Organized download folder with different categories(2).py"

The script will:

Open the configured Downloads folder.
Get a list of files.
Check each file's extension.
Determine its category.
Move the file to the corresponding category directory.
Move unsupported file types to others.

The categorization is handled by the sorting() function.

📊 Example
Before
Downloads/
├── photo.jpg
├── movie.mp4
├── song.mp3
├── report.pdf
├── project.py
├── archive.zip
└── installer.exe
After
download-sorting/
├── images/
│   └── photo.jpg
│
├── videos/
│   └── movie.mp4
│
├── musics/
│   └── song.mp3
│
├── documents/
│   └── report.pdf
│
├── programs/
│   └── project.py
│
├── zip/
│   └── archive.zip
│
└── setup/
    └── installer.exe

Files that don't match a configured extension are moved to:

download-sorting/others/




🔄 How It Works
                 Downloads Folder
                        │
                        ▼
                  Read All Files
                        │
                        ▼
                Check File Extension
                        │
          ┌─────────────┴─────────────┐
          ▼                           ▼
    Known Extension             Unknown Extension
          │                           │
          ▼                           ▼
   Find Category                    others/
          │
          ▼
    Move File to
   Category Folder
⚠️ Important Notes
1. Folder Structure

The script expects the destination structure to exist:

download-sorting/
├── images/
├── videos/
├── musics/
├── zip/
├── documents/
├── setup/
├── programs/
├── design/
└── others/
2. Duplicate Files

If a file with the same name already exists in the destination, the script prints:

filename is already exist

The current implementation catches the move error and continues processing.

3. File Extensions

Extension matching is performed using endswith(), so the current implementation is case-sensitive in general, although some uppercase extensions are explicitly included in the configuration.
