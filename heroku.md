# Heroku Setup
For More info: [Getting Start on Heroku](https://devcenter.heroku.com/articles/getting-started-with-php)

## Login/signup Heroku
1. Navigate to [Heroku](https://www.heroku.com/)
2. Login to Heroku (Create account if you haven't already: [Free Signup](https://signup.heroku.com/))

## Connect credit/debit card (Optional)
 Attaching credit/debit card is optional, you can also use free features. But to use Paid Dynos, Configure SSL, extra feature or more usage(than free limit) You must add credit/debit card.

* Goto Profile icon on Top-right corner.
* Click on `Account Settings`.
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-settings.png "Account Settings")
* Click on `Billing` Tab.
* Add Credit/Debit Card.
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-billing.png "Billing - Add card")
* Fill all the required information in form and save.

## Create 2 apps (UAT/Prod)
1. Go to Heroku app by clicking heroku logo from anywhere.
2. Click on button `New` on right side(lower-top) and select `create new app`.
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-new-app.png "Create new app")

3. Fill your app name (as per availability). You can add environment prefix to app name i.e. uat-app-name.
You can also choose region as per project region. For ucreate we choose Europe.
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-new-app-create.png "Create new app")
4. After click on `create app` button, your app will be created and show in app list.
5. Similarly create another app for Production environment i.e. prod-app-name.

## Add/Attach apps to pipeline
A pipeline is created to deploy changes to production manually at specific time after validating all changes on uat/staging environment.
To create pipeline and attaching apps to it follow the below steps.

1. Click on `New` button as we have done while creating new app.
2. This time choose `Create new pipeline`.
3. Name the pipeline.
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/create-pipeline.png "Create new pipeline")
4. Search GitHub repo for your app and connect it to pipeline. Click on `create pipeline`.
5. Now it will show you pipeline details page. Here you can add Staging app and production app which you have created in earlier.
    * Click on `Add app` button.
    * Search name of your app for staging and select from list. It will be attached to pipeline on select.
    * Similarly, search app name for production and attach it to project section of pipeline.
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-pipeline-detail.png "Create new pipeline")
6. After attaching both apps to pipeline click on `create new pipeline`.
Now your pipeline will show on dashboard in apps list.

**Note**: your apps will show no more in list. instead you can access apps from pipeline details page. But still you can directly search you app from search on dashboard/app list page.

## Add buildpack
* Add nodejs buildpack
  Go to settings > Buildpacks, click on add buildpacks , it will open popup, select nodejs & click on add buildpack.
![picture alt](https://github.com/pro-pooja/chaos-monkey-dox/blob/d0836d1186ea77610ea0bb03d9a28eac1966b9dc/img/heroku-add-buildpack.png "Add buildpack")

## Configure addons (explain)
Heroku offers some addons(development tools) easy to integrate with few clicks.
Few common and necessary addons used at ucreate are:

* Heroku Postgres
* Rollbar
* Papertrail
* New Relic APM
* Heroku Scheduler
* Heroku Redis
* PointDNS (for configuring domain name/SSL)

Some common steps to configure addons are below:
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-resources.png "Heroku resources")
1. Goto your app details for which you want to configure addon.
2. Click on `Resources` tab.
3. It will show you list of already configured Addons (empty if no addon configured yet).
4. Type/Search the name of Addon your want to configure and select the exact addon from result list.
5. On click of addon it will show a popup, where you can select addon plan i.e. free, paid depends upon usage and features required.
6. Click on `Provision` button and your addon will show in list of resources.
7. For further configuration or settings click on particular addon in the list. It will take you to dashboard of that particular addon platform.

## Add ENV variables
You can App specific ENV variables on Heroku by visiting app detail page.

* Goto `settings` tab
* Click on `Reveal Config Vars`. It will show you already added ENV variables, some variables(addon related) automatically added when you configure Addons.
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/env-variables.png "Add ENV Variables")
* To add new ENV variable scroll to end of the list and add ENV variable Key and Value in given inputs then click `Add` button.
* You can edit ENV variable value any time.
* To delete any ENV variable click on cross(X) icon ahead of variable.

