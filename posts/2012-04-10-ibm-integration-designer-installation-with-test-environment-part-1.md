---
title: IBM Integration Designer Installation with Test Environment Part 1
author: Seth
type: post
date: 2012-04-10T08:00:00+00:00
url: /ibm-integration-designer-installation-with-test-environment-part-1/
blogger_blog:
  - www.sethgagnon.com
blogger_author:
  - Seth Gagnon
blogger_3e80d94236879be645dcffcd98a21f45_permalink:
  - 2402512651849882764
publicize_results:
  - 'a:2:{s:7:"twitter";a:1:{i:223852360;a:2:{s:7:"user_id";s:10:"sethgagnon";s:7:"post_id";s:18:"190155655208894465";}}s:2:"fb";a:1:{i:585439918;a:2:{s:7:"user_id";s:9:"585439918";s:7:"post_id";s:17:"10150782150464919";}}}'
categories:
  - Integration Designer
tags:
  - IBM IID
  - Integration Designer
  - websphere

---
### This is the first of a two part series that outlines the installation and configuration process for IBM Integration Designer v7.5

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 19px; font-style: normal; font-variant: normal; font-weight: bold; text-decoration: none; vertical-align: baseline;">Installation Process</span>
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Prior to installation, open Control Panel > Administrative Services > Computer Management and Create a new local user named bpmadmin following the password policies for your operating system (password1):</span>

[<img class="alignnone size-medium wp-image-252" title="1" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/1-300x296.png?resize=300%2C296" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/1.png?resize=300%2C296 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/1.png?w=384 384w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][1]

<!--more-->


  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Also Create new local Groups named DB2ADMNS and DB2USERS and add the local user bpmadmin to those groups:</span>

[<img class="alignnone size-medium wp-image-253" title="2" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/2-300x159.png?resize=300%2C159" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/2.png?resize=300%2C159 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/2.png?w=463 463w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][2]

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Add the bpmadmin local user to the administrators group:</span>

[<img class="alignnone size-medium wp-image-254" title="3" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/3-300x159.png?resize=300%2C159" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/3.png?resize=300%2C159 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/3.png?w=463 463w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][3]

&nbsp;

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Extract Integration Designer and Test Environment files to the same directory. For example see below:</span>

[<img class="alignnone size-medium wp-image-255" title="4" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/4-300x223.png?resize=300%2C223" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/4.png?resize=300%2C223 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/4.png?w=800 800w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][4]

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Open the launchpad.exe file and select the first option as seen below. Indicate if you are able to install as an administrative user or not. To install DB2 Express, you will need admin rights. This is the recommended installation method.</span>

[<img class="alignnone size-medium wp-image-256" title="5" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/5-300x210.png?resize=300%2C210" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/5.png?resize=300%2C210 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/5.png?w=1000 1000w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][5]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Click Check for Other Versions, Fixes, and Extensions. Select the most recent versions for the options you want to install on the Install Packages Page. You want to make sure you have Integration Designer 7.5.0.101 or higher. Click Next:</span>

[<img class="alignnone size-medium wp-image-257" title="6" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/6-300x181.png?resize=300%2C181" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/6.png?resize=300%2C181 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/6.png?resize=1024%2C620 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/6.png?w=1280 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][6]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Make sure all fixes are selected and click Next:</span>

[<img class="alignnone size-medium wp-image-266" title="7" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/71-300x181.png?resize=300%2C181" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/71.png?resize=300%2C181 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/71.png?resize=1024%2C620 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/71.png?w=1280 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][7]

[<img class="alignnone size-medium wp-image-267" title="8" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/81-300x225.png?resize=300%2C225" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/81.png?resize=300%2C225 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/81.png?w=1024 1024w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][8]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Select the installation directories and click Next:</span>

[<img class="alignnone size-medium wp-image-268" title="9" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/91-300x225.png?resize=300%2C225" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/91.png?resize=300%2C225 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/91.png?w=1024 1024w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][9]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Select appropriate translation packages and click Next:</span>

[<img class="alignnone size-medium wp-image-269" title="10" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/101-300x225.png?resize=300%2C225" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/101.png?resize=300%2C225 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/101.png?w=1024 1024w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][10]

[<img class="alignnone size-medium wp-image-271" title="11" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/112-300x225.png?resize=300%2C225" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/112.png?resize=300%2C225 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/112.png?w=1024 1024w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][11]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Click Next on the translations supported:</span>

[<img class="alignnone size-medium wp-image-272" title="12" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/121-300x225.png?resize=300%2C225" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/121.png?resize=300%2C225 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/121.png?w=1024 1024w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][12]

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Do </span><span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: bold; text-decoration: none; vertical-align: baseline;">NOT</span><span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;"> install the Process Server Profile or the WESB profile at this time. You will create these later using the Profile Management Tool. Click Next on the installation package summary:</span>

[<img class="alignnone size-medium wp-image-264" title="13" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/13-300x181.png?resize=300%2C181" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/13.png?resize=300%2C181 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/13.png?resize=1024%2C620 1024w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/13.png?w=1280 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][13]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Enter the bpmadmin user that you previously created for the profile configuration and click Next:</span>

[<img class="alignnone size-medium wp-image-273" title="14" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/14-300x225.png?resize=300%2C225" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/14.png?resize=300%2C225 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/14.png?w=1024 1024w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][14]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Select the appropriate bit architecture for Websphere:</span>

[<img class="alignnone size-medium wp-image-274" title="15" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/15-300x225.png?resize=300%2C225" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/15.png?resize=300%2C225 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/15.png?w=1024 1024w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][15]

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Click Install on the Summary Screen:</span>

[<img class="alignnone size-medium wp-image-275" title="16" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/16-300x181.png?resize=300%2C181" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/16.png?resize=300%2C181 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/16.png?resize=1024%2C620 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/16.png?w=1280 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][16]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Look for successful installation. Do NOT start the Profile Management Tool. Click Finish:</span>

[<img class="alignnone  wp-image-276" title="17" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/17-300x180.png?resize=300%2C180" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/17.png?resize=300%2C180 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/17.png?resize=1024%2C617 1024w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/17.png?w=1284 1284w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][17]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Verify DB2 services are up and running:</span>

[<img class="alignnone size-medium wp-image-277" title="18" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/18-300x216.png?resize=300%2C216" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/18.png?resize=300%2C216 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/18.png?w=902 902w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][18]

<div class="blogger-post-footer">
</div>

 [1]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/1.png
 [2]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/2.png
 [3]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/3.png
 [4]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/4.png
 [5]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/5.png
 [6]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/6.png
 [7]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/71.png
 [8]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/81.png
 [9]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/91.png
 [10]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/101.png
 [11]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/112.png
 [12]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/121.png
 [13]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/13.png
 [14]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/14.png
 [15]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/15.png
 [16]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/16.png
 [17]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/17.png
 [18]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/18.png