# Github
For More info: 

## Register/Signup on Github
1. Navigate to [Github](https://github.com/join)
2. Login to Github
3. Create new repository
4. Clone the existing app repository to your local
    git clone https://github.com/{your}/{project-repo}
    Copy whole project folder to new folder
    delete .git folder from new folder
5. Push project to new github repo
    git init
    git add .
    git commit -m "first commit"
    git remote add origin https://github.com/{your}/{chaos-monkey-repo}.git
6. Check your repo on github and verify if now its showing your project files.


push an existing repository from the command line
    git remote add origin https://github.com/suri4ucreate/chaos-monkey.git
    git push -u origin master