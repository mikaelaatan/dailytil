I have been previously using GitHub to transfer files from my Linux machine to my AWS server. But after going through  [this lesson](https://www.coursera.org/learn/os-power-user/lecture/Z46ei/remote-connection-file-transfer) from [Google's class on Operating System from Coursera](https://www.coursera.org/learn/os-power-user/home/welcome), I learned that it's possible to send via **Remote Connection File Transfer**

Use Linux command  with the following syntax: 

```shell
scp -i <insert private key here> <source filename> <target location>
```

For example: 
``` shell
scp -i ~/dev/gitlab/cicd-salonappointmentsystem/cicd.pem ~/dev/csci-hw4/readme.txt ec2-user@ec2-3-91-194-135.c
ompute-1.amazonaws.com:~/ec2-user
```