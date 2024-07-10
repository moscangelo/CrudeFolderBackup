# Crude Folder Backup
A python script that crudely backs up a folder every so often. This is most useful as a way to create temporary backups of videogame saves that would otherwise become overridden due to frequent auto-saving.

## Setup
Requirements:
- It has been tested only on Widows 11 so far. It should work on other OS in theory.
- Python 3 or newer. [Download it here](https://www.python.org/downloads/).
- The following python modules: os, shutil, time, and filecmp. They're part of the Standard Library and should come pre-installed; in case they're not you can run `pip install os shutil time filecmp` in the command prompt.
- A text editor. [Notepad++ is the simplest option](https://notepad-plus-plus.org/downloads/).

Configuration:
1. Locate or create the Source Folder and the Backup Folder. You need the full path for each folder, such as `C:/Users/User/Desktop/SourceFolder`. :warning: Note how the divisors are `/`, not `\`, as the latter will break the script.
2. Open the script `backup_script.py` with a text editor. 
3. In the Configuration section, you will find two variables that you must edit for the script to operate:
   - On `source_folder`, replace the default value of `C:/SourceFolder` with the Source Folder path, as explained on step 1. This is the folder that will backed up. It will be regularly checked for new or updated files. 
   - On `backup_folder`, replace the default value of `C:/BackupFolder` with the Backup Folder path, as explained on step 1. This is the folder that will contain the backups. Each backup will be contained in its own separate and newly created subfolder.
4. In the Configuration section, you will also find two variables that change how the script operates:
   - `max_backups` (default is `25`) specifies how many backups will be allowed to be present at any one time, before the script starts deleting the oldest backup to make space for the newest one. This is a crude script, each backup will contain the full contents of the Source Folder, so make sure you're not overdoing it! :warning: If your Source Folder contains large files and/or a great number of files, please reconsider using this script altogether. This is meant for folders with a small number of small files that are updated frequently.
   - `backup_interval` (default is `5`) specifies how often the backups will be attempted, in seconds. A backup will only occurr if the script detects that the contents of the Source Folder are different from the contents within the latest backup subfolder.
5. Save the script.
6. Run the script by opening it with python. It should display a command prompt, where a new log message should be appearing regularly, once every X seconds, as per `backup_interval`.
7. If the script is not operating as expected, please review all Requirements and all previous steps before opening an issue. Thank you!