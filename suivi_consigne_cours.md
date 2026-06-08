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
| Verifier Minikube | A installer ou ajouter au PATH | `minikube version` |
| Demarrer Minikube | A faire localement | `minikube start` |
| Creer YAML Deployment | Fait | `k8s/deployment.yaml` |
| Creer YAML Service | Fait | `k8s/service.yaml` |
| Deployer avec kubectl | A faire localement | `kubectl apply -f k8s/` |
| Tester via minikube service | A faire localement | URL fournie par Minikube |
| Installer Istio | A installer ou ajouter au PATH | `istioctl version` |
| Configurer Gateway / VirtualService | Fait | `istio/gateway.yaml` et `istio/virtualservice.yaml` |
| Tester via port-forward | A faire localement | `localhost:31380/carservice` |
| Verifier Kiali | A faire localement | Dashboard Kiali |

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
- Executer les parties qui dependent de Docker Desktop, Minikube, Istio, Kiali et Google Cloud si elles ne sont pas deja faites sur la machine.
- Prendre la capture du board GitLab apres retrait du label `En cours` sur l'issue `#9 build` fermee.
