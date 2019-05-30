# Rollbar
Rollbar provides real-time exception reporting and continuous deployment monitoring for developers.

## Setup
To integrate rollbar with your project you may follow below steps:

1. Add `Rollbar` as heroku addon as explained in [Configure addons (explain)](https://github.com/suri4ucreate/chaos-monkey-dox/blob/master/heroku.md#configure-addons-explain)
2. Add package `jenssegers/rollbar` using composer command:
    
    ```
    composer require jenssegers/rollbar
    ```
3. To make exceptions/errors to be reported, edit your Exception Handler i.e. `app/Exceptions/Handler.php` and add below code in already existing method:

```
    \Log::error($exception); //rollbar
    parent::report($exception);
```

Fatal exceptions will always be sent to Rollbar.

**Note**: all ENV credentials/details required to package are automatically added to Heroku ENV.

## Integrate with Trello and Slack
Above we have just setup reporting Exception/Error to rollbar. Now how rollbar will report that error to us. In ucreate we use 2 mediums for rollbar notification.

1. Goto Rollbar dashboard via Heroku Adon (App `resources` tab)
2. Click on `Settings` in main navbar.
3. Check Left-side menu under `INTEGRATIONS`, select Notifications.
It will show you available options to get notifications from rollbar(for error reported by app.)

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/rollbar-notifications.png "Rollbar notification setup")

### Slack
1. Click on Slack section
2. Click on `Add to Slack` button.
3. Select your project `Channel or Group` from dropdown. Then click on `Enable Slack Integration`.

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/rollbar-slack-setup.png "Rollbar notification setup")

### Trello
1. Click on Trello section

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/select-trello.png "Trello integration")

2. Click on trello button.
3. Now on next screen click on connect button.
![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/connect-trello.png "Connect to trello")
4. Now it will ask to login in trello.

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/login-trello.png "login to trello")
5. After login you can select the project board where you want to send notifications.

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/choose-trello-board.png "Choose trello board")


## Generate and Verify Error reporting

1. You can test notifications by press "Send Test Notification" button.

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/send-test-notification.png "Send test notifications")

2. It will create card on the Rollbar section for the chosen project.

![picture alt](https://github.com/shivali-ucreate/chaos-monkey-dox/blob/master/img/trello-card.png "Test notifications")