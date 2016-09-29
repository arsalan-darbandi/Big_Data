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
# 1. Introduction
<a name="structures"/>
## a. A Road Map for Reader and Structures

In this github, it is tried to explain how to install Hadoop by using Cloudera on CentOs. It is not aimed to go to details on Big Data and platforms related to it but in some parts will be explained to briefly. 

This github maybe have problems and by sending email to me let me correct those problems and if you have problems on github or installing cloudera feel free to send email by using my email address: arsalan@darbandi.net. Also you can find the video of installing hadoop and cloudera on CentOS by following my youtube channel: https://www.youtube.com/watch? v=pRAdQtErpp4

<a name="hadoop">
## b. About Hadoop and other Platform

Hadoop is a machine which could explain as a server which try to make a connection between several nodes. On Hadoop we have one or more nodes which is called as a master. Master has an important duty to control and distribute file and data between other nodes which are called as slaves. The main important part of Hadoop is Hadoop Distribution File System(HDFS) which has a duty to split file and data and distribute them on different nodes. Hadoop to be alone cannot use for analyzing data thus we must install other tools and platform to analyze data. Hadoop has two versions from which we use V.2 as V.1 has several limitations such as number of nodes. MapReduce 2(Yarn) is one of the important tools. MapReduce(MR) splits data in to the
several maps and processes them in parallel. For instance, if we try to count words in a page, MR can divide them by paragraph and counting words of paragraphs in parallel process. In this way we are counting our data very fast.
HBase is another way to save data on Hadoop. As it was mentioned earlier HDFS is the first method to storing data on Hadoop but lack of writing and reading random data HBase comes to improve Hadoop and we can mention low latency access to small data as another benefit for HBase. Totally HBase is used when you have real-time data. There is one more data warehouse which is Hive. Hive it has a structure looks like sql but it has some disadvantages such as long time processing but it is very good to analyzing sql data by using Spark.
Ambari and CDH(Cloudera manager) are two tools for Hadoop cluster management, Ambari is used by Hortonworks however CDH is used by cloudera. There are more platforms and tools which you must know about them such as Pig, Perl and Hive are using for MR or Sqoop, Flume and Storm for moving data.

<a name="manually">
## c. Installing Hadoop and Platforms Manually

There are two ways for installing Hadoop and platforms. You can install Hadoop manually which does not suggest for first time because there are lots of points that you must be careful about them. Therefore, you should install it through with companies that have packages for it after you understand about all tools and how they are working with each other then you can install it by manual. For instance, there are lots of setup that you have to change it making connection between your tools and your nodes or the process of installing also is very important that you must install Hadoop then map reduce then installing zookeeper on odd number of nodes and after that you can install other tools. The most negative point is about version of Hadoop and other platforms, it means that you have to search and install different version of platforms to find which version of one tool is the best match to others. You can find how to Install them manually by using the book “Big Data Made Easy”[1].

<br>
# 2. Cloudera and Hortonworks:
<a name="c_vs_h"/>
## a. Compare Cloudera and Hortonworks

As It is mentioned in part 1.d there are some companies bring packages to
install Hadoop and other platforms very fast. Cloudera and Hortonworks
are two of them which are open source and you can install them as free.
This pdf does not cover materials about Hortonworks but you can find
documents how to install and use it. The method is used to compare two package of companies is figure out from documentations and information from website of two companies. Generally, it is very hard to compare both them and Cloudera is chosen because most of companies are using CDH and also documents which cloudera has are very better than Hortonworks and you can install and work with it very easily.

<a name="cloudera">
## b. Cloudera

In this part will be explained about different type of Cloudera and some important points that during installing and working with Cloudera you must be careful.
By going to http://www.cloudera.com/downloads.html you will face with 3 different
types of Cloudera. QuickStarts is a demo for Cloudera which is installed on a single node and has amazing tutorial for beginner which is suggested before installing Cloudera Manager try QuickStarts and It is built for VM and Docker. On part 4.b you can find more information about Cloudera QuickStarts.
Cloudera Manager is the second package for analyzing big data. This package is very useful because you can run it on several machines and analyzing your dataset. QuickStarts is for a node and Cloudera Director is for cloud with many nodes however Cloudera Manager can be defined for a single node or as many as nodes you need. You can find information about supported operating systems for different version of Cloudera under Download Cloudera Manager. Also you can find components which are supported by Cloudera Manager.
The last type of Cloudera is Cloudera Director which is for cloud area and this pdf does not cover it and you can find all documents related to it on Cloudera website.


<br>
# 2. Installation:
<a name="centos"/>
## a. Installing CentOS

In this part will be shown how to install CentOS and is selected because it is one of the operator system which Cloudera supports. Moreover, in this pdf is tried to show how to install CentOs 6.6 and installing Cloudera on this version and if you want to install CentOs 7 or latest version of CentOs maybe you will face with several problems since you must find other documents to see how installing Cloudera on those versions. The number of machines that are installed by this tutorial is three and by following these steps in this pdf you can install cloudera on two or more nodes. An important point about virtual machine, VMware is selected as a virtual machine because for connecting different machines
together it does not need any changes in setup however for Virtual Box or other virtual machines you need to change settings.
For installing Cloudera, There is a master node which has better system configuration and two slave nodes with very simple configuration.
Master’s Hard disk capacity is depended on your data but for number of processor, it is better you give 2 processor cores and for memory more than 4GB which I give 8GB(Fig.1) while you can leave configuration of slaves as default.

![Fig.1](https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.1.png?raw=true)
<img align="center" width="100px" src="https://github.com/asikhalaban/Big_Data/blob/master/img/Fig.1.png?raw=true">


### Image 1

After installation page comes up you only have to past steps without any changes until the page that asks you for Hostname. 
hostname you should put name with name of group or cluster. For instance, First by selecting master or any name for you master as the name for your system then by selecting shadoop which you can define any name you want for your cluster(Fig.2).

### Image 2

pass all other steps without any changes until the page to select mode of your operator system. For master Desktop and for slaves Database server are selected because on Desktop you have GUI which is necessary for CDH however GUI it does not have any usage for slaves(Fig.3).

### Image 3

<a name="cloudera">
## b. Cloudera

In this part will be explained about different type of Cloudera and some important points that during installing and working with Cloudera you must be careful.
By going to http://www.cloudera.com/downloads.html you will face with 3 different
types of Cloudera. QuickStarts is a demo for Cloudera which is installed on a single node and has amazing tutorial for beginner which is suggested before installing Cloudera Manager try QuickStarts and It is built for VM and Docker. On part 4.b you can find more information about Cloudera QuickStarts.
Cloudera Manager is the second package for analyzing big data. This package is very useful because you can run it on several machines and analyzing your dataset. QuickStarts is for a node and Cloudera Director is for cloud with many nodes however Cloudera Manager can be defined for a single node or as many as nodes you need. You can find information about supported operating systems for different version of Cloudera under Download Cloudera Manager. Also you can find components which are supported by Cloudera Manager.
The last type of Cloudera is Cloudera Director which is for cloud area and this pdf does not cover it and you can find all documents related to it on Cloudera website.

