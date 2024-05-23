<h1>Keylogger</h1>

<h2>Setup</h2>

1. Clone the repository

   ```bash
    git clone https://github.com/Matteo406/keylogger.git
   ```

   ```bash
    git clone git@github.com:Matteo406/keylogger.git
   ```

2. Copy the Repository into the desired Repository where you have the `README.md` file where you want to add your keylogger statistics. You dont need the `.git` folder in the new Repository. You DO need the `.github` folder and the rest in the new folder.

3. Install the requirements in the new folder
   ```bash
    pip install -r requirements.txt
   ```
4. Create the `.env` file

   1. Add the path to the log file
      ```env
      PATH_TO_LOGFILE=/path/to/log/file
      ```
   2. Add the path to your Repository
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
   ```

   ```txt
   From: 17 May 2024 - To: 17 May 2024

   Total Keystrokes: 1862
   Total Mouse Clicks: 302
   ```

    <!--END_SECTION:activity-->

   ```

   ```
