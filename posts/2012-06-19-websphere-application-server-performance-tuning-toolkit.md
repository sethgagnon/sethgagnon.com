---
title: WebSphere Application Server Performance Tuning Toolkit
author: Seth
type: post
date: 2012-06-20T00:38:08+00:00
url: /websphere-application-server-performance-tuning-toolkit/
jabber_published:
  - 1340152780
email_notification:
  - 1340152780
categories:
  - General IBM
tags:
  - application tuning
  - monitoring
  - performance
  - tuning
  - websphere

---
If you are trying to find a good free tool to help with performance tuning your WebSphere Application Server environment, then I think this is a great start. IBM provides this very simple and easy to use tool. After you download (see URL below) and unzip, all you need to do is tell the tool a Deployment Manager to connect to and you can begin viewing PMI data and tuning your environment.

Once you launch the tool, you will be presented with a welcome screen (I had to block out some server names):

<img src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/06/062012_0036_websphereap1.png?w=900" alt="" data-recalc-dims="1" />

<!--more-->

You can click on the Add New Host button and specify the server information that you wish to monitor:

<img src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/06/062012_0036_websphereap2.png?w=900" alt="" data-recalc-dims="1" />

You will then see the host in the Hosts section on the upper left. If you double-click on this, it will connect the Deployment Manager and begin taking snapshots of the environment (at 1 minute intervals by default, which you can change):

<img src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/06/062012_0036_websphereap3.png?w=900" alt="" data-recalc-dims="1" />

The tool captures a lot of detailed information which you can then use to tune your environment accordingly. The bottom portion of the screen allows you to see a variety of tuning parameters and what their current values are. You can even change these values from here and it will be saved to your environment:

<img src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/06/062012_0036_websphereap4.png?w=900" alt="" data-recalc-dims="1" />

This tool is definitely worth a download if you need a free and easy to use monitor to begin tuning your environment. Along with monitoring your environments, the Tuning Toolkit records these snapshots and allows you to generate a report highlighting areas that need to be researched and tuned.

You can download it here:

<http://www.ibm.com/developerworks/websphere/downloads/peformtuning.html>