## Basics
```bash
touch file

git stage file -v | git add file -v              # Put file to stage
git mv file file.tmp                             # Rename
git rm -f file.tmp                               # Remove

git stage foo.txt                                # \
                                                 #  | -> git commit -am "message"
git commit -m "message"                          # /
```

## Reset
```bash
git reset -- file0 file1 file2                  # Reset staged files (--mixed deprecated)
```

```bash
git reset --soft COMMIT_HASH                    # Reset to specified commit
git reset --soft HEAD^                          # Reset last commit
git reset --soft HEAD~1                         # Reset last commit
git reset --soft HEAD^^                         # Reset last two commit
git reset --soft HEAD~2                         # Reset last two commit
```

```bash
git reset --hard                                # Reset all changes
```

## Pull / Fetch
```bash
git pull -vvvv

git fetch --all -vvv
git fetch --prune -vvv
```

## Logs
```bash
git log COMMIT_HASH
git show COMMIT_HASH

git revert COMMIT_HASH
git revert COMMIT_HASH
```

## Stash
```bash
git stash push -m "probably good changes"
git stash list
git stash show stash@{0} -p

git pop stash@{0}

git stash apply stash@{0}
git stash drop stash@{0}
```

```bash
git stash create

git stash store -m "test" xxxxx
```

## Branch
```bash
git branch

git branch -a -vvv                      # Show all branches

git checkout bname                      # Switch to branch
git checkout -b bname                   # Create new branch from current
git checkout -b bname origin/bname      # Create new branch from specified branch
git checkout -b 2.7.2 tags/v2_7_2       # Create new branch from specified tag
```

```bash
git push --set-upstream origin bname    # Set upstream
git branch -u origin/bname              # Set upstream
```

## Remote
```bash
git remote -vvv

git remote show origin

git remote rename origin test
git remote rename test origin

git remote remove origin

git remote add origin git@github.com:theanotherwise/git.git

git remote get-url --all origin
git remote get-url --push origin

git remote set-url --add origin gi2t@github.com:theanotherwise/git.git
git remote set-url --delete origin git2@github.com:theanotherwise/git.git
```
