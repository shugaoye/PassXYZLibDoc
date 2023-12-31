# Unit Test

Use the following information to setup a new user `pxtestuser` in WSL.

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