# SSH
Notes on SSH Tunneling
- Requires a router with DD-WRT firmware
- Putty as ssh client
- Firefox as SOCKS compatible browser

- Download Putty
- Run PUTTYGEN.EXE
- Key -> Generate key pair.
- Private key will be stored in a .PPK file
- Each device used will need a key pair
- DD-WRT have built-in SSH servers.
- Open the router amdin page
- Administration –>SSH Daemon.
- Check both Enable at Startup and Remote Access
- Using a key pair require password login option to be unchecked
- Paste public key in the authorised key box
- Each key should be its own entry separated by a line break
- Click Start Now and save
- Extracted and the .PPK on the remoate machine
- Launch putty
- Public IP address of your home internet connection
- Change the Port to 2222
- Connection –> Auth -> Browse button and select the .PPK file 
- SSH –> Tunnels. To configure putty as a proxy server
- Check both boxes under Port Forwarding
- Add new forwarded port section, enter 80 for the Source port and the Public IP address of your router for the Destination
- Launch terminal
- At the login prompt type root. At the passphrase prompt enter your RSA keyring password

- https://www.ssh.com/ssh/putty/windows/

For linux:
- ssh -D 9999 -C user@host,  command in terminal
- Open your web browser and set the SOCKS proxy to port 9999 and localhost.
- to copy a local file to a remote system, scp /path/to/local/file user@host:/path/to/destination/file
- copy a file on a remote SSH server to the local system, scp -r user@host:/path/to/remote/file /path/to/destination/file
- command to connect to an SSH server with VisualHostKey enabled, ssh -o VisualHostKey=yes user@host
