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

**git branch -D [br_name]**
elimina una rama localmente. Generalmente lo ocupo después de aceptar un pull request en la web de GitHub, y eliminar la rama remota, y aplicar git fetch --prune, para eliminar la rama local.

-------

## Upload a new repository

**git remote add origin git@github.com:yourusername/your-repo-name.git**
This tells your local git "that GitHub URL is called origin".

**git push -u origin mi-rama**
Subir nueva rama a GitHub, sólo la primera vez

-------
## Undo changes, going back to a previous commit
To do this you first do it locally and then do a hard push to the remote repo.
- Step 1 — go back one commit locally
    `git reset --hard HEAD~1`
- Step 2 — force push to make the remote match
    `git push --force-with-lease origin main`

-------

## .gitattributes file to fix end of lines
When working with WSL to run git commands, an issue may arise with the end of line codifications. To fix this for a particular repo you can add a file to specify the end of line code (lf).
This problem I first faced when doing a pool request and then merging branches online. Then I pulled the changes to the local repo and ran into an error: local files differed to remote files. After asking Claude code, the answer was that end of lines codes differed, but all the content in the files in question where just fine and did not differ.
Claude code did the following command to  restore my local files and discard the changes in end of line format:
`git restore src/interfaz.py src/main.py src/proceso.py`
After the restore, you should be able to pull the changes without getting an error.

### A permanent solution for each repo

At the root of each repo, add a file with the name `.gitattributes`, which should contain just this line of code:

`* text=auto eol=lf`

-------

**ctrl + shift + P,  then "developer: reload window".**
To reload the window in vscode. Sometimes it helps when Ubuntu terminal doesn't show available in VSCode.

**Create live badges**
https://shields.io/badges  
Activity, GitHub commit activity, notes repository, commits per month ![GitHub commit activity](https://img.shields.io/github/commit-activity/m/seba-E/notes).

## Editor web vscode para ediciones rápidas

En la página principal de un repositorio presiona la tecla punto (.), o la tecla Enter. Este editor es sólo un editor de texto, no es lo mismo que una máquina virtual como codespaces.

## GitHub CLI  
CLI = Command Line Interface
Permite usar comandos en la terminal para controlar GitHub.
[Manual de CLI GitHub](https://cli.github.com/manual/gh)

## Version control in jupyter notebooks

### Solving local merge conflicts with nbdime

In your local folder run `git init`.
Then you should have installed the nbdime package in the current virtual environment (you can do this either in a venv or in a conda environment). `conda install nbdime`
Now run `nbdime config-git --enable` or `nbdime config-git --enable --global` to set up nbdime in the current project or in all projects(global).
To trigger `nbdime mergetool`, Git needs to be in an active ***merge conflict state***. nbdime acts as Git's helper, so if Git hasn't flagged a conflict, nbdime rightly reports "No files need merging". 
To create a merge conflict state you must have 2 branches and locally atempt to merge them with `git merge [branch]`. Then run `nbdime mergetool`.