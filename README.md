# DevOps / Cloud Native

Projet réalisé pour le cours DevOps / Cloud Native.

L'application est un service Java Spring Boot. Le dépôt contient le code de l'application, le Dockerfile, la CI GitHub Actions, les fichiers Kubernetes, les fichiers Istio et les documents de suivi.

## Liens

- GitHub : https://github.com/Issou7756/DevOps-CloudNative
- GitLab : https://gitlab.com/Issam7756/issamk-devops
- DockerHub : https://hub.docker.com/r/issou7756/devops-cloudnative

## Application

Endpoints principaux :

- `/`
- `/cars`
- `/cars/{plateNumber}`

## Docker

Image utilisée :

```text
issou7756/devops-cloudnative:latest
```

Commandes :

```bash
docker build -t issou7756/devops-cloudnative:latest ./MyService
docker run -p 4000:8080 issou7756/devops-cloudnative:latest
docker push issou7756/devops-cloudnative:latest
```

URL locale :

```text
http://localhost:4000/
```

## CI

Le workflow GitHub Actions est dans `.github/workflows/action.yml`.

Il exécute les tests Gradle et le build Docker.

## Kubernetes

Fichiers :

- `k8s/deployment.yaml`
- `k8s/service.yaml`

Commandes :

```bash
kubectl apply -f k8s/
kubectl get pods
kubectl port-forward service/carservice 4001:8080
```

URL locale :

```text
http://localhost:4001/
```

## Istio

Fichiers :

- `istio/gateway.yaml`
- `istio/virtualservice.yaml`

Commandes :

```bash
kubectl apply -f istio/
kubectl -n istio-system port-forward deployment/istio-ingressgateway 31380:8080
```

URL locale :

```text
http://localhost:31380/carservice
```

## Documents du rendu

- `rendu_professeur.md`
- `suivi_consigne_cours.md`
- `commandes_utilisees.md`
- `gitlab_issues_milestones.md`
- `matrice_des_risques.md`
