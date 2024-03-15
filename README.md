# Simple Reverse Shell in C
This is a basic reverse shell written in C that sets up a TCP connection between  two devices in a same network and executes the Windows Command Prompt (cmd.exe).
All the output, including errors, is being redirected to us so that allowing us to control the remote machine.

Let's summarize what's happening behind the scenes:
1. The Winsock is initialized using the WSAStartup() fucntion.
2. The socket is created using the WSASocket() function.
3. After assigning ip address and port, connection is established 
   using WSAConnect() function. This establishes a TCP connection.
4. After the connection, a new process is created using CreateProcessA() function.
   This function creates a cmd.exe and all the input, output and errors are redirected to us.