## Register/Add domain name
You can register any available domain name for any of domain register service provider like [Godaddy](https://in.godaddy.com/), [Bigrock](https://www.bigrock.in/dod#/netcom-domain-deals), [Hostgator](https://www.hostgator.in/domain-registration) etc.
If you wish to register a free domain name(with limit choices) you can register your domain on [freenom.com](https://www.freenom.com/en/index.html), [dot.tk](www.dot.tk)

In below pic there is button `Configure SSL` that will be visible only if you have paid dynos.

After registering/purchasing domain-name follow below steps:
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/add-domain.png "Add Domain")

1. Goto App details page and click on settings tab.
2. Scroll down to `Domains and certificates` section and Click on `Add domain` button on right side.
3. In popup write your domain name in given field and `Save changes`.
Now you domain name will show in Table below `Add domain` button.

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/add-domain-name.png "Add domain name popup")

You can add more than 1 domain names (upto 10,000) to single app.
For more details refer to: [Rules on adding domains](https://devcenter.heroku.com/articles/custom-domains#rules-on-adding-domains)

### Add PointDNS
PointDNS is addon offered by Heroku to manage DNS records for your app/domain.

PointDNS addon can be added to Heroku by following steps given in [Configure addons](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/heroku.md#configure-addons-explain)

### Add DNS records
After adding, click on PointDNS addon from resources list. It will take you to PointDNS dashboard where you can see your added domain name under domains tab.

Click on domain name for which you want to add DNS records.

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/pointdns-nameserver-records.png "PointDNS Domain DNS records")

Copy NameServers(NS)(from PointDNS) records to domain registrar i.e. freenom

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/freenom-domains-list.png "Freenom Domain NS records")

* Services -> My Domains
* Click on `Manage Domain` button in row of your registered domain name.
* Management Tools -> NameServers

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/freenom-domain-nameservers-records.png "Freenom Domain NS records")

## Generate/Configure SSL certificate
I am assuming that your have heard about SSL certificate or HTTPS and why we need that for our domain/website. So here I will only explain how we can get an SSL certificate and configure it on Heroku. I am taking example of [sslforfree.com](https://www.sslforfree.com/) which provide free SSL certificate and supported by [letsencrypt.org](https://letsencrypt.org/) (Certificate Authority).

### Generate
* Go to [sslforfree.com](https://www.sslforfree.com/) to get free SSL certificate.
* Provide you domain name for which you want to generate an SSL certificate and Click on `Create Free SSL Certificate` button.

    **Note:** To create a wildcard certificate for multiple domains such as example.com enter `*.example.com example.com`.

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/sslforfree-manual-verification.png "SSLforfree Manual Verification for generating SSL certificate")

* Choose Manual Verification(DNS) and Press Try Manual Verification.
* Copy and add DNS records to PointDNS addon under your domain name.
    
    ![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/pointdns-add-record-popup.png "PointDNS add new record")

    * Click on CTA `+ Add record` on right top of DNS records list table.
    * Select TXT from dropdown of `Record Type`.
    * Copy Name - remove domain name suffix as it will add automatically.
    * Put value in `Text` input and update TTL to 1 same as given in sslforfree.com.
    * Click on `Add record`, now your record will show in DNS records list. You can edit it any time.

    ![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/pointdns-add-record.png "PointDNS add new record")
* Now click on Verification links given under DNS records on sslforfree.com (step 3)

    ![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/sslforfree-txt-records.png "Copy TXT records to PointDNS domain records")

* After successful verification, click on Download SSL certificate”.
* It will take few seconds to process your request and generate Certificate and Public Key. 
    
    ![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/generated-ssl-files.png "Generate SSL files")

You can either directly copy/paste these while Configuring SSL certificate OR download all files by click on `Download All SSL Certificate Files` (recommended) then upload .cert and .key files while configuring SSL.

### Configure
* Now go to Heroku app -> settings

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-configure-ssl.png "Configure SSL")

* Click on `Configure SSL` button (to enable this option you must have paid dyno).
* Choose `Manual` option in pop-up.
(You can also choose `Automatically` option in-case you want to use Heroku SSL certificate and auto-managed by Heroku itself. In this No need to add .cert and .key files.)

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-ssl-add-certificate-and-key.png "Upload/Copy Certificate and Key")

* Add public key(.cert) and private key (.key) in 1st and 2nd step respectively. Then continue and save. 

* Make sure your CNAME or ALIAS records are added to PointDNS as per Added Domains in Heroku App settings.

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-ssl-configured.png "Successfully configured SSL certificate")

**Note**: Generally SSL certificate reflects on domain within 5 mins of configuration. If not reflect heroku app details page after 10-15 minus check if SSL certificate Expiry statement is still showing there. If not it means SSL is not configured properly, you can repeat the configure process again.