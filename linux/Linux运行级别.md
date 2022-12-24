## 运行级别

Linux操作系统有7种运行级别，如下：

- 0：关机状态，不能将0设置为默认的运行级别，否则系统无法正常启动.
- 1：单用户模式，root权限，用于系统维护(例如忘记密码)，禁止远程登陆.
- 2：多用户模式，命令行界面，无网络.
- 3：多用户模式，命令行界面，有网络.
- 4：保留.
- 5：多用户模式，图形户界面.
- 6：重启状态，不能将6设置为默认的运行级别，否则系统无法正常启动.



## 查看、切换运行级别

Linux操作系统默认是哪种运行级别，取决于 `/etc/systemd/system/default.target` 链接了 `/usr/lib/systemd/system/` 目录下的那个目标文件，Linux操作系统7种运行级别对应的目标文件如下表：

| 运行级别 | 目标文件         | 其它目标文件      |
| -------- | ---------------- | ----------------- |
| 0        | runlevel0.target | poweroff.target   |
| 1        | runlevel1.target | rescue.target     |
| 2        | runlevel2.target | multi-user.target |
| 3        | runlevel3.target | multi-user.target |
| 4        | runlevel4.target | multi-user.target |
| 5        | runlevel5.target | graphical.target  |
| 6        | runlevel6.target | reboot.target     |

查看当前Linux使用的运行级别：

```shell
# systemctl get-default
systemctl get-default
```

修改Linux的运行级别，需要重启后才能生效：

```shell
# systemctl set-default 目标文件
systemctl set-default rescue.target
```

修改Linux的运行级别，不需要重启便可生效：

```shell
# systemctl isolate 目标文件
systemctl isolate rescue.target
```



## 关机指令

```shell
init 0
shutdown -h now
shutdown -h 0:00
shutdown -h +10
halt
poweroff
```



## 重启指令

```shell
init 6
shutdown -r now
shutdown -r 0:00
shutdown -r +10
reboot
```

