# gitcommand

 #### Getting started "clone remote repository"

After joining any team or an organisation you need to first learn about the code for which you need to clone the remote repository to your local machine. 
[ Cloning a repository pulls down a full copy of all the repository data that GitHub.com has at that point in time, including all versions of every file and folder for the project.]
Cloning can be done from github website where the repository is present and using command as well. As we are focusing on understanding git commands we will clone https://github.com/AkshayDevkate/gitcommand repository using following command.
```
git clone https://github.com/AkshayDevkate/gitcommand.git
```
This will download a complete copy of all the repository data available on GitHub.com at the time, including all versions of every file and folder in the project.
After running above command you will be able to see the folder named gitCommands.  When you go inside the gitcomand folder you will be able to see the following folders and files .
This means now you have two copies of code. One in the remote repository and one in your local computer. 
If you dont have gh-pages installed install it using following command. Make sure git is installed on your computer check package.json file 
npm install gh-pages --save-dev
This will install github pages on local folder. gh-pages is used to deploy local changes to http://akshaydevkate.github.io/gitcommand

#### 2. Making "commit" to remote repository. 
Now open project /gitcommand with your favourite IDE i use Visual Studio Code. Now you have opened the the folder navigate to /gitcommand/src/App.js. You will make changes in App.js. We will edit table in App.js and then track changes.
Now you have cloned the repository and you have all the code in the local machine. No go to the terminal or command prompt and write following commands.
```
git add .
```
This will 
```
git commit -m "Write your message about what changes you made to it"
```
Git commit will add the files from staging area to 
```
git push 
```
:exclamation: Some times when you run this command you might get an error like
```
! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/AkshayDevkate/gitcommand.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
This error come when two or more users push code to the master repository and they have variations in code. This commands are only prefereable when you are a lone contributor to the repository. 
```
While working with team it is always advised to create a branch of your commit and create a pull request for same. That we will see in the coming tutorial. 
If you are a lone contributor and you know that the local changes are the final one you can try running following command to push changes to the master repository. 
```
git push origin master --force
```
#### 3. Creating a new branch. 
When you have an existing application running and you want to add a new feature. You create a branch and write the additional code about the feature. 
You can either create a new branch by 
```
git checkout -b <branch-name>
```
using git checkout command you will create a new branch and also will switch to the branch automatically.
If you dont want to switch to the branch and only create a new brach you can do it with 
```
git branch <branch_name>
```
You can later on switch to your new Git branch by using the
```
git checkout <branch_name>
```
You can use -a to list all the available branches to the git repository 
```
git branch -a 
```
Now update the code in the branch and make sure that the branch is uptodate to the other changes made by your team mates. 
When you write code and want to commit if you run following commands 
```
git add .
git commit -m "Now you are commit the code"
git push
```
:exclamation: When you run git push command you might get an error like 
```
fatal: The current branch branchOneTest has no upstream branch.
To push the current branch and set the remote as upstream, use

   git push --set-upstream origin branchOneTest
```
This is because 
You can run following command and then 
```
git push -u origin <your_branch_name>
```
After this you will not face problem to git push to this branch. you will also need to change the branch name once you are working on other branch active branch.
#### 4. Working Parallely with the team 
:exclamation: Some times while you are writting a new feature someone else would also have updated the repository for that thing you need to change the code.
```
! [rejected]        branchOneTest -> branchOneTest (fetch first)
error: failed to push some refs to 'https://github.com/AkshayDevkate/gitcommand.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details
```
#### 5. How to go back to previous code commits.

Its impossible to make no errors, Sometimes you would have made chanegs that are unnesessary and want to go back to the previos code this can be done using. To roll back to your previos commits changes that you made you can track them using.
```
git log
```
This will log all the changes with an unique code and accompanied by the date and time. 
```
Akshays-MacBook-Air-2:gitcommand akshaydevkate$ git log
commit be2395c5f0f22f2a8c348926cadb555ef708822d (HEAD -> branchOneTest, origin/branchOneTest)
Merge: ef572f2 3168242
Author: Akshay Devkate <devkatte.akshay98@gmail.com>
Date:   Mon May 23 12:33:50 2022 +0200

test new commits

commit ef572f2121123d8f96be3118602fb2775b2ab5d8
Author: Akshay Devkate <devkatte.akshay98@gmail.com>
Date:   Mon May 23 12:17:08 2022 +0200

adding code to branch one again

commit 3168242e3f6d12703a89ba2684c14553dcdd98c9
Merge: a2ede6f e125af7
Author: Akshay Dattatray Devkate <42045980+AkshayDevkate@users.noreply.github.com>
Date:   Mon May 23 11:48:13 2022 +0200

If you temporarily want to switch to the previos commits overlook the code and come back again use 
git checkout 3168242e3f6d12703a89ba2684c14553dcdd98c9
```

The unique number is to identify the commits.

[ The git checkout command allows you to move between the branches. Checking out a branch modifies the files in the working directory to match the branch's version, and also notifies Git to keep track of any new commits. ]
If you want to make a new brach out of your old commit use command 
```
git checkout -b old-state 3168242e3f6d12703a89ba2684c14553dcdd98c9
```
Simply check out the branch you were on to get back to where you were.
Hard Delete unpublished changes
If you want to get rid of the uncommitted changes than use the command 
```
git reset hard 3168242e3f6d12703a89ba2684c14553dcdd98c9
```
This will all the changes you made to the branch and take the development to the previous state.
If you want to keep the work on the top of the previos commit you can also do it with 
```
git stash 
git reset hard 3168242e3f6d12703a89ba2684c14553dcdd98c9
git stash pop 
```
```
git revert 
git clean 
git reset 
git rm 
git branch 
```
References
1] [reverting git repository to previos commits] (https://stackoverflow.com/questions/4114095/how-do-i-revert-a-git-repository-to-a-previous-commit)
2]
