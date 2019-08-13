# Logons attempts

- 4624 - successful Logon

- 4625 - failed Logon

- 4634/4647 - Successful Logoff

- 4672 - Account logon with superuser rights (Administrator)

# Logon Type

- 2	Interactive (logon at keyboard and screen of system)

- 3	Network (i.e. connection to shared folder on this computer from elsewhere on network)

- 4	Batch (i.e. scheduled task)

- 5	Service (Service startup)

- 7	Unlock (i.e. unnattended workstation with password protected screen saver)

- 8	NetworkCleartext (Logon with credentials sent in the clear text. Most often indicates a logon to IIS with "basic authentication") See this article for more information.

- 9	NewCredentials such as with RunAs or mapping a network drive with alternate credentials.  This logon type does not seem to show up in any events.  If you want to track users attempting to logon with alternate credentials see 4648.  MS says "A caller cloned its current token and specified new credentials for outbound connections. The new logon session has the same local identity, but uses different credentials for other network connections."

- 10	RemoteInteractive (Terminal Services, Remote Desktop or Remote Assistance)

- 11	CachedInteractive (logon with cached domain credentials such as when logging on to a laptop when away from the network)

# Tracking usage of RDP

- 4778 - Session Connected/Reconnected

- 4779 - Session Disconnected

Both events contatin information about IP and hostname. Event 4778 will be followed by 4624 (successful logon) and 4779 and 4647 (successful logout). Windows workstation allows only only one interactive logon at time. When RDP is done to system that has a user logged into the console need to disconnect him. 

# File and folder Access

- 4656 - A handle to an object was requested

- 4660 - An object was deleted

- 4663 - An attempt was made to access an object (Keywords: Audit Success / Audit Failure)

# Processes

- 4688 - A new process has been created

Example: 

A new process has been created.

Creator Subject:
 Security ID:  SYSTEM
 Account Name:  RFSH$
 Account Domain:  LAB
 Logon ID:  0x3E7

Target Subject:
 Security ID:  LAB\rsmith
 Account Name:  rsmith
 Account Domain:  LAB
 Logon ID:  0x2C9D82

Process Information:
 New Process ID:  0x2e0e4
 New Process Name: C:\Windows\System32\RuntimeBroker.exe
 Token Elevation Type: %%1938
 Mandatory Label:  Mandatory Label\Medium Mandatory Level
 Creator Process ID: 0x268
 Creator Process Name: C:\Windows\System32\svchost.exe
 Process Command Line: 
 
 # USB (Windows 2016 and 10)
 
 - 6416 - A new external device was recognized by the system.
 
 - 4663 - An attempt was made to access an object (Keywords: Audit Success / Audit Failure)
 
 We need to corelated both of them to make some conlusion.
