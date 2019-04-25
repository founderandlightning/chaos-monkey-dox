# CircleCI setup
CircleCI is tool for contineous integration (CI) of your project modules developed. CircleCI controls your deployement acting as gateway to pass, hence helps to automates the software development process.

## Login/Signup
Signup to [CircleCI](https://circleci.com/signup/) with your existing github/bitbucket account. Choose as per the project repo you have.
**Note:** We use github because heroku gives option to connect with github.
If already has an account then login.

## CircleCI configuration
CiclCI is configured using `config.yml` file generally kept in folder `.cirlceci` in root directory of app/project. complete file relative path is `.circleci/config.yml` .

Know more about format of config.yml [Sample config.yml Files](https://circleci.com/docs/2.0/sample-config/#section=configuration)  

## Project Setup
You need to setup new project on circleCI for your app:

1. Login to Circle Account.
2. Click on `ADD PROJECTS` from left side main nav.
    It will open list of all repos you have in your github/bitbucket account.
3. Choose the repo of your project and Click on button `Set Up Project` in front of your project repo.

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/circleci-setup-project.png "CircleCI project Setup")

4. Select the operating system on which you are actually deploying your project(same should be used to on CircleCI) from `Linux` or `macOS`
5. Select programing language of your app project. If not given in options, select Others and submit `Request a language` .  Below this you can find guide for next steps.
6. Create Configuration file (you can copy sample file) OR can copy from any exiting project and edit it as per your project requirements.
7. Click on `Start Building` to finilise Project setup.
8. Now your project will show in Workflows.

**Note** : before clicking on `Start Building` you should add and push `config.yml` to github repo. Otherwise your first build will show as failed.

## Add ENV variables
CircleCI env variables can be used in configuration file to supply credentials or other secret values(can't write on config file directly and push to github). Variables can be added to KEY, VALUE pairs and KEY can be used in config file with prefix $ i.e. $KEY.

You can add ENV variables to CircleCI as below:
1. Goto `WORKFLOWS` from left side Nav.
2. Click on setting icon in front of your project. It will take you to project settings for circle CI.
3. Click on `Environment Variables` under Build Settings from secondary left side nav.

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/circleci-project-setting.png "CircleCI add ENV variables")

4. You can add ENV variable in 2 ways. You can import from other project or can add own new ENV variable using `Add Variable` button.

![picture alt](https://raw.githubusercontent.com/suri4ucreate/chaos-monkey-dox/master/img/circleci-project-add-env-variable.png "CircleCI add ENV variables")
