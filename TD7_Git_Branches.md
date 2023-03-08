## TD7/9: Git Branches

# Exercise 1: Clone a Git repository

# 3. Using only command-line in your Linux shell, clone it to a local repository.
```
git clone https://github.com/Loris-fleho/GIT-BRANCHES.git
```

# Exercise 2: Push files to common repository

# 1. Create a branch named after you.
```
git branch DYLAN
```
ou pour accéder directement à la branche en meme temps que de la créer
```
git checkout -b DYLAN
```

pour naviguer dans les différentes branches
```
git checkout <nom_de_la_branche>
```

# 2. Create a new text file named after you (with the content you want).
```
> Dylan.txt
echo "New content" Dylan.txt
```
:wq pour sauvegarder

# 3. Commit this new file.
```
git add Dylan.txt
git commit -m "Add new file named after me"
```

# 4. Push your branch to the remote repository.
```
git push -u origin DYLAN
```

Check in the web UI you see your branch (there is a button with ’master’ as
default).
```
git log --graph --oneline
```
output: 
* 13ddf9f (HEAD -> RIBOULET) Added TD7_git_branch
* 955530b (master, abc) Add description
* 78adfdd New file
* 36ab98f Update
* 83586f1 New files
* a195580 Add function.py file
* ec58fec Add main.py file
* b5bdd6e Add readme file

# Exercise 3: Merge simple changes

# 1. Merge your branch into the ’master’ branch
```
git checkout DYLAN
git merge main
```
 
# 2. Push your changes in the ’master’ branch to the remote repository.
```
git push origin master
```

Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
To GIT-BRANCHES
 * [new branch]      master -> master


```
git log --oneline
```


# Exercise 4: Resolve merge conflicts

# 1. Switch back to your own branch (not including the latest changes from
the master branch).
```
 git checkout RIBOULET
```

# 2. Edit the lines 2 to 6 of the README.md file with a text you like (a
poem, a quote, some clever code...). It can be any readable text, it may
be incomplete, it must just take about 5 lines and be different from your
teammates. It must start on line 2 to trigger conflicts between team
members
```
vim README.md
"This is amazing"
```

# 3. Commit this change
```
git add README.MD
git commit -m "Add text to README.md"
```

# 4. Pull latest status from the remote repository ’master’ branch into your
local ’master’ branch.
```
git checkout main
git pull origin main
```


5. Merge your branch into the local ’master’ branch.
```
git merge DYLAN
```

6. If there are conflicts, we want the paragraph to appear in alphabetical
order in the final README.md file.
```
git add README.md
git commit -m "Merge DYLAN into main"
```

7. Push your changes in the ’master’ branch to the remote repository.
```
git push origin master
```


# Exercise 5: Take latest changes from master in local branch

1. Pull the latest changes in the ’master’ branch, check the README.md
is up-to-date (contains all the paragraphs and the new line).
```
git checkout master
git pull origin master
cat README.md
```

2. Switch back to your own branch (not including the latest changes from
the master branch).
```
 git checkout RIBOULET
```

3. Merge the changes from ’master’ to your own branch.
```
git merge master
```

4. Commit this change.
```
git add README.md
git commit -am "New changes"
```


# Exercise 6: Delete a branch

1. Delete your branch on local repository
```
git branch -d RIBOULET
```

2. Delete your branch on distant repository.
```
git push GIT-BRANCHES --delete RIBOULET
```



# Exercise 7: Rebase interactively to have a clean history


1. Pull the latest changes in the ’master’ branch.
```
git checkout master
git pull origin master
```

2. Create a new local branch named after you and switch to it.
```
git checkout -b RIBOULET_2
```


3.
```
git rm README.md
git commit -m "Clear the whole file, removing all text."

echo "Git interactive rebase" > README.md
git add README.md
git commit -m "Add title line 'Git interactive rebase'."

curl https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History | head -n 14 > README.md
git add README.md
git commit -m "Copy the first paragraph from https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History."

curl https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History | head -n 24 | tail -n 10 >> README.md
git add README.md
git commit -m "Add the second paragraph from the same page."

curl https://git-scm.com/book/en/v2/Git-Tools-Rewriting-History | head -n 53 | tail -n 16 >> README.md
git add README.md
git commit -m "Add the first and second paragraphs from the 'Changing Multiple Commit Messages' section in the same page."

sed -i '16d' README.md
git add README.md
git commit -m "Remove the second paragraph from your file."

sed -i '4i Changing Multiple Commit Messages' README.md
git add README.md
git commit -m "Add missing title 'Changing Multiple Commit Messages' on a line just before the two paragraphs your copied."

echo "RIBOULET" >> README.md
git add README.md
git commit -m "Add a final line with your name or alias."
```

4. Use interactive rebase to have a single commit with message "Explain git
interactive rebase."
```
git rebase -i HEAD~8
```

5. Push your branch on the remote repository
```
git push GIT-BRANCHES RIBOULET
```


# Exercise 8: Create and approve a Merge/Pull Request


```
git checkout RIBOULET
git log --oneline
```

```
git rebase -i HEAD~1
git push GIT-BRANCHES

```

