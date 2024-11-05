# File Transfer Protocol (FTP) - Important Theory

## 1. Definition of FTP
FTP (File Transfer Protocol) is a set of rules (protocol) for transferring files between computers connected via the Internet.

## 2. Functionality and Accessibility
FTP enables access to a large number of systems and files, providing a foundation for sharing information and software archives across various platforms (e.g., DOS, UNIX, Macintosh).

## 3. Importance in Internet Development
FTP was one of the main factors contributing to the early popularity of the Internet, as it allowed easy file and information sharing on virtually any topic.

## 4. Client-Server Model
FTP operates on a **client-server model**, where both the client and server need to be running compatible FTP software to enable file transfer.

## 5. FTP Software and Interface Limitations
- Traditional FTP clients, especially on non-Windows systems, may not have user-friendly interfaces.
- Web browsers such as **Netscape** and **Internet Explorer** can also be used for FTP access but typically only allow file downloads, not uploads.


The input lines extracted from the code within lab manual are given below
<details>
  <summary>The Lab Manual Whole Code</summary>
  
  ```bash
  FTP installation steps
  Install ProFTPD Server
  root@www:~# apt-get -y install proftpd //Standalone
  root@www:~# vi /etc/proftpd/proftpd.conf
  # line 11: turn off if not needed
  UseIPv6 off
  # line 15: change to your hostname
  ServerName "www.srv.world"
  # line 34: uncomment ( specify root directory for chroot )
  DefaultRoot ~
  root@www:~# vi /etc/ftpusers
  # add users you prohibit FTP connection
  test
  root@www:~# systemctl restart proftpd
  ---------------------------------------------------------------------------------------------------------------------
  ------
  Install FTP Client.
  root@client:~# apt-get -y install lftp
  # lftp [option] [hostname]
  xerus@client:~$ lftp -u ubuntu www.srv.world // lftp -u pc_user server_ip
  Password:
  # password of the user
  lftp ubuntu@www.srv.world:~>
  # show current directory on FTP server
  lftp ubuntu@www.srv.world:~> pwd
  ftp://ubuntu@www.srv.world
  # show current directory on local server
  lftp ubuntu@www.srv.world:~> !pwd
  /home/ubuntu
  # show files in current directory on FTP server
  lftp ubuntu@www.srv.world:~> ls
  drwxr-xr-x 2 1000 1000 23 Jul 19 01:33 public_html
  -rw-r--r-- 1 1000 1000 399 Jul 20 16:32 test.py
  # show files in current directory on local server
  lftp ubuntu@www.srv.world:~> !ls -l
  total 12
  -rw-rw-r-- 1 ubuntu ubuntu 10 Jul 20 14:30 ubuntu.txt
  -rw-rw-r-- 1 ubuntu ubuntu 10 Jul 20 14:59 test2.txt
  -rw-rw-r-- 1 ubuntu ubuntu 10 Jul 20 14:59 test.txt
  # change directory
  lftp ubuntu@www.srv.world:~> cd public_html
  lftp ubuntu@www.srv.world:~/public_html> pwd
  ftp://ubuntu@www.srv.world/%2Fhome/ubuntu/public_html
  # upload a file to FTP server
  # "-a" means ascii mode ( default is binary mode )
  lftp ubuntu@www.srv.world:~> put -a ubuntu.txt test.txt
  22 bytes transferred
  Total 2 files transferred
  lftp ubuntu@www.srv.world:~> ls
  drwxr-xr-x 2 1000 1000 23 Jul 19 01:33 public_html
  -rw-r--r-- 1 1000 1000 10 Jul 20 17:01 ubuntu.txt
  -rw-r--r-- 1 1000 1000 399 Jul 20 16:32 test.py
  -rw-r--r-- 1 1000 1000 10 Jul 20 17:01 test.txt
  # upload some files to FTP server
  lftp ubuntu@www.srv.world:~> mput -a test.txt test2.txt
  22 bytes transferred
  Total 2 files transferred
  lftp ubuntu@www.srv.world:~> ls
  drwxr-xr-x 2 1000 1000 23 Jul 19 01:33 public_html
  -rw-r--r-- 1 1000 1000 399 Jul 20 16:32 test.py
  -rw-r--r-- 1 1000 1000 10 Jul 20 17:06 test.txt
  -rw-r--r-- 1 1000 1000 10 Jul 20 17:06 test2.txt
  # download a file from FTP server
  # "-a" means ascii mode ( default is binary mode )
  lftp ubuntu@www.srv.world:~> get -a test.py
  416 bytes transferred
  # download some files from FTP server
  lftp ubuntu@www.srv.world:~> mget -a test.txt test2.txt
  20 bytes transferred
  Total 2 files transferred
  # create a directory in current directory on FTP Server
  lftp ubuntu@www.srv.world:~> mkdir testdir
  mkdir ok, `testdir' created
  lftp ubuntu@www.srv.world:~> ls
  drwxr-xr-x 2 1000 1000 23 Jul 19 01:33 public_html
  -rw-r--r-- 1 1000 1000 399 Jul 20 16:32 test.py
  -rw-r--r-- 1 1000 1000 10 Jul 20 17:06 test.txt
  -rw-r--r-- 1 1000 1000 10 Jul 20 17:06 test2.txt
  drwxr-xr-x 2 1000 1000 6 Jul 20 17:16 testdir
  226 Directory send OK.
  # delete a direcroty in current directory on FTP Server
  lftp ubuntu@www.srv.world:~> rmdir testdir
  rmdir ok, `testdir' removed
  lftp ubuntu@www.srv.world:~> ls
  drwxr-xr-x 2 1000 1000 23 Jul 19 01:33 public_html
  -rw-r--r-- 1 1000 1000 399 Jul 20 16:32 test.py
  -rw-r--r-- 1 1000 1000 10 Jul 20 17:06 test.txt
  -rw-r--r-- 1 1000 1000 10 Jul 20 17:06 test2.txt
  # delete a file in current directory on FTP Server
  lftp ubuntu@www.srv.world:~> rm test2.txt
  rm ok, `test2.txt' removed
  lftp ubuntu@www.srv.world:~> ls
  drwxr-xr-x 2 1000 1000 23 Jul 19 01:33 public_html
  -rw-r--r-- 1 1000 1000 399 Jul 20 16:32 test.py
  -rw-r--r-- 1 1000 1000 10 Jul 20 17:06 test.txt
  # delete some files in current directory on FTP Server
  lftp ubuntu@www.srv.world:~> mrm ubuntu.txt test.txt
  rm ok, 2 files removed
  lftp ubuntu@www.srv.world:~> ls
  drwxr-xr-x 2 1000 1000 23 Jul 19 01:33 public_html
  # execute commands with "![command]"
  lftp ubuntu@www.srv.world:~> !cat /etc/passwd
  root:x:0:0:root:/root:/bin/bash
  bin:x:1:1:bin:/bin:/sbin/nologin
  ...
  ...
  ubuntu:x:1001:1001::/home/ubuntu:/bin/bash
  # exit
  lftp ubuntu@www.srv.world:~> quit
  221 Goodbye.
  ```
</details>

1. FTP Server Installation

- `root@www:~# apt-get -y install proftpd`
- `root@www:~# vi /etc/proftpd/proftpd.conf`
- `root@www:~# vi /etc/ftpusers`
- `root@www:~# systemctl restart proftpd`

