# Unit Test

Use the following information to setup a new user `pxtestuser` in WSL.

```
$ ls -al
total 12
drwxr-xr-x 1 pxtestuser pxtestuser  512 Oct 15 12:02 .
drwxr-xr-x 1 root       root        512 Oct 15 10:10 ..
-rw------- 1 pxtestuser pxtestuser  672 Oct 29 16:57 .bash_history
-rw-r--r-- 1 pxtestuser pxtestuser  220 Oct 15 10:10 .bash_logout
-rw-r--r-- 1 pxtestuser pxtestuser 3771 Oct 15 10:10 .bashrc
drwx------ 1 pxtestuser pxtestuser  512 Oct 15 10:11 .cache
drwx------ 1 pxtestuser pxtestuser  512 Oct 15 10:11 .config
drwx------ 1 pxtestuser pxtestuser  512 Oct 15 10:11 .local
-rw-rw-r-- 1 pxtestuser pxtestuser    0 Oct 29 15:56 .motd_shown
-rw-r--r-- 1 pxtestuser pxtestuser  807 Oct 15 10:10 .profile
lrwxrwxrwx 1 pxtestuser pxtestuser   36 Oct 15 11:23 bak -> /mnt/c/Users/pxtest/AppData/Local/bak
drwxrwxr-x 1 pxtestuser pxtestuser  512 Oct 29 16:01 data
lrwxrwxrwx 1 pxtestuser pxtestuser   37 Oct 15 11:23 data1 -> /mnt/c/Users/pxtest/AppData/Local/data
lrwxrwxrwx 1 pxtestuser pxtestuser   36 Oct 15 11:23 key -> /mnt/c/Users/pxtest/AppData/Local/key
drwxrwxrwx 1 pxtestuser pxtestuser  512 Oct 15 10:23 sshtest -> /home/pxtest/src/sg/PassXYZLib/Documentation/src/sshtest
lrwxrwxrwx 1 pxtestuser pxtestuser   58 Oct 15 10:49 temp -> /home/pxtest/src/sg/PassXYZLib/PassXYZLib.xunit/bin/Debug/net7.0
lrwxrwxrwx 1 pxtestuser pxtestuser   36 Oct 15 11:23 tmp -> /mnt/c/Users/pxtest/AppData/Local/tmp

$ ls data
pass_d_E8f4pEk.xyz            pass_e_EFZGmRz.xyz      pass_e_VpdPx4ZcUZs8Fpzpmuu.xyz  test_file1
pass_e_2TjEf1Dy9V2jiEgbS.xyz  pass_e_JyHzpRxcopt.xyz  pass_e_WCXaKYYvXygN3nVYW3u.xyz
```

Create soft links in WSL using the below settings.

**PxDataFile.DataFilePath**: `%USERPROFILE%\AppData\Local\data`
**PxDataFile.KeyFilePath**: `%USERPROFILE%\AppData\Local\key`
**PxDataFile.TmpFilePath**: `%USERPROFILE%\AppData\Local\tmp`
**PxDataFile.BakFilePath**: `%USERPROFILE%\AppData\Local\bak`
**PxDataFile.LogFilePath**: `%USERPROFILE%\AppData\Local\log`

```csharp
public const string DEFAULT_USERNAME = "pxtestuser";
public const string DEFAULT_PASSWORD = "pxtestpw";
public const string DEFAULT_HOSTNAME = "";
public const int DEFAULT_PORT = 22;
public const string DEFAULT_REMOTEHOMEPATH = "pxtest/";
```

Run the following command to start sshd.

```bash
$ cd /home/pxtestuser/sshtest
$ sudo /usr/sbin/sshd -D -d -f ./sshd_config
```

or

```bash
$ /usr/sbin/rsyslogd -n
$ sudo service ssh start
$ tail -f /var/log/auth.log
```