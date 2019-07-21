# Operating System Version:

SOFTWARE\Microsoft\Windows NT\CurrentVersion

# Historical Networks (Vista/7/8) Managed by a Domain:

SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures\Managed

–DnsSuffix = Domain 
–FirstNetwork = SSID 
–DefaultGatewayMac = Media Access Control (MAC) Address of Gateway 
–Last Written Time = Last time the computer connected to this network.

# Historical Networks (Vista/7/8) Not Managed by a Domain:

SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Signatures\Managed 

–DnsSuffix = Domain 
–FirstNetwork = SSID 
–DefaultGatewayMac = Media Access Control (MAC) Address of Gateway 
–Last Written Time = Last time the computer connected to this network.

# Network Type:

SOFTWARE\Microsoft\WZCSVC\Parameters\Interfaces\{GUID} (XP)
SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Profiles (Vista/7/8)

- NameType 0x47 = Wireless 
- NameType 0x06 = Wired 
- NameType 0x17 = Broadband
- Date fields are recorded as 128-bit System date .... use Dcode to convert.
