# Rendu DevOps / Cloud Native

## Présentation

Ce projet a été réalisé dans le cadre du cours DevOps / Cloud Native.

Il s'agit d'une application Java Spring Boot, préparée pour être construite avec Docker, testée avec GitHub Actions, puis déployée localement avec Kubernetes et Istio.

## Liens du projet

- GitHub : https://github.com/Issou7756/DevOps-CloudNative
- GitLab : https://gitlab.com/Issam7756/issamk-devops
- DockerHub : https://hub.docker.com/r/issou7756/devops-cloudnative

Image Docker utilisée :

```text
issou7756/devops-cloudnative:latest
```

## Travail réalisé

### Gestion de projet

Le suivi du projet est fait sur GitLab.

Le projet contient les issues, les labels, les milestones et le board demandés dans le cours. Une matrice des risques est aussi disponible dans le dépôt.

### Développement et GitHub

Le code est publié sur GitHub dans le dépôt personnel du projet.

Une branche de travail a été utilisée, puis une Pull Request a été ouverte et mergée après validation de la CI.

### Docker

L'application peut être construite sous forme d'image Docker.

Commandes principales :

```bash
docker build -t issou7756/devops-cloudnative:latest ./MyService
docker run -p 4000:8080 issou7756/devops-cloudnative:latest
```

L'image a été publiée sur DockerHub.

### Intégration continue

Le workflow GitHub Actions se trouve dans :

```text
.github/workflows/action.yml
```

Il lance les tests Gradle et vérifie le build Docker.

### Kubernetes

Les fichiers Kubernetes sont placés dans le dossier `k8s/`.

Ils permettent de déployer l'application avec :

```bash
kubectl apply -f k8s/
```

Le service peut ensuite être testé localement avec un port-forward.

### Istio et Kiali

Les fichiers Istio sont placés dans le dossier `istio/`.

Ils ajoutent une Gateway et un VirtualService pour accéder au service avec le chemin `/carservice`.

Kiali est utilisé pour visualiser le service mesh.

### Google Cloud

La partie Google Cloud est à illustrer avec les captures du lab ou de la console, selon ce qui est demandé dans le support de cours.

## Captures à fournir

- dépôt GitHub avec les dossiers `k8s/` et `istio/` ;
- Pull Request GitHub mergée ;
- workflow GitHub Actions en succès ;
- image DockerHub publiée ;
- application lancée avec Docker ;
- projet GitLab avec issues, labels, milestones et board ;
- déploiement Kubernetes ;
- test Istio sur `/carservice` ;
- interface Kiali ;
- matrice des risques ;
- capture Google Cloud si demandée.

## Conclusion

Le projet regroupe les éléments principaux attendus pour le rendu : gestion de projet, dépôt GitHub, CI, Docker, Kubernetes, Istio, Kiali et suivi des risques.
