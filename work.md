# part1
## exercises
```bash

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git reset HEAD~1

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git status
On branch main
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test3.md
        test4.md

nothing added to commit but untracked files present (use "git add" to track)

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git add test3.md

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git commit -m "Recreated test3 file"
[main 1fc5951] Recreated test3 file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git add test4.md

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git commit -m "Recreated test4 file"
[main 396d1ff] Recreated test4 file
 1 file changed, 0 insertions(+), 0 deletions(-)   
 create mode 100644 test4.md

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git log --oneline
396d1ff (HEAD -> main) Recreated test4 file
1fc5951 Recreated test3 file
b8f4585 chore: Create initial file and second file 

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git rebase -i HEAD~2
[detached HEAD fa9ecea] Recreated test3 and test4 files
 Date: Thu Sep 18 23:39:52 2025 +0200
 2 files changed, 0 insertions(+), 0 deletions(-)  
 create mode 100644 test3.md
 create mode 100644 test4.md
Successfully rebased and updated refs/heads/main.  

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git log --oneline
fa9ecea (HEAD -> main) Recreated test3 and test4 files
b8f4585 chore: Create initial file and second file 

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git add unwanted.txt
fatal: pathspec 'unwanted.txt' did not match any files

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git add unwanted.txt

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git commit -m "Unwanted commit"
[main 487b08f] Unwanted commit
 1 file changed, 1 insertion(+)
 create mode 100644 unwanted.txt

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git rebase -i HEAD~3
fatal: invalid upstream 'HEAD~3'

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git rebase -i --root
Successfully rebased and updated refs/heads/main.  

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git log --oneline
fa9ecea (HEAD -> main) Recreated test3 and test4 files
b8f4585 chore: Create initial file and second file 

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git log --oneline
fa9ecea (HEAD -> main) Recreated test3 and test4 files
b8f4585 chore: Create initial file and second file 

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git rebase -i --root
Successfully rebased and updated refs/heads/main.  

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git log --oneline
6e9c4aa (HEAD -> main) chore: Create initial file and second file
f8f5cf6 Recreated test3 and test4 files

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git rebase -i --root
Successfully rebased and updated refs/heads/main.  

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (ft/branch)    
$ touch test5.md

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (ft/branch)    
$ git add test5.md

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (ft/branch)    
$ git commit -m "Implemented test 5"
[ft/branch 4c6c0a5] Implemented test 5
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (ft/branch)    
$ git switch main
Switched to branch 'main'
Your branch is based on 'origin/main', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)     

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git log ft/branch --oneline
4c6c0a5 (ft/branch) Implemented test 5
6e9c4aa (HEAD -> main) chore: Create initial file and second file
f8f5cf6 Recreated test3 and test4 files

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git cherry-pick 4c6c0a5
[main 569ebf6] Implemented test 5
 Date: Fri Sep 19 00:02:31 2025 +0200
 1 file changed, 1 insertion(+)
 create mode 100644 test5.md

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git log --oneline
569ebf6 (HEAD -> main) Implemented test 5
6e9c4aa chore: Create initial file and second file 
f8f5cf6 Recreated test3 and test4 files

Shami dieu aime@SHAMI MINGW64 /d/Thegyme/GitAdvanced/my-repository/git-advanced-course (main)
$ git log --graph
* commit 569ebf6d93c6ebe37a78175a24066593137f2b77 (HEAD -> main)
| Author: dieuaime-shami <shamidieuaime272@gmail.com>
| Date:   Fri Sep 19 00:02:31 2025 +0200
|
|     Implemented test 5
|
* commit 6e9c4aa8c962fb352eb79a3ff372de79375bfcd3  
| Author: dieuaime-shami <shamidieuaime272@gmail.com>
| Date:   Thu Sep 18 22:58:34 2025 +0200
|
|     chore: Create initial file and second file   
|
* commit f8f5cf660470aa97364e84db82a67541bad0024e  
  Author: dieuaime-shami <shamidieuaime272@gmail.com>
  Date:   Thu Sep 18 23:39:52 2025 +0200

      Recreated test3 and test4 files
```
git