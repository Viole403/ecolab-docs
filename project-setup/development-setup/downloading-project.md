---
description: >-
  This guide outlines two methods for downloading projects from GitHub for use
  in Android Studio:
---

# Downloading Project

## **Downloading from GitHub**

GitHub is a popular platform for hosting code repositories. Here's how to import a project from GitHub:

1. **Locate the Repository:** Find the desired project on [Here](https://github.com/Viole403/ecolab).
2. **Download the Project:** Click the green "Code" button on the repository's main page (see image below).

\[Image]

1. **Choose Download Option:** In the dropdown menu, select "Download ZIP" to download a compressed archive of the entire project. This archive contains all the necessary files and folders for the Ecolab project.
2. **Save the ZIP File:** Choose a suitable location on your computer to save the downloaded ZIP file. It's recommended to create a dedicated folder for downloaded projects.
3. **Extract the Archive:** Once the download is complete, use a file extraction tool (e.g., WinRAR, 7-Zip) to uncompress the downloaded ZIP file. This will create a new folder containing all the project's files and subfolders.

## **Downloading from a Git**

If you're familiar with Git, an alternative method is to clone the repository directly using the command line. Here's a quick overview:

1. **Open a Terminal:** Launch your terminal application (Command Prompt on Windows, Terminal on macOS/Linux).
2. **Navigate to Project Directory:** Use the `cd` command to change the directory to where you want to clone the project files.
3.  **Clone the Repository:** Type the following command (Bash):\


    ```bash
    $ git clone https://github.com/Viole403/ecolab.git
    ```



    Press Enter to execute the command. This will download and clone the Ecolab repository into a new folder named `Ecolab` (or the name specified in the URL).

**Next Steps**

Once you have downloaded the project files (either as a ZIP archive or a Git clone), you're ready to import them into Android Studio for development. Look for a guide on "Importing Existing Projects into Android Studio" for further instructions.
