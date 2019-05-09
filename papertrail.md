# Papertrail
Papertrail is a cloud based platform for providing hosted log aggregation and management, including real-time tail, search, and alerts on application and platform logs.

## Why Papertrail

1. It logs all actions performed by your application/website 
2. We can search through all logs, very quickly and without the need to download any log files to our local systems
3. We can search by using keywords eg “status=500” to get all the errors that happened
4. We can search for specific Heroku errors like “H21” to see all timeouts. You will learn more about heroku errors later.
5. We can set up alerts when certain actions happen. Eg. a 404 is reached, this sends an email to the dev team to fix the problem.
6. It can work as an audit trail of what happened on the app/website and we can recreate the steps done by the users.
7. It helps when our users complain that at eg. 15:23 something was not working. We can search for this exact time and see all calls to and from the app. We can see if everything was ok or not.

Adding log management to an application provides truly real time app visibility, faster troubleshooting, elegant alerting optimized for Heroku, and painless archives. Papertrail is accessible via Web browser, command-line client, and HTTP API. 

## Setup
On heroku server, go to the Heroku's Add-on page for Papertrail. Select the appropriate subscription plan and Heroku does the job for you to configure papertrail as an add-on.

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/papertrail-plan.png "Papertrail subscription plan")

## How to Use Papertrail: 
For using papertrail, there is only a small set of instructions. Papertrail keeps on collecting the logs, What we have to do is to be familiar with the environment. Let’s take a look at the components.

