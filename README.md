# VideoIA Studio — prototype MVP

Interface web en français pour préparer un brief vidéo et organiser une future chaîne de production IA.

## Lancer le prototype
- Ouvre `index.html` dans un navigateur moderne.
- Aucun serveur ni installation n'est nécessaire pour tester l'interface.
- Le prototype stocke uniquement l'état temporaire dans la page : il ne génère pas de vidéo et ne publie rien.

## Architecture recommandée pour la version connectée
- Frontend : Next.js + TypeScript.
- Backend : routes serveur Next.js ou API dédiée.
- Base de données : PostgreSQL (projets, tâches, comptes liés, publications).
- Stockage vidéo : stockage objet privé avec URLs temporaires.
- Génération : service de texte pour le script, Runway API pour les scènes, synthèse vocale et assemblage FFmpeg côté serveur.
- Publication : Metricool si les réseaux et formats voulus sont pris en charge pour le compte connecté ; sinon APIs officielles avec OAuth et autorisations nécessaires.
- Hébergement : plateforme prenant en charge les tâches longues, stockage et variables d'environnement.

## Variables d'environnement prévues
Voir `.env.example`. Ne jamais committer de vraies clés dans GitHub.

## Prochaines étapes
1. Créer un dépôt GitHub privé `videoia-studio`.
2. Ajouter cette interface au dépôt.
3. Créer le backend et une base de données.
4. Configurer l'accès de génération vidéo et la gestion des tâches.
5. Connecter les comptes sociaux avec autorisation explicite.
6. Ajouter validation avant publication, logs, retries et suivi d'état.
7. Tester d'abord avec une publication privée ou brouillon.

## Garde-fous de publication
- Demander une validation humaine avant la première publication.
- Conserver l'état exact de chaque tâche (brouillon, génération, prêt, programmé, publié, échec).
- Respecter les autorisations OAuth, limites d'API et règles des plateformes.
- Signaler le contenu généré par IA quand la plateforme l'exige.
