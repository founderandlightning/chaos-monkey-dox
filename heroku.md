# Heroku Setup
For More info: [Getting Start on Heroku](https://devcenter.heroku.com/articles/getting-started-with-php)

### Login/signup Heroku
1. Navigate to [Heroku](https://www.heroku.com/)
2. Login to Heroku (Create account if haven't already: [Free Signup](https://signup.heroku.com/))

### Connect credit/debit card (Optional)
 Attaching credit card is optional, you can also use free features. But to use Paid Dynos, Configure SSL, extra feature or more usage(than free limit) You must add credit card.

* Goto Profile icon on Top-right cornor.
* Click on `Account Settings`.
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-settings.png "Account Settings")
* Click on `Billing` Tab.
* Add Credit Card.
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-billing.png "Billing - Add card")

### Create 2 apps (UAT/Prod)
1. Go to Heroku app by cliking heroku logo from anywhere.
2. Click on button `New` on right side(lower-top) and select `create new app`.
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-new-app.png "Create new app")

3. Fill your app name (as per availability). You can add environment prefix to app name i.e. uat-app-name.
You can also choose region as per project region. For ucreate we choose Europe.

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-new-app-create.png "Create new app")
4. After click on `create app` button, your app will be created and show in app list.
5. Similarly create another app for Production environment i.e. prod-app-name.

### Add/Attach apps to pipeline
A pipeline is created to deploy changes to production manually at specific time after validating all changes on uat/staging environment.
To create pipeline and attaching apps to it follow the below steps.

1. Click on `New` button as we have done while creating new app.
2. This time choose `Create new pipeline`.
3. Name the pipeline.
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/create-pipeline.png "Create new pipeline")
4. Search github repo for your app and connect it to pipeline. Click on `create pipeline`.
5. Now it will show you pipeline details page. Here you can add Staginge app and production app which you have created in earlier.
    * Click on `Add app` button.
    * Seach name of your app for staging and select from list. It will be attached to pipeline on select.
    * Similarly search app name for production and attach it to project section of pipeline.
![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/heroku-pipeline-detail.png "Create new pipeline")
6. After attaching both apps to pipeline click on `create new pipeline`.
Now your pipeline will show on dashboard in apps list.

**Note**: your apps will show no more in list. instead you can access apps from pipeline details page. But still you can directly search you app from search on dashboard/app list page.

### Configure addons (explain)
Heroku offers some addons(development tools) easy to integrate with few clicks.
Few common and neccessary adons used at ucreate are:

* Heroku Postgres
* Rollbar
* Papertrail
* New Relic APM
* Heroku Scheduler
* Heroku Redis
* PointDNS (for configuring domain name/SSL)

Some common steps to configure adons are below:

1. Goto your app details for which you want to configure adon.
2. Click on `Resources` tab.
3. It will show you list of already configured Adons (empty if no adon configured yet).
4. Type/Search the name of Adon your want to configure and select the exact adon from result list.
5. On click of adon it will show a popup, where you can select adon plan i.e. free, paid depends upon usage and features required.
6. Click on `Provision` button and your adon will show in list of resources.
7. For further configuration or settings click on particular adon in the list. It will take you to dashboard of that particular adon plateform.

### Add ENV variables
You can App specific ENV variables on Heroku by visiting app detail page.

* Goto `settings` tab
* Click on `Reveal Config Vars`. It will show you already added ENV variables, some variables(adon related) automatically added when you configure Adons.
* To add new ENV variable scroll to end of the list and add ENV variable Key and Value in given inputs then click `Add` button.
* You can edit ENV variable value any time.
* To delet any ENV variable click on cross(X) icon ahead of variable.

### Add Procfile
Procfile is a configuration file for Heroku app which tells Heroku the commands/tasks to execute before and post doployment i.e. 

- Your app’s web server (Configure Application path)
- Run migrations
- Dynos configuration

Procfile is a file without extension.
Format to write commands in Procfile is `<process type>: <command>`
    where process can be type of `web, worker, urgentworker, clock` etc.

For Heroku to use your Procfile, add the Procfile to the root directory of your application.


