---
title: Deploying to Prod (Through Automation), or Not to Prod? That is the Question!
author: Seth
type: post
date: 2016-10-14T14:43:23+00:00
url: /deploying-to-prod-through-automation-or-not-to-prod-that-is-the-question/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - DevOps
tags:
  - automation
  - continuous delivery
  - continuous deployment
  - continuous integration
  - deployment
  - IBM UrbanCode

---
_<span style="font-family: Arial; font-size: small;">This article focuses on code deployment practices and how you deploy your code to production. Many are believers that automation is the key all the way, while others want to control their production deployments through manual intervention. Which method do you follow?</span>_

## Background

<span style="font-family: Arial; font-size: medium;">I often hear that an application practicing continuous delivery is not truly embracing the practice if the team is still delivering their code to production manually. This got me thinking, as it is an interesting question. Am I still following a continuous delivery methodology, if I deploy my application to production in a manual or semi-manual fashion? Let me first clarify what Continuous Delivery really is. I believe Martin Fowler’s <a href="http://martinfowler.com/bliki/ContinuousDelivery.html" target="_blank">definition</a></span> <span style="font-family: Arial; font-size: medium;">does a great job outlining the key components:</span>

> <span style="font-family: Arial; font-size: medium;">You’re doing continuous delivery when: </span>[<span style="font-family: Arial; font-size: medium;">[1]</span>][1]
> 
>   * <span style="font-family: Arial; font-size: medium;">Your software is deployable throughout its life cycle </span>
>   * <span style="font-family: Arial; font-size: medium;">Your team prioritizes keeping the software deployable over working on new features </span>
>   * <span style="font-family: Arial; font-size: medium;">Anybody can get fast, automated feedback on the production readiness of their systems any time somebody makes a change to them </span>
>   * <span style="font-family: Arial; font-size: medium;">You can perform push-button deployments of any version of the software to any environment on demand</span>
> 
> <span style="font-family: Arial; font-size: medium;">You achieve continuous delivery by continuously integrating the software done by the development team, building executables, and running automated tests on those executables to detect problems. Furthermore you push the executables into increasingly production-like environments to ensure the software will work in production. To do this you use a <a href="http://martinfowler.com/bliki/DeploymentPipeline.html" target="_blank">DeploymentPipeline</a></span><span style="font-family: Arial; font-size: medium;">.</span>

<span style="font-family: Arial; font-size: medium;">So, you need to be using a deployment pipeline (check out my previous post <a href="http://www.sethgagnon.com/an-example-of-a-continuous-integration-delivery-pipeline/" target="_blank">here</a></span><span style="font-family: Arial; font-size: medium;">) and practicing the bullets outlined above. We should note that we are talking about Continuous Delivery here, not Continuous Deployment. Here’s my two cents on what each of these items mean.</span>

## Software is Deployable Throughout its Life Cycle

<span style="font-family: Arial; font-size: medium;">I believe the key takeaway here is that you have your master branch or trunk (depending on your SCM tool of choice) always in a state that has stable code and it can be deployed at any point in time. Obviously, as your team evolves and you take on additional work, the code will be evolving as well. You want to ensure that you have a strong versioning policy in place and a strong workflow in place so that the code is always in a stable state in the master branch or your trunk.</span>

## Team Prioritizes Keeping the Code Deployable Over Working New Features

<span style="font-family: Arial; font-size: medium;">Similar to the topic mentioned above, the idea here is that your delivery team always ensures that the focus is on keeping your master in a working state and ensuring it can be deployed. When issues arise and the master becomes unstable, getting it back into a stable state needs to be the top priority. Likewise, when you are working on new features and functionality and your code breaks a build, you also want to ensure that gets resolved first, before continuing work on new user stories and new features. The bottom line is that the master is always stable and your aren&#8217;t breaking the builds.</span>

## Anyone Can Get Fast, Automated Feedback on the Production Readiness

