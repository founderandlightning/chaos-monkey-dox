# Github
For More info: 

## Register/Signup on Github
1. Navigate to [Github](https://github.com/join)
2. Login to Github
3. Create new repository
4. Clone the existing app repository to your local:
```
    git clone https://github.com/{your}/{project-repo}
```
5. Copy whole project folder to new folder.
6. Delete `.git` folder from new folder.
7. Push project to new github repo using terminal
```
    git init
    git add .
    git commit -m "first commit"
    git remote add origin https://github.com/{your}/{chaos-monkey-repo}.git
```
6. Check your repo on github and verify if now its showing your project files.