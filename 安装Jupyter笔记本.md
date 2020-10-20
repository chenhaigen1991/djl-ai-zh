# 安装步骤

为了使您起步并获得动手学习的经验，我们需要为您设置一个运行Python，Jupyter笔记本，相关库以及运行本书本身所需的代码的环境。

（此实例是在Linux环境下进行安装）

## 1.安装JDK 11（不是jre）

需要JDK 11（或更高版本）才能运行此文件夹中提供的示例。

[root@djl /]# curl -O https://download.java.net/java/GA/jdk11/13/GPL/openjdk-11.0.1_linux-x64_bin.tar.gz

[root@djl /]# tar zxvf openjdk-11.0.1_linux-x64_bin.tar.gz

[root@djl /]# mv jdk-11.0.1 /usr/local/

[root@djl /]# vi /etc/profile.d/jdk11.sh

#create new

export JAVA_HOME=/usr/local/jdk-11.0.1

export PATH=$PATH:$JAVA_HOME/bin

[root@djl /]# source /etc/profile.d/jdk11.sh

[root@djl /]# java -version

openjdk version "11.0.1" 2018-10-16

OpenJDK Runtime Environment 18.9 (build 11.0.1+13)

OpenJDK 64-Bit Server VM 18.9 (build 11.0.1+13, mixed mode)

到此java环境就算安装成功了！

## 2.安装Python3（文档版本是3.7.1，根据实际情况自选版本安装，若自带Python环境请跳过）

[root@47 /]# wget https://www.python.org/ftp/python/3.7.1/Python-3.7.1.tgz

如若出现找不到wget命令，输入yum -y install wget，安装其依赖将会被安装

[root@djl /]# tar -zxvf Python-3.7.1.tgz

[root@djl /]# cd Python-3.7.1

[root@djl /]# ./configure

[root@djl /]# make && make install

[root@djl /]# python3 -V

Python 3.7.1
