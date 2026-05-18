# Commandes utilisées

## Git
- `git clone https://github.com/Issou7756/DevOps-CloudNative.git`
- `git remote remove origin` (si le remote devait être remplacé)
- `git remote add origin https://github.com/Issou7756/DevOps-CloudNative.git`
- `git branch -M main`
- `git push -u origin main`
- `git checkout -b newcarservice-docs`
- `git add .`
- `git commit -m "Ajout de la documentation et préparation du devoir"`
- `git push -u origin newcarservice-docs`
- `git pull origin main`

## Docker
- `docker build -t myservice:latest ./MyService`
- `docker run -p 4000:8080 myservice:latest`
- `docker tag myservice:latest issou7756/devops-cloudnative:latest`
- `docker push issou7756/devops-cloudnative:latest`

## GitHub CLI / GitLab CLI (sous réserve d’installation)
- `gh pr status`
- `gh pr checks`
- `glab issue create --title "..." --description "..." --milestone "..."`
- `glab milestone create --title "..." --description "..." --due-date "YYYY-MM-DD"`
