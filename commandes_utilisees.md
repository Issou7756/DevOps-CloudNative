# Commandes utilisées

Ce fichier garde les commandes utiles pour refaire les principales étapes du rendu.

## Git

```bash
git remote -v
git status
git checkout -b newcarservice-docs
git add .
git commit -m "Ajout Kubernetes Istio et finalisation du rendu"
git push origin main
```

## GitHub

```bash
gh --version
gh auth status
gh pr status
gh pr checks
```

La Pull Request finale a été mergée après succès des checks.

## GitLab

```bash
glab --version
glab auth status
glab issue list -R Issam7756/issamk-devops --all
glab label list -R Issam7756/issamk-devops
glab milestone list -R Issam7756/issamk-devops
```

Le board GitLab sert au suivi des issues du projet.

## Docker

```bash
docker --version
docker build -t issou7756/devops-cloudnative:latest ./MyService
docker run -p 4000:8080 issou7756/devops-cloudnative:latest
docker push issou7756/devops-cloudnative:latest
docker manifest inspect issou7756/devops-cloudnative:latest
```

URL de test :

```text
http://localhost:4000/
```

## Tests Gradle

```bash
cd MyService
./gradlew test
```

Sous Windows :

```powershell
cd MyService
.\gradlew.bat test
```

Le projet utilise JDK 21.

## Kubernetes

```bash
minikube version
minikube start -p devops-cloudnative --driver=docker
kubectl version --client
kubectl apply -f k8s/
kubectl get pods
kubectl get service carservice
kubectl port-forward service/carservice 4001:8080
```

URL de test :

```text
http://localhost:4001/
```

## Istio

```bash
minikube -p devops-cloudnative addons enable istio-provisioner
minikube -p devops-cloudnative addons enable istio
kubectl get pods -n istio-system
kubectl apply -f istio/
kubectl -n istio-system port-forward deployment/istio-ingressgateway 31380:8080
```

URL de test :

```text
http://localhost:31380/carservice
```

## Kiali

```bash
kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.23/samples/addons/prometheus.yaml
kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.23/samples/addons/kiali.yaml
kubectl get pods -n istio-system
kubectl -n istio-system port-forward service/kiali 20001:20001
```

URL :

```text
http://localhost:20001/kiali/
```

## Google Cloud

```bash
gcloud --version
gcloud auth login
gcloud config set project ID_DU_PROJET
gcloud compute instances list
terraform --version
ansible --version
```

Ces commandes dépendent du lab Google Cloud utilisé pendant le cours.
