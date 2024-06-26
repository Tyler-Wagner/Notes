- **Daily**
	- ==3/11/24==
		- Needed a baseline for what the packets looked like and where the data is so I can find an entry point for breaking confidentiality
		- Coded a python3 server on message2 and a client on message1
			- Sends packets where I **KNOW** the message being sent
			- This allowed me to see where the data is stored within the packet
			- Now I can start the server up on my machine and see if I can intercept the packets or break its encryption
			- I know the byte it starts at so *MAYBE* I can ignore everything outside of those packets and decode that and see what I come up with
	- ==3/12/24==
		- Continuing work on starting to mess with the key. Any attacks that Dan asks for today I can give.
		- Stored the over night pcap file in the necessary folder so the AI team can get their baseline "normal" data. 
			- I say "normal" because they will have to filter out the other stuff on the network
		- ==Question:== At first the key request packet comes at a static 45-50 seconds, as the boards stay powered on this time gets progressively longer. Why is that?
		- I think I sent something over the network that made me not connect to the client via ssh anymore, I need to look further into it.
		- ==Question:== is there a direct order the key exchange is supposed to happen? If so what is it?
			- Under the sheets
				- client looks to send the key first meaning that it should initiate the key exchange
				- Hub sends a 112 length packet prior to a key exchange
					- THIS IS CONSISTENT
		- ==Question:== is the Hub a barrier to the client? Does it act as a wall where if the hub detects a weird key it stops communication to the client.
- **General**
	- Client IP = 192.168.0.2
	- Hub IP = 192.168.0.1
	- The hub sends a 112 length packet to the client 1 minute prior to receiving a new key
	- sudo -i is still enabled
		- This gives the users root access to the boards and allows them to do what ever they wanted to it
- **RECON**
	- Website
		- Turning firewall on and off opens and closes ports
			- We aren't sure what this means entirely yet but soon to find out
		- Found where logs are stored on the machines so those might actually be useful
		- Changing the protocol messes some things up
			- UDP to SCTP
- **ATTACKS**
	- ==DOS==
		- When you the 112 length packet is received wait 45 - 50 seconds then perform DOS attack
		- Should mess up the key exchange and might not allow a key to come through
	- ==Key Manipulation==
		- Sent a modified key over the network to the hub
		- After sending the key I can no longer communicate directly with the Client board
			- SSH
		- Noticing odd redirects that were not happening prior to the key exchange
			- ICMP redirect every time I try to ssh client
			- ICMP Redirect every time I try to ping client
		- Still performing a normal key exchange but how much of it is normal and how much is messed up
		- Key's and the communication between two machines is perfectly fine from what I can tell
		- After hard reset
			- SSH still disabled
			- website is disabled
			- Deleting known hosts from .ssh did not resolve the issue on my end
		- To access 192.168.0.2 via ssh you have to tunnel from 0.1 to 0.2
		- Must be hub's IP to access client's ssh
- **ENCRYPTION**
	- The minimum number of characters in a message before it stops padding is 18
		- Padding is the same exact bunch of characters for each key
		- Since padding is the same the encryption COULD be broken that way
- **HOW KEY MANIPULATION IS BUILT**
	- Starting with a basic client and server file to send packets via the local host
		- Got that to work, stored in Tools folder
	- Starting a TCP chat client between a server and client
		- Got it to work on a local host
		- Got it working over a network
	- Starting to read a pcap file
- **Dictionary Building**
	- Padding looks the same but finding 
	