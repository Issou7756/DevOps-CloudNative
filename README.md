# DevOps / Cloud Native - Projet final

## Presentation du projet

Ce depot contient un service Java Spring Boot prepare pour le rendu DevOps / Cloud Native.
Le travail couvre la gestion de projet, GitHub, Docker, CI, GitLab, Kubernetes, Istio et Google Cloud.

## Depots

- GitHub : `https://github.com/Issou7756/DevOps-CloudNative.git`
- GitLab projet : `https://gitlab.com/Issam7756/issamk-devops`
- Branche principale GitHub : `main`
- Pull Request finale : `https://github.com/Issou7756/DevOps-CloudNative/pull/2`

## Etat GitHub

- La Pull Request `newcarservice-docs` vers `main` a ete creee.
- Les checks GitHub Actions ont reussi.
- La Pull Request a ete mergee.
- La branche distante `newcarservice-docs` a ete supprimee.
- Le fichier `gitlab_board_a_faire.md` a ete ajoute sur `main`.

## Etat GitLab

Les elements de gestion de projet ont ete crees dans GitLab :

- labels principaux : `En cours`, `Dev`, `Ops`, `Docker`, `CI-CD`, `Kubernetes`, `Documentation`, `Risque`, `Monitoring`, `Cloud`;
- labels complementaires : `Build`, `Test`, `GitHub`, `Terraform`, `Ansible`, `Infrastructure`, `Google Cloud`, `PostgreSQL`, `Java`, `Istio`, `Kiali`, `Service Mesh`, `Agile`, `Minikube`, `CD`;
- milestones du cours : `08/04`, `18/05`, `08/06`, `15/06`;
- issues initiales et issues complementaires issues du support de cours;
- board GitLab avec une liste basee sur le label `En cours`.

Point de controle GitLab : le doublon `#9 build` a ete commente comme doublon de `BUILD-01`, le label `En cours` a ete retire, puis l'issue a ete fermee.
`BUILD-01` reste l'issue canonique pour le build executable de l'application.

## Commandes Docker principales

```bash
docker build -t issou7756/devops-cloudnative:latest ./MyService
docker run -p 4000:8080 issou7756/devops-cloudnative:latest
docker push issou7756/devops-cloudnative:latest
```

## GitHub Actions

Le workflow est dans `.github/workflows/action.yml`.
Il execute les tests Gradle et verifie le build Docker.

## Kubernetes et Istio

Les manifests de deploiement local sont fournis :

- `k8s/deployment.yaml` : deploiement de l'image `issou7756/devops-cloudnative:latest`.
- `k8s/service.yaml` : service `carservice` sur le port `8080`.
- `istio/gateway.yaml` : gateway HTTP Istio.
- `istio/virtualservice.yaml` : route `/carservice` vers le service Kubernetes.

Commandes principales :

```bash
kubectl apply -f k8s/
minikube service carservice --url
kubectl apply -f istio/
kubectl -n istio-system port-forward deployment/istio-ingressgateway 31380:8080
```

URL Istio attendue :

```text
http://localhost:31380/carservice
```

## Documents de rendu

- `commandes_utilisees.md`
- `gitlab_issues_milestones.md`
- `gitlab_board_a_faire.md`
- `matrice_des_risques.md`
- `rendu_professeur.md`
- `suivi_consigne_cours.md`

## Captures d'ecran a fournir

1. Depot GitHub sur `main`.
2. Pull Request GitHub mergee.
3. GitHub Actions en succes.
4. Docker build reussi.
5. Application lancee localement.
6. Docker Hub si l'image est publiee.
7. Labels GitLab.
8. Milestones GitLab.
9. Issues GitLab.
10. Issue board GitLab avec `Open`, `En cours`, `Closed`, sans doublon build.
11. Kubernetes : `kubectl apply -f k8s/` et service `carservice`.
12. Istio : Gateway, VirtualService et URL `http://localhost:31380/carservice`.
13. Matrice des risques.
