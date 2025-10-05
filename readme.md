* This is the readme file that i will be using to share how i have done the tasks.

# Git Exercises
### 1.Getting started
* I have created a repository online and cloned it successfull.
``` bash
git clone https://github.com/dieuaime-shami/git-tasks.git
cd git-tasks
```
### Initializing the Environment:
* I have created and commited dummy files on a separet branc (dev) so that i wil request a PR to merge in the main branch after the riews.:
```bash
  // creating files
  touch test1.md
  touch test2.md
  touch test3.md
  touch test4.md

  // adding and commiting files
  git add test1.md && git commit -m "chore: Create initial file"
  git add test2.md && git commit -m "chore: Create another file"
  git add test3.md && git commit -m "chore: Create third and fourth files"
```

### Challenges:
#### 1.Missing file:
* After checking my git status i have fund that i have a file that is not tracked, and after that i check the history i have found that i only have the commit history for 3 files .
* All i did was to add the file and then amend it to the last commit.
```bash
git add test4.md
git commit --amend -m "feature/ Adding task4 file"
```
#### 2.Editing Commit History:
Create another file was my 3rd commit after i have check my commit history
so i did
```bash
git log --oneline
git rebase -i HEAD~4
```
and this opened a file with the last 4 commits and then on the commit i wanted to edit,i replaced pick to reword.
```bash
pick 6afc6f8 chore: Create initial file
reword 5b1f6b8 chore: Create another file
pick 923257d chore: Create third and fourth files
pick a962c41 feature/ Adding task4 file
```
I saved and after saving the opened another file with that commit message "create another file" , so i replaced this commit message with "Create second file"
### 3.Keeping History Tidy - Squashing Commits:
As create second and create initial files were the 4th commits i rebased from the 4th head and then added the keyword squash to the second most commit to be combined to the first one.
```bash
git log
git rebase -i HEAD~4
```
This opens a file with all the commits(the last 4 commits). and the i changed pick to sqash. and then save.
```bash
pick 6afc6f8 chore: Create initial file
sqash 5b1f6b8 chore: Create another file
pick 923257d chore: Create third and fourth files
pick a962c41 feature/ Adding task4 file
```
after saving, another file was opened and then i renamed the first commit"chore: Create initial file and Create second file"
and then save and close that file.
### 4.Splitting a Commit:
By reset you have the ability to take back the commit to unstage area which allow to recommit it with a different commit message. I had a commit that had 2 files. this is how i have reset.
```bash
git log --oneline
git reset
git add test3.md
git commit -m "Create Third File"
git add test4.md
git commit -m "Create fourth file"
```

### 5.Advanced Squashing:
* The first thing i did was to rebase the last two commits. and then replace the liest pick message create fourt file with squash. and after saving another file is open and we edit the first commit with the Create third and fourth files and then delete the last one.
```bash
 git log --oneline
 git rebase -i HEAD~2
```
another file opens with the last two commit messages. the change the last commit to squash
```bash
pick Create Third File
squash Create fourth File
```
this will bring a new file and the all we have to do is to replace the first commit message to Create third and fourth files and delete the last message. and then save.

### 6.Dropping a Commit:
With the key drop after rebasing we easy drop the commit history.
```bash
git log
git rebase -i HEAD~1
```
This will open one commit history in a file and the replace pick word to drop and the save.
```bash
drop unwanted commit
```
### 7.Reordering Commits:
I did was to rebase and the arrange the commit history messages, save and continue.
```bash
 git rebase -i
 // arrange the commit message
 git rebase --continue
```
### 8.Cherry-Picking Commits:
Cherry-picking help us to copy a commit from one branch to another
* I first created a branch and made some changes then commited it.
```bash
git checkout -b fr/branch
touch test5.md
//made some changes
```
* I then switched to dev and cherry-picked the commit
```bash
  git checkout dev
  git log ft/branch --oneline // to see the commit history
```
* this is mine
```bash
31c4b1f (ft/branch) Implemented test 5
8af29cf Create third and fourth files
923257d (origin/dev) chore: Create third and fourth files
5b1f6b8 c
```
The next step was to cherry-pick the commit
```bash
git cherry-pick 31c4b1f
git log --oneline // I will see this commit in dev by now.
```
### Visualizing Commit History (Bonus):
By typing git log --graph i have seen the commit history of each commit and when i was created.
```bash
git log --graph
```
### 10.Understanding Reflogs (Bonus):
* Reflogs keep or recods the update of all the branches and HEAD.
This is how i did it and i have seen all the commits,checkout,rebase and other more.

