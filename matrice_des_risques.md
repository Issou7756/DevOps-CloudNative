# Matrice des risques DevOps / Cloud Native

| Risque | Impact | Probabilité | Gravité | Mitigation | Statut |
|---|---|---|---|---|---|
| Docker Desktop non démarré | Ne peut pas builder ni lancer les conteneurs | Moyen | Élevé | Vérifier que Docker Desktop est lancé avant les opérations | Ouvert |
| Dockerfile introuvable | Échec du `docker build` | Faible | Élevé | Confirmer que `MyService/Dockerfile` existe et est accessible | Ouvert |
| build Docker en erreur | Image non construite, déploiement stoppé | Moyen | Critique | Lire les logs, corriger le Dockerfile et relancer `docker build` | Ouvert |
| port local déjà utilisé | L’application ne démarre pas localement | Moyen | Moyen | Choisir un port différent (`-p 4001:8080`) ou libérer le port | Ouvert |
| échec du docker push | Image non publiée sur Docker Hub | Moyen | Élevé | Vérifier l’authentification Docker Hub avec `docker login` et le nom du tag | Ouvert |
| mauvais remote Git | Push vers le mauvais dépôt | Faible | Critique | Vérifier `git remote -v` et corriger avec `git remote set-url origin ...` | Ouvert |
| secrets poussés par erreur | Fuite de clés ou données sensibles | Faible | Critique | Ne pas committer de secrets ; utiliser `.gitignore` et variables d’environnement | Ouvert |
| tests GitHub Actions en échec | Merge retardé, livraison repoussée | Moyen | Élevé | Corriger les tests, analyser les logs GitHub Actions, relancer | Ouvert |
| erreur de branche ou conflit de merge | Merge non appliqué, travail interrompu | Moyen | Élevé | Faire `git pull origin main` avant push ; résoudre les conflits localement | Ouvert |
| Minikube non démarré | Environnement Kubernetes non disponible | Moyen | Moyen | Démarrer Minikube avec `minikube start` avant les déploiements | Ouvert |
| erreur YAML Kubernetes | Manifeste invalide, déploiement impossible | Faible | Élevé | Valider le YAML avec `kubectl apply --dry-run=client -f` | Ouvert |
| Istio / Kiali non accessibles | Observabilité et service mesh indisponibles | Faible | Moyen | Vérifier l’état des services Istio/Kiali et accéder via `minikube service` | Ouvert |
