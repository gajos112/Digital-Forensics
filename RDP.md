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
  
   - [Windows event ID = 4624](#Event-ID-4624)
   - [Windows event ID = 4625](#Event-ID-4625)
   
  :link: *Session Disconnect/Reconnect*
  
   - [Windows event ID = 4778](#Event-ID-4778)
   - [Windows event ID = 4779](#Event-ID-4779)
     
 :link: *Logoff*  
   - [Windows event ID = 4634](#Event-ID-4634)
   - [Windows event ID = 4647](#Event-ID-4647)
   
:four: **Log: Systemn**
  
  :link: *Connection closed*  
   - [Windows event ID = 9009](#Event-ID-9009)


# Log: Microsoft-Windows-TerminalServices-LocalSessionManager/Operational

### Event ID: 21
**(LOGON)**

Description: “Remote Desktop Services: Session logon succeeded:”
Indicates successful RDP logon and session instantiation, so long as the “Source Network Address” is NOT “LOCAL”.

### Event ID: 22
**(LOGON)**

Description: “Remote Desktop Services: Shell start notification received:”
Indicates successful RDP logon and shell (i.e. Windows GUI Desktop) start, so long as the “Source Network Address” is NOT “LOCAL”.

### Event ID: 24
**(Session Disconnect/Reconnect)**

Description: “Remote Desktop Services: Session has been disconnected:”
The user has disconnected from an RDP session, so long as the “Source Network Address” is NOT “LOCAL”.

### Event ID: 25
**(Session Disconnect/Reconnect)**

Description: “Remote Desktop Services: Session reconnection succeeded:”
The user has reconnected to an existing RDP session, so long as the “Source Network Address” is NOT “LOCAL”.

### Event ID: 39
**(Session Disconnect/Reconnect)**

Description: “Session <X> has been disconnected by session <Y>”
 Cases where the Session ID of <X> differs from <Y> may indicate a separate RDP session has disconnected (i.e. kicked off) the given user.
  
 The user formally disconnected from the RDP session.

### Event ID: 40
**(Session Disconnect/Reconnect)**

Description: “Session <X> has been disconnected, reason code <Z>”

- 0 – “No additional information is available.” (Occurs when a user informally X’es out of a session, typically paired with Event ID 24)

- 5 – “The client’s connection was replaced by another connection.” (Occurs when a user reconnects to an RDP session, typically paired with an Event ID 25)

- 11 – “User activity has initiated the disconnect.” (Occurs when a user formally initiates an RDP disconnect, for example via the Windows Start Menu Disconnect option.)

The user disconnected from or reconnected to an RDP session.

### Event ID: 23
**(Logoff)**

Description: “Remote Desktop Services: Session logoff succeeded:”

The user has initiated a logoff. This is typically paired with an Event ID 4634 (logoff). Take note of the SessionID as a means of tracking/associating additional Event Log activity with this user’s RDP session. This event with a will also be generated upon a system shutdown/reboot.

The user initiated a formal system logoff (versus a simple session disconnect).

# Log: Microsoft-Windows-Terminal-Services-RemoteConnectionManager/Operational

### Event ID: 1149
**(Network Connection)**

Description: “User authentication succeeded”

This event actually DOES NOT indicate a successful user authentication. Someone launched an RDP client, specified the target machine (possibly with a username and domain), and hit enter to make a successful network connection to the target. Nothing more, nothing less.

# Log: Security

### Event ID: 4624
**(Authentication)**

LogonType:

-	Type 3 (Network) when NLA is Enabled (and at times even when it’s not) followed by 

-	Type 10 (RemoteInteractive / a.k.a. Terminal Services / a.k.a. Remote Desktop)

-	Type 7 from a Remote IP (if it’s a reconnection from a previous/existing RDP session)

User successfully logged on to this system with the  specified TargetUserName and TargetDomainName from the specified IpAddress.

### Event ID: 4625
**(Authentication)**

LogonType: 

-	Type 3 (Network) when NLA is Enabled (and at times even when it’s not) and/or 

-	Type 10 (RemoteInteractive / a.k.a. Terminal Services / a.k.a. Remote Desktop)

User failed to log on to this system with the specified TargetUserName and TargetDomainName from the specified IpAddress.

### Event ID: 4778
**(Session Disconnect/Reconnect)**

Description: “A session was reconnected to a Window Station.”

The user reconnected to an existing RDP session.
 
### Event ID: 4779
**(Session Disconnect/Reconnect)**

Description: “A session was disconnected from a Window Station.”

The user disconnected from from an RDP session.

### Event ID: 4634
**(Logoff)**

LogonType:

-	10 (RemoteInteractive / a.k.a. Terminal Services / a.k.a. Remote Desktop)

- Type 7 from a Remote IP (if it’s a reconnection from a previous/existing RDP session)

A user disconnected from, or logged off, an RDP session.

### Event ID: 4647
**(Logoff)**

The user initiated a formal logoff (NOT a simple disconnect).

# Log: System

### Event ID: 9009
A user has closed out an RDP connection.