## Part 2: Branching Basics (10 Challenges)
### 1.Feature Branch Creation:
I have successfully created a branch and switched to it in oneline.
```bash
git checkout -b ft/new-feature
```
### 2.Working on the Feature Branch:
I have created a file , added the changes and the made some commits.
```bash
touch feature.txt
//added changes
commit -m "Implemented core functionality for new feature"
```
### 3.Switching Back and Making More Changes:
I have switch back to dev and created a new file added changes and commited it
```bash
git switch dev
touch readme.txt
git add readme.txt
git commit -m "Updated project readme"
```
### 4.Local vs. Remote Branches:
According to the reaserch i have made, I have seen the following:
* you have to be in the branch in which you want to create other branches from
* Create a branch and add some changes
* commit the change and the push the changes to the branch you are working on.

###### the next step is to merge it
* to marge the branch you have to first switch back to the parent branch dev or main
* the pull the changes from the branch you have pushed
* then merge that child branch
In most cases you will get the confilct so you shoul resolve them.

The push the dev remotely

### 5.Branch Deletion:
I have deleted the banch by using this command
```bash
git branch -D ft/new-feature
```

### 6.Creating a Branch from a Commit:
I have first seen the commit history for me to get the commit hash. the i created a new branch switch to it and added the commit hash for me to enter it.
and the push it.
```bash
git log --oneline
git checkout -b ft/new-branch-from-commit 3019faa
git log --oneline --decorate // for me to see the branch that it is pointing to.
git push -u origin ft/new-branch-from-commit
```
### 7.Branch Merging:
 What i did was to first make sure the every thing in ft/new-branch-from-commit was upto date, the get back to the branch i wanted to merge to which was dev in my case. and the merge.
 ```bash
 git git push -u origin ft/new-branch-from-commit
 git switch dev
 git merge ft/new-branch-from-commit
 ```
 In my case i did not get any conflict.

 ### 8.Branch Rebasing:
 Rebase takes all the commits from one branch and put them on the top of another branch. This is how i did everthing
 ```bash
 git checkout ft/new-branch-from-commit
 git rebase main
 git push origin ft/new-branch-from-commit
 ```
 ### 9.Renaming Branches:
 By the commamd git branch -m i renamed a branch name
 ```bash
 git branch -m ft/new-branch-from-commit ft/improved-branch-name
 git branch // to make sure that the name changed.
 ```
### 10.Checking Out Detached HEAD:
 We need detach HEAD to experiment with a past commit without affecting any branch. This is how i approached the challenge
 ```bash
 git log --oneline // a sow all the commit and took one hash commit
 git checkout df85815
 ```
 This took me in the detached HEAD

## Part 3: Advanced Workflows (10+ Challenges)

### 1.Stashing Changes:
Stash help us to temporary keep the changes in case we want to switch to another branch and we are not ready to commit the changes.
In this case i have created a file on dev branch and added some changes and the stash it.
```bash
touch test.md
//add some changes
git add test.md
git stash
```
### 2.Retrieving Stashed Changes
command like pop and apply help un unstash the changes we have stashed.
In this case i have used stash pop to bring back what i have stashed.
```bash
git stash pop
```

### 3.Branch Merging Conflicts (Continued):
 I created a new branch and added a file and also put some change and commit, after that i also came to the dev and added the same file and change.
```bash
git branch -b new-branch
touch file.md
//add changes
git add file.md
git commit -m "adding a file"
```
```bash
git switch dev
  touch file.md
//add changes
git add file.md
git commit -m "adding a file"

git merge new-branch // it raised a conflict
```
I resolved the conflict by accepting the changes.