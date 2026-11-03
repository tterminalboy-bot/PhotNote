# Sauvegarde et inventaire — Studio Notes

Date de l'inventaire : 3 novembre 2026

## Point de restauration

La version complète du dépôt avant la refonte est conservée sur la branche :
`backup/avant-refonte-2026-11-03`

Commit de référence : `e05fb7483d81d47540f8afa1ac24cdc876bb22b2`

Pour retrouver exactement l'état antérieur, sélectionner cette branche dans GitHub. Aucun dossier fonctionnel n'est supprimé dans le cadre de cette sauvegarde.

## Inventaire complet

| Chemin | Type | Utilité | Décision |
|---|---|---|---|
| `.github/` | Dossier | Configuration GitHub liée au dépôt. | À conserver |
| `.github/workflows/` | Dossier | Contient les automatisations GitHub Actions. | À conserver |
| `.github/workflows/pages.yml` | Fichier | Publie le site sur GitHub Pages à chaque push sur `main`. | À conserver |
| `.nojekyll` | Fichier vide | Empêche GitHub Pages d'appliquer Jekyll et de masquer certains fichiers/dossiers. | À conserver |
| `README.md` | Documentation | Explique l'application, son déploiement, le stockage local et les limites de synchronisation. | À conserver et actualiser |
| `icon.svg` | Image vectorielle | Icône de l'application installable (PWA). | À conserver |
| `index.html` | Application | Contient l'interface, les styles et la logique JavaScript de Studio Notes. | À conserver et refondre |
| `manifest.webmanifest` | Configuration PWA | Définit le nom, l'affichage, le thème et l'icône de l'application installée. | À conserver |
| `supabase/` | Dossier | Prépare une future base de données Supabase. | À conserver tant que la synchronisation cloud reste envisagée |
| `supabase/schema.sql` | SQL | Schéma de départ pour événements, contacts, authentification et règles d'accès Supabase. Il n'est pas exécuté par le site actuel. | À conserver, clairement identifié comme préparation non active |
| `sw.js` | JavaScript | Service worker : cache la coquille du site pour faciliter son ouverture hors ligne et actualise le cache. | À conserver |

## Bilan du nettoyage

Aucun élément ne peut être qualifié de totalement inutile avec certitude : chaque fichier a un rôle identifiable. Le dossier `supabase/` n'est pas utilisé par la version actuelle, mais il sert de base documentée à une synchronisation future ; le supprimer ferait perdre ce travail. Il est donc conservé. Aucun dossier ne sera supprimé sans preuve qu'il est sans usage.

## Limites importantes

- Les données actuelles sont enregistrées dans le stockage local du navigateur.
- Le dépôt GitHub ne contient pas les fiches personnelles enregistrées par l'utilisateur dans son navigateur.
- La branche de sauvegarde protège le code du dépôt, pas les données locales du téléphone ou du PC.
- Pour sauvegarder les shootings et contacts, utiliser aussi l'export JSON depuis l'application.
