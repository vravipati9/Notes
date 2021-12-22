# Git Useful Commands #

### To get repository from Github ###

* `` git clone https://github.com/vvsrk/restwebservices.git ``

### To commit below are the steps: ###
* `` git get index.html (or) git get . or git get -A ``

to view the status

* `` git status ``

(If any new files)

* ``git add . ``

* `` git commit -m "modifications commited"``

* ``git push  (or) git push -f origin master``

* ``git pull``



### Push existing project into Github ###

1) Create repository in Github (ex: https://github.com/vvsrk/rest_workspace.git)

2) Move to the folder which you want to checkIngit

3) Run below commandsgit

* ``git init``
* ``git add .``
* ``git commit -m "Initial commit"``
* ``git remote add origin <project url> (ex: https://github.com/vvsrk/rest_workspace.git)``
* ``git push -f origin master``


### Create a new Repository ###

1) Create repository or folder in Github (ex: git clone git@gitlab.dep.state.fl.us:learn/angular12.git)

2) Move to the folder which you want to checkIngit

3) Run below commandsgit

* ``git clone git@gitlab.dep.state.fl.us:learn/angular12.git``
* ``cd angular12``
* ``git switch -c main``
* ``touch add README.md``
* ``git commit -m "add README"``
* ``git push -u origin main``

### Push an existing folder (this is similar to above push existing project into Github) ###
* ``cd existing_folder``
* ``git init --initial-branch=main``
* ``git remote add origin git@gitlab.dep.state.fl.us:learn/angular12.git``
* ``git add .``
* ``git commit -m "Initial commit"``
* ``git push -u origin main``

 ### Push an existing Git repository ###
* ``cd existing_repo``
* ``git remote rename origin old-origin``
* ``git remote add origin git@gitlab.dep.state.fl.us:learn/angular12.git``
* ``git push -u origin --all``
* ``git push -u origin --tags``


## To get remote URL ##

1) If you want only the remote URL, or if your are not connected to a network that can reach the remote repo:
* ``git config --get remote.origin.url``

2) If you require full output and you are on a network that can reach the remote repo where the origin resides :
* ``git remote show origin``


### If we want to change the ::project url:: after we created the URL.  ###
ex: ``git remote set-url origin https://github.com/vvsrk/rest_workspace.git``

### Ignore some of the folders: ###
1) create file with name .gitignore in root directory(`` touch .gitignore``)
2) specify the list of folder which we want to ignore ending with slash (ex: ``folder1\``) 

### determine the URL that a local Git repository was originally cloned from? ###
* `` git config --get remote.origin.url``

## If git command screen is asking for User Id and Pwd every time, we can avoid this by executing these properties from cmd scr##
* ``config --global user.email "githubuserId@gmail.com" ``
* ``config --global user.name "githubuserId" ``


### Creating Branch in GitHub and Merge to Master ###
1) goto folder where our master is located(d:\JavaPractice\rest_workspace>)
* ``d:\JavaPractice\rest_workspace>git branch git_branch_test``
* ``d:\JavaPractice\rest_workspace>git checkout git_branch_test``
* ``d:\JavaPractice\rest_workspace>git status``
* ``d:\JavaPractice\rest_workspace>git add .``
* ``d:\JavaPractice\rest_workspace>git commit -m "added to test branching"``

2) (After commiting that only the branch will displays in GitHub)
3) If we want to switch to Master#
* ``d:\JavaPractice\rest_workspace>git checkout master``

### Note: Once we switched to Master, the files which we created will not apper in Master ###

### Merge ###
When we want to Merge it to Master, first we have to checkout Master then Merge with branch
* ``d:\JavaPractice\rest_workspace>git merge git_branch_test``

### Once we push then only it will update in Master###
* ``git push -u origin master``

* ``d:\JavaPractice\rest_workspace>git branch -d git_branch_test`` // only deletes from local

### To Delete from Remote ###
* ``git push origin --delete git_branch_test``

### How to make .gitignore tracking files ###
* ``#git rm --cached <file>``
https://stackoverflow.com/questions/1274057/how-to-make-git-forget-about-a-file-that-was-tracked-but-is-now-in-gitignore

### How do I resolve git saying “Commit your changes or stash them before you can merge”? ###
https://stackoverflow.com/questions/15745045/how-do-i-resolve-git-saying-commit-your-changes-or-stash-them-before-you-can-me

### Merge specific files from feature branch to master branch ###
https://jasonrudolph.com/blog/2009/02/25/git-tip-how-to-merge-specific-files-from-another-branch/

### Undo Most recent commit ###
https://stackoverflow.com/questions/927358/how-do-i-undo-the-most-recent-local-commits-in-git?rq=1

### Undo pushed changes ###
``git reset --hard <<committed hash>> ``

### Ignore branch commit history while Meging to Master ###
You are in branch iss10, and now wants to merge changes to master with out commit history ( git merge --squash )
``git checkout master``
``git merge --squash iss10``
``git commit -m "Merged iss10"``
In case you need to merge iss10 into master again in the future, right now you should update iss10 to base off master
``git branch -D iss10``
``git checkout -b iss10``
``git push -f origin iss10''
https://coderwall.com/p/ysor6a/git-merge-squash-for-merging-without-commit-history
