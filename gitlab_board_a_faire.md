# Board GitLab a verifier

## Objectif

Verifier que le board GitLab contient les colonnes attendues :

- Open
- En cours
- Closed

## Etapes dans l'interface GitLab

1. Aller dans `Plan > Issue boards`.
2. Creer le label `En cours` si le label n'existe pas deja.
3. Ajouter une liste basee sur le label `En cours`.
4. Verifier que les colonnes `Open`, `En cours` et `Closed` sont visibles.
5. Deplacer une issue de test dans `En cours` pour verifier que le board fonctionne.
6. Fermer une issue terminee pour verifier son passage dans `Closed`.

## Nettoyage des doublons build

Des doublons ont ete signales entre les colonnes `En cours` et `Closed` pour le build.
Correction effectuee :

1. `BUILD-01` est conservee comme issue principale.
2. L'issue `#9 build` a recu un commentaire `Doublon de BUILD-01`.
3. Le label `En cours` a ete retire de `#9`.
4. L'issue `#9` a ete fermee.
5. Le controle `glab issue list --all --label "En cours"` montre uniquement des issues ouvertes.

## Note

Si `glab` ne permet pas de creer les colonnes du board automatiquement,
cette verification doit etre faite manuellement dans l'interface GitLab.
