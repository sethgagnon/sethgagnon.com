---
title: IBM Integration Designer Installation with Test Environment Part 2
author: Seth
type: post
date: 2012-04-10T17:31:00+00:00
url: /ibm-integration-designer-installation-with-test-environment-part-2/
blogger_blog:
  - www.sethgagnon.com
blogger_author:
  - Seth Gagnon
blogger_3e80d94236879be645dcffcd98a21f45_permalink:
  - 1772817176483153156
publicize_results:
  - 'a:2:{s:7:"twitter";a:1:{i:223852360;a:2:{s:7:"user_id";s:10:"sethgagnon";s:7:"post_id";s:18:"190155942959120384";}}s:2:"fb";a:1:{i:585439918;a:2:{s:7:"user_id";s:9:"585439918";s:7:"post_id";s:17:"10150782157449919";}}}'
categories:
  - Integration Designer
tags:
  - IBM IID
  - Integration Designer
  - websphere

---
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 19px; font-style: normal; font-variant: normal; font-weight: bold; text-decoration: none; vertical-align: baseline;">Creating Profiles</span>
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Launch PMT tool as the user you created in the previous steps. Open a command prompt and change directory to C:/IBM/WebSphere/AppServer/bin/ProfileManagement. Enter runas /user:bpmadmin /env pmt.bat. Enter password when prompted.</span>