2. FTP Client Installation and Usage

- `root@client:~# apt-get -y install lftp`
- `xerus@client:~$ lftp -u ubuntu www.srv.world`
- `Enter password when prompted.`

3. Commands within the FTP session

- `lftp ubuntu@www.srv.world:~> pwd`
- `lftp ubuntu@www.srv.world:~> !pwd`
- `lftp ubuntu@www.srv.world:~> ls`
- `lftp ubuntu@www.srv.world:~> !ls -l`
- `lftp ubuntu@www.srv.world:~> cd public_html`
- `lftp ubuntu@www.srv.world:~/public_html> pwd`
- `lftp ubuntu@www.srv.world:~> put -a ubuntu.txt test.txt`
- `lftp ubuntu@www.srv.world:~> mput -a test.txt test2.txt`
- `lftp ubuntu@www.srv.world:~> get -a test.py`
- `lftp ubuntu@www.srv.world:~> mget -a test.txt test2.txt`
- `lftp ubuntu@www.srv.world:~> mkdir testdir`
- `lftp ubuntu@www.srv.world:~> rmdir testdir`
- `lftp ubuntu@www.srv.world:~> rm test2.txt`
- `lftp ubuntu@www.srv.world:~> mrm ubuntu.txt test.txt`
- `lftp ubuntu@www.srv.world:~> !cat /etc/passwd`
- `lftp ubuntu@www.srv.world:~> quit`

These are all the commands or inputs provided in the code, primarily focusing on installing and configuring the FTP server, initiating the FTP client, and performing various FTP commands such as uploading, downloading, listing, and removing files.







