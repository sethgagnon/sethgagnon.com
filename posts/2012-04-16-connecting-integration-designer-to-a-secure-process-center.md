---
title: Connecting Integration Designer to a Secure Process Center
author: Seth
type: post
date: 2012-04-16T20:09:40+00:00
url: /connecting-integration-designer-to-a-secure-process-center/
jabber_published:
  - 1334606981
publicize_results:
  - 'a:2:{s:7:"twitter";a:1:{i:223852360;a:2:{s:7:"user_id";s:10:"sethgagnon";s:7:"post_id";s:18:"191981739911032833";}}s:2:"fb";a:1:{i:585439918;a:2:{s:7:"user_id";s:9:"585439918";s:7:"post_id";s:17:"10150793983104919";}}}'
categories:
  - Integration Designer
tags:
  - IBM IID
  - Integration Designer

---
If you would like to connect your IBM Integration Designer to a secured Process Center (over HTTPS). You need to import the server certificate into your Integration Designer cacerts file.

First, open the Process Center you want to connect to in a browser and then export that certificate so that you can save it locally. For example, in Internet Explorer, click on the icon of the lock at the end of the url and then click on View Certificates.  From here, you can click on the Details tab and then select Copy to a File. The certificate export wizard opens and you can save the certificate.

<img class="size-medium wp-image-107 aligncenter" title="cert1" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/cert1.png?resize=300%2C230" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/cert1.png?w=503 503w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/cert1.png?resize=300%2C230 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/cert1.png?resize=390%2C300 390w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />

<!--more-->

Once you have the certificate saved locally, you can now import it into the Integration Designer cacerts file. From a command prompt, navigate to you IID\_INSTALL\_ROOTjdkbin and execute:

keytool.exe -import -v -file &#8220;PATH TO THE CERT YOU SAVED&#8221;  -alias ALIASNAME -keystore &#8220;IID\_INSTALL\_ROOTjdkjrelibsecuritycacerts&#8221;

where:

IID\_INSTALL\_ROOT = the path that your IID is installed to (i.e. C:IBMIntegrationDesignerv7.5.1),

PATH TO THE CERT YOU SAVED = the full path to where you saved the certificate from the export (if the path has spaces in it, then put the whole path in double quotes

ALIASNAME = name you want to store the cetificate as in the cacerts file

While this script is running, it will prompt you for a password, which the default password is **changeit**. It will then ask you a yes/no question if you want to import the certificate you provided for import. Type yes and you are done.

You will need to restart IID to connect to your secure Process Center over HTTPS.