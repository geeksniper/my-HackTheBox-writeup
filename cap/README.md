
1. at first set the dns host in local machine.

![task 1](https://github.com/geeksniper/hack-the-box-writeup/blob/76cab619b9e6a85172279da83c03124dfb0505b9/cap/cap-images/01.setdnshost.png)

2. Firstly the exploit began with the scan of open ports on the target. This is the first and the most important step while enumerating a machine.

![task 2](https://github.com/geeksniper/hack-the-box-writeup/blob/76cab619b9e6a85172279da83c03124dfb0505b9/cap/cap-images/02.nmapscan.png)

3. Nmap script scan shows we don’t have access to anonymous ftp. So, I opened the web server.

![task 3](https://github.com/geeksniper/hack-the-box-writeup/blob/76cab619b9e6a85172279da83c03124dfb0505b9/cap/cap-images/03.webview.png)

4. It is a nice dashboard that displays the result of monitoring of the network. On the left sidebar menu, we can see PCAP analysis. PCAP means “packet capture”. This means it contains the data of packets that are sent over network. Furthermore, we can store these files and analysis them later using tools like wireshark. Thus, I clicked the second options.

![task 4](https://github.com/geeksniper/hack-the-box-writeup/blob/76cab619b9e6a85172279da83c03124dfb0505b9/cap/cap-images/04.clicksecondoption.png)

5. However, the application didn’t show any packets. So, I changed the path parameter from 20 to 0.

![task 5](https://github.com/geeksniper/hack-the-box-writeup/blob/4930556dce96ba078624173073f2ee5e6480b783/cap/cap-images/05.path0.png)

6. Fortunately, it worked. If it hadn’t worked, I would have started doing fuzzing rather than testing one by one. Next, I downloaded the pcap file and opened in wireshark.

` wireshark 0.pcap`

![task 6](https://github.com/geeksniper/hack-the-box-writeup/blob/4930556dce96ba078624173073f2ee5e6480b783/cap/cap-images/06.open-with-wireshark.png)

7. I got the ftp user and password.

![task 7](https://github.com/geeksniper/hack-the-box-writeup/blob/57e6a7ac52cbaff1c2bf2bace6a88a29a52ea974/cap/cap-images/07.got-user-pass-ftp-login.png)

8. 




