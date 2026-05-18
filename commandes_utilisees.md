# Commandes utilisees

## Git

```bash
git clone https://github.com/Issou7756/DevOps-CloudNative.git
git remote -v
git remote remove origin
git remote add origin https://github.com/Issou7756/DevOps-CloudNative.git
git branch -M main
git push -u origin main
git checkout -b newcarservice-docs
git add .
git commit -m "Ajout de la documentation et preparation du devoir"
git push -u origin newcarservice-docs
git pull origin main
```

## GitHub

```bash
gh --version
gh auth status
gh pr status
gh pr checks
```

Dans cet environnement, `gh` n'etait pas installe. La Pull Request a donc ete finalisee via l'integration GitHub disponible.

## GitLab

```bash
glab --version
glab auth status
```

Dans cet environnement, `glab` n'etait pas installe. Les labels, milestones et issues ont ete crees via l'API GitLab avec un token en variable d'environnement.

## Docker

```bash
docker --version
docker build -t issou7756/devops-cloudnative:latest ./MyService
docker run -p 4000:8080 issou7756/devops-cloudnative:latest
docker tag issou7756/devops-cloudnative:latest issou7756/devops-cloudnative:latest
docker push issou7756/devops-cloudnative:latest
```

## Gradle / tests

```bash
cd MyService
./gradlew test
```

Sous Windows :

```powershell
cd MyService
.\gradlew.bat test
```

## Kubernetes local

```bash
minikube version
minikube start
kubectl version --client
kubectl apply -f k8s/
kubectl get pods
kubectl get services
minikube service nom-du-service --url
```

## Istio

```bash
istioctl version
istioctl install
kubectl apply -f istio/
kubectl -n istio-system port-forward deployment/istio-ingressgateway 31380:8080
```

URL de test attendue :

```text
http://localhost:31380/carservice
```

## Kiali

```bash
kubectl get pods -n istio-system
istioctl dashboard kiali
```

## Google Cloud / infrastructure

```bash
gcloud --version
gcloud auth login
gcloud config set project ID_DU_PROJET
gcloud compute instances list
terraform --version
ansible --version
```

Ces commandes sont a adapter au lab Google Cloud demande par le cours.
