# CircleCI setup
CircleCI is tool for contineous integration (CI) of your project modules developed. CircleCI controls your deployement acting as gateway to pass, hence helps to automates the software development process.

## Login/Signup
Signup to [CircleCI](https://circleci.com/signup/) with your existing github/bitbucket account. Choose as per the project repo you have.
**Note:** We use github because heroku gives option to connect with github.
If already has an account then login.

## CircleCI configuration
CiclCI is configured using `config.yml` file generally kept in folder `.cirlceci` in root directory of app/project. complete file relative path is `.circleci/config.yml` .

Know more about format of config.yml [Sample config.yml Files](https://circleci.com/docs/2.0/sample-config/#section=configuration)  

## Add required ENV variables
CircleCI env variables can be used in configuration file to supply credentials or other secret values(can't write on config file directly and push to github). Variables can be added to KEY, VALUE pairs and KEY can be used in config file with prefix $ i.e. $KEY.

You can add ENV variables to CircleCI as below:
1. Login to Circle Account.
2. Click on `ADD PROJECTS` from left side main nav.
    It will open list of all repos you have in your github/bitbucket account.
3. Choose the repo of your project and Click on button `Set Up Project` in front of your project repo.