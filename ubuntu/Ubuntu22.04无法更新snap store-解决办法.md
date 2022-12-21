## 问题再现

在Ubuntu中，snap store是用来安装和更新应用软件的，但是snap store无法更新自己.



## 原因

一个应用软件在更新时，这个应用软件是无法运行的.



## 解决办法

通过以下步骤，使用命令行的方式对snap store进行更新.

1. 输入如下命令

   ```shell
   sudo snap refresh snap-store
   ```

2. 输入如下命令：

   ```shell
   kill 进程号
   ```

   第一条命令执行时会报错，因为snap store正在运行，这条命令的作用是杀死snap进程.

3. 输入如下命令：

   ```shell
   sudo snap refresh snap-store
   ```

4. 到这里，snap store就更新完成了.
