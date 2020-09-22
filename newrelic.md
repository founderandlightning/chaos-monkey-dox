# NEWRELIC
New Relic helps the developers and other concerned users to have insights of the applications on production for debugging the errors and performance issues.
## Setup
On heroku server, go to the Heroku's Add-on page for New Relic. Select the appropriate subscription plan and Heroku does the job for you to configure new relic as an add-on.

1. Choose the product New Relic APM: It’s analytics product for application performance monitoring (APM) delivers real-time and trending data about 
your application's performance and the level of satisfaction.

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/newrelic-firstscreen.png "New relic first screen")

Click on Add more button.

2. Install the agent:  A New Relic agent is a software that you install on a host or in an application that sends performance data to New Relic. New Relic uses different agents for different products and coding languages (Go, Java, .NET, Node.js, PHP, Python, or Ruby) for your app.Specific installation steps vary, based on your application's agent language e.g Select PHP. 

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/newrelic-agent.png "New relic APM screen")

3. Now you will get your license key.
Copy the license key and add it to environment variables named `NEW_RELIC_LICENSE_KEY` on heroku by click on settings in heroku app.

4. Restart dynos, Generate some traffic to your app and and see the results in 5 minutes.

## View Performance Data

To view data about application performance, end user experience, and server performance:
1. From your Heroku dashboard, select the app(production or staging) that has the New Relic add-on installed.
2. From your list of add-ons, select the New Relic icon.
3. After being redirected via SSO to your account(production or staging app) on the New Relic site.
4. Click on the application, it will take you to the Dashboard(APM) for Monitoring.

## App apdex score
The Apdex score is a ratio value of the number of satisfied and tolerating requests to the total requests made. Each satisfied request counts as one request, while each tolerating request counts as half a satisfied request.

An Apdex score varies from 0 to 1, with 0 as the worst possible score (100% of response times were Frustrated), and 1 as the best possible score (100% of response times were Satisfied).

Example Apdex score:

During a 2 minute period a host handles 200 requests. The Apdex threshold T = 0.5 seconds (500ms). This value is arbitrary and is selected by the user.

170 of the requests were handled within 500ms, so they are classified as Satisfied.
20 of the requests were handled between 500ms and 2 seconds (2000 ms), so they are classified as Tolerating.
The remaining 10 were not handled properly or took longer than 2 seconds, so they are classified as Frustrated.
The resulting Apdex score is 0.9: (170 + (20/2))/200 = 0.9.

## Alert for High Apdex Score






