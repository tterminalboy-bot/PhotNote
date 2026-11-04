# Carnet Photographe

Application web responsive en français pour organiser des shootings cosplay, gérer les fiches des personnes photographiées et suivre les autorisations.

## Fonctionnalités

- Liste séparée des **shootings en cours** et des **shootings terminés**.
- Ouverture d'un shooting pour consulter sa liste de personnes.
- Fin d'un shooting avec double confirmation ; possibilité de le relancer ensuite.
- Modification et suppression des shootings (avec confirmation avant suppression).
- Fiches cosplayers avec nom, pseudo, Instagram, cosplay, lieu de la photo, notes et autorisations de tag/publication.
- Tableau des personnes avec recherche, tri A–Z / Z–A et choix des colonnes affichées.
- Modification d'une fiche depuis la ligne correspondante.
- Export et import des données au format JSON.
- Installation PWA et cache de la coquille de l'application.

## Sauvegarde du code et inventaire

Consulter [BACKUP-ET-INVENTAIRE.md](BACKUP-ET-INVENTAIRE.md) pour l'inventaire de tous les fichiers et dossiers et le point de restauration.

La branche `backup/avant-refonte-2026-11-03` conserve l'état du dépôt avant cette refonte.

## Mise en ligne

Le workflow `.github/workflows/pages.yml` publie le site sur GitHub Pages après un push sur `main`. Dans GitHub, ouvre **Settings → Pages** et vérifie que la source est **GitHub Actions**. Consulte ensuite **Actions** pour confirmer que le déploiement a réussi.

Adresse attendue : https://tterminalboy-bot.github.io/carnet-photographe/

## Stockage et synchronisation

Les données sont conservées dans le stockage local du navigateur (`localStorage`). Elles ne se synchronisent donc pas automatiquement entre PC et téléphone. Un export JSON est nécessaire pour transférer ou sauvegarder les données.

Le dossier `supabase/` contient uniquement un schéma préparatoire : aucune connexion Supabase n'est active dans cette version. Une base distante et une authentification devront être configurées avant toute synchronisation multi-appareils.

## Confidentialité

Les liens Instagram sont enregistrés dans les fiches ; l'application ne se connecte pas à l'API Instagram et ne récupère pas automatiquement les photos de profil. Les cases d'autorisation servent de suivi et ne remplacent pas le consentement explicite des personnes photographiées.
