# Github
This is guide for creating github account, new repository and upload code from local system to newly created repo.

## Login/Signup on Github
* Navigate to [Github](https://github.com/)
* Login to Github (Create account if haven't one: [Join Github](https://github.com/join))

## Create new repository
1. In the upper right corner, next to your avatar or identicon, click *+* and then select `New repository`.
    ![picture alt](https://github.com//uCreateit/openmind-api/blob/master/public/images/logo.png?raw=true "Create new repository")

2. Name your repository `chaos-monkey`.
3. Write a short description.
4. Keep unselect `Initialize this repository with a README` Because actual project README.md will be used. (If still want to create own README then select it.) 
5. Click Create repository.
    ![picture alt](https://github.com//uCreateit/openmind-api/blob/master/public/images/logo.png?raw=true "Create new repository")


## Push Local code to repo
1. Clone the existing app repository to your local:
```
    git clone https://github.com/{your}/{project-repo}
```
2. Copy whole project folder to new folder.
3. Delete `.git` folder from new folder.
4. Push project to new github repo using terminal
```
    git init
    git add .
    git commit -m "first commit"
    git remote add origin https://github.com/{your}/{chaos-monkey-repo}.git
```
5. Check your repo on github and verify if now its showing your project files.