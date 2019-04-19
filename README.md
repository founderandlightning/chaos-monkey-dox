# chaos-monkey-dox
This repo contains the steps to re-create an application running on Heroku server (along with all the addons), on another Heroku app.


## Table of contents:
* Github
    * Register / Signup
    * Create repo
    * Create team
    * Assign members to team
    * Push Local code to repo
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