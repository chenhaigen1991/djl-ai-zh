# 安装

为了使您起步并获得动手学习的经验，我们需要为您设置一个运行Python，Jupyter笔记本，相关库以及运行本书本身所需的代码的环境。

## 安装JDK 11（不是jre）

需要JDK 11（或更高版本）才能运行此文件夹中提供的示例。

[root@djl ~]#
curl -O https://download.java.net/java/GA/jdk11/13/GPL/openjdk-11.0.1_linux-x64_bin.tar.gz

[root@djl ~]#
tar zxvf openjdk-11.0.1_linux-x64_bin.tar.gz

[root@djl ~]#
mv jdk-11.0.1 /usr/local/

[root@djl ~]#
vi /etc/profile.d/jdk11.sh

#create new

export JAVA_HOME=/usr/local/jdk-11.0.1

export PATH=$PATH:$JAVA_HOME/bin

[root@djl ~]#
source /etc/profile.d/jdk11.sh

[root@djl ~]#
java -version

openjdk version "11.0.1" 2018-10-16

OpenJDK Runtime Environment 18.9 (build 11.0.1+13)

OpenJDK 64-Bit Server VM 18.9 (build 11.0.1+13, mixed mode)

