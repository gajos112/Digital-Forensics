# AUTO-START PROGRAMS

NTUSER.dat\Software\Microsoft\Windows\CurrentVersion\Run

NTUSER.dat\Software\Microsoft\Windows\CurrentVersion\RunOnce

# Windows XP Search History
NTUSER.DAT\Software\Microsoft\Search Assistant\ACMru

# Windows 7 Search History
NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\WordWheelQuery

# Windows 8 Search History
NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\SearchHistory

# Windows 8.1 Search History
\Users\<USER>\AppData\Local\Microsoft\Windows\ConnectedSearch\History

# Internet Explorer Typed URLs

NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\TypedPaths

# Recently Accessed Files

NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs

- MRUList shows the order in which the files were accessed. 
– The most recent file opened will be first.

# Microsoft Office Recent Documents

NTUSER.DAT\Software\Microsoft\Office\14.0\Word\FileMRU

NTUSER.DAT\Software\Microsoft\Office\14.0\Excel\FileMRU

NTUSER.DAT\Software\Microsoft\Office\14.0\Powerpoint\FileMRU 

- Office XP - Version 10.0

- Office 2003 - Version 11.0 

- Office 2007 - Version 12.0

- Office 2010 - Version 14.0

# Common Dialogs API (ComDlg32) 
**Open and Save As APIs**  


NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSaveMRU **(XP)**

NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePidMRU **(Vista/7/8)**


<br/>
**Last Visited - records specific executable used to open the files along with the directory that was last accessed.**  

NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedMRU **(XP)**

NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedPidMRU **(Vista/7/8)**

# Commands Executed from the Run Box

NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU 

MRU List provides the order in which the commands were executed.

# UserAssit

Records what application(s) a user has run, when and how many times: 

NTUSER\Software\Microsoft\Windows\CurrentVersion\Explorer\UserAssist\{GUID}\Count

- Valuable resource to determine user activity and technical knowledge.

- Values are encoded using a simple substation cipher (ROT13).

- Run count starts a 6(?) .... some viewers will automatically adjust this value so it is important to know what your tool is doing 

- {CEBFF5CD-ACE2-4F4F-9178-9926F41749EA} = Executable File

- {F4E57C4B-2036-45F0-A9AB-443BCFE33D9F} = Shortcut File Execution

**Win XP/Vista**

All values begin with 

•UEME_RUNPATH 

•Launched from the Absolute Path 

•UEME_RUNCPL 

•Launched from the Control Panel Applet 

•UEME_RUNPIDL 

•Launched from a Shortcut 

•UEME_UIQCUT 

•Launched from the Quick Launch Menu 

•UEME_UISCUT 

•Launched from a Desktop Shortcut 

•UEME_UITTOOLBAR •Launched from the Windows Explorer ToolbarNTUSER.DAT HIVE

**Win 7/8**

•http://www.aldeid.com/wiki/Windows-userassist-keys#Translation_of_directoriesNTUSER.DAT HIVE
