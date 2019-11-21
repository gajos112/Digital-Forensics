:one: **Log: Microsoft-Windows-TerminalServices-LocalSessionManager/Operational** 

  :link: *Logon*
   - [Windows event ID = 21](#Event-ID-21)
   - [Windows event ID = 22](#Event-ID-22)  
  
  :link: *Session Disconnect/Reconnect*
   - [Windows event ID = 24](#Event-ID-24)
   - [Windows event ID = 25](#Event-ID-25)
   - [Windows event ID = 39](#Event-ID-39)
   - [Windows event ID = 40](#Event-ID-40)
  
  :link: *Logoff*
   - [Windows event ID = 23](#Event-ID-23)



:two: **Log: Microsoft-Windows-Terminal-Services-RemoteConnectionManager/Operational**
  
  :link: *Network connection*
   - [Windows event ID = 1149](#Event-ID-1149)
   
   
   
:three: **Log: Security**
  
  :link: *Authentication*
  
  :link: *Session Disconnect/Reconnect*
 
 :link: *Logoff*  
  
  
  
:four: **Log: Systemn**
  
  :link: *Connection closed*  
  




## Event ID: 21
Description: “Remote Desktop Services: Session logon succeeded:”
Indicates successful RDP logon and session instantiation, so long as the “Source Network Address” is NOT “LOCAL”.

## Event ID: 22
Description: “Remote Desktop Services: Shell start notification received:”
Indicates successful RDP logon and shell (i.e. Windows GUI Desktop) start, so long as the “Source Network Address” is NOT “LOCAL”.

## Event ID: 24
Description: “Remote Desktop Services: Session has been disconnected:”
The user has disconnected from an RDP session, so long as the “Source Network Address” is NOT “LOCAL”.

## Event ID: 25
Description: “Remote Desktop Services: Session reconnection succeeded:”
The user has reconnected to an existing RDP session, so long as the “Source Network Address” is NOT “LOCAL”.

## Event ID: 39
Description: “Session <X> has been disconnected by session <Y>”
 Cases where the Session ID of <X> differs from <Y> may indicate a separate RDP session has disconnected (i.e. kicked off) the given user.
 The user formally disconnected from the RDP session.

## Event ID: 40
Description: “Session <X> has been disconnected, reason code <Z>”

0 – “No additional information is available.” (Occurs when a user informally X’es out of a session, typically paired with Event ID 24)
5 – “The client’s connection was replaced by another connection.” (Occurs when a user reconnects to an RDP session, typically paired with an Event ID 25)
11 – “User activity has initiated the disconnect.” (Occurs when a user formally initiates an RDP disconnect, for example via the Windows Start Menu Disconnect option.)
The user disconnected from or reconnected to an RDP session.
