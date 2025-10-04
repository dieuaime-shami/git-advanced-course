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