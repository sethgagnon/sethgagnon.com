---
title: Moving my WordPress Site from Dreamhost to Amazon Web Services (AWS)
author: Seth
type: post
date: 2017-08-31T12:45:02+00:00
url: /moving-wordpress-site-dreamhost-amazon-web-services-aws/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - AWS
  - Cloud

---
<div class="clarify-article-content">
  <div class="clarify-article-description">
    <p>
      The article will review some of the high level steps I took to move my WordPress site from being hosted on Dreamhost over to AWS.
    </p>
  </div>
</div>

<!--more-->

<div class="clarify-article-content">
  <div class="clarify-steps-container">
    <div id="clarify-step-1" class="clarify-step-container">
      <h3 class="clarify-step-title">
        1. Create a Hosted Zone in AWS that matches your domain name
      </h3>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-6" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.1 In the AWS console, navigate to Services > Route53 > Hosted Zones
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              Here you can see I have a few hosted zones, but for this article, we will be focusing on sethgagnon.com
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
		  <div class="clarify-step-image-container">![](/wp-content/uploads/2017/08/in-the-aws-console-navigate-to-services-gt-route53-gt-hosted-zones.png)</div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-7" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.2 Click Create Hosted Zone to create the new zone in AWS.
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              You will want to enter in the exact domain name that you are using today. Keep the defaults for the rest and click Create.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/click-create-hosted-zone-to-create-the-new-zone-in-aws-.png?resize=481%2C657" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-8" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.3 Confirm you now see your hosted zone in the list.
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              At this point, you are now ready to move on to updating your DNS records on your existing domain provider.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/confirm-you-now-see-your-hosted-zone-in-the-list.png?resize=814%2C262" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-9" class="clarify-step-container">
      <h3 class="clarify-step-title">
        2. Create record sets in AWS on newly created Hosted Zone to match your existing DNS records.
      </h3>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-10" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            2.1 Obtain your current DNS settings
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              You will need to login to your existing domain provider and review the DNS settings that are currently in place for your name. Here is a copy of what I observed in Dreamhost.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/obtain-youe-current-dns-settings.png?resize=814%2C868" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-11" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            2.2 Select your Hosted Zone
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              You will now need to create these in AWS for the Hosted Zone you previously created. Click on the domain you created in the Hosted Zone list.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/select-your-hosted-zone.png?resize=645%2C273" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-12" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            2.3 Then click on Create Record Set
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/then-click-on-create-record-set.png?resize=813%2C141" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-13" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            2.4 Create Records Sets
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              Carefully go through the list you obtained from step 2.1 and ensure you create the EXACT same records in AWS. The only records you should omit for now are the Name Server (NS) records. Just leave those as is for now in AWS. You should have a list similar to the following (picture doesnt show all the records):
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/create-records-sets.png?resize=779%2C527" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-2" class="clarify-step-container">
      <h3 class="clarify-step-title">
        3. Update your DNS records on your existing domain vendor (Dreamhost in my case)
      </h3>
      
      <div class="clarify-step-instructions">
        <p style="padding-left: 30px;">
          You may now update your domain registration with your existing provider to point to AWS Name Servers.
        </p>
      </div>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-14" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            3.1 Obtain the AWS name servers from your hosted zone you previously created.
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              Search for the NS record type and obtain those values
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/obtain-the-aws-name-servers-from-your-hosted-zone-you-previously-created.png?resize=547%2C113" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-15" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            3.2 Update your existing DNS settings
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              Login to your existing domain registration (Dreamhost for me) and point your name servers to the ones you obtained in step 3.1. Please note this could take up to 48 hours before your DNS settings are propagated. This all depends on your vendor. Please do not proceed to step 4 until you are sure that your DNS settings are using the AWS name servers.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/update-your-existing-dns-settings.png?resize=687%2C255" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-3" class="clarify-step-container">
      <h3 class="clarify-step-title">
        4. Transfer your domain so that AWS has the registration
      </h3>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-16" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            4.1 Obtain the Authorization code from your existing domain provider
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              You will need to enter an Authorization Code in AWS to initiate the domain transfer. I have masked some of this code out here.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/obtain-the-authorization-code-from-your-existing-domain-provider.png?resize=583%2C377" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-17" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            4.2 Initiate Transfer to AWS
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              Go to Route53 in AWS console and click on Registered domains in the left menu. Then click on Transfer Domain.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/initiate-transfer-to-aws.png?resize=813%2C327" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-18" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            4.3 Enter in the domain name you wish to transfer and click Check.
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/enter-in-the-domain-name-you-wish-to-transfer-and-click-check.png?resize=813%2C467" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-19" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            4.4 Click Add to Cart and then click Continue
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/click-add-to-cart-and-then-click-continue.png?resize=813%2C365" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-20" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            4.5 Auth Code and name servers
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              Enter in your Auth code you obtained from step 4.1 and then select Import name servers from a Route53 hosted zone that has the same name as the domain. Ensure the hosted zone populates and it is correct. Then click Continue.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/auth-code-and-name-servers.png?resize=813%2C405" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-21" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            4.6 Contact Details for 1 Domain
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              Enter in your contact details as the domain owner.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/contact-details-for-1-domain.png?resize=813%2C457" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-22" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            4.7 Agree to terms and conditions and purchase
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/agree-to-terms-and-conditions-and-purchase.png?resize=813%2C265" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-23" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            4.8 Validatation email
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              You will receive an email asking you to approve the transfer and validate your email address. After you have done so, the transfer process will begin.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/validatation-email.png?resize=813%2C305" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-4" class="clarify-step-container">
      <h3 class="clarify-step-title">
        5. Export existing WordPress site so it can be moved over
      </h3>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-24" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            5.1 Select your plugin to use for migration
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              There are several good WordPress plugins available for migration of a site. I choose to use All-in-One WP Migration. If you don&#8217;t have it, install the plugin and then do an Export site. You can select where you would like to export the site to. I choose a file for now. Save the file somewhere safe, as we will need to use it for import later.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/select-your-plugin-to-use-for-migration.png?resize=813%2C525" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-5" class="clarify-step-container">
      <h3 class="clarify-step-title">
        6. Create an EC2 instance that is running WordPress
      </h3>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-25" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.1 Go back into the AWS console and navigate to EC2. Then click on Launch Instance
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/go-back-into-the-aws-console-and-navigate-to-ec2-then-click-on-launch-instance.png?resize=813%2C273" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-26" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.2 Choose your Amazon Machine Image (AMI)
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              In the left menu, select AWS Marketplace and then search for WordPress. Select the first option in the list and click Select
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/choose-your-amazon-machine-image-ami-.png?resize=813%2C387" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-27" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.3 Click Continue after your review the pricing options (we will be using the AWS Free Tier option)
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/click-continue-after-your-review-the-pricing-options-we-will-be-using-the-aws-free-tier-option-.png?resize=813%2C385" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-28" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.4 Choose Instance Type
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              Select the free tier eligible option here, unless you need to choose a different type for your needs. Click Next Configure Instance Details.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/choose-instance-type.png?resize=813%2C379" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-29" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.5 Configure Instance Details
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              You can keep the defaults here. I also enabled Cloudwatch for monitoring purposes, but you can always do that later if you so choose. Click Next: Add Storage
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/configure-instance-details.png?resize=813%2C389" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-30" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.6 Add Storage
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              Enter the storage requirements you have. Pay attention to the free tier requirements. Click Next: Add Tags
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/add-storage.png?resize=813%2C375" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-31" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.7 Enter Tag (optional)
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              I like to use tags so that I can groups resources and easily find usage patterns. Then click on Next: Configure Security Group
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/enter-tag-optional-.png?resize=813%2C385" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-32" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.8 Configure Security Group
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              This is an important step. This tells AWS how you want to communicate and open up your new server instance. Here, I am creating a new security group and I entered in a meaningful name and then I changed the SSH type to only allow my IP address (masked out) to SSH into this server. This is recommended. I will want to keep HTTP and HTTPS open as this will be how users access my WordPress blog. Click Review and Launch.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/configure-security-group.png?resize=813%2C387" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-33" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.9 Review final details and Launch instance.
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              Click on Launch
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/review-final-details-and-launch-instance.png?resize=813%2C383" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-34" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.10 Select Key Pairs
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              This is the security key that will be used to access this server instance you are creating. You can either create a new key pair, or use an existing one. Select Launch Instances
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/select-key-pairs.png?resize=713%2C445" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-35" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.11 Launch Status
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              The instances are launching. Select View Instances at the bottom of the screen.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/launch-status.png?resize=813%2C169" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-36" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.12 Confirmation
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              Ensure that your instance is launching and in running state.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/confirmation.png?resize=813%2C187" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-37" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            6.13 Get the username and password to be able to login to your newly WordPress site.
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              The usage instructions tab outlines what you need to do to find the password for the user account to login to the site and manage WordPress.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/get-the-username-and-password-to-be-able-to-login-to-your-newly-wordpress-site.png?resize=813%2C423" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-38" class="clarify-step-container">
      <h3 class="clarify-step-title">
        7. Import your WordPress site
      </h3>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-39" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            7.1 Login to your newly created WordPress site.
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              Look for the public DNS to use to access your WordPress instance. Use that in a browser and add /wp-admin to the end of the DNS. (Refer to those usage instructions from above on how to obtain the password for the default user account.)
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/login-to-your-newly-created-wordpress-site.png?resize=813%2C937" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-40" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            7.2 Install the All-in-One WP Migration plugin and activate it.
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/install-the-all-in-one-wp-migration-plugin-and-activate-it.png?resize=813%2C335" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-41" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            7.3 Go to All-in-One WP Migration > Import
          </h4>
          
          <div class="clarify-step-instructions">
            <p style="padding-left: 30px;">
              I am importing from a file. I selected the file and then waited for the upload to complete.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/go-to-all-in-one-wp-migration-gt-import.png?resize=813%2C425" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-42" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            7.4 Look for successful import and follow any instructions.
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/look-for-successful-import-and-follow-any-instructions.png?resize=813%2C461" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-43" class="clarify-step-container">
      <h3 class="clarify-step-title">
        8. Create an Elastic IP for your new EC2 instance
      </h3>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-44" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            8.1 Navigate to AWS console EC2 > Elastic IPs and click on Allocate new address
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/navigate-to-aws-console-ec2-gt-elastic-ips-and-click-on-allocate-new-address.png?resize=813%2C353" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-45" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            8.2 Select allocate and then look for the new IP address
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/select-allocate-and-then-look-for-the-new-ip-address.png?resize=813%2C233" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-46" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            8.3 Select the Elastic IP address you just created
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/select-the-elastic-ip-address-you-just-created.png?resize=813%2C199" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-47" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            8.4 Then go to Actions > Associate address
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/then-go-to-actions-gt-associate-address.png?resize=813%2C339" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-48" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            8.5 Enter in the appropriate info from the drop down menus then click Associate
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/enter-in-the-appropriate-info-from-the-drop-down-menus-then-click-associate.png?resize=813%2C335" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-49" class="clarify-step-container">
      <h3 class="clarify-step-title">
        9. Update your hosted zone to point to the new Elastic IP address
      </h3>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-50" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            9.1 In AWS console, navigate to Services > Route53 > Hosted Zone
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/in-aws-console-navigate-to-services-gt-route53-gt-hosted-zone.png?resize=813%2C209" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-51" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            9.2 Select the domain you wish to use to point to your newly created WordPress site and click on that domain name.
          </h4>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/select-the-domain-you-wish-to-use-to-point-to-your-newly-created-wordpress-site-and-click-on-that-do.png?resize=813%2C541" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-52" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            9.3 Click on Create Record Set and enter in the new Elastic IP Address as an A type record. Then click Create
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              If you already have an existing A record pointing to your older IP address from when it was with your previous domain, just edit existing record so that it now contains this new elastic IP address.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2017/08/click-on-create-record-set-and-enter-in-the-new-elastic-ip-address-as-an-a-type-record-then-click-cr.png?resize=415%2C653" alt="" data-recalc-dims="1" />
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