[<img class="alignnone size-medium wp-image-280" title="image00" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image00-300x186.png?resize=300%2C186" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image00.png?resize=300%2C186 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image00.png?w=668 668w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][1]

&nbsp;

<!--more-->

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Click on launch Profile Management Tool:</span>

[<img class="alignnone size-medium wp-image-281" title="image01" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image01-300x300.png?resize=300%2C300" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image01.png?resize=300%2C300 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image01.png?resize=150%2C150 150w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image01.png?w=700 700w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][2]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Click on Create:</span>

[<img class="alignnone size-medium wp-image-282" title="image02" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image02-300x300.png?resize=300%2C300" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image02.png?resize=300%2C300 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image02.png?resize=150%2C150 150w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image02.png?w=700 700w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][3]

&nbsp;

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Select the IBM BPM Advanced, Process Server stand-alone profile option and click Next:</span>

[<img class="alignnone size-medium wp-image-283" title="image03" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image03-300x250.png?resize=300%2C250" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image03.png?resize=300%2C250 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image03.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][4]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Select Advanced Profile Creation and click Next:</span>

[<img class="alignnone size-medium wp-image-284" title="image04" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image04-300x250.png?resize=300%2C250" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image04.png?resize=300%2C250 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image04.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][5]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Select both checkboxes and click Next:</span>

[<img class="alignnone size-medium wp-image-285" title="image05" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image05-300x250.png?resize=300%2C250" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image05.png?resize=300%2C250 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image05.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][6]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Name your profile and click Next:</span>

[<img class="alignnone size-medium wp-image-286" title="image06" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image06-300x250.png?resize=300%2C250" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image06.png?resize=300%2C250 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image06.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][7]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Click Next:</span>

[<img class="alignnone size-medium wp-image-287" title="image07" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image07-300x250.png?resize=300%2C250" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image07.png?resize=300%2C250 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image07.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][8]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Provide user name and password for administrative security, default is bpmadmin/bpmadmin1. Click Next:</span>

[<img class="alignnone size-medium wp-image-288" title="image08" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image08-300x250.png?resize=300%2C250" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image08.png?resize=300%2C250 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image08.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][9]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Click Next:</span>

[<img class="alignnone size-medium wp-image-289" title="image09" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image09-300x250.png?resize=300%2C250" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image09.png?resize=300%2C250 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image09.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][10]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Click Next:</span>

[<img class="alignnone size-medium wp-image-290" title="image10" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image10-300x250.png?resize=300%2C250" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image10.png?resize=300%2C250 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image10.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][11]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Verify ports and click Next:</span>

[<img class="alignnone size-medium wp-image-291" title="image11" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image11-300x250.png?resize=300%2C250" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image11.png?resize=300%2C250 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image11.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][12]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Click Next:</span>

[<img class="alignnone size-medium wp-image-292" title="image12" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image12-300x250.png?resize=300%2C250" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image12.png?resize=300%2C250 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image12.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][13]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Select the Web Server definition if needed and click Next:</span>

[<img class="alignnone size-medium wp-image-293" title="image13" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image13-300x250.png?resize=300%2C250" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image13.png?resize=300%2C250 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image13.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][14]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Name your environment with a meaningful name and select the appropriate environment type. Also, provide your Process Center url or decide if you want your local server to work offline. Click Next:</span>

[<img class="alignnone size-medium wp-image-294" title="image14" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image14-300x250.png?resize=300%2C250" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image14.png?resize=300%2C250 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image14.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][15]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Click Next:</span>

[<img class="alignnone size-medium wp-image-295" title="image15" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image15-300x250.png?resize=300%2C250" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image15.png?resize=300%2C250 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image15.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][16]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Verify you have the same names as below and also select the Run database scripts to initialize databases. Click Next:</span>

[<img class="alignnone size-medium wp-image-296" title="image16" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image16-300x250.png?resize=300%2C250" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image16.png?resize=300%2C250 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image16.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][17]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Provide the same local user that you created earlier in the instructions for the database user name. Click Next:</span>

[<img class="alignnone size-medium wp-image-298" title="image17" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image171-300x250.png?resize=300%2C250" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image171.png?resize=300%2C250 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image171.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][18]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Select Business Space if needed and Forms Server if needed, and click Next:</span>

[<img class="alignnone size-medium wp-image-299" title="image18" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image18-300x250.png?resize=300%2C250" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image18.png?resize=300%2C250 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image18.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][19]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Select Configure Business Rules Manager, if needed. Click Next:</span>

[<img class="alignnone size-medium wp-image-300" title="image19" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image19-300x250.png?resize=300%2C250" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image19.png?resize=300%2C250 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image19.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][20]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Select Create a sample Business process Choreographer configuration and click Next:</span>

[<img class="alignnone size-medium wp-image-301" title="image20" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image20-300x250.png?resize=300%2C250" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image20.png?resize=300%2C250 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image20.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][21]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Verify the profile creation summary and click Create:</span>

[<img class="alignnone size-medium wp-image-302" title="image21" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image21-300x250.png?resize=300%2C250" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image21.png?resize=300%2C250 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image21.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][22]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Look for a successful creation and click Finish:</span>

[<img class="alignnone size-medium wp-image-303" title="image22" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image22-300x250.png?resize=300%2C250" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image22.png?resize=300%2C250 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image22.png?w=840 840w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][23]

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: bold; text-decoration: none; vertical-align: baseline;">SEE APPENDIX IF CONNECTING TO A SECURE PROCESS CENTER AND FOLLOW THOSE STEPS BEFORE PROCEEDING! </span><span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Open Integration Designer 7.5, Start>Programs>IBM>Integrations Designer. Enter a path to save your workspace and click OK:</span>

[<img class="alignnone size-medium wp-image-304" title="image23" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image23-300x123.png?resize=300%2C123" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image23.png?resize=300%2C123 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image23.png?w=595 595w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][24]

&nbsp;

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Provide your Process Center connection information. If connecting to a secure Process Center, then click Cancel for now and follow instructions in Appendix:</span>

[<img class="alignnone size-medium wp-image-305" title="image24" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image24-300x181.png?resize=300%2C181" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image24.png?resize=300%2C181 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image24.png?resize=1024%2C620 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image24.png?w=1280 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][25]

&nbsp;

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Click on the Servers tab on the bottom half of the screen and right-click in the white space and select New>Server:</span>

[<img class="alignnone size-medium wp-image-306" title="image25" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image25-300x181.png?resize=300%2C181" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image25.png?resize=300%2C181 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image25.png?resize=1024%2C620 1024w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image25.png?w=1280 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][26]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Select IBM Process Server 7.5 and click Next:</span>

[<img class="alignnone size-medium wp-image-307" title="image26" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image26-279x300.png?resize=279%2C300" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image26.png?resize=279%2C300 279w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image26.png?w=498 498w" sizes="(max-width: 279px) 100vw, 279px" data-recalc-dims="1" />][27]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Verify the Profile Name is the profile you created in the previous steps. Provide the credentials you provided during profile creation for administrative security.Click Next:</span>

[<img class="alignnone size-medium wp-image-308" title="image27" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image27-279x300.png?resize=279%2C300" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image27.png?resize=279%2C300 279w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image27.png?w=498 498w" sizes="(max-width: 279px) 100vw, 279px" data-recalc-dims="1" />][28]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Click Finish:</span>

[<img class="alignnone size-medium wp-image-309" title="image28" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image28-279x300.png?resize=279%2C300" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image28.png?resize=279%2C300 279w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image28.png?w=498 498w" sizes="(max-width: 279px) 100vw, 279px" data-recalc-dims="1" />][29]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Verify server is now listed in the Servers Tab:</span>

[<img class="alignnone size-medium wp-image-310" title="image29" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image29-300x181.png?resize=300%2C181" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image29.png?resize=300%2C181 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image29.png?resize=1024%2C620 1024w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image29.png?w=1280 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][30]

<span style="color: black; font-family: 'Times New Roman'; font-size: 19px; font-weight: bold;">Appendix</span>

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Please follow the following instructions for connecting your Integration Designer environment to your Process Center over a secure (https) URL.</span>
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: bold; text-decoration: underline; vertical-align: baseline;">To Connect to a Secure Process Center:</span>
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Make sure Integration Designer is not running. You will need to import the certificate from the secured process center to you Integration Designer cacerts file.</span>
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Open a command prompt and run the following command (make sure you edit the paths based on where you installed ID and WebSphere:</span>
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">C:IBMWebSphereAppServerjavabinkeytool.exe -import -file CERTNAME.cer -alias CERTALIAS -keystore C:IBMWebSphereAppServerjavajrelibsecuritycacerts</span>

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Start your Server from Integration Designer:</span>

[<img class="alignnone size-medium wp-image-311" title="image30" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image30-300x181.png?resize=300%2C181" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image30.png?resize=300%2C181 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image30.png?resize=1024%2C620 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image30.png?w=1280 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][31]

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Once the server is Started, login to the Admin Console:</span>

[<img class="alignnone size-medium wp-image-312" title="image31" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image31-300x181.png?resize=300%2C181" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image31.png?resize=300%2C181 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image31.png?resize=1024%2C620 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image31.png?w=1280 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][32]

<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Navigate to Security>SSL Certificate and Key Management>Key stores and certificates>NodeDefaultTrustStore>Signer certificates, click on Retrieve from port:</span>

[<img class="alignnone size-medium wp-image-313" title="image32" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image32-300x181.png?resize=300%2C181" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image32.png?resize=300%2C181 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image32.png?resize=1024%2C620 1024w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image32.png?w=1280 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][33]
  
<span style="background-color: transparent; color: black; font-family: Times New Roman; font-size: 16px; font-style: normal; font-variant: normal; font-weight: normal; text-decoration: none; vertical-align: baseline;">Type in the appropriate information to retrieve the certificate from the secured process server and click on OK and then Save. Restart your server.</span>

[<img class="alignnone size-medium wp-image-314" title="image33" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image33-300x181.png?resize=300%2C181" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image33.png?resize=300%2C181 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image33.png?resize=1024%2C620 1024w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/image33.png?w=1280 1280w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][34]

&nbsp;

<div class="blogger-post-footer">
</div>

 [1]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image00.png
 [2]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image01.png
 [3]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image02.png
 [4]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image03.png
 [5]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image04.png
 [6]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image05.png
 [7]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image06.png
 [8]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image07.png
 [9]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image08.png
 [10]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image09.png
 [11]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image10.png
 [12]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image11.png
 [13]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image12.png
 [14]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image13.png
 [15]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image14.png
 [16]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image15.png
 [17]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image16.png
 [18]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image171.png
 [19]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image18.png
 [20]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image19.png
 [21]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image20.png
 [22]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image21.png
 [23]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image22.png
 [24]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image23.png
 [25]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image24.png
 [26]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image25.png
 [27]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image26.png
 [28]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image27.png
 [29]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image28.png
 [30]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image29.png
 [31]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image30.png
 [32]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image31.png
 [33]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image32.png
 [34]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/image33.png