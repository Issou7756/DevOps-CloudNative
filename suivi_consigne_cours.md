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
| Verifier le board Open / En cours / Closed | A verifier dans l'interface | Capture du board |
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
| Verifier Docker Desktop | A capturer | `docker --version` ou Docker Desktop |
| Builder l'image Docker | Verifie precedemment | Sortie `docker build` |
| Lancer le conteneur | A capturer | `docker run` |
| Tester dans le navigateur | A capturer | Page locale |
| Publier sur Docker Hub | A confirmer par capture | Page Docker Hub |
| Executer la CI GitHub Actions | Fait | Workflow en succes |

## Kubernetes et Istio

| Consigne | Etat | Preuve attendue |
| --- | --- | --- |
| Verifier Minikube | A faire localement | `minikube version` |
| Demarrer Minikube | A faire localement | `minikube start` |
| Creer YAML Deployment | A faire si demande | Fichier dans `k8s/` |
| Creer YAML Service | A faire si demande | Fichier dans `k8s/` |
| Deployer avec kubectl | A faire localement | `kubectl apply -f ...` |
| Tester via minikube service | A faire localement | URL fournie par Minikube |
| Installer Istio | A faire localement | `istioctl version` |
| Configurer Gateway / VirtualService | A faire si demande | YAML Istio |
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
- Ajouter des fichiers YAML Kubernetes/Istio dans le repo si le professeur demande une preuve par fichier et pas seulement par suivi GitLab.
