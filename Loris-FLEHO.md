# TD7/9: Git Branches
## Exercise 2: Push files to common repository
### Q1 
git branch FLEHO
### Q2
git checkout FLEHO
nano Loris_FLEHO.txt
git add Loris_FLEHO.txt
### Q3
git commit -m "Ajout d'un nouveau fichier texte nommé Loris_FLEHO"
### Q4
git push -u depôt_distant FLEHO

## Exercise 3: Merge simple changes
### Q1 
git checkout master
git pull depôt_distant master
git merge FLEHO
### Q2
git push depôt_distant master

## Exercise 4: Resolve merge conflicts
### Q1 
git checkout FLEHO
### Q2
vim README.md
#### On peut ensuite appuyer sur la touche "i" pour ensuite taper ou copier coller le texte que l'on veut. Ensuite, on appuie sur la touche echappe pour revenir sur notre shell.
:wq
### Q3
git add README.md
git commit -m "Modifications des lignes 2 à 6 de README.md"
### Q4
git checkout master
git pull depôt_distant master
### Q5
git checkout FLEHO
git merge master
### Q6
#### Si des conflits apparaissent, il faut éditer le fichier README.md et résoudre les conflits manuellement en ordonnant les paragraphes par ordre alphabétique.
### Q7
git push origin master

## Exercise 5: Take latest changes from master in local branch
### Q1
git pull depôt_distant master
cat README.md
### Q2
git checkout FLEHO
### Q3
git merge master
### Q4
