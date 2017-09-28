---
title: An Example of a Continuous Integration Delivery Pipeline
author: Seth
type: post
date: 2016-09-26T05:43:47+00:00
url: /an-example-of-a-continuous-integration-delivery-pipeline/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - DevOps
tags:
  - Ansible
  - automation
  - CI
  - continuous delivery
  - continuous deployment
  - continuous integration
  - DevOps
  - pipeline
  - uDeploy
  - UrbanCode

---
This article will provide an example delivery pipeline used through continuous integration, as well as, the DevOps tools involved in the automation of building, testing, and deploying code through your SDLC.

### **Background **

In the IT world today, you can’t go to any organization, regardless of the industry, without hearing the term “DevOps.” In short, it originally stems from the effort to have better communication and synergies between your Development organization and your Operations organization, hence the term DevOps. The main focus was to improve the efficiency, quality, and speed to market within the software development world. Furthermore, you may hear and see a lot about continuous integration and continuous delivery/deployment. There are differences between the two for sure, but for the purposes of simplicity, I would like to really focus on breaking down the different stages of the process. This way you can get the basics and hit the ground running with a delivery pipeline in your organization. The delivery pipeline can be broken down into a few major buckets of work, or stages, as mentioned below.

In my opinion, and again trying to keep things simple for now, the stages can be broken down as follows:

1. Source Code Control (Management)
  
2. Build Automation
  
3. Unit Test Automation (could also include Integration Testing here as well)
  
4. Deployment Automation
  
5. Monitoring – not included in this discussion, and can be added at any time

I have outlined the progression of these stages in Figure 1 below. Let’s review each of the stages in a little more detail.

<a href="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2016/09/image.png" target="_blank"><img class="alignnone" style="display: block; margin-left: auto; margin-right: auto;" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2016/09/image.png?resize=600%2C335" border="0" data-recalc-dims="1" /></a>

<p style="text-align: center;">
  <em>Figure 1 &#8211; Continuous Integration Delivery Pipeline Sample</em>
</p>

<h3 style="text-align: left;">
  <strong>Source Code Control (Management) </strong>
</h3>

#### Background

Source code management, or source code control, is certainly not a new topic. This has been around for decades and has evolved over time. The basics here are that your organization stores its code in a source code control system or repository, so that it can be tracked, maintained, versioned, and audited. You do not want the developers storing the code on their laptops or virtual machines and trust that will suffice for managing the code.

#### Possible Tools

  1. <a href="https://git-scm.com/" target="_blank">Git</a><span style="line-height: 1.42857;"> is probably the most widely used SCM system out there. It is an open source system.</span>
  2. <a href="https://subversion.apache.org/" target="_blank">Subversion (SVN)</a> has been around for quite some time. It is also an open source system. It is still heavily used across many organizations out there, but there has been more of a push towards Git. If you are just starting out, I would highly recommend using Git.

Git and Subversion comparison can be found <a href="https://git.wiki.kernel.org/index.php/GitSvnComparison" target="_blank">here</a>.

### **Build Automation**

#### Background

Once a source code management system is in place and actively being used by your development team, the team will need to be able to compile and build their code. This is probably the first step in the whole chain of continuous integration events. This is what gets the ball rolling. The code needs to build cleanly before you can even think about deploying out to your environments for testing and production.

#### Possible Tools

  1. <span style="line-height: 1.42857;"><a href="https://gradle.org/" target="_blank">Gradle</a> is an open source build automation system. Pretty widely used </span>by top <span style="line-height: 1.42857;">companies like Netflix, Google, and LinkedIn.</span>
  2. <a href="https://maven.apache.org/" target="_blank">Maven</a> is another open source build automation system.

Gradle and Maven comparison can be found <a href="https://gradle.org/maven_vs_gradle/" target="_blank">here</a> and <a href="http://devops.com/2015/03/27/puzzle-gradle-maven/" target="_blank">here</a>.

### **Unit Test Automation**

#### Background

Developers unit test their code to ensure that the functionality they are building works as expected. In an ideal world, the development team should be saving these unit tests, so that they can be reused and also put into a regression test bed.

#### Possible Tools

There are multiple tools out there for helping developers unit test their code. Many of these tools are open source and can be used freely.

  1. <span style="line-height: 1.42857;"><a href="http://junit.org/junit4/" target="_blank">JUnit </a>is an open source unit test framework. This is pretty widely used in </span>the industry<span style="line-height: 1.42857;">.</span>
  2. <a href="https://docops.ca.com/devtest-solutions/8-0/en/" target="_blank">CA DevTest</a> allows for the automation of unit testing, as well as a few other bells and whistles, like service virtualization.

### **Deployment Automation**

#### Background

For the last stage in the process, delivery teams need to deploy their code/applications out to various test environments and, of course, production. To reduce errors and overhead in the deployment process, while increasing speed to market, this step can be automated through a variety of tools and methods.

#### Possible Tools

  1. <span style="line-height: 1.42857;"><a href="http://www-03.ibm.com/software/products/en/ucdep" target="_blank">IBM Urbancode uDeploy</a> allows you to model a process and orchestrate </span>your deployment<span style="line-height: 1.42857;">. This process can then be repeated across all your environments, </span>and of <span style="line-height: 1.42857;">course tweaked for each environment as needed.</span>
  2. <a href="http://www.ansible.com/" target="_blank">Ansible</a> is an open source IT automation tool. It can be used for everything from configuration management to product installation to application deployments.This tool is rapidly gaining acceptance and momentum in the DevOps community.

### **Conclusion**

In conclusion, this is a quick overview to be able to get you started down the path of continuous integration and the DevOps world. Below in Figure 2 is a sample of what the whole flow looks like from committing your code to your repo to deploying the code to an environment. I thought this would help put all the stages mentioned into perspective. You can see how the tools interact with each other (some of these tools were not mentioned in this article), as you move on your journey to production.

<a href="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2016/09/CI_Process_Overview.png" target="_blank"><img class="alignnone" style="display: block; margin-left: auto; margin-right: auto;" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2016/09/CI_Process_Overview.png?resize=600%2C768" border="0" data-recalc-dims="1" /></a>

<p style="text-align: center;">
  <em>Figure 2 &#8211; Continuous Integration Process Flow</em>
</p>

###