- IP = 54.200.47.94
- OS: Windows
- Shodan Results
	- https://www.shodan.io/host/54.200.47.94
- Nmap
	- 443
	- 8443
- Fuzzing
	- ran command
		- ffuf -u https://api.wyzecam.com/FUZZ -w /usr/share/wordlists/dirb/common.txt
	- returned
		- auth                    Status: 401, Size: 109, Words: 1, Lines: 1, Duration: 68ms
		- internal                Status: 403, Size: 0, Words: 1, Lines: 1, Duration: 60ms
		- ping                    Status: 200, Size: 2, Words: 1, Lines: 1, Duration: 59ms
	- Going down each of their respective rabbit holes
		- Auth
			- Gave a whitelabel error page
			- Unexpected error
				- Unauthorized
				- Status 401
			- Multiple different paths to go down
				- Returns 401 errors on each webpage
		- Internal
			- 403 Forbidden
			- Multiple different paths to go down
				- Returns 403 errors on each webpage
		- Ping
			- 
