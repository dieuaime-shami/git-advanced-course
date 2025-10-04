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
