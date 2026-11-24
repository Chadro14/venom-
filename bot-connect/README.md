# Venom pour Bot Connect

Ce worker possède son propre point d’entrée et son propre dossier de sessions. Le menu et le traitement des messages utilisent le même registre. Les commandes disponibles sont `.menu`, `.ping`, `.aide` et l’alias `.help`. Les commandes se lancent dans la discussion du client avec lui-même.

## Exécution

- Utiliser Node.js 22 ou plus récent.
- Depuis la racine du dépôt, lancer `npm ci --prefix bot-connect`, puis `node bot-connect/start.mjs`.
- Définir `SUPABASE_URL`, `SUPABASE_PUBLISHABLE_KEY` (ou `SUPABASE_ANON_KEY`) et `VENOM_WORKER_KEY` dans l’environnement de l’hébergeur.
- Enregistrer un bot `venom` dans le backend Bot Connect avec une clé dédiée et une capacité de 16 sessions au maximum. Démarrer une seule instance pour ce bot. Conserver `bot-connect/site-sessions/` sur un volume persistant.
- Tester le jumelage et la révocation avec un compte de test avant d’activer le catalogue public.

Lancer les tests du registre avec `npm test --prefix bot-connect`.
