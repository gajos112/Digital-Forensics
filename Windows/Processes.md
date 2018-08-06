# System

Image Path: N/A – Not generated from an executable image
Parent Process: None
Number of Instances: One
User Account: Local System
Start Time: At boot time
Description: The System process is responsible for most kernel-mode threads.
Modules run under System are primarily drivers (.sys files), but also several
important DLLs as well as the kernel executable, ntoskrnl.exe

# smss.exe

Image Path: %SystemRoot%\System32\smss.exe
Parent Process: System
Number of Instances: One master instance and another child
instance per session. Children exit after creating their session.
User Account: Local System
Start Time: Within seconds of boot time for the master instance
Description: The Session Manager process is responsible for creating new sessions.
The first instance creates a child instance for each new session. Once the child instance
initializes the new session by starting the Windows subsystem (csrss.exe) and
wininit.exe for Session 0 or winlogon.exe for Session 1 and higher, the
child instance exits.

# wininit.exe

Image Path: %SystemRoot%\System32\wininit.exe
Parent Process: Created by an instance of smss.exe that exits,
so tools usually do not provide the parent process name.
Number of Instances: One
User Account: Local System
Start Time: Within seconds of boot time
Description: Wininit starts key background processes within Session 0. It starts
the Service Control Manager (services.exe), the Local Security Authority process
(lsass.exe), and the Local Session Manager (lsm.exe).

# taskhost.exe

Image Path: %SystemRoot%\System32\taskhost.exe
Parent Process: services.exe
Number of Instances: One or more
User Account: Multiple taskhost.exe processes are normal. One or more may be owned by logged-on users and/or by local service accounts.
Start Time: Start times vary greatly

Description: The generic host process for Windows Tasks. Tasks are similar in nature to services, and in fact beginning with Windows 7, are handled through the same Universal Background Process Manager (UBPM) facility. Upon initialization, taskhost.exe runs a continuous loop listening for trigger events. Example trigger events that can initiate a task include a defined schedule, user logon, system startup, idle CPU time, a Windows log event, workstation lock, or workstation unlock. There are more than 70 tasks preconfigured on a default installation of Windows 7 Enterprise (though many are disabled). For example, defrag.exe is scheduled to run against all volumes every Wednesday at 1:00 am. Another default task backs up the core registry hive files every 10 days. All executable files (DLLs & EXEs) used by the default Windows 7/8 scheduled tasks are signed by Microsoft.

# lsass.exe

Image Path: %SystemRoot%\System32\lsass.exe
Parent Process: wininit.exe
Number of Instances: One
User Account: Local System
Start Time: Within seconds of boot time
Description: The Local Security Authentication Subsystem Server process is
responsible for authenticating users by calling an appropriate Security Service Provider
(SSP) authentication package specified in
HKLM\SYSTEM\CurrentControlSet\Control\Lsa. Typically this
will be the Kerberos SSP for domain accounts or the MSV1_0 SSP for local accounts.
Once a user is authenticated, lsass.exe generates an access token for the user
that specifies security rights and constraints for the user and the user’s processes. Only
one instance of this process should occur and it should never have child processes.

# winlogon.exe

Image Path: %SystemRoot%\System32\winlogon.exe
Parent Process: Created by an instance of smss.exe that exits,
so analysis tools usually do not provide the parent process name.
Number of Instances: One or more
User Account: Local System
Start Time: Within seconds of boot time for the first instance (for
Session 1). Start times for additional instances occur as new sessions are
created, typically through Remote Desktop or Fast User Switching logons.
Description: Winlogon handles interactive user logons and logoffs. It launches
LogonUI.exe, which accepts the username and password at the logon screen and
passes the credentials to lsass.exe to validate the credentials. Once the user
is authenticated, Winlogon loads the user’s NTUSER.DAT into HKCU and starts the
user’s shell (explorer.exe) via Userinit.exe.
