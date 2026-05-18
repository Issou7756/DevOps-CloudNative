# Plan GitLab : issues, milestones et board

## Milestones
1. **Sprint 1 - Import et analyse**
   - Objectif : récupérer le projet existant et analyser le code.
   - Livrables : dépôt GitHub configuré, README initial, Dockerfile identifié.

2. **Sprint 2 - Docker et tests**
   - Objectif : construire l’image Docker, lancer l’application localement et vérifier les tests.
   - Livrables : image Docker locale, application accessible sur `localhost`, preuves de build.

3. **Sprint 3 - CI/CD et documentation**
   - Objectif : créer la Pull Request, activer GitHub Actions et finaliser la documentation.
   - Livrables : PR ouverte, workflow GitHub Actions, rapport final.

## Issues recommandées
- **Issue 1 : Importer le projet rent**
  - Description : cloner le dépôt source, copier le projet dans le dépôt GitHub personnel et vérifier l’arborescence.

- **Issue 2 : Vérifier le Dockerfile et builder l’image**
  - Description : valider `MyService/Dockerfile`, construire l’image Docker, noter les commandes.

- **Issue 3 : Tester l’application localement**
  - Description : lancer le conteneur Docker, vérifier l’accès sur `http://localhost:4000`, tester la réponse `Hello`.

- **Issue 4 : Publier l’image sur Docker Hub**
  - Description : taguer l’image Docker et la pousser sur Docker Hub sous le compte `issou7756`.

- **Issue 5 : Créer la branche `newcarservice` et la Pull Request**
  - Description : créer une branche dédiée, pousser les changements, ouvrir une PR vers `main`.

- **Issue 6 : Activer GitHub Actions et vérifier les tests**
  - Description : s’assurer que le workflow GitHub Actions est présent et exécuter `./gradlew test` sur `MyService`.

- **Issue 7 : Rédiger le rendu final et la matrice des risques**
  - Description : préparer les documents finaux pour le professeur, incluant la matrice des risques et le rapport.

## Board GitLab recommandé
- Colonne `Open` : issues créées et prêtes à traiter.
- Colonne `In Progress` : issues en cours de travail.
- Colonne `Closed` : issues terminées.

## Remarques
- Les issues doivent être liées aux milestones correspondantes.
- Chaque issue peut contenir des sous-tâches pour Git, Docker, CI/CD et documentation.
