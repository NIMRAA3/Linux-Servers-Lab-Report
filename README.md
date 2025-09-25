# Lab Report: Linux Servers

## Objectives
- Use the Linux command line to identify servers running on a computer.
- Explore server and client interactions.
- Use the telnet command to test TCP services.



## Theory
- **Servers** are programs that provide specific information or services upon request.
- **Clients** are programs that request information from servers.
- In Linux, running programs are called **processes**. Some processes are background services started at boot time.
- **Common tools**:
  - `ps` → displays running processes.
  - `netstat` → shows active network connections and listening servers.
  - `telnet` → used to test TCP services (default port 23, but you can specify others like 80 for HTTP or 22 for SSH).



## Steps & Commands

### Part 1: Servers
1. **Access Command Line**
   - Log in to the VM as `analyst` (password: `cyberops`).
   - Open terminal.

2. **Display Services Running**
   ```bash
   sudo ps -elf
Shows all background processes.

View Process Hierarchy

sudo /usr/sbin/nginx
sudo ps -ejH


Displays running process tree, highlighting nginx service.

List Active Network Connections

netstat


Shows active internet connections.

Detailed Network Servers

sudo netstat -tunap


Displays TCP/UDP connections with process info.

Part 2: Using Telnet to Test TCP Services

Telnet is an insecure remote shell (no encryption).

Still useful for testing TCP services by connecting directly to a port.

Example:

telnet 127.0.0.1 80
telnet 127.0.0.1 22


On port 80 (HTTP): server responds with HTTP messages (e.g., 400 Bad Request if invalid input).

On port 22 (SSH): server responds with SSH version, rejects invalid input.

Questions

What command shows all processes running on the system?
➝ ps -elf

Which command shows the process hierarchy?
➝ ps -ejH

How can you list active TCP/UDP connections with process info?
➝ netstat -tunap

Why is Telnet not recommended for remote access?
➝ Because it sends data in clear text, no encryption.

How can Telnet still be useful?
➝ For testing TCP services quickly.

How is the process hierarchy represented by ps?
➝ Through indentation.

Why was it necessary to run ps as root (with sudo)?
➝ Some processes do not belong to analyst and may not be displayed otherwise.

What is the meaning of the -t, -u, -n, -a, and -p options in netstat?

-a: shows both listening and non-listening sockets

-n: numeric output only

-p: show the PID of the process

-t: show TCP connections

-u: show UDP connections

What is nginx? What is its function?
➝ Nginx is a lightweight web server.

Why was the error sent as a web page?
➝ Nginx is a web server and communicates using HTTP.

Use Telnet to connect to port 68. What happens?
➝ Connection refused, because Telnet (TCP) cannot connect to UDP ports.

What are the advantages of using netstat?
➝ Displays all connections, source/destination, ports, and process IDs.

What are the advantages of using Telnet? Is it safe?
➝ Useful for quick service testing. Not safe for remote shells, but safe for quick checks.

Learning Outcomes

Gained experience using ps to explore processes.

Learned how to use netstat to identify servers and network connections.

Understood the role of nginx as a web server.

Practiced using telnet to connect to specific TCP ports and interpret responses.

Recognized why SSH is preferred over Telnet for secure remote access.

Summary

In this lab, we used the Linux command line to identify and analyze running servers. Using ps and netstat, we viewed processes and active connections. We tested services with telnet on different ports (HTTP and SSH), observing how each responded to input. This demonstrated the differences in protocol behavior and highlighted why Telnet is insecure but useful for quick TCP service testing.

[click here to downolad file with  lab images ](https://github.com/NIMRAA3/Linux-Servers-Lab-Report/blob/main/Lab%20%20server%20report.docx)
