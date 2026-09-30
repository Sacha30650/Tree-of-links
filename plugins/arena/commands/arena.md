---
description: Confronte une idée, un problème ou un axe de réflexion à 100 agents et produit une synthèse
argument-hint: <idée | problème | axe de réflexion> [--rapide | --famille=<nom>]
---

Sujet soumis à l'Arena : $ARGUMENTS

Suis précisément le skill `arena` (fichier `skills/arena/SKILL.md` de ce plugin) et le roster `skills/arena/roster.md`.

Résumé du protocole :
1. Reformule le sujet en une question claire et tranchable (affiche-la).
2. **Round 1 – Positions** : lance les 100 agents `arena-debater` (10 familles x 10 personas), en parallèle par lots de 10 (une famille par lot).
3. **Round 2 – Duel** : donne à chaque famille la synthèse des 3 positions les plus fortes des autres familles ; chaque famille réagit (1 agent relais par famille, 10 au total).
4. **Round 3 – Verdict** : agrège les scores, repère les clivages et les angles morts.
5. Écris le rapport dans `sujets/<AAAA-MM-JJ>-<slug>/rapport.md` (modèle : `sujets/_modele/rapport.md`) et met à jour `sujets/INDEX.md`.
6. Réponds à l'utilisateur avec : verdict global, 3 meilleurs arguments pour, 3 meilleurs contre, risques, recommandation, lien vers le rapport.

Options : `--rapide` = 1 persona sur 2 par famille (50 agents) ; `--famille=<nom>` = une seule famille (10 agents).
Ne commite que si l'utilisateur le demande.
