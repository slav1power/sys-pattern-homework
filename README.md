# Домашнее задание к занятию "`Уязвимости и атаки на информационные системы`" - `Уляшев Дмитрий`



### Задание 1

1.1 Открытые порты и доступные службы:
```
22/tcp    open  ssh         OpenSSH 4.7p1 Debian 8ubuntu1 (protocol 2.0)
| ssh-hostkey: 
|   1024 60:0f:cf:e1:c0:5f:6a:74:d6:90:24:fa:c4:d5:6c:cd (DSA)
|_  2048 56:56:24:0f:21:1d:de:a7:2b:ae:61:b1:24:3d:e8:f3 (RSA)
23/tcp    open  telnet      Linux telnetd
25/tcp    open  smtp        Postfix smtpd
|_smtp-commands: metasploitable.localdomain, PIPELINING, SIZE 10240000, VRFY, ETRN, STARTTLS, ENHANCEDSTATUSCODES, 8BITMIME, DSN
53/tcp    open  domain      ISC BIND 9.4.2
| dns-nsid: 
|_  bind.version: 9.4.2
80/tcp    open  http        Apache httpd 2.2.8 ((Ubuntu) DAV/2)
|_http-server-header: Apache/2.2.8 (Ubuntu) DAV/2
|_http-title: Metasploitable2 - Linux
111/tcp   open  rpcbind     2 (RPC #100000)
| rpcinfo: 
|   program version    port/proto  service
|   100000  2            111/tcp   rpcbind
|   100000  2            111/udp   rpcbind
|   100003  2,3,4       2049/tcp   nfs
|   100003  2,3,4       2049/udp   nfs
|   100005  1,2,3      41017/tcp   mountd
|   100005  1,2,3      58172/udp   mountd
|   100021  1,3,4      40476/tcp   nlockmgr
|   100021  1,3,4      60311/udp   nlockmgr
|   100024  1          32902/tcp   status
|_  100024  1          55391/udp   status
139/tcp   open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp   open  netbios-ssn Samba smbd 3.0.20-Debian (workgroup: WORKGROUP)
512/tcp   open  exec        netkit-rsh rexecd
513/tcp   open  login?
514/tcp   open  shell       Netkit rshd
1099/tcp  open  java-rmi    GNU Classpath grmiregistry
1524/tcp  open  bindshell   Metasploitable root shell
2049/tcp  open  nfs         2-4 (RPC #100003)
2121/tcp  open  ftp         ProFTPD 1.3.1
3306/tcp  open  mysql       MySQL 5.0.51a-3ubuntu5
| mysql-info: 
|   Protocol: 10
|   Version: 5.0.51a-3ubuntu5
|   Thread ID: 9
|   Capabilities flags: 43564
|   Some Capabilities: SupportsTransactions, ConnectWithDatabase, Support41Auth, SupportsCompression, Speaks41ProtocolNew, LongColumnFlag, SwitchToSSLAfterHandshake
|   Status: Autocommit
|_  Salt: +s$T]VumDK+6i4ap/6`c
3632/tcp  open  distccd     distccd v1 ((GNU) 4.2.4 (Ubuntu 4.2.4-1ubuntu4))
5432/tcp  open  postgresql  PostgreSQL DB 8.3.0 - 8.3.7
| ssl-cert: Subject: commonName=ubuntu804-base.localdomain/organizationName=OCOSA/stateOrProvinceName=There is no such thing outside US/countryName=XX
| Not valid before: 2010-03-17T14:07:45
|_Not valid after:  2010-04-16T14:07:45
|_ssl-date: 2026-01-09T05:49:01+00:00; +8s from scanner time.
5900/tcp  open  vnc         VNC (protocol 3.3)
| vnc-info: 
|   Protocol version: 3.3
|   Security types: 
|_    VNC Authentication (2)
6000/tcp  open  X11         (access denied)
6667/tcp  open  irc         UnrealIRCd
6697/tcp  open  irc         UnrealIRCd
8009/tcp  open  ajp13       Apache Jserv (Protocol v1.3)
|_ajp-methods: Failed to get a valid response for the OPTION request
8180/tcp  open  http        Apache Tomcat/Coyote JSP engine 1.1
|_http-favicon: Apache Tomcat
|_http-title: Apache Tomcat/5.5
8787/tcp  open  drb         Ruby DRb RMI (Ruby 1.8; path /usr/lib/ruby/1.8/drb)
32902/tcp open  status      1 (RPC #100024)
40476/tcp open  nlockmgr    1-4 (RPC #100021)
41017/tcp open  mountd      1-3 (RPC #100005)
52728/tcp open  java-rmi    GNU Classpath grmiregistry
MAC Address: 00:0C:29:F3:87:34 (VMware)
Device type: general purpose
Running: Linux 2.6.X
OS CPE: cpe:/o:linux:linux_kernel:2.6
OS details: Linux 2.6.9 - 2.6.33
Network Distance: 1 hop
Service Info: Hosts:  metasploitable.localdomain, irc.Metasploitable.LAN; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel
```
1.2 Найденные уязвимости: 
1) https://www.exploit-db.com/exploits/15449
2) https://www.exploit-db.com/exploits/16320
3) https://www.exploit-db.com/exploits/16922
   


### Задание 2


- SYN - быстро и точно показывает открытые и закрытые порты (Стандартный ответ RFC), однако является более заметным
- FIN/Xmas - более скрытные тесты имитирующие разрыв соединения, открытые порты игнорируют такие пакеты (ответ закрытых портов RST-ACK)
- UDP -  в отличии от TCP тестов не устанавливает рукопожатие, открытые порты дают ответ, закрытые выдают ICMP ошибку
  
  Файлы записей сеансов доступны в репозитории:
  SYN - https://github.com/slav1power/sys-pattern-homework/blob/main/SYN.pcapng
  FIN - https://github.com/slav1power/sys-pattern-homework/blob/main/FIN.pcapng
  Xmas - https://github.com/slav1power/sys-pattern-homework/blob/main/Xmas.pcapng
  UDP - https://github.com/slav1power/sys-pattern-homework/blob/main/Xmas.pcapng









