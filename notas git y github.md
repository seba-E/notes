# Git and GitHub notes

**git init**
initialize an existing directory as a Git repository.

**git clone [url]**
retrieve an entire repository from a hosted location via url.

**git status**
**git add [file]** : adds file to the staging area
**git add .** : adds all untracked files to staging area

**git fetch --prune**
Limpiar referencias locales a remotas

-------

## Upload a new repository

**git remote add origin git@github.com:yourusername/your-repo-name.git**
This tells your local git "that GitHub URL is called origin".

**git push -u origin mi-rama**
Subir nueva rama a GitHub, sólo la primera vez

-------

**ctrl + shift + P,  then "developer: reload window".**
To reload the window in vscode. Sometimes it helps when Ubuntu terminal doesn't show available in VSCode.

**Create live badges**
https://shields.io/badges  
Activity, GitHub commit activity, notes repository, commits per month ![GitHub commit activity](https://img.shields.io/github/commit-activity/m/seba-E/notes).

## Editor web vscode para ediciones rápidas

En la página principal de un repositorio presiona la tecla punto (.), o la tecla Enter. Este editor es sólo un editor de texto, no es lo mismo que una máquina virtual como codespaces.

# GitHub CLI
Permite usar comandos en la terminal para controlar GitHub.
[Manual de CLI GitHub](https://cli.github.com/manual/gh)