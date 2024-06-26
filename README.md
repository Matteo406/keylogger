<h1>Keylogger and Shortcut Analyzer</h1>

This Python script is a friendly tool for logging and analyzing keyboard and mouse events. It is not malware. It is designed to monitor user interactions with the system, such as key presses and mouse clicks, and then analyze these events to generate statistics. These statistics include the number of clicks, key presses, and specific keyboard shortcuts used. The script also includes functionality to commit and push these statistics to a Git repository on a scheduled basis. It is important to note that this script should only be used for legitimate purposes and with the user's consent.

**Features**

- _Keylogging_: The tool logs every key press and mouse click event, storing them for further analysis.
- _Shortcut Analysis_: The tool is capable of recognizing a variety of common shortcuts and key combinations, such as copy (Ctrl+C), paste (Ctrl+V), save (Ctrl+S), cut (Ctrl+X), undo (Ctrl+Z), redo (Ctrl+Y), select all (Ctrl+A), find (Ctrl+F), replace (Ctrl+H), and print (Ctrl+P).
- _Event Analysis_: The tool analyzes the logged events, counting the number of clicks, key presses, and each recognized shortcut or key combination.
- _Data Persistence_: The analyzed data is stored in a JSON file, which is updated after each analysis. If the file already exists, the new data is added to the existing data.
- _Git Integration_: The tool is integrated with Git, allowing it to commit and push the updated data file to a specified repository every hour.
- _Logging_: The tool uses Python's logging module to log informational messages about its operation, which can be useful for debugging and understanding its behavior.
- _Lock File Mechanism_: The tool uses a lock file to ensure that only one instance of the script is running per day. The lock file contains the timestamp of the last script start.
- _Error Handling_: The tool has robust error handling, logging any errors that occur during its operation and cleaning up the lock file before exiting.

**Example**

```txt
keyboard events:
AmountOfPress        257        ████████████████████ 100.00 %
AmountOfCopy         2          ░░░░░░░░░░░░░░░░░░░░ 0.78 %
AmountOfPaste        3          ░░░░░░░░░░░░░░░░░░░░ 1.17 %
AmountOfSave         7          ░░░░░░░░░░░░░░░░░░░░ 2.72 %
AmountOfCut          1          ░░░░░░░░░░░░░░░░░░░░ 0.39 %
AmountOfUndo         1          ░░░░░░░░░░░░░░░░░░░░ 0.39 %
AmountOfRedo         0          ░░░░░░░░░░░░░░░░░░░░ 0.00 %
AmountOfSelectAll    1          ░░░░░░░░░░░░░░░░░░░░ 0.39 %
AmountOfFind         2          ░░░░░░░░░░░░░░░░░░░░ 0.78 %
AmountOfReplace      0          ░░░░░░░░░░░░░░░░░░░░ 0.00 %
AmountOfPrint        0          ░░░░░░░░░░░░░░░░░░░░ 0.00 %

```

<h2>Setup</h2>

1. Clone the repository

   ```bash
    git clone https://github.com/Matteo406/keylogger.git
   ```

   ```bash
    git clone git@github.com:Matteo406/keylogger.git
   ```

2. Copy the Repository into the desired Repository where you have the `README.md` file where you want to add your keylogger statistics. You dont need the `.git` folder in the new Repository. You DO need the `.github` folder and the rest in the new folder. the `createVBS.py` file you only need one time in the beginning to create the script. The `updateREADEME.py` file is needed for the GitHub Action flow.

3. Install the requirements in the new folder
   ```bash
    pip install -r requirements.txt
   ```
4. Create the `.env` file

   1. Add the path to your Repository

   ```env
   PATH_TO_REPO=/path/to/repo
   ```

5. Run the `createVBS.py` script in order to create the VBS file

   ```bash
    python createVBS.py
   ```

6. Check if the VBS file has been created in the AutoStart folder

   1. Open the Run dialog box by pressing `Win + R`
   2. Type `shell:startup` and press `Enter`
   3. Check if the `keylogger.vbs` file is present

7. Create a section in the README.md file where you want to add the statistics. It is important that you add the ```txt tag to the code block and the start and end tags for the activity section

   ```markdown
   <!--START_SECTION:activity-->

   <!--END_SECTION:activity-->
   ```

8. Start the script by double clicking the `keylogger.vbs` file in the AutoStart folder or restart your computer. The script will start automatically. You know that the script is running when you see the `taskLog.log` file in the AutoStart folder and a `script.lock` file.
