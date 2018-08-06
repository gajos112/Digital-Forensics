#serAssist

**Description:** 
GUI-based programs launched from the desktop are tracked in the launcher on a Windows System.

**Location:** 
NTUSER.DAT HIVE NTUSER.DAT\Software\Microsoft\Windows\Currentversion\Explorer\UserAssist\{GUID}\Count

**Interpretation:**
All values are ROT-13 Encoded

• GUID for XP
 - 75048700 Active Desktop
 
• GUID for Win7
 - CEBFF5CD Executable File Execution
 - F4E57C4B Shortcut File Execution
 
• Program Locations for Win7 Userassist
 - ProgramFilesX64 6D809377-…
 - ProgramFilesX86 7C5A40EF-…
 - System 1AC14E77-…
 - SystemX86 D65231B0-…
 - Desktop B4BFCC3A-…
 - Documents FDD39AD0-…
 - Downloads 374DE290-…
 - UserProfiles 0762D272-…
 
# Last Visited MRU

**Description:**

Tracks the specific executable used by an application to open the files documented in the OpenSaveMRU key. In
addition, each value also tracks the directory location for the last file that was accessed by that application.
Example: Notepad.exe was last run using the C:\Users\<Username>\Desktop folder

**Location:**

- XP NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedMRU

- Win7 NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedPidlMRU

**Interpretation:**

Tracks the application executables used to

Jump Lists
Description:
• The Windows 7 task bar (Jump List) is engineered to
allow users to “jump” or access items they frequently
or have recently used quickly and easily. This
functionality cannot only be recent media files, but
recent tasks as well.
• The data stored in the AutomaticDestinations folder
will each have a unique file prepended with the
AppID of the associated application.
Location:
Win7 C:\Users\<user>\AppData\Roaming\Microsoft\
Windows\Recent\ AutomaticDestinations
Interpretation:
• First time of execution of application.
- Creation Time = First time item added to the AppID
file.
• Last time of execution of application w/file open.
- Modification Time = Last time item added to the
AppID file.
• List of Jump List IDs -> http://www.forensicswiki.
org/wiki/List_of_Jump_List_IDs

Prefetch
Description:
• Increases performance of a system by pre-loading
code pages of commonly used applications. Cache
Manager monitors all files and directories referenced
for each application or process and maps them into a
.pf file. Utilized to know an application was executed
on a system.
• Limited to 128 files on XP and Win7
• (exename)-(hash).pf
Location:
Win7/XP C:\Windows\Prefetch
Interpretation:
• Each .pf will include last time of execution, # of times
run, and device and file handles used by the program
• Date/Time File by that name & path was first executed
- Creation Date of .pf file (-10 seconds)
• Date/Time File by that name & path was last executed
- Embedded last execution time of .pf file
- Last Modification Date of .pf file (-10 seconds)

Shell bags
Description:
• Can track user window viewing preferences to Windows
Explorer
• Can be utilized to tell if activity occurred in a folder
• In some cases, you can see the files from a specific folder as
well
Location:
XP NTUSER.DAT\Software\Microsoft\Windows\Shell\Bags
XP NTUSER.DAT\Software\Microsoft\Windows\Shell\BagMRU
XP NTUSER.DAT\Software\Microsoft\Windows\ShellNoRoam\
Bags
XP NTUSER.DAT\Software\Microsoft\Windows\ShellNoRoam\
BagMRU
Win7 USRCLASS.DAT\Local Settings\Software\Microsoft\
Windows\Shell\Bags
Win7 USRCLASS.DAT\Local Settings\Software\Microsoft\
Windows\Shell\BagMRU
Win7 NTUSER.DAT\Software\Microsoft\Windows\Shell\BagMRU
Win7 NTUSER.DAT\Software\Microsoft\Windows\Shell\Bags
Interpretation:
Store information about which folders were most recently
browsed by the user.

Shortcut (LNK) Files
Description:
• Shortcut Files automatically created by Windows
 - Recent Items
 - Opening local and remote data files and documents
will generate a shortcut file (.lnk)
Location:
XP C:\Documents and Settings\<username>\Recent\
Win7 C:\Users\<user>\AppData\Roaming\Microsoft\
Windows\Recent\
Win7 C:\Users\<user>\AppData\Roaming\Microsoft\
Office\Recent\
Note these are primary locations of LNK files. They can
also be found in other locations.
Interpretation:
• Date/Time File of that name was first opened
- Creation Date of Shortcut (LNK) File
• Date/Time File of that name was last opened
- Last Modification Date of Shortcut (LNK) File
• LNKTarget File (Internal LNK File Information) Data:
- Modified, Access, and Creation times of the target file
- Volume Information (Name, Type, Serial Number)
- Network Share information
- Original Location
- Name of System
