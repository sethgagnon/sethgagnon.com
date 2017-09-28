---
title: Adding A Remote Secure Process Center Server to Your Integration Designer
author: Seth
type: post
date: 2012-04-20T16:04:25+00:00
url: /adding-a-remote-secure-process-center-server-to-your-integration-designer/
jabber_published:
  - 1334937865
publicize_results:
  - 'a:2:{s:7:"twitter";a:1:{i:223852360;a:2:{s:7:"user_id";s:10:"sethgagnon";s:7:"post_id";s:18:"193369555752595458";}}s:2:"fb";a:1:{i:585439918;a:2:{s:7:"user_id";s:9:"585439918";s:7:"post_id";s:17:"10150811717049919";}}}'
categories:
  - Integration Designer
tags:
  - IBM IID
  - IID
  - Integration Designer
  - websphere

---
To add a remote secure Process Center to Integration Designer, start by having a clean workspace. Then provide your connection information to the remote Process Center. Click Login (Click Yes if prompted for certificates):

[<img class="alignnone size-full wp-image-117" title="securePC1" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc12.png?resize=600%2C375" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc12.png?w=1280 1280w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc12.png?resize=300%2C187 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc12.png?resize=1024%2C640 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc12.png?resize=480%2C300 480w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][1]

<!--more-->

Switch to Business Integration View by clicking here (top right icon next to the question mark)

Click on the Servers tab on the bottom:

 [<img class="alignnone size-full wp-image-118" title="securePC3" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc3.png?resize=600%2C375" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc3.png?w=1280 1280w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc3.png?resize=300%2C187 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc3.png?resize=1024%2C640 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc3.png?resize=480%2C300 480w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][2]

Right click on the white space on the bottom and go to New:

 [<img class="alignnone size-full wp-image-119" title="securePC4" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc4.png?resize=600%2C375" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc4.png?w=1280 1280w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc4.png?resize=300%2C187 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc4.png?resize=1024%2C640 1024w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc4.png?resize=480%2C300 480w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][3]

Select IBM Process Center V7.5 and specify the host and click on Next:

[<img class="alignnone size-full wp-image-120" title="securePC5" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc5.png?resize=600%2C375" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc5.png?w=1280 1280w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc5.png?resize=300%2C187 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc5.png?resize=1024%2C640 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc5.png?resize=480%2C300 480w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][4]

Name the Process Center and provide the path to the WAS\_INSTALL\_HOME directory for your local test environment, click Next:

 [<img class="alignnone size-full wp-image-121" title="securePC6" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc6.png?resize=600%2C375" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc6.png?w=1280 1280w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc6.png?resize=300%2C187 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc6.png?resize=1024%2C640 1024w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc6.png?resize=480%2C300 480w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][5]

Specify the hostname, HTTP port (nonsecure), and credentials for the Process Center server and click Test Connection. If successful connection, click OK and Next:

 [<img class="alignnone size-full wp-image-122" title="securePC7" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc7.png?resize=600%2C375" alt="" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc7.png?w=1280 1280w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc7.png?resize=300%2C187 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc7.png?resize=1024%2C640 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc7.png?resize=480%2C300 480w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][6]

Specify the Process Center host name and SOAP port (of DM if in clustered env) and your credentials and click Finish:

[<img class="alignnone size-full wp-image-123" title="securePC8" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc8.png?resize=600%2C375" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc8.png?w=1280 1280w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc8.png?resize=300%2C187 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc8.png?resize=1024%2C640 1024w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc8.png?resize=480%2C300 480w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][7]

Server is now saved in your configuration and synchronized:

 [<img class="alignnone size-full wp-image-124" title="securePC9" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc9.png?resize=600%2C375" alt="" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc9.png?w=1280 1280w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc9.png?resize=300%2C187 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc9.png?resize=1024%2C640 1024w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/04/securepc9.png?resize=480%2C300 480w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][8]

 [1]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc12.png
 [2]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc3.png
 [3]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc4.png
 [4]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc5.png
 [5]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc6.png
 [6]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc7.png
 [7]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc8.png
 [8]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/securepc9.png