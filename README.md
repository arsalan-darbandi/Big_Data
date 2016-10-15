<h1 align="center">
  <img align="center" src="https://github.com/asikhalaban/Big_Data/blob/master/img/cloud.png?raw=true">
<br>
  Hadoop and Big Data
</h1>

## Table of Contents

1. Introduction<br>
[a. A Road Map for Reader and Structures](#structures)  
[b. About Hadoop and Other Big Data Platforms](#hadoop)  
[c. Installing Hadoop and Platforms Manually](#manually)  
2. Cloudera and Hortonworks<br>
[a. Compare Cloudera and Hotronworks](#c_vs_h)  
[b. Cloudera](#cloudera)  
3. Installation<br>
[a. Installing CentOS](#centos)
[b. Installing Cloudera Manager](#manager)

<br>
## 1. Introduction
<a name="structures"/>
### a. A Road Map for Reader and Structures

In this github, it is tried to explain how to install Hadoop by using Cloudera on CentOs. It is not aimed to go to details on Big Data and platforms related to it but in some parts will be explained to briefly. 

This github maybe have problems and by sending email to me let me correct those problems and if you have problems on github or installing cloudera feel free to send email by using my email address: arsalan@darbandi.net. Also you can find the video of installing hadoop and cloudera on CentOS by following my youtube channel: https://www.youtube.com/watch? v=pRAdQtErpp4

<a name="hadoop">
### b. About Hadoop and other Platform

Hadoop is a machine which could explain as a server which try to make a connection between several nodes. On Hadoop we have one or more nodes which is called as a master. Master has an important duty to control and distribute file and data between other nodes which are called as slaves. The main important part of Hadoop is Hadoop Distribution File System(HDFS) which has a duty to split file and data and distribute them on different nodes. Hadoop to be alone cannot use for analyzing data thus we must install other tools and platform to analyze data. Hadoop has two versions from which we use V.2 as V.1 has several limitations such as number of nodes. MapReduce 2(Yarn) is one of the important tools. MapReduce(MR) splits data in to the
several maps and processes them in parallel. For instance, if we try to count words in a page, MR can divide them by paragraph and counting words of paragraphs in parallel process. In this way we are counting our data very fast.
HBase is another way to save data on Hadoop. As it was mentioned earlier HDFS is the first method to storing data on Hadoop but lack of writing and reading random data HBase comes to improve Hadoop and we can mention low latency access to small data as another benefit for HBase. Totally HBase is used when you have real-time data. There is one more data warehouse which is Hive. Hive it has a structure looks like sql but it has some disadvantages such as long time processing but it is very good to analyzing sql data by using Spark.
Ambari and CDH(Cloudera manager) are two tools for Hadoop cluster management, Ambari is used by Hortonworks however CDH is used by cloudera. There are more platforms and tools which you must know about them such as Pig, Perl and Hive are using for MR or Sqoop, Flume and Storm for moving data.

<a name="manually">
### c. Installing Hadoop and Platforms Manually

There are two ways for installing Hadoop and platforms. You can install Hadoop manually which does not suggest for first time because there are lots of points that you must be careful about them. Therefore, you should install it through with companies that have packages for it after you understand about all tools and how they are working with each other then you can install it by manual. For instance, there are lots of setup that you have to change it making connection between your tools and your nodes or the process of installing also is very important that you must install Hadoop then map reduce then installing zookeeper on odd number of nodes and after that you can install other tools. The most negative point is about version of Hadoop and other platforms, it means that you have to search and install different version of platforms to find which version of one tool is the best match to others. You can find how to Install them manually by using the book “Big Data Made Easy”[1].

<br>
## 2. Cloudera and Hortonworks:
<a name="c_vs_h"/>
### a. Compare Cloudera and Hortonworks

As It is mentioned in part 1.d there are some companies bring packages to
install Hadoop and other platforms very fast. Cloudera and Hortonworks
are two of them which are open source and you can install them as free.
This pdf does not cover materials about Hortonworks but you can find
documents how to install and use it. The method is used to compare two package of companies is figure out from documentations and information from website of two companies. Generally, it is very hard to compare both them and Cloudera is chosen because most of companies are using CDH and also documents which cloudera has are very better than Hortonworks and you can install and work with it very easily.

<a name="cloudera">
### b. Cloudera

In this part will be explained about different type of Cloudera and some important points that during installing and working with Cloudera you must be careful.
By going to http://www.cloudera.com/downloads.html you will face with 3 different
types of Cloudera. QuickStarts is a demo for Cloudera which is installed on a single node and has amazing tutorial for beginner which is suggested before installing Cloudera Manager try QuickStarts and It is built for VM and Docker. On part 4.b you can find more information about Cloudera QuickStarts.
Cloudera Manager is the second package for analyzing big data. This package is very useful because you can run it on several machines and analyzing your dataset. QuickStarts is for a node and Cloudera Director is for cloud with many nodes however Cloudera Manager can be defined for a single node or as many as nodes you need. You can find information about supported operating systems for different version of Cloudera under Download Cloudera Manager. Also you can find components which are supported by Cloudera Manager.
The last type of Cloudera is Cloudera Director which is for cloud area and this pdf does not cover it and you can find all documents related to it on Cloudera website.


<br>
## 2. Installation:
<a name="centos"/>
### a. Installing CentOS

In this part will be shown how to install CentOS and is selected because it is one of the operator system which Cloudera supports. Moreover, in this pdf is tried to show how to install CentOs 6.6 and installing Cloudera on this version and if you want to install CentOs 7 or latest version of CentOs maybe you will face with several problems since you must find other documents to see how installing Cloudera on those versions. The number of machines that are installed by this tutorial is three and by following these steps in this pdf you can install cloudera on two or more nodes. An important point about virtual machine, VMware is selected as a virtual machine because for connecting different machines
together it does not need any changes in setup however for Virtual Box or other virtual machines you need to change settings.
For installing Cloudera, There is a master node which has better system configuration and two slave nodes with very simple configuration.
Master’s Hard disk capacity is depended on your data but for number of processor, it is better you give 2 processor cores and for memory more than 4GB which I give 8GB ([Fig.1](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.1.png?raw=true)). while you can leave configuration of slaves as default.

After installation page comes up you only have to past steps without any changes until the page that asks you for Hostname. 
hostname you should put name with name of group or cluster. For instance, First by selecting master or any name for you master as the name for your system then by selecting shadoop which you can define any name you want for your cluster([Fig.2](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.2.png?raw=true)).

pass all other steps without any changes until the page to select mode of your operator system. For master Desktop and for slaves Database server are selected because on Desktop you have GUI which is necessary for CDH however GUI it does not have any usage for slaves([Fig.3](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.3.png?raw=true)).



<a name="manager">
### b. Installing Cloudera Manager

After installing CentOs on all machines, it is time to change a couple of changes on some of system files to make a connection between all of nodes in your cluster.
First you have to login to the system, by typing "root" and pressing enter you will login as a root then you have to insert root password.

I used ### to add comment for those codes need more description. 
```javascript
### slave1 is name of one of my nodes. 
slave1 login: root
Password: 
```
Below command is used for checking connection of system([Fig.4](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.4.png?raw=true)). If your system doesn't show any ip, it means that you are not connected to any system. 
```javascript
[root@slave1 ~]# ip route show
```
To connect the system to a network, First we have to go to below direction([Fig.5](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.5.png?raw=true)). 
```javascript
[root@slave1 ~]# cd /etc/sysconfig/network-scripts  ### cd is a Linux command to change the directory/folder.
[root@slave1 network-scripts]# ls ### By this command you sould see all files and folders inside the directory/folder that we are in.  
```
To make a connection between your system to network we have to change ONBOOT from no to yes in ifcfg file. This file may has different name in different system because of that we used ls command to find the name.
```javascript
[root@slave1 network-scripts]# vi ifcfg-eth0 ### Editing ifcfg-eth0 file, you can use nano instead of vi as another editer. 
```
Information in that file(leave all setting as default except ONBOOT)([Fig.6](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.6.png?raw=true)):
```javascript
### To make a change in a folder by pressing "a" you are able to make any changes you want.
DEVICE=eth0
HWADDR=##:##:##:##:##:##
TYPE=Ethernet
UUID=########-####-####-####-#############
ONBOOT=yes
NM_CONTROLLED=yes
BOOTPROTO=dhcp
### After make all changes you want by pressing escape button and then by typing ":wq!" you can save and exit from the file. 
```
After all changes you should restart your system([Fig.7](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.7.png?raw=true)).
```javascript
[root@slave1 network-scripts]# service network restart
```
Repeat all these processes for all nodes you have.
We assigned hostname during installaion for nodes but if you forgot to do it you can do it now by editing the file network in etc/sysconfig directory. 
```javascript
[root@slave1 network-scripts]# cd ### You would go back to first page. 
[root@slave1 ~]# cd /etc/sysconfig
[root@slave1 sysconfig]# vi network
```
```javascript
NETWORKING=yes
HOSTNAME=slave1
```
Now it is time to introduce ip and name of each system to other systems in the cluster by adding name and ip of all machines for all machines. By using vi /etc/hosts you are opening hosts file and you must add ip and name which by using ip route show you can find. Following [Fig.8](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.8.png?raw=true) and [Fig.9](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.9.png?raw=true) and do not forget to do it for all machines.
```javascript
[root@slave1 sysconfig]# ip route show ### check ip configuration
[root@slave1 sysconfig]# vi /etc/hosts 
```
```javascript
127.0.0.1 localhost localhost.localdomain localhost4 localhost4.localdomain4
::1       localhost localhost.localdomain localhost6 localhost6.localdomain6

192.168.101.173 master.shadoop.com master
192.168.101.174 slave1.shadoop.com slave1
192.168.101.175 slave2.shadoop.com slave2
```
Only two more steps are left to do on all machines before installing Cloudera.
First you should disable selinux by going to below directory and after that reboot your systems([Fig.10](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.10.png?raw=true)).
```javascript
[root@slave1 sysconfig]# vi /etc/selinux/config
```
```javascript
# This file controls the state of SELinux on the system.
# SELINUX= can take one of these three values:
#     enforcing - SELinux security policy is enforced.
#     permissive - SELinux prints warnings instead of enforcing.
#     disabled - No SELinux policy is loaded.
SELINUX=disabled
# SELINUXTYPE= can take one of these two values:
#     targeted - Targeted processes are protected,
#     mls - Multi Level Security protection.
SELINUXTYPE=targeted
```
Second, you must stop firewall on master machine and iptables on slaves. try using service iptables stop and service ip6tables stop on slaves and for master by going to system-tab\ administration\ firewall, disable it from there ([Fig.11](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.11.png?raw=true)),([Fig.12](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.12.png?raw=true)).
```javascript
[root@slave1 ~]# service iptables stop
[root@slave1 ~]# service ip6tables stop
```
After all these steps, your machines are ready for Cloudera. By going to Cloudera link address(www.cloudera.com), by going to download page you can find Cloudera Manager there. Click on download it will give you commands to installing Cloudera on your master. Attention that instead of using installer/latest/ we want to install version 5.4.0 so change latest to 4.5.0 ([Fig.13](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.13.png?raw=true)),([Fig.14](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.14.png?raw=true)). Moreover, under that instructions you can find how to prepare your machines to install Cloudera which we prepared.

After Cloudera installing is done your browser automatically will be open and by typing username and password both “admin” login to your account and you do not need to change any options, only in page to select edition you can select free edition. In the page “specify hosts for your CDH cluster installation.” by typing name of your systems which in this pdf are used as “master, slave1, slave2”, you can find machines in the cluster. At last by adding password for your ssh your installation will start.

After all these steps and finish installation, you must to configure setting of Cloudera and it was left as default([Fig.15](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.15.png?raw=true)),([Fig.16,17](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.16,17.png?raw=true)). 
Finally, in the last figure you can see area of Cloudera but in some cases you will face with red and yellow circles which are important but they are configuration issue such as memory capacity and other things which do not have make any issue to run your analyzing([Fig.18](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.18.png?raw=true)).


