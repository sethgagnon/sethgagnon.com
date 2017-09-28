---
title: Not Seeing Events Come Through After Upgrading to IBM Business Monitor Version 8.0.1.1?
author: Seth
type: post
date: 2013-05-24T15:58:05+00:00
url: /not-seeing-events-come-through-after-updating-to-ibm-business-monitor-to-version-8-0-1-1/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - BPM Infrastructure Issues
  - Business Monitor
  - Business Process Manager
tags:
  - business monitor
  - business process manager
  - events
  - IBM
  - IBM BPM
  - IBM Business Monitor
  - monitor

---
After a recent upgrade to both IBM Business Process Manager Advanced and IBM Business Monitor to version 8.0.1.1, events stopped flowing through in our cross cell environment configuration, despite this working prior to the upgrade. There were no errors in any log files and the events were being emitted from the applications. After some troubleshooting, it was noticed that the events were flowing through to the **LombardiJMSEmitterErrorQueue**, instead of the** LombardiJMSEmitterInputQueue**. (If you need to see instructions on setting up cross cell communication between BPM and Monitor, please visit my posting found here:  <a title="Setting Up Cross Cell Communication Between IBM Business Monitor and IBM Business Process Manager" href="http://www.sethgagnon.com/setting-up-cross-cell-communication-between-ibm-business-monitor-and-ibm-business-process-manager/" target="_blank">Setting Up Cross Cell Communication Between BPM and Monitor</a>.)

IBM does provide specific instructions for applying the Business Monitor fix pack, found here:

<a title="Installing IBM Business Monitor V8.0.1 Fix Pack 1" href="http://www-01.ibm.com/support/docview.wss?uid=swg27037908" target="_blank">http://www-01.ibm.com/support/docview.wss?uid=swg27037908</a>

However, there is a specific section that we determined to be the root of the issue described above. In the section of the instructions titled &#8220;Updating support applications in a cross-cell environment,&#8221; the instructions state that if your BPM environment is already at version 8.0.1.1, then you do not need to copy over the plugins from the Monitor cell. It turns out, that you do actually need to copy these plugins over, even if your BPM environment is at version 8.0.1.1. After the plugins were copied over and a complete restart of both the BPM and Monitor environments, we started seeing events flowing through properly again.

&nbsp;

&nbsp;