<span style="font-family: Arial; font-size: medium;">With the continuous integration tools available on the market today, it is very easy to know the state of your code and how &#8220;ready&#8221; it is to deploy to any of your environments. Developers need to know when they commit code that is breaking a build and they need to correct the issue sooner, rather than later. If you have a source code management system in place like <a href="https://git-scm.com/" target="_blank">Git</a></span><span style="font-family: Arial; font-size: medium;">, then it becomes fairly easy to track and audit the commits that have been made and who made them. This helps the team see their audit trail and learn how their code changed over time. When you add in a continuous integration engine like <a href="https://jenkins.io/" target="_blank">Jenkins</a></span> <span style="font-family: Arial; font-size: medium;">to the mix, developers can now see when builds are failing and why they are failing. They can refer back to their SCM (Git) and track down who made a change that broke the code and get it resolved fairly fast. Tools like Jenkins can send out automated emails to your team and inform them when the code is unstable, so they can jump right on it to get things resolved.</span>

## Push-Button Deployments of any Version of Software to any Environment on Demand

<span style="font-family: Arial; font-size: medium;">So, now that the above items have some definition to them, this is where the heart of discussion truly lies. There are many organizations out there that want to ride the automation train through all the environments, and you can’t blame them right? Automation certainly can reduce errors, improve productivity, and increase speed to market. Of course, this is when the automation works properly. The automation will only work to the best of its ability based upon how you design it, and this all depends on the prep work that went into the automation. Think of when you are painting a room and the amount of prep work that is needed before you even start putting paint on the wall. I would say that from beginning to end, about 70% of the project work is all prep work. This same concept holds true with your automation for deploying code. You will need the following, at least, to get things started:</span>

  * <span style="font-family: Arial; font-size: medium;">Established SCM system and versioning policies</span>
  * <span style="font-family: Arial; font-size: medium;">Workflow for the team for interacting with the SCM (branching, etc)</span>
  * <span style="font-family: Arial; font-size: medium;">Continuous integration configured</span>
  * <span style="font-family: Arial; font-size: medium;">Automated unit testing established</span>
  * <span style="font-family: Arial; font-size: medium;">Automated deployments to your testing environments</span>
  * <span style="font-family: Arial; font-size: medium;">Automated smoke testing in your environments (to ensure successful deployment)</span>
  * <span style="font-family: Arial; font-size: medium;">And the list goes on…….</span>

<span style="font-family: Arial; font-size: medium;">If you are confident that all the items above have been addressed and your pipeline is pretty mature, then I believe you can have the discussion around automating your deployments to production and possibly increases the frequency of your releases to the production environment. However, this can take a fairly long time to get to a mature state and some organizations may not ever get to a mature state. With that said, it is understandable why plenty of organizations out there have no issue with automation through their lower testing environments, but when it comes to deploying to production, they still want a person involved managing that deployment.</span>

<span style="font-family: Arial; font-size: medium;">Now there are some tools out there that can help with this type of automation for deploying your code. <a href="http://www-03.ibm.com/software/products/en/ucdep" target="_blank">IBM Urbancode</a> is a product designed for this very purpose. It allows you to orchestrate your deployment process through a series of steps and it can handle virtually all types of deployments. There are some additional features like approvals in the flow that will require a person or group of people to approve the request before the code can be deployed, or a scheduling feature that will allow a requester to kick off a process for deployment but not have the code get deployed until a specified date and time (as seen below).</span>

&nbsp;

<div style="width: 609px" class="wp-caption alignnone">
  <a href="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2016/10/image.png"><img title="Figure 1 – IBM UrbanCode Scheduling Feature" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2016/10/image_thumb.png?resize=599%2C388" alt="Figure 1 – IBM UrbanCode Scheduling Feature" border="0" data-recalc-dims="1" /></a>
  
  <p class="wp-caption-text">
    Figure 1 – IBM UrbanCode Scheduling Feature
  </p>
</div>

## Conclusion

<span style="font-family: Arial; font-size: medium;">In summary, there are many options for deploying your code to your environments and there are always many reasons why the code is deployed the way it is being deployed. Some of those reasons can include organizational culture & politics, technology at play, lack of knowledge around deployment automation, etc. So, before you are quick to ask your colleagues <em>“Why aren’t we just deploying everything automatically, it would make our lives so much easier?”, </em>please remember these reasons and understand the state of the pipeline maturity for your organization.</span>

&nbsp;

### References:

<span style="font-family: Arial; font-size: xx-small;">1. Continuous Delivery. Martin Fowler. </span>[<span style="font-family: Arial; font-size: xx-small;">http://martinfowler.com/bliki/ContinuousDelivery.html</span>][2]

 [1]: http://martinfowler.com/bliki/ContinuousDelivery.html#footnote-when
 [2]: http://martinfowler.com/bliki/ContinuousDelivery.html