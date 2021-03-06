# JDK 安装


## CentOS 下过程

- JDK 在 CentOS 和 Ubuntu 下安装过程是一样的，所以这里不再讲 Ubuntu 系统下的安装
- JDK 1.8 下载
    - 官网：<http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html>
    - `jdk-8u72-linux-x64.tar.gz`：<http://pan.baidu.com/s/1eQZffbW>
    - `jdk-8u212-linux-x64.tar.gz`，密码:wmwn：<https://pan.baidu.com/s/1a2-QqzOy3aavynneEBr1DQ>
- 默认 CentOS 有安装 openJDK，建议先卸载掉
 - 检查 JDK 命令：`java -version`
 - 查询本地 JDK 安装程序情况； `rpm -qa|grep java`
    - 我查询出来的结果如下：
   
```
java-1.6.0-openjdk-1.6.0.38-1.13.10.0.el6_7.x86_64
java-1.7.0-openjdk-1.7.0.95-2.6.4.0.el6_7.x86_64
tzdata-java-2015g-2.el6.noarch
```

- 卸载上面三个文件（`--nodeps` 的作用：忽略依赖的检查）：
- `sudo rpm -e --nodeps java-1.6.0-openjdk-1.6.0.38-1.13.10.0.el6_7.x86_64`
- `sudo rpm -e --nodeps java-1.7.0-openjdk-1.7.0.95-2.6.4.0.el6_7.x86_64`
- `sudo rpm -e --nodeps tzdata-java-2015g-2.el6.noarch`
- 也可以一起卸载：`sudo rpm -e --nodeps java-1.6.0-openjdk-1.6.0.38-1.13.10.0.el6_7.x86_64 java-1.7.0-openjdk-1.7.0.95-2.6.4.0.el6_7.x86_64 tzdata-java-2015g-2.el6.noarch`
- 如果是 CentOS 7 的话：`sudo rpm -e --nodeps javapackages-tools-3.4.1-11.el7.noarch java-1.8.0-openjdk-1.8.0.121-0.b13.el7_3.x86_64 java-1.7.0-openjdk-headless-1.7.0.131-2.6.9.0.el7_3.x86_64 python-javapackages-3.4.1-11.el7.noarch java-1.7.0-openjdk-1.7.0.131-2.6.9.0.el7_3.x86_64 java-1.8.0-openjdk-headless-1.8.0.121-0.b13.el7_3.x86_64 tzdata-java-2017a-1.el7.noarch`

### JDK 1.8 安装

- 解压：`tar zxvf jdk-8u212-linux-x64.tar.gz`
- 编辑配置文件：`sudo vim ~/.zshrc`
- 在该文件的最尾巴，添加下面内容：
```
# JDK
JAVA_HOME=/usr/local/jdk1.8.0_212
JRE_HOME=$JAVA_HOME/jre
PATH=$PATH:$JAVA_HOME/bin
CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
export JAVA_HOME
export JRE_HOME
export PATH
export CLASSPATH
```
- 执行命令，刷新该配置（必备操作）：`source ~/.zshrc`
- 检查是否使用了最新的 JDK：`java -version`



## 其他

- JDK 历史版本下载地址整理（不间断更新）：
    - **JDK 9**：<https://jdk9.java.net/download/>
    - **JDK 8**：<http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html>
    - **JDK 7**：<http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html>
        - JDK 7 - 64 位：`wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/7u79-b15/jdk-7u79-linux-x64.tar.gz`
        - JDK 7 - 32 位：`wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/7u79-b15/jdk-7u79-linux-i586.tar.gz`
    - **JDK 6**：<http://www.oracle.com/technetwork/java/javasebusiness/downloads/java-archive-downloads-javase6-419409.html>



## 资料

 - <http://www.jikexueyuan.com/course/480_1.html?ss=1>

 