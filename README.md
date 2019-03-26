# hdfs-over-sftp
SFTP server which works on a top of HDFS

Hdfs-over-sftp is an open source project based on Apache sshd to access and operate HDFS through SFTP protocol

# How to Run?
1. import project to your IDE(e.g: Intellij Idea).
2. run `com.avery.hdfs.sftp.SftpServer#main`.
3. input`sftp -oPort=2233 -o HostKeyAlgorithms=+ssh-dss yourusername@localhost` at your terminal and press "Return" key.
4. enter "yes".
5. enter your password and  press "Return" key.
```
AveryZhong$ sftp -oPort=2233 -o HostKeyAlgorithms=+ssh-dss root@localhost
root@localhost's password: 
Connected to root@localhost.
sftp> ls          
hbase               inject              log                 logs                merger              
opt                 security            test                tmp                 
user                words.txt           
sftp> 

```

# Configuration
### Server conf
Edit the `resources/hdfs-over-sftp.properties` file as yours, some conf like this:
```
#uncomment this to run sftp server
host = localhost
port = 2233
# hdfs uri
hdfs-uri = hdfs://172.16.0.234:8020
```
 ### Users conf
 Edit the `resources/users.properties` file file as yours, some conf like this:
 ```
# username: admin, password: 123456 (md5 format)
sftpserver.user.admin.userpassword=e10adc3949ba59abbe56e057f20f883e
sftpserver.user.admin.homedirectory=/log
sftpserver.user.admin.enableflag=true

# username: sftpuser, password: 123456 (md5 format)
sftpserver.user.sftpuser.userpassword=e10adc3949ba59abbe56e057f20f883e
sftpserver.user.sftpuser.homedirectory=/log/log-download
sftpserver.user.sftpuser.enableflag=true


 
 ```
