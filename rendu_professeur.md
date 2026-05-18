# Rendu final pour le professeur

## 1. Introduction
Ce document présente l’état final du devoir DevOps / Cloud Native sur le dépôt `DevOps-CloudNative`. Il décrit les actions faites localement, le lien avec GitHub et Docker Hub, la CI/CD, ainsi que la matrice des risques du projet.

## 2. Contexte du projet
Le projet reprend le service `rent` initialement développé avec Spring Boot. L’objectif est de gérer un projet en mode DevOps et Cloud Native, avec un démarrage local, un build Docker, un déploiement d’image, une Pull Request et la validation par GitHub Actions.

## 3. Gestion de projet GitLab
Le cadre de la gestion de projet demandé est préparé pour GitLab :
- création de milestones structurés ;
- création d’issues pour chaque étape ;
- utilisation d’un issue board avec les colonnes `Open`, `In Progress` et `Closed`.

> Remarque : la création effective des issues et milestones n’a pas été effectuée automatiquement car l’outil `glab` n’est pas installé dans cet environnement. Les commandes prêtes à copier-coller sont fournies dans `gitlab_issues_milestones.md`.

## 4. Dépôt GitHub
- Dépôt personnel : `https://github.com/Issou7756/DevOps-CloudNative.git`
- Remote configuré : `origin https://github.com/Issou7756/DevOps-CloudNative.git`
- Branche principale : `main`
- Pull Request existante : `newcarservice` vers `main`.

## 5. Build Docker
- Chemin du Dockerfile : `MyService/Dockerfile`
- Commande locale : `docker build -t issou7756/devops-cloudnative:latest ./MyService`
- Preuve de build : le projet a été compilé et l’image Docker construite avec succès sans erreur.

## 6. Test local
- Commande locale de lancement : `docker run -p 4000:8080 issamdevops`
- Service visible sur `http://localhost:4000`
- Réponse attendue : message `Hello`

## 7. Docker Hub
- Compte Docker Hub : `issou7756`
- Image déjà poussée sur Docker Hub selon l’état actuel du projet.
- Commandes types :
  - `docker tag issou7756/devops-cloudnative:latest issou7756/devops-cloudnative:latest`
  - `docker push issou7756/devops-cloudnative:latest`

## 8. Pull Request
Une Pull Request a été créée depuis la branche `newcarservice` vers `main`. Elle permet de valider la modification en revue de code et d’assurer que la mise à jour est testée avant fusion.

## 9. CI/CD GitHub Actions
Le workflow GitHub Actions est présent dans `.github/workflows/action.yml`.
Il effectue :
- checkout du code ;
- installation du JDK 21 ;
- exécution de `./gradlew test` dans `MyService` ;
- build Docker de l’image `myservice:latest`.

> Dans cet environnement, la CLI `gh` n’est pas installée, donc le statut de PR et des checks ne peut pas être récupéré automatiquement ici.

## 10. Matrice des risques
La matrice des risques du projet est fournie dans `matrice_des_risques.md`.

## 11. Captures à insérer
Les captures d’écran à fournir sont :
- `git remote -v` avec le remote GitHub personnel ;
- structure du dépôt (`README.md`, `MyService/Dockerfile`, `.github/workflows/action.yml`) ;
- sortie d’un `docker build` réussi ;
- sortie d’un `docker run` et page `http://localhost:4000` affichant `Hello` ;
- page Docker Hub montrant l’image publiée ;
- page GitHub Pull Request ouverte ;
- page GitHub Actions montrant le workflow ;
- schéma de la matrice de risques.

## 12. Conclusion
Ce rendu final présente un projet DevOps / Cloud Native complet et structuré. Les éléments essentiels sont prêts : dépôt GitHub, build Docker, test local, documentation, workflow GitHub Actions et matrice des risques. La dernière étape consiste à compléter la création des issues et milestones GitLab si nécessaire dans l’interface GitLab.
