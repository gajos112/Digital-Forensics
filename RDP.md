:one: **Log: Microsoft-Windows-TerminalServices-LocalSessionManager/Operational** 

  :link: *Logon*
  - [checklist](#checklist) 
 
  :link: *Session Disconnect/Reconnect*
  - [gobuster](#gobuster)

  :link: *Logoff* 
  - [gobuster](#gobuster)


:two: **Log: Microsoft-Windows-Terminal-Services-RemoteConnectionManager/Operational**

:three: **Log: Security**

:four: **Log: Systemn**

  

### Checklist
1. Enumerate Hostname - nmblookup -A [ip]
2. List Shares
- `smbmap -H [ip/hostname]`
- `echo exit | smbclient -L \\\\[ip]`
- `nmap --script smb-enum-shares -p 139,445 [ip]`


### Gobuster
1. Using gobuster to scan the website with big dictionary: 
- `gobuster -e -u http://10.10.10.6/ -w /usr/share/wordlists/dirb/big.txt`
