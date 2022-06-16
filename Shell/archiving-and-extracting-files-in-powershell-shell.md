## Windows Powershell

**Archive file**
```shell
Compress-Archive -Path  <folder or file path here, file> <zip path>
```

**Unarchive file**
```shell
Expand-Archive -Path <source> -DestinationPath <destination>
```


---
## Linux Bash

**Installing 7ZIP**
```shell
sudo apt install p7zip-full
```

**Extracting archive**
```shell
7z e <archive file path>
# extracts files to archive filename folder
```

**Extracting TAR file**
```shell
sudo tar -xvf <filename extract_me.tar>
```

**Archiving TAR files**
```shell
tar -cvf Planets.tar --absolute-names 
/home/qwiklab/documents/Earth /home/qwiklab/documents/Mercury /home/qwiklab/documents/Venus
```
