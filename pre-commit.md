# Pre-Commit Hooks
Pre-commits hooks helps us to execute any task before the commit. It can be used for analysing the code we have changed, any syntax, functionality issue. Can also run Tests before any code get commited and pushed to remote repo.

## Setup

Pre-commit tasks can be configured as following below steps:
1. Open `.git/hooks` directory.
2. You will see `pre-commit.sample` file, Copy and rename it to `pre-commit`.
3. Remove all sample code (or make it blank).
4. Now simply add command for each task you want to perform before every commit. i.e.

    `echo "pre-commit tasks starting..."`

This is a simple command to to test pre-commit hook. You can also provide any command as per your requirement. Multiple commands can also given either one command per line or separated by ` && `. 
i.e.

    chmod +x .deploy/pre_commit.sh
    .deploy/pre_commit.sh

OR
    
    chmod +x .deploy/pre_commit.sh && .deploy/pre_commit.sh

As you can see the command, Its giving read permissions to a file `.deploy/pre_commit.sh` and reading it.
We used `pre-commit.sh` file as main file to list all the tasks to execute via pre-commit hook.
Hence here we just call pre_commit.sh which has all the task listed.

![picture alt](img/pre-commit-sh.png "Main pre commit command file")

Here we configure pre-commit tasks/activities using below packages to analyse our code before commit.

## PHP CodeSniffer
CodeSniffer is used to check code against syntax standards recommendations i.e. PSR2.

To setup PHP CodeSniffer for your project follow below steps.

1. Add package to your project app via composer, run below command:

    `composer require squizlabs/php_codesniffer --dev`

2. It will provide you command in vendors->bin i.e. `./vendor/bin/phpcs`. You can run this command to check your code against PSR2 guidelines by defualt. But you can also custom `phpcs_ruleset.xml` as 'Standard' option i.e.
    
    `./vendor/bin/phpcs app/* --runtime-set --standard=./.deploy/phpcs_ruleset.xml`

It also accept various other options to customize make analysis and visually good. [check more](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Usage)

3. Write this command with desired options to file `phpcs.sh`  and save it in dir `.deploy/commands`. below is sample command with options:

![picture alt](img/pre-commit-phpcs.png "PHP Codesniffer commands")

4. Now call this command file in main file `pre_commit.sh` (It makes it easy to manage pre-commit tasks from one file, while keeping individual task file uneffected.)

5.   

## MessDetector

To setup PHP Mess Detector for your project follow below steps.

1. Add package to your project app via composer, run below command:

    `composer require phpmd/phpmd --dev`

2. It will provide you command in vendors->bin i.e. `./vendor/bin/phpmd`. You can run this command to check your code against PHP standards of programming.
Here also you can provide custom ruleset `phpmd_ruleset.xml` with ruleset defined as per your requirement. check more about [Phpmd ruleset](https://phpmd.org/documentation/creating-a-ruleset.html)

It also accept various options to make analysis customized and visually nice. [check more](https://github.com/phpmd/phpmd#command-line-usage) 

3. Write this command with desired options to file `phpmd.sh`  and save it in dir `.deploy/commands`. below is sample command with options:

`./vendor/bin/phpmd app/ text .deploy/phpmd_ruleset.xml --exclude app/Console/Kernel.php,app/Repositories/`

![picture alt](img/pre-commit-phpmd.png "PHP Messdetector commands")

4. Now call this command file in main file `pre_commit.sh` as shown above.

## PHPUnit/TDD

I hope you already know about TDD, if not please check our [TDD sessions](https://github.com/sandymadaan/php_tdd_sessions)

PHPunit is already intigrated with Laravel, so if you are using Laravel ignore step 1.

To setup PHPunit for your project follow below steps. 

1. Add package to your project app via composer, run below command:

    `composer require phpunit/phpunit --dev`

2. It will provide you command in vendors->bin i.e. `./vendor/bin/phpunit`. You can run this command to run your unit and feature test-case.

3. By default phpunit use environment variables from main `.env` to provide different env variable (like db, queue, env etc) you can either update your `phpunit.xml` at application root OR simply copy paste main `.env` file to `.env.testing` and udpate variables values as per your testing enviroment.

```
<?xml version="1.0" encoding="UTF-8"?>
<phpunit backupGlobals="false"
         backupStaticAttributes="false"
         bootstrap="vendor/autoload.php"
         colors="true"
         convertErrorsToExceptions="true"
         convertNoticesToExceptions="true"
         convertWarningsToExceptions="true"
         processIsolation="false"
         stopOnFailure="true">
    <testsuites>
        <testsuite name="Unit">
            <directory suffix="Test.php">./tests/Unit</directory>
        </testsuite>

        <testsuite name="Feature">
            <directory suffix="Test.php">./tests/Feature</directory>
        </testsuite>
    </testsuites>
    <php>
        <env name="APP_ENV" value="testing"/>
        <env name="BCRYPT_ROUNDS" value="4"/>
        <env name="CACHE_DRIVER" value="array"/>
        <env name="MAIL_DRIVER" value="array"/>
        <env name="QUEUE_CONNECTION" value="sync"/>
        <env name="SESSION_DRIVER" value="array"/>
        <env name="DATABASE_URL" value="postgres://postgres:postgres@localhost:5432/test_tdd"/>
    </php>
</phpunit>

```

You can further customize `phpunit.xml` to set different options. [check more](https://phpunit.de/manual/6.5/en/appendixes.configuration.html)

3. Write this command with desired options to file `phpunit.sh`  and save it in dir `.deploy/commands`. below is sample command with options:

`./vendor/bin/phpunit --color=always`

4. Now call this command file in main file `pre_commit.sh` as shown above.
