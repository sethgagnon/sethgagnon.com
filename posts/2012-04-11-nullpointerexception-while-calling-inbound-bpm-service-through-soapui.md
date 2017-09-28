---
title: NullPointerException While Calling Inbound BPM Service Through SoapUI
author: Seth
type: post
date: 2012-04-11T22:51:24+00:00
url: /nullpointerexception-while-calling-inbound-bpm-service-through-soapui/
jabber_published:
  - 1334184685
publicize_results:
  - 'a:2:{s:7:"twitter";a:1:{i:223852360;a:2:{s:7:"user_id";s:10:"sethgagnon";s:7:"post_id";s:18:"190210480156049408";}}s:2:"fb";a:1:{i:585439918;a:2:{s:7:"user_id";s:9:"585439918";s:7:"post_id";s:17:"10150782563329919";}}}'
categories:
  - BPM Application Issues
  - Business Process Manager
tags:
  - BPM
  - business process manager
  - IBM BPM
  - nullpointerexception
  - web service
  - websphere

---
While doing some application testing on the Business Process Manager (BPM) 7.5.1 Advanced platform, I noticed some strange behavior while making a call out to a Lombardi service using SoapUI. You may see this error in SoapUI:

<!--more-->

[2/16/12 14:57:34:534 CST] 00000034 wle\_inbnd\_ws  I   CWLLG1122I: The TWSOAPLogger has provided a message: Message Type: SOAP Request Name: XXXXX XML String: [http://XXXX.tws][1]&#8220;; xmlns:sch=&#8221;[http://XXXXX/schema/][2]&#8220;>;
  
<soapenv:Header />
  
<soapenv:Body>
  
<sendJobResult>
  
<batchJobID>XXXXXX</batchJobID>
  
<jobResult>
  
<returnCode>0</returnCode>
  
<returnMsg>Ended OK</returnMsg>
  
<jobStartedAt>2012-02-16 13:27:53</jobStartedAt>
  
<jobEndedAt>2012-02-16 14:07:31</jobEndedAt>
  
<isTimedOut>false</isTimedOut>
  
<isKilledByRequest>false</isKilledByRequest>
  
<isInterrupted>false</isInterrupted>
  
<resultValues>
  
<item>
  
<item>
  
<key>CONTROLM_STATUS</key>
  
<value>Ended OK</value>
  
</item>
  
<item>
  
<key>CONTROLM_JOBID</key>
  
<value>4u6hk</value>
  
</item>
  
</item>
  
</resultValues>
  
</jobResult>
  
</sendJobResult>
  
soapenv:Body>
  
soapenv:Envelope>
  
[2/16/12 14:57:34:537 CST] 00000034 wle\_inbnd\_ws  I   CWLLG1122I: The TWSOAPLogger has provided a message: Message Type: SOAP Response Name: XXXXX XML String: <http://schemas.xmlsoap.org/soap/envelope/>&#8220;; xmlns:xsd=&#8221;<http://www.w3.org/2001/XMLSchema>&#8220;; xmlns:xsi=&#8221;<http://www.w3.org/2001/XMLSchema-instance>&#8220;>;
  
<soapenv:Body>
  
<soapenv:Fault>
  
<span style="color: #ff0000;">   soapenv:Server.userException </span>
  
<span style="color: #ff0000;">      <faultstring>java.lang.NullPointerException</faultstring> </span>
  
<detail>
  
<ns1:hostname xmlns:ns1=&#8221;[http://xml.apache.org/axis/&#8221;>XXXXXns1:hostname][3]>;
  
</detail>
  
soapenv:Fault>
  
soapenv:Body>
  
soapenv:Envelope>

I have put XXXX in the request and response to protect sensitive data and I have highlighted the NullPointerException in red text.

After doing some research, it turns out that this issue appears if you have the following iFix installed on your platform:

7.5.1.0-WS-BPM-IFJR41755

You can check for this iFix by navigating to your {WAS\_INSTALL\_ROOT)/bin and executing versionInfo.sh (or bat for windows) -maintenancePackages. This will produce a list of all fixes installed on your platform. If the fix mentioned above is installed, simply bring down all of your jvms, nodeagents, and deployment manager (whole environment needs to be down). Then navigate to you Installation Manager Root directory/eclipse/tools and execute the following command:

imcl uninstall 7.5.1.0-WS-BPM-IFJR41755 -installationDirectory {WAS\_INSTALL\_ROOT}  -log /logs/uninstallfix.log

where installationDirectory is where your BPM product is installed and specify the location to where you want to write the uninstall log to.

Then bring up your whole environment and again run the versionInfo.sh -maintenancePackages command to validate that the iFix was removed.

You should then be able to execute you SoapUI request without receiving a NullPointerException.

 [1]: http://xxxx.tws/
 [2]: http://xxxxx/schema/
 [3]: http://xml.apache.org/axis/%22%3EXXXXX%3C/ns1:hostname