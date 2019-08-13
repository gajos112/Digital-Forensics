# Logons attempts

4624
4625
4634
4647
4672

# Tracking usage of RDP

- 4778 - Session Connected/Reconnected

- 4779 - Session Disconnected

Both events contatin information about IP and hostname. Event 4778 will be followed by 4624 (successful logon) and 4779 and 4647 (successful logout). Windows workstation allows only only one interactive logon at time. When RDP is done to system that has a user logged into the console need to disconnect him. 
