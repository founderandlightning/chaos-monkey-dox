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

## Event viewer:
The simplest form, where you will be seeing lots of text. Each line representing the access log of any request. It contains some useful data like IP address of dyno, id, protocols type, time of request, url.
Some default types of events  are defined by heroku, useful to track things which is best suited to heroku setup.The event viewer, also called the log viewer, is a core part of Papertrail.

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/papertrail-events.png "Papertrail Events")

When you arrive in the log viewer, Papertrail is showing events as they happen. It’s real te, aims if you were logged directly into a system (or hundreds of systems). Logs are live.

## Pause logs

To pause live logs, scroll up or click PAUSE:

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/pause-event.png "Papertrail Pause Event")

## Resume live tail

When paused on current logs, click LIVE to resume live tail:

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/resume-event.png "Papertrail Resume Event")

## Return to current and resume live tail

When viewing older logs, click the down arrow or scroll down to return to current logs and resume live tail.

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/current-event.png "Papertrail Current Event")

## Search

Search is integrated into Papertrail’s event viewer:

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/search.png "Search")

Find anything just by typing what you know. If you’ve used Google search, Papertrail search works much the same way, including phrases ("), logical operators (AND, OR), and exclusion (-).
Click the upper right Help menu to see example searches without leaving the log viewer.
### Save searches

As your team uses Papertrail more, some searches will probably be worth accessing again, receiving in email, graphing, or otherwise retaining.
After entering a search query, click Save Search to retain the query:

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/save-search.png "Save Search")

### Create Events Alerts

## Time seek

To seek directly to any date or time in the searchable history, click the clock icon:

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/time-seek.png "Time Seek")


