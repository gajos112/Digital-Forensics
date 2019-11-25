# Remote Access

## Remote Desktop (RDP)

### Event Logs

- security.evtx
 4648 – Logon specifying alternate credentials - if NLA enabled on destination
  * Current logged-on User Name
  * Alternate User Name
  * Destination Host Name/IP
  * Process Name
  
- Microsoft-WindowsTerminalServicesRDPClient%4Operational.evtx
  -1024 - Destination Host Name
 - 1102 -  Destination IP Address

### Registry

- Remote desktop destinations are tracked per-user
  - NTUSER\Software\Microsoft\TerminalServer Client\Servers

- ShimCache – **SYSTEM**
  - mstsc.exe - Remote Desktop Client
  
- BAM/DAM – SYSTEM – Last Time Executed 
  - mstsc.exe Remote Desktop Client

- AmCache.hve – First Time Executed
   - mstsc.exe

- UserAssist – NTUSER.DAT
 mstsc.exe Remote
Desktop Client execution
 Last Time Executed
 Number of Times Executed
- RecentApps – NTUSER.DAT
 mstsc.exe Remote
Desktop Client execution
 Last Time Executed
 Number of Times Executed
 RecentItems subkey tracks
connection destinations and
times

### File system


### Map Network Shares
