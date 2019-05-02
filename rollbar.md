# Rollbar
Rollbar provides real-time exception reporting and continuous deployment monitoring for developers.

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