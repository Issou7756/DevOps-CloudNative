# Rendu final pour le professeur

## 1. Contexte

Le projet reprend un service Java Spring Boot du depot `rent`.
L'objectif du devoir est de montrer une demarche DevOps / Cloud Native : gestion de projet, Git, Docker, CI, Kubernetes, Istio, monitoring et ouverture vers Google Cloud.

## 2. Gestion de projet GitLab

Projet GitLab : `https://gitlab.com/Issam7756/issamk-devops`

Les elements suivants ont ete prepares :

- labels de suivi et labels techniques;
- milestones correspondant aux quatre dates du cours;
- issues initiales du rendu;
- issues complementaires extraites du support de cours;
- issue board avec la colonne `En cours`.

Point de controle du board : des doublons ont ete constates sur les issues de build entre `En cours` et `Closed`.
La correction a ete faite : `BUILD-01` reste l'issue canonique, l'issue `#9 build` a ete commentee comme doublon, le label `En cours` a ete retire, puis l'issue a ete fermee.
La capture finale du board doit confirmer que les colonnes `Open`, `En cours` et `Closed` ne presentent plus ce doublon.

Le fichier `gitlab_issues_milestones.md` recapitule la structure.
Le fichier `suivi_consigne_cours.md` liste les consignes couvertes et celles qui restent a demontrer par capture ou execution locale.

## 3. GitHub

- Depot personnel : `https://github.com/Issou7756/DevOps-CloudNative.git`
- Branche cible : `main`
- Pull Request finale : `https://github.com/Issou7756/DevOps-CloudNative/pull/2`
- Statut : Pull Request mergee apres succes des checks GitHub Actions.

## 4. Docker

Dockerfile : `MyService/Dockerfile`

Commandes principales :

```bash
docker build -t issou7756/devops-cloudnative:latest ./MyService
docker run -p 4000:8080 issou7756/devops-cloudnative:latest
docker push issou7756/devops-cloudnative:latest
```

## 5. CI GitHub Actions

Le workflow GitHub Actions est present dans `.github/workflows/action.yml`.
Il verifie les tests Gradle et le build Docker.
Le dernier controle de Pull Request etait en succes avant merge.

## 6. Kubernetes, Istio et Google Cloud

Les consignes correspondantes sont tracees dans GitLab, les manifests attendus ont ete ajoutes au depot et l'execution locale a ete validee avec Minikube :

- demarrage Minikube avec le profil `devops-cloudnative` et le driver Docker;
- fichiers YAML Kubernetes Deployment et Service dans `k8s/`;
- deploiement local avec `kubectl apply -f k8s/` et pod `carservice` en etat `Running`;
- test Kubernetes via port-forward `http://localhost:4001/` retournant `Hello`;
- installation Istio via les addons Minikube `istio-provisioner` et `istio`;
- Gateway et VirtualService dans `istio/`;
- test via `istio-ingressgateway` avec `http://localhost:31380/carservice`, reponse `Hello` servie par `istio-envoy`;
- monitoring avec Kiali, accessible via `http://localhost:20001/kiali/`;
- preparation Google Cloud, reseau, Terraform et Ansible.

## 7. Matrice des risques

La matrice des risques est fournie dans `matrice_des_risques.md`.

## 8. Captures d'ecran a fournir

- GitHub : depot, PR mergee, checks GitHub Actions en succes.
- Docker : build reussi, conteneur lance, application accessible.
- GitLab : labels, milestones, issues, board sans doublon entre `En cours` et `Closed`.
- Kubernetes : `minikube start`, `kubectl apply -f k8s/`, pod `carservice` en `Running`, URL locale `http://localhost:4001/`.
- Istio : gateway, virtual service, port-forward, URL `http://localhost:31380/carservice`.
- Kiali : dashboard de monitoring accessible sur `http://localhost:20001/kiali/`.
- Google Cloud : console ou lab realise.
- Matrice des risques.

## 9. Conclusion

Le rendu couvre la partie GitHub, Docker, CI et gestion de projet GitLab.
Les consignes Kubernetes et Istio sont maintenant materialisees par des manifests YAML dans le depot.
Les autres consignes du cours sont tracees sous forme d'issues et de checklist afin de pouvoir les suivre et les prouver par captures d'ecran.
