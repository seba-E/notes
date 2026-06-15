# Git and GitHub notes

**git init**
initialize an existing directory as a Git repository.

**git clone [url]**
retrieve an entire repository from a hosted location via url.

**git status**
**git add [file]** : adds file to the staging area
**git add .** : adds all untracked files to staging area

**git fetch --prune**
limpiar referencias locales a remotas

-------

### Upload a new repository

**git remote add origin git@github.com:yourusername/your-repo-name.git**
This tells your local git "that GitHub URL is called origin".

**git push -u origin mi-rama**
Subir nueva rama a GitHub, sólo la primera vez

-------

**ctrl + shift + P,  then "developer: reload window".**
To reload the window. Sometimes it helps when Ubuntu terminal doesn't show in VSCode.
