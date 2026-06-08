# Plan GitLab : issues, milestones et board

Projet GitLab : `https://gitlab.com/Issam7756/issamk-devops`

## Labels principaux

- En cours
- Dev
- Ops
- Docker
- CI-CD
- Kubernetes
- Documentation
- Risque
- Monitoring
- Cloud

## Labels complementaires

- Build
- Test
- GitHub
- Terraform
- Ansible
- Infrastructure
- Google Cloud
- PostgreSQL
- Java
- Istio
- Kiali
- Service Mesh
- Agile
- Minikube
- CD

## Milestones du cours

- 08/04 - Gestion de projet / Git
- 18/05 - Docker / CI-CD
- 08/06 - Kubernetes / Istio
- 15/06 - Google Cloud / Rendu final

## Issues initiales creees

- DEV-01 a DEV-05
- DOCKER-01 a DOCKER-05
- CI-01 a CI-02
- KUBE-01 a KUBE-03
- ISTIO-01 a ISTIO-02
- MON-01
- GCP-01
- DOC-01 a DOC-03

## Issues complementaires creees depuis le support de cours

- GP-01 a GP-03 : organisation GitLab et gestion de projet.
- GIT-01 a GIT-05 : installation Git, clonage, remote, lien GitHub.
- AGILE-01 : travail en binome.
- BUILD-01 : creation d'une version executable.
- TEST-01 : programme de test.
- DOCKER-06 a DOCKER-07 : Dockerfile multi-stage et tag Docker Hub.
- CI-03 a CI-05 : workflow CI et tests avant merge.
- KUBE-04 a KUBE-09 : kubectl, YAML, deployment, service, Minikube.
- JAVA-01 a JAVA-04 : JDK 17, projet Java, image Docker, Docker Hub.
- ISTIO-03 a ISTIO-05 : Gateway, VirtualService, ingressgateway.
- MON-02 : Kiali.
- DB-01 : besoin PostgreSQL.
- SM-01 : Service Mesh.
- GCP-02 a GCP-05 : Google Cloud, machine, reseau, Terraform.
- INFRA-01 : Terraform / Ansible.
- CD-01 a CD-03 : deploiement continu Kubernetes.

## Board GitLab

Le board GitLab contient une liste basee sur le label `En cours`.
Les colonnes `Open` et `Closed` sont les colonnes natives de GitLab.

Si l'interface ne les affiche pas, verifier dans `Plan > Issue boards` que les listes par defaut ne sont pas masquees.

## Nettoyage des doublons build

Des doublons ont ete constates sur le build entre `En cours` et `Closed`.
Correction effectuee :

- `BUILD-01` reste l'issue canonique du build executable.
- L'issue `#9 build` a ete commentee comme doublon de `BUILD-01`.
- Le label `En cours` a ete retire de `#9`.
- L'issue `#9` a ete fermee.
- La capture finale du board doit montrer `Open`, `En cours` et `Closed` sans issue build dupliquee.

Tentative de controle local :

```bash
glab auth status
```

Resultat : authentification valide et nettoyage distant effectue avec `glab`.
