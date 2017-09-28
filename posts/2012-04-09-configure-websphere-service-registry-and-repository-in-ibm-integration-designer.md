---
title: Configure WebSphere Service Registry and Repository in IBM Integration Designer
author: Seth
type: post
date: 2012-04-09T20:56:00+00:00
url: /configure-websphere-service-registry-and-repository-in-ibm-integration-designer/
blogger_blog:
  - www.sethgagnon.com
blogger_author:
  - Seth Gagnon
blogger_3e80d94236879be645dcffcd98a21f45_permalink:
  - 9183893409366634593
categories:
  - WebSphere Service Registry Repository
tags:
  - repository
  - service registry
  - websphere

---
<div class="MsoNormal" style="margin: 0 0 10pt; text-align: left;">
  <span style="font-family: Calibri;">Start IBM Integration Designer and start your local server instance in your test environment.  If you wish to connect to a secure WebSphere Service Registry and Repository registry over https, then proceed to Step 1, otherwise proceed to Step 2.</span>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">Step 1  &#8211; Import certificate</span>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">Open your admin console and navigate to Security > SSL certificate and key management > Key stores and certificates > NodeDefaultTrustStore > Signer certificates > Retrieve from port</span>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">Complete the necessary information below to retrieve the certificate for connecting to your secured WSRR registry. Click on Retrieve signer information and click OK. Save your changes and restart your server.</span>
</div>

<div class="separator" style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/wsrrpic1.png"><img src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/wsrrpic1.png?resize=320%2C241" alt="" border="0" data-recalc-dims="1" /></a>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <!--more-->
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">Step 2- Navigate to Window >Preferences>Service Registries>WebSphere Service Registry & Repository>Click on Add:</span>
</div>

<div class="separator" style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/wsrrpic3.png"><img src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/wsrrpic3.png?resize=320%2C241" alt="" border="0" data-recalc-dims="1" /></a>
</div>

<p class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">Complete the following information and ensure your provide your username and password that you can use to login to the WebSphere Service Registry & Repository as a user. Also be sure to provide the path to your WebSphere server certificates (which can be found by navigating to Security > SSL certificate and key management > Key stores and certificates and viewing the path to the NodeDefaultTrustStore). The password is usually the default JKS store password WebAS.</span>
</p>

<p class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">Step 3 – Test connection</span>
</p>

<p class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">Click on Test Connection and ensure you get a successful connection message in the Note field</span>
</p>

<div class="blogger-post-footer">
  <img src="https://blogger.googleusercontent.com/tracker/7034800122336943439-9183893409366634593?l=www.sethgagnon.com" alt="" width="1" height="1" />
</div>