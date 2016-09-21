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
