---
title: Part 1 – Install Ansible on Linux
author: Seth
type: post
date: 2016-09-08T16:37:00+00:00
url: /part-1-installing-configuring-ansible/
categories:
  - DevOps
tags:
  - Ansible
  - ansible installation

---
<div class="clarify-article-content">
  <div class="clarify-article-description">
    <p>
      This article outlines how to install Ansible on Linux. This assumes that you already have a Linux machine ready to install Ansible on and some additional Linux VMs for Ansible to manage.
    </p>
  </div>
</div>

<!--more-->

<div class="clarify-article-content">
  <div class="clarify-steps-container">
    <div id="clarify-step-5" class="clarify-step-container">
      <h3 class="clarify-step-title">
        1. Ansible Installation
      </h3>
      
      <div class="clarify-step-instructions">
        <p>
          These are the steps to get Ansible installed on an Linux system.
        </p>
      </div>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-1" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.1 Install Ansible through Package Manager
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              Since we are using Ubuntu, we will be installing Ansible through the Apt package manager. First, we need to configure PPA on the Ubuntu machine:
            </p>
            
            <p>
              sudo apt-get install software-properties-common
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2016/09/install-ansible-through-package-manager.png?resize=813%2C131" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-2" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.2 Add Ansible PPA Repository
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              sudo apt-add-repository ppa:ansible/ansible
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2016/09/add-ansible-ppa-repository.png?resize=813%2C279" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-3" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.3 Get Updates
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              sudo apt-get update
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2016/09/get-updates.png?resize=813%2C935" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-4" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.4 Install Ansible
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              sudo apt-get install ansible
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2016/09/install-ansible.png?resize=813%2C631" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-6" class="clarify-step-container">
      <h3 class="clarify-step-title">
        2. Configure Ansible
      </h3>
      
      <div class="clarify-step-instructions">
        <p>
          These steps outline some basic configuration that needs to occur before you really begin using Ansible.
        </p>
      </div>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-8" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            2.1 Configure Ansible Inventory
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              Ansible needs you to list out the servers that it will manage in its inventory file. The default inventory file is located at /etc/ansible/hosts.
            </p>
            
            <p>
              In my scenario here, I have two webservers that I would like Ansible to manage. I have listed them under the webservers group and have provided them with aliases mapped to their respective IP addresses.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2016/09/configure-ansible-inventory.png?resize=814%2C542" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-9" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            2.2 Try a command
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              Now that we have some servers set up in our inventory file, we can try to ping those servers using the following ansible ad-hoc command:
            </p>
            
            <p>
              ansible all -m ping
            </p>
            
            <p>
              You could also try the following to ping only the servers listed in the webservers group:
            </p>
            
            <p>
              ansible webservers -m ping
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2016/09/try-a-command.png?resize=599%2C237" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
  </div>
</div>