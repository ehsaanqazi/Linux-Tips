### Accessing Windows Share folder in Linux

```bash
mount.cifs //192.168.29.216/WindowsShare /root/Desktop/LinuxShare -o user=Ehsaan
```

### Generate 20 Characters long string

```bash
openssl rand -base64 20
```

### Delete all specific file types in all subdirectories

```bash
find . -name \*.srt -type f -delete
```

### Create a 2048 bit RSA key with certificate

```bash
openssl req --newkey rsa:2048 -nodes -keyout private.key -x509 -out certificate.crt
```
### Remove Duplicates

```bash
sort file.log | uniq -u
```

### Number Images in a folder

```bash
ls | cat -n | while read n f; do mv "$f" "file-$n.jpg"; done
```


