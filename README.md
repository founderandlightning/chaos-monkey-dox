# chaos-monkey-dox
This repo contains the steps to re-create an application running on Heroku server (along with all the addons), on another Heroku app.


## Table of contents:
* [Github setup](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/github.md)
    * [Signup/Login](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/github.md#loginsignup-on-github)
    * [Create repo](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/github.md#create-new-repository)
    * Create team
    * Assign members to team
    * [Push Local code to repo](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/github.md#push-local-code-to-repo)
* [Heroku setup](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/heroku.md)
    * [Register / Login](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/heroku.md#loginsignup-heroku)
    * [Connect credit/debit card](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/heroku.md#connect-creditdebit-card-optional)
    * [Create 2 apps (UAT/Prod)](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/heroku.md#create-2-apps-uatprod)
    * [Create a pipeline](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/heroku.md#addattach-apps-to-pipeline)
    * [Add/Attach apps to pipeline](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/heroku.md#addattach-apps-to-pipeline)
    * [Configure addons (explain)](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/heroku.md#configure-addons-explain)
    * [Add ENV variables](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/heroku.md#add-env-variables)
    * [Add Procfile](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/heroku.md#add-procfile)
    * [Register/Add domain name](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/heroku.md#registeradd-domain-name)
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