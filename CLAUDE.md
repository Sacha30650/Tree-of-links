# Tree-of-links : centre de réflexion

Ce dépôt contient une landing page (`index.html`, HistoireDuDodo) et un **centre de réflexion** propulsé par le skill `arena` (`.claude/skills/arena/`, upstream : https://github.com/Jakeschincariol/arena-skill).

- `/arena <idée, problème ou axe>` : 100 sous-agents, même tâche, cartes stratégie différentes, tournoi jusqu'à une seule réponse. `--quick` = 16 agents.
- Les runs bruts restent dans `.arena/` (ignoré par git).
- Après un run, si l'utilisateur veut garder le résultat : `sujets/<AAAA-MM-JJ>-<slug>/rapport.md` depuis `sujets/_modele/rapport.md`, plus une ligne dans `sujets/INDEX.md`. N'y rapporter que ce que `bracket.py winner` et la solution championne disent vraiment.
- Ne pas modifier les fichiers du skill sans demande explicite : ils suivent l'upstream.
