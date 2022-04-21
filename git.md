git config --global -e
git config --global user.email "you@example.com"

CR LF
En windows: git config --global core.autocrlf true
En Linux: git config --global core.autocrlf input

### Usando Git
git status

git add *.txt

git commmit -m "Mensaje de commit"

Ver archivos en staging area: git ls-files

Remover archivos de working dir y de staging area de manera simultánea: 

git rm filet.txt *.txt

Renombrar archivos

git mv main.js file.js
