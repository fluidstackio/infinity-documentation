# Connection Info

---

## Connecting to your machine

1. Based on your operating system, you will have different options

| |Windows Client|Linux Client|Mac Client|
|---|---|---|---|
|Windows Server (RDP)|[RDP](https://support.microsoft.com/en-us/windows/how-to-use-remote-desktop-5fe128d5-8fb1-7a23-3b8a-41e636865e8c)|[Remmina](https://remmina.org/how-to-install-remmina/)|[Microsoft RDP](https://apps.apple.com/us/app/microsoft-remote-desktop/id1295203466?mt=12)
|Linux Server (SSH)|[PuTTY](https://www.ssh.com/academy/ssh/putty/windows)|[SSH via terminal](https://www.digitalocean.com/community/tutorials/how-to-use-ssh-to-connect-to-a-remote-server)|[SSH via terminal](https://www.servermania.com/kb/articles/ssh-mac/)

## Extra Info

### SSH: Secure Shell Protocol

SSH provides a secure connection over an unsecured network between two untrusted hosts. Through this connection, many things are possible such as file transfers, remote commands, and automated processes. SSH uses a client-server model where the client initiates the SSH connection and uses public-key cryptography to authenticate the server’s identity. During the connection setup, the client and the server decide upon parameters on which the encryption of data is based. Once the setup is complete, the protocol uses hashing algorithms and strong symmetric encryption to make sure all data transfers between the client and the server are secure.

**If you are on Windows,** to use SSH, install [PuTTY](https://putty.org/). Copy & paste your FluidStack’s server IP address into the IP address field, include a port if applicable and connect. 

**If you are on MacOS,** open the terminal command and type ```ssh user@ip -p port```, where the username of your user on the server is user, the IP of the server is ip, and the port number is substituted in where the port is.

### SCP: Secure Copy Protocol

SCP makes sure that the transfer of the data between a local host and a remote host (or two remote hosts) is secure. Between the two hosts, the SCP provides an authentication procedure and encryption for the transfer of data through the use of SSH. An SSH connection is needed and there are two different modes of transfer available: source mode and sink mode. In source mode, the files in the targeted remote host are sent back to the client. In sink mode, the client-side signals to the remote host that there is incoming data to be written.

Here are some useful SCP resources:  
[SCP – definition, function, and syntax - IONOS](https://www.ionos.com/digitalguide/server/know-how/scp-secure-copy/)  
[SCP Command in Linux: How to Use It, with Examples](https://linuxiac.com/scp-command-in-linux/#:~:text=%20Some%20of%20the%20most%20widely%20used%20scp,%E2%80%93%20Identity%20file%20or%20private%20key%20More%20)

### RDP: Remote Desktop Protocol

Remote Desktop is the ability to control a remote desktop computer from another separate computer. The users can access all parts of the remote desktop like files and applications. The user’s keystrokes and mouse movements are sent over to the remote desktop through the internet and the remote desktop is displayed on the user’s computer. RDP initiates a dedicated network channel where the data is sent back and forth. This data is encrypted by the RDP so that it is more secure over public internet connections. There may be delays when the user uses RDP since the inputs have to be sent over to the remote desktop and then the responses have to be displayed back at the user’s desktop. This is available for most Windows operating systems and Mac operating systems. 

**If you are on Windows,** type “Remote Desktop Connection” into your Windows search bar. By default, an RDP client is installed. Use the “Show Options” button to enter the username needed to access your FluidStack server, and then enter your IP and port in the following format: ```ip:port```. Press the connect button to connect. 

**If you are on MacOS,** download the Microsoft Remote Desktop client [here](https://apps.apple.com/us/app/microsoft-remote-desktop/id1295203466?mt=12). Then, follow the same connection instructions as on Windows.