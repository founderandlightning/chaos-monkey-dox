# chaos-monkey-dox
This repo contains the steps to re-create an application running on Heroku server (along with all the addons), on another Heroku app.


## Table of contents:
* [Github setup](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/github.md)
    * [Signup/Login](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/github.md#loginsignup-on-github)
    * [Create repo](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/github.md#create-new-repository)
    * Create team
    * Assign members to team
    * [Push Local code to repo](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/github.md#push-local-code-to-repo)
* Heroku
    * Register / Login
    * Connect credit/debit card
    * Create 2 apps (UAT/Prod)
    * Create a pipeline
    * Add/Attach apps to pipeline
    * Configure addons (explain)
    * Add ENV variables
    * Add Procfile
    * Register/Add domain name
    * Add PointDNS
    * Add DNS records
    * Generate/Configure SSL certificate
    * Connect Github repo
* Circle CI
    * CircleCI configuration i.e. config.yml
    * Add required ENV variables
* Rollbar
    * Integrate with Trello and Slack
    * Generate and Verify Error reporting
* New Relic
* Papertrail
    * Setup Events Alerts
* Pre-Commit Hooks
    * CodeSniffer
    * MessDetector
    * PHPUnit/TDD