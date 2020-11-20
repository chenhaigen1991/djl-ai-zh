# 安装步骤

为了使您起步并获得动手学习的经验，我们需要为您设置一个运行Python，Jupyter笔记本，相关库以及运行本书本身所需的代码的环境。

（此实例是在Linux环境下进行安装）

## 1.安装JDK 11（不是jre）

需要JDK 11（或更高版本）才能运行此文件夹中提供的示例。

<code># curl -O https://download.java.net/java/GA/jdk11/13/GPL/openjdk-11.0.1_linux-x64_bin.tar.gz</code>

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

[root@Python-3.7.1 /]# ./configure

[root@Python-3.7.1 /]# make && make install

[root@Python-3.7.1 /]# python3 -V

Python 3.7.1

## 3.在python3上安装jupyter笔记本

使用以下命令在Python 3中安装Jupyter Notebook：

[root@djl /]# pip3 install jupyter

## 4.为Jupyter Notebook安装Java内核

默认情况下，jupyter Notebook仅运行Python3。您需要安装Java内核才能运行Java代码，例如DJL，这里下载jar缓慢，请耐心等待

[root@djl /]# git clone https://github.com/frankfliu/IJava.git

[root@djl /]# cd IJava/

[root@IJava /]# ./gradlew installKernel

构建完成后你会看见绿色标识BUILD SUCCESSFUL，表示安装成功

## 5.下载并运行D2L-Java笔记本

[root@djl /]# git clone https://github.com/aws-samples/d2l-java

[root@djl /]# cd d2l-java

这里的IP是内部环境IP，由于我部署的环境是在云服务器上，实际根据自己网络环境情况填写

[root@d2l-java /]# jupyter notebook --ip=XXX.XXX.XX.XX --allow-root

到此，整本书的环境搭建完成，通过访问 http://localhost:8888 该地址就会打开Jupyter笔记本，输入终端上的token，就大功告成！

这里提供一个我安装在云端的Jupyter笔记本,地址：http://47.114.1.215:8888/

token：f88e11e47d8e6be72f30d8374578c7f018263cfeb3733fab

## 6.后记

您可以通过添加Java单元来添加对DJL和MXNet的maven依赖关系，包括：

// Add the maven dependencies

%maven ai.djl:api:0.7.0-SNAPSHOT

%maven org.slf4j:slf4j-api:1.7.26

%maven org.slf4j:slf4j-simple:1.7.26

// See https://github.com/awslabs/djl/blob/master/mxnet/mxnet-engine/README.md

// for more MXNet library selection options

%maven ai.djl.mxnet:mxnet-native-auto:1.7.0-b
