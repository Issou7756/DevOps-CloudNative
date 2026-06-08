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
glab issue list -R Issam7756/issamk-devops --all --search build --in title,description
```

`glab` est installe et le nettoyage des doublons GitLab a ete fait avec `glab` :

```bash
glab issue note 9 -R Issam7756/issamk-devops --message "Doublon de BUILD-01. L'issue BUILD-01 devient l'issue canonique pour le build executable de l'application."
glab issue update 9 -R Issam7756/issamk-devops --unlabel "En cours"
glab issue close 9 -R Issam7756/issamk-devops
glab issue list -R Issam7756/issamk-devops --all --label "En cours" --output json --per-page 100
```

Resultat : l'issue `#9 build` est fermee sans label `En cours`; `BUILD-01` reste l'issue canonique.

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

Verification locale actuelle :

```text
java -version -> 1.8.0_361 dans le PATH par defaut
JAVA_HOME temporaire -> C:\Program Files\Eclipse Adoptium\jdk-21.0.11.10-hotspot
java -version avec JAVA_HOME temporaire -> 21.0.11
```

Le projet et la CI utilisent JDK 21. Les tests Gradle locaux ont ete relances avec JAVA_HOME temporaire :

```powershell
$env:JAVA_HOME='C:\Program Files\Eclipse Adoptium\jdk-21.0.11.10-hotspot'
$env:Path="$env:JAVA_HOME\bin;$env:Path"
.\gradlew.bat test
```

Resultat : tests en succes.

## Etat local des outils

```text
docker --version -> Docker version 29.4.3
docker info -> serveur Docker 29.4.3 accessible
docker build -t issou7756/devops-cloudnative:latest ./MyService -> succes
docker run --rm -d --name devops-cloudnative-test -p 4000:8080 issou7756/devops-cloudnative:latest -> conteneur demarre
Invoke-WebRequest http://localhost:4000/ -> 200 Hello
kubectl config current-context -> devops-cloudnative apres demarrage du nouveau profil Minikube
ancien contexte myAKSCluster -> endpoint AKS inaccessible, non utilise pour le rendu final
minikube version -> v1.38.1 via C:\Program Files\Kubernetes\Minikube\minikube.exe
istioctl version -> non utilise ; Istio valide via addons Minikube
```

## Kubernetes local

```bash
minikube version
minikube start -p devops-cloudnative --driver=docker
kubectl version --client
kubectl apply -f k8s/
kubectl rollout status deployment/carservice
kubectl get deployment carservice
kubectl get pods
kubectl get service carservice
kubectl port-forward service/carservice 4001:8080
```

Test HTTP Kubernetes :

```powershell
Invoke-WebRequest -UseBasicParsing http://localhost:4001/
```

Resultat attendu : `200 Hello`.

## Istio

```bash
minikube -p devops-cloudnative addons enable istio-provisioner
minikube -p devops-cloudnative addons enable istio
kubectl wait --for=condition=Ready pod --all -n istio-system --timeout=240s
kubectl apply -f istio/
kubectl -n istio-system port-forward deployment/istio-ingressgateway 31380:8080
```

URL de test attendue :

```text
http://localhost:31380/carservice
```

Resultat obtenu : `200 Hello` avec l'en-tete `Server: istio-envoy`.

## Kiali

```bash
kubectl get pods -n istio-system
kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.23/samples/addons/prometheus.yaml
kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.23/samples/addons/kiali.yaml
kubectl get pods -n istio-system
kubectl -n istio-system port-forward service/kiali 20001:20001
```

URL de test :

```text
http://localhost:20001/kiali/
```

Resultat obtenu : `200 OK`.

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
