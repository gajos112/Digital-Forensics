:one: **Artefacts**

  :link: [Registry](#Registry)

:one: **Persistence**

  :link: [AutoStart Persistence Locations](#AutoStart-Persistence-Locations)
  :link: [Windows Services](#Windows-Services)
  :link: [Scheduled Tasks](#Scheduled-Tasks)
    
    - at.exe
    - schtasks.exe
  
# Artefacts
  
## Registry
  
- HKEY_LOCAL_MACHINE \SYSTEM : **\system32\config\system**
- HKEY_LOCAL_MACHINE \SAM : **\system32\config\sam**
- HKEY_LOCAL_MACHINE \SECURITY : **\system32\config\security**
- HKEY_LOCAL_MACHINE \SOFTWARE : **\system32\config\software**
- HKEY_USERS \UserProfile :  **\winnt\profiles\username**
- HKEY_USERS.DEFAULT : **\system32\config\default**
- C:\Users\*\AppData\Local\Microsoft\Windows\UsrClass.DAT
- C:\Users\Username\Username.DAT

# Persistence
  
## AutoStart Persistence Locations
  
- NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Run
- NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\RunOnce
- SOFTWARE\Microsoft\Windows\CurrentVersion\Runonce
- SOFTWARE\Microsoft\Windows\CurrentVersion\policies\Explorer\Run
- SOFTWARE\Microsoft\Windows\CurrentVersion\Run
- %AppData%\Roaming\Microsoft\Windows\Start Menu\Programs\Startup
