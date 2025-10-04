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
