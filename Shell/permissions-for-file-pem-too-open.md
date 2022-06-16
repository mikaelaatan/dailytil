"PEM or Privacy Enhanced Mail is **a Base64 encoded DER certificate**."[^1] 

PEM files are private keys generated when connecting to a remote server. In my case, I use this to connect to my AWS server for deployment purposes. 

To fix the error: "Permissions 0644 for 'file.pem' are too open," use Linux bash and enter the command:
```bash
$ sudo chmod 600 /path/to/my/file.pem
```

The `chmod` command changes the permission of the file and `600` means that only the owner can read and write  the file. 

[^1]: [What is PEM Format? (digicert.com)](https://knowledge.digicert.com/quovadis/ssl-certificates/ssl-general-topics/what-is-pem-format.html)