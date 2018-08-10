# Using netstat and powershell on windows to learn more about what processes are communicating with the outside world.

## How to check what ports are open?
QUESTION: What is the different between NMAP and netstat?  
QUESTION: What is your local address? What does it represent?  
Open a command line prompt. Type `netstat`
What IP address are they communicating with?
What port are they communicating with?
What protocol it is using?

## How to know what processes are opening those ports?
Check out where I got my info and to read more: [link](https://helpdeskgeek.com/how-to/use-netstat-to-see-listening-ports-and-pid-in-windows/)

To get the PID number you can use the following flag with the netstat command:
`netstat -o`
The -o command provided the PID.

## How to get more info about those processes?
Using the windows powershell.


Using command line

You can use tasklist to get a list of running processes `tasklist`
If you want to narrow your search by the PID you can use
`tasklist /fi "pid eq processId"`
Check out where I got my info regarding tasklist and to read more: [link](https://www.windows-commandline.com/tasklist-command/)


Once you have the name of the process you can get the exe file path and other info with the following command commands:
To get more info about a process using image name:
`tasklist /FI "ImageName eq Spring.Tests.exe" /v /fo List`

To get where the executable is located:
`wmic process where "name='mysqld.exe'" get ProcessID, ExecutablePath`

Check out where I got my info and to read more: [link](https://superuser.com/questions/768984/show-exe-file-path-of-running-processes-on-the-command-line-in-windows)

---

# Group exercise "capture the flag"
