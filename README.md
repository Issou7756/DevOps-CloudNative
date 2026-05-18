# DevOps / Cloud Native - Projet final

## Présentation du projet
Ce dépôt contient un service Java Spring Boot adapté à un rendu DevOps / Cloud Native. Le projet a été préparé pour :
- l’import dans un dépôt personnel GitHub ;
- la construction d’une image Docker ;
- l’exécution locale du service ;
- la publication sur Docker Hub ;
- la création d’une Pull Request ;
- la validation via GitHub Actions.

## Gestion de projet, DevOps et Cloud Native
- **Gestion de projet** : piloter les tâches, créer des issues, organiser des milestones, suivre l’avancement.
- **DevOps** : automatiser les builds, les tests et les déploiements, favoriser la collaboration entre développeurs et opérationnels.
- **Cloud Native** : concevoir une application conteneurisée, indépendante de l’infrastructure, facile à déployer et à mettre à l’échelle.

## Dépôt GitHub personnel
- Repository : `https://github.com/Issou7756/DevOps-CloudNative.git`
- Remote Git configuré : `origin https://github.com/Issou7756/DevOps-CloudNative.git`
- Branche principale : `main`
- Branche de travail : `newcarservice-docs`

## Fichiers vérifiés
- `MyService/Dockerfile` ✅
- `.github/workflows/action.yml` ✅
- `README.md` ✅

## Commandes Git utiles
- `git clone https://github.com/Issou7756/DevOps-CloudNative.git`
- `git remote remove origin` (si le remote doit être remplacé)
- `git remote add origin https://github.com/Issou7756/DevOps-CloudNative.git`
- `git branch -M main`
- `git push -u origin main`
- `git checkout -b newcarservice-docs`
- `git add .`
- `git commit -m "Ajout de la documentation et préparation du devoir"`
- `git push -u origin newcarservice-docs`
- `git pull origin main`

## Commandes Docker utiles
- `docker build -t issou7756/devops-cloudnative:latest ./MyService`
- `docker run -p 4000:8080 issou7756/devops-cloudnative:latest`
- `docker tag issou7756/devops-cloudnative:latest issou7756/devops-cloudnative:latest`
- `docker push issou7756/devops-cloudnative:latest`

## Preuves attendues
- **Preuve du docker build** : la construction s’effectue sans erreur.
- **Preuve du docker run** : l’application répond sur `http://localhost:4000` et renvoie le message `Hello`.
- **Preuve du docker push** : l’image est publiée sur Docker Hub sous le compte `issou7756`.

## Pull Request
Une Pull Request a été créée depuis `newcarservice-docs` vers `main`. Elle permet de valider les changements avant fusion et de déclencher la CI/CD.

## GitHub Actions
Le workflow GitHub Actions se trouve dans `.github/workflows/action.yml`.
Il réalise les étapes suivantes :
1. checkout du code ;
2. installation du JDK 21 ;
3. exécution de `./gradlew test` dans `MyService` ;
4. build Docker de l’image.

## Liste des captures d’écran à fournir
1. `git remote -v` avec le remote GitHub personnel.
2. Arborescence du dépôt montrant `MyService/Dockerfile` et `.github/workflows/action.yml`.
3. Sortie du `docker build` réussi.
4. Page `http://localhost:4000` affichant `Hello`.
5. Page Docker Hub montrant l’image publiée.
6. Interface GitHub Pull Request ouverte.
7. Interface GitHub Actions avec le statut des checks.
8. Matrice des risques.

## Conclusion
Le dépôt est structuré et prêt pour un rendu de niveau M2I. La documentation du projet est complétée, la matrice des risques est créée, et les fichiers de synthèse sont disponibles. Il reste à finaliser la création d’issues et de milestones dans GitLab si nécessaire, et à vérifier les checks GitHub Actions depuis l’interface GitHub si la CLI n’est pas installée.
    