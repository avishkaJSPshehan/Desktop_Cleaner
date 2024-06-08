# File Organizer 📂✨

Welcome to the **File Organizer** project! This script helps you organize files in a specified directory by sorting them into subfolders based on their file extensions. It's a simple and efficient way to keep your files neat and easy to find.

## Features 🎯
- Automatically organizes files in a given directory by their extensions.
- Creates subfolders for each file type if they don't already exist.
- Moves files into the appropriate subfolders.

## Requirements 🛠️
- Python 3.x

## Setup Instructions 🚀

### Clone the Repository
First, clone the repository to your local machine:
```bash
git clone https://github.com/avishkaJSPshehan/Desktop_Cleaner.git
cd Desktop_Cleaner
```

## How to Use 📖

1. **Run the Script**: Execute the script using Python:
   ```bash
   python file_organizer.py
   ```
   
2. **Enter Folder Path**: When prompted, enter the full path to the folder you want to organize:
   ```
   Enter Folder Path: /path/to/your/folder
   ```

3. **Watch the Magic Happen**: The script will list all files in the specified folder and sort them into subfolders based on their extensions.

### Example
Given a directory with the following files:
```
document.pdf
photo.jpg
script.py
notes.txt
```
After running the script, the directory will be organized as:
```
pdf/
  └── document.pdf
jpg/
  └── photo.jpg
py/
  └── script.py
txt/
  └── notes.txt
```

## Project Structure 📂
```
file-organizer/
├── file_organizer.py  # The main script
├── README.md          # Project readme file
└── LICENSE            # License file
```

## Code Explanation 📝
```python
import os
import shutil

path = input("Enter Folder Path : ")
files = os.listdir(path)
print(files)

for file in files:
    filename, extension = os.path.splitext(file)
    extension = extension[1:]

    if os.path.exists(path + '/' + extension):
        shutil.move(path + '/' + file, path + '/' + extension + '/' + file)
    else:
        os.makedirs(path + '/' + extension)
        shutil.move(path + '/' + file, path + '/' + extension + '/' + file)
```

- **Imports**: The script uses the `os` and `shutil` modules for interacting with the file system and moving files.
- **Path Input**: Prompts the user to enter the path to the folder they want to organize.
- **File Listing**: Lists all files in the specified directory.
- **Sorting Logic**: 
  - Extracts the file extension.
  - Checks if a subfolder for the extension exists; if not, creates it.
  - Moves the file into the appropriate subfolder.

## Contributions 🤝
Contributions are welcome! If you have suggestions or find any bugs, feel free to submit a pull request or open an issue.

---

Happy organizing! 🎉📂

---

Feel free to customize the script and make it your own. This simple tool can save you a lot of time and keep your files neatly organized.
