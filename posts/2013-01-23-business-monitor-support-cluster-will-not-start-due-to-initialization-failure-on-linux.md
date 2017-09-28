---
title: Business Monitor Support Cluster Will Not Start Due to Initialization Failure on Linux
author: Seth
type: post
date: 2013-01-23T21:30:05+00:00
url: /business-monitor-support-cluster-will-not-start-due-to-initialization-failure-on-linux/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - Business Monitor
tags:
  - business monitor
  - initialization failure
  - linux
  - monitor
  - Support cluster
  - websphere

---
If you are running your Business Monitor installation on Redhat Linux 6.x, you may encounter the following issue when trying to start your Support cluster members:

**WSVR0501E: Error creating component com.ibm.ws.channelfw.secure.FirstChannelActions**

**java.lang.NoClassDefFoundError: com.ibmws.process.linuxutil.ThreadUtil (initialization failure)**

**Caused by: java.lang.NoClassDefFoundError: com.ibm.ws.process.linuxutil.ThreadUtil (initialization failure)**
  
 **at java.lang.J9VMInternals.initialize(J9VMInternals.java:168)**

<!--more-->

and see this in your FFDC logs:

<div>
  <p>
    <b>FFDC Exception:java.lang.NoClassDefFoundError SourceId:null ProbeId:1011 Reporter:com.ibm.ws.runtime.component.ContainerHelper@81c1141</b><br /> <b>java.lang.NoClassDefFoundError: com.ibm.ws.process.linuxutil.ThreadUtil (initialization failure)</b><br /> <b>Caused by: java.lang.UnsatisfiedLinkError: Ws60ProcessManagement (/opt/IBM/MonV8/cognos/bin64/libfreebl3.so: version `NSSRAWHASH_3.12.3&#8242; not found (required by /lib64/libcrypt.so.1))</b>
  </p>
  
  <p>
    Fortunately, there is a fairly easy fix. It turns out that the libfreebl3.so file that is shipped with COGNOS 10.1.1 is not compatible with Redhat Linux 6.x. To resolve, you need to edit your .bashrc or .profile for the user id you are running Monitor under to include the following:
  </p>
  
  <div>
    <p>
      <b>export LD_PRELOAD=/lib64/libfreebl3.so</b>
    </p>
    
    <p>
      Please see the following IBM Support document outlining the issue and the resolution:
    </p>
    
    <p>
      <a href="http://www-01.ibm.com/support/docview.wss?uid=swg21612810" target="_blank">http://www-01.ibm.com/support/docview.wss?uid=swg21612810</a>
    </p>
    
    <p>
      &nbsp;
    </p>
  </div>
</div>