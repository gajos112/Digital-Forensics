# RunMRU Start->Run

**Description:**
Whenever someone does a Start -> Run command, it will log the entry for the command they executed.

**Location:**
NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU


# Typed Path

**Description:**

Registry Key that will track full path typed in explorer.

**Location:**

- NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\TypedPAths

# UserAssist

**Description:** 
GUI-based programs launched from the desktop are tracked in the launcher on a Windows System.

**Location:** 
NTUSER.DAT HIVE NTUSER.DAT\Software\Microsoft\Windows\Currentversion\Explorer\UserAssist\{GUID}\Count

**Interpretation:**
All values are ROT-13 Encoded
 
# Open/Save MRU

**Description:**

In simplest terms, this key tracks files that have been opened or saved within a Windows shell dialog box. This happens to be a big data set, not only including web browsers like Internet Explorer and Firefox, but also a majority of commonly used applications.

**Location:**

- XP: NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSaveMRU

- Win7: NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\OpenSavePIDlMRU
 
# Last Visited MRU

**Description:**

Tracks the specific executable used by an application to open the files documented in the OpenSaveMRU key. In
addition, each value also tracks the directory location for the last file that was accessed by that application.
Example: Notepad.exe was last run using the C:\Users\<Username>\Desktop folder

**Location:**

- XP NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedMRU

- Win7 NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\ComDlg32\LastVisitedPidlMRU

# Recent Files

**Description:**

Registry Key that will track the last files and folders opened and is used to populate data in “Recent” menus of the Start menu.

**Location:** 

- NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs

# Office Recent Files

**Description:**

MS Office programs will track their own Recent Files list to make it easier for the user to remember the last file they were editing.

**Location:**

- NTUSER.DAT\Software\Microsoft\Office\VERSION

# Jump Lists

**Description:**

• The Windows 7 task bar (Jump List) is engineered to allow users to “jump” or access items they frequently
or have recently used quickly and easily. This functionality cannot only be recent media files, but recent tasks as well. 

• The data stored in the AutomaticDestinations folder will each have a unique file prepended with the AppID of the associated application.

**Location:**

- Win7 C:\Users\<user>\AppData\Roaming\Microsoft\Windows\Recent\ AutomaticDestinations


# Prefetch

**Description:**

• Increases performance of a system by pre-loading code pages of commonly used applications. Cache Manager monitors all files and directories referenced for each application or process and maps them into a
.pf file. Utilized to know an application was executed
on a system.

• Limited to 128 files on XP and Win7

• (exename)-(hash).pf

**Location:**

Win7/XP C:\Windows\Prefetch

# Shell bags

**Description:**

• Can track user window viewing preferences to Windows Explorer

• Can be utilized to tell if activity occurred in a folder

• In some cases, you can see the files from a specific folder as well

Location:

XP NTUSER.DAT\Software\Microsoft\Windows\Shell\Bags
XP NTUSER.DAT\Software\Microsoft\Windows\Shell\BagMRU
XP NTUSER.DAT\Software\Microsoft\Windows\ShellNoRoam\Bags
XP NTUSER.DAT\Software\Microsoft\Windows\ShellNoRoam\BagMRU

Win7 USRCLASS.DAT\Local Settings\Software\Microsoft\Windows\Shell\Bags
Win7 USRCLASS.DAT\Local Settings\Software\Microsoft\Windows\Shell\BagMRU
Win7 NTUSER.DAT\Software\Microsoft\Windows\Shell\BagMRU
Win7 NTUSER.DAT\Software\Microsoft\Windows\Shell\Bags

# Shortcut (LNK) Files

**Description:**

• Shortcut Files automatically created by Windows
 - Recent Items
 - Opening local and remote data files and documents will generate a shortcut file (.lnk)
 
**Location:**

XP C:\Documents and Settings\<username>\Recent\

Win7 C:\Users\<user>\AppData\Roaming\Microsoft\Windows\Recent\
Win7 C:\Users\<user>\AppData\Roaming\Microsoft\Office\Recent\

# Shimcache

**Description:**

Shimcache also known as AppCompatCache, is a component of the Application Compatibility Database, which was created by Microsoft (beginning in Windows XP) and used by the operating system to identify application compatibility issues.

The cache stores various file metadata depending on the operating system, such as:

- File Full Path

- File Size

- $Standard_Information (SI) Last Modified time

- Shimcache Last Updated time

- Process Execution Flag

Similar to a log file, the Shimcache also “rolls” data, meaning that the oldest data is replaced by new entries.
