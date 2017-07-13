# setup and config
## git help
```shell
git help
git help log
```
## git config
```shell
git config [--global] xxx.xxx xxxx
git config [--global] -e
```
# creating and getting project
## git init
```shell
git init
git init <name>
```
## git clone
```shell
git clone ssh://grant_shen@pcbugit.realsil.com.cn:29418/repo/fw/ipcam/rts3903
git clone /path/to/local/git/repo
```
# basic snapshotting
## git add/mv/rm
```shell
git add .
git add -A
git add <path..>
git add -p
git add -i

git rm <path...> [-r]
rm <path...> [-r] && git add <path...>

git mv <oldpath> <newpath>
mv <oldpath> <newpath> && git add <oldpath> <newpath>
```
## git status
```shell
git status
```
## git diff
```shell
git diff
git diff --cached
git diff <commit>

git diff <commit1> <commit2>
git diff <commit1>..<commit2>

git diff <commit1>...<commit2>
git diff $(git merge-base <commit1> <commit2>) <commit2>

git difftool
```
## git commit
```shell
git commit
git commit -m "commit message"
git commit --amend
git commit <path...> -m "commit message"
```
## git reset
```shell
git reset [<commit>]
git reset --hard [<commit>]
git reset <path> [<commit>]
```
## git log
```shell
git log
git log --author
git log --grep
git log --stat
git log <path>
git log <revision-range>
git log --oneline --graph --decorate
gitg/gitk
git log --help
```
## git show
```shell
git show
git show <commit>
```
# branching and merging
## git branch
```shell
git branch
git branch -v
git branch -r
git branch -a
git branch <newbranch>
git branch -d <branch>
git branch --set-upstream-to=<up-stream> <branch>
```
## git checkout
```shell
git checkout <path>
git checkout <branch>
git checkout -b <branch>
```
## git merge
```shell
git merge <branch>
git merge --continue
git merge --abort
```
## git mergetool
```shell
git mergetool
```
## git rebase
```shell
git rebase <branch>
git rebase --continue
git rebase --abort
```
## git revert
```shell
git revert <commit>
git revert --continue
git revert --abort
```
## git cherry-pick
```shell
git cherry-pick <commit>
git cherry-pick --continue
git cherry-pick --abort
```
## git stash
```shell
git stash
git stash save "stash message"
git stash list
git stash apply <stash-id>
git stash pop <stash-id>
```
## git tag
```shell
git tag
git tag <tagname> <commit>
git tag -d <tagname>
```
# sharing and updating projects
## git remote
```shell
git remote show origin
git remote add <name> <url>
```
## git fetch
```shell
git fetch
```
## git pull
```shell
git pull
git pull --rebase
git pull <remote>
```
## git push
```shell
git push
git push origin master
git push -u origin master
git push --all
git push --tags
```

## git reversion range
```
A =      = A^0
B = A^   = A^1     = A~1
C = A^2  = A^2
D = A^^  = A^1^1   = A~2
E = B^2  = A^^2
F = B^3  = A^^3
G = A^^^ = A^1^1^1 = A~3
H = D^2  = B^^2    = A^^^2  = A~2^2
I = F^   = B^3^    = A^^3^
J = F^2  = B^3^2   = A^^3^2

    G   H   I   J
     \ /     \ /
      D   E   F
       \  |  / \
        \ | /   |
         \|/    |
          B     C
           \   /
            \ /
             A

D                G H D
D F              G H I J D F
^G D             H D
^D B             E I J F B
B..C             C
B...C            G H D E B C
^D B C           E I J F B C
C                I J F C
C^@              I J F
C^!              C
F^! D            G H D F
```
