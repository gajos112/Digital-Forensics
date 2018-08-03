# ShimCache
Introduced in Windows 95 and it remains today a mechanism to ensure backward compatibility of older
binaries into new versions op-erating systems. ShimCache acts as a proxy layer between the old application and the new operating system. 
From a forensics perspective the ShimCache is valuable because the cache tracks metadata for binary  that was executed and stores it 
in the ShimCache.

Tools: From Kernel memory, you can parse it and analyze it with Volatility ShimCache and ShimCacheMem plugin. 

# ShellBags
Stores folder settings in the registry. Dimensions of folder is stored as ShellBags in action. 
This information is stored in the user profile hive 
- “NTUSER.dat” in “C:\Users\%Username%\” 
- “UsrClass.dat” in “%LocalAppData%\Microsoft\Windows”. 

When a profile is loaded into the registry, both hives are mounted into the HKEY_USERS and 
then then linked to the root key HKEY_CURRENT_USER and HKEY_CURRENT_USER\Software\Classes respectively.

On Windows XP and 2003 the ShellBags registry keys are stored at: 
- HKEY_USERS\{SID}\Software\​Microsoft\Windows\Shell\ and HKEY_USERS\{SID}\Software\​Microsoft\Windows\ShellNoRoam\.  

On Windows 7 and beyond the ShellBags registry keys are stored at 
- “HKEY_USERS\{SID}_Classes\​Local Settings\Software\​Microsoft\Windows\Shell\”.

# UserAssist
The UserAssist registry key keeps track of the applications that were executed by a particular user. The data is encoded using ROT-13 substitution cipher and maintained on the registry key HKEY_USERS\{SID}\Software\​Microsoft\Windows\CurrentVersion​\Explorer\UserAssist.

# LNK Files
LNK files are Windows Shortcuts. Windows operating system behind the scenes keeps track of recently opened files by creating LNK files within the directory “C:\Documents and Settings\%USERNAME%\Recent\”.

The LNK files, like JumpLists, are stored in Shell Link Binary File Format known as [MS-SHLLINK]. When parsed, the LNK file, contains metadata that, among other things, shows the target file Standard Information timestamps, path, size and MFT entry number. 

*This information is maintained even if the target file does no longer exists on the file system.*

#Jump Lists
Maintain the records of recently accessed files and folders and group them as per application basis. Before the feature was introduced, forensic analysts had access to a short list of Most Recently Used (MRU) and Most Frequently Used (MFU) items in the Windows Registry.

Types:
**- automatic** (autodest, or *.automaticDestinations-ms) files

**- custom** (custdest, or *.customDestinations-ms) files

**E- xplorer StartPage2** ProgramsCache Registry valu
