# Suivi des consignes du cours

Ce fichier reprend les consignes du support de cours et indique comment elles sont couvertes dans le rendu.

## Gestion de projet

| Consigne | Etat | Preuve attendue |
| --- | --- | --- |
| Creer un projet GitLab | Fait | Capture du projet GitLab |
| Creer les issues | Fait | Capture de la liste des issues |
| Creer 4 milestones | Fait | Capture des milestones |
| Associer issues et milestones | Fait | Capture d'une issue avec milestone |
| Ajouter le label En cours | Fait | Capture des labels |
| Verifier le board Open / En cours / Closed | Nettoyage des doublons build fait ; capture a prendre | Capture du board |
| Etablir la matrice des risques | Fait | `matrice_des_risques.md` |

## Git et GitHub

| Consigne | Etat | Preuve attendue |
| --- | --- | --- |
| Verifier Git | A capturer | `git --version` |
| Cloner le projet source | Trace | Historique / arborescence |
| Creer le depot GitHub personnel | Fait | Page GitHub |
| Configurer le remote | Fait | `git remote -v` |
| Creer une branche de travail | Fait | PR GitHub |
| Ouvrir une Pull Request | Fait | PR #2 |
| Verifier les checks | Fait | GitHub Actions en succes |
| Merger la Pull Request | Fait | PR mergee |

## Docker et CI

| Consigne | Etat | Preuve attendue |
| --- | --- | --- |
| Verifier Docker Desktop | Fait | `docker --version` et `docker info` |
| Builder l'image Docker | Fait | `docker build` en succes |
| Lancer le conteneur | Fait | `docker run` sur le port `4000` |
| Tester dans le navigateur | Fait en ligne de commande, capture navigateur a prendre | `http://localhost:4000/` retourne `Hello` |
| Publier sur Docker Hub | A confirmer par capture | Page Docker Hub |
| Executer la CI GitHub Actions | Fait | Workflow en succes |

## Kubernetes et Istio

| Consigne | Etat | Preuve attendue |
| --- | --- | --- |
| Verifier Minikube | Fait | `minikube version` : v1.38.1 |
| Demarrer Minikube | Fait | Profil `devops-cloudnative` avec driver Docker |
| Creer YAML Deployment | Fait | `k8s/deployment.yaml` |
| Creer YAML Service | Fait | `k8s/service.yaml` |
| Deployer avec kubectl | Fait | `kubectl apply -f k8s/` |
| Tester via minikube service | Fait via port-forward | `http://localhost:4001/` retourne `Hello` |
| Installer Istio | Fait via addons Minikube | `istio` et `istio-provisioner` actives |
| Configurer Gateway / VirtualService | Fait | `istio/gateway.yaml` et `istio/virtualservice.yaml` |
| Tester via port-forward | Fait | `localhost:31380/carservice` retourne `Hello` via `istio-envoy` |
| Verifier Kiali | Fait | `http://localhost:20001/kiali/` retourne `200 OK` |

## Google Cloud et infrastructure

| Consigne | Etat | Preuve attendue |
| --- | --- | --- |
| Decouvrir Google Cloud | A faire dans le lab | Capture Cloud Skills Boost |
| Reserver une machine | A faire dans le lab | Capture VM |
| Configurer le reseau | A faire dans le lab | Capture VPC / firewall |
| Etudier Terraform | Trace dans GitLab | Issue GCP-05 |
| Preparer Terraform / Ansible | Trace dans GitLab | Issue INFRA-01 |

## Ce qui reste vraiment manuel

- Capturer les ecrans demandes.
- Executer ou capturer les parties Google Cloud si elles ne sont pas deja faites.
- Prendre la capture du board GitLab apres retrait du label `En cours` sur l'issue `#9 build` fermee.
