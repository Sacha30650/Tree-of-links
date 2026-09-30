# Tree-of-links : centre de réflexion

Landing page HistoireDuDodo (`index.html`) + centre de réflexion propulsé par le skill **Arena**.

## Arena

[Arena](https://github.com/Jakeschincariol/arena-skill) (Jake Schincariol, licence MIT) confronte une idée, un problème ou un axe de réflexion à **100 sous-agents Claude**. Chacun reçoit exactement la même question, plus une « carte stratégie » différente : un mode de raisonnement, un workflow et une stratégie. Il y a 2 160 cartes possibles, sans doublon.

Les agents s'affrontent ensuite en tournoi à élimination directe. Chacun attaque la solution de l'autre, défend et révise la sienne, puis un juge note le match selon une grille écrite (`rubric.md`). Le perdant sort : 100 → 50 → 25 → 13 → 7 → 4 → 2 → 1. On obtient la réponse qui a survécu, les attaques qu'elle a encaissées et le nombre de rounds.

### Installation

Déjà installé dans ce dépôt, dans `.claude/skills/arena/` (copie de l'upstream au commit `df07b8e`). La commande `/arena` est disponible dans toute session Claude Code ouverte sur ce dépôt. Python 3.8+ suffit, sans rien à installer avec pip.

Pour l'avoir aussi hors de ce dépôt (au niveau de l'utilisateur) :

```bash
cp -r .claude/skills/arena ~/.claude/skills/
```

### Usage

```
/arena Faut-il sortir une version audio du livre avant la version papier ?
/arena --quick Trouve le meilleur titre pour le prochain tome   # 16 agents
/arena --agents 32 Comment doubler l'audience TikTok en 3 mois ?
/arena --seed 7 <sujet>                                        # tirage reproductible
/arena                                                          # re-joue ta dernière demande contre la réponse qui ne t'a pas plu
```

Formule ton sujet comme une tâche avec une réponse attendue, par exemple « Décide si… et recommande… », « Trouve la meilleure… ». Donne tout le contexte utile : les sous-agents ne voient pas la conversation, seulement le fichier de tâche.

### Coût

Le skill est gratuit, mais les tokens sont à ta charge.

| agents | rounds | appels de sous-agents |
|---|---|---|
| 100 (défaut) | 7 | 595 |
| 32 | 5 | 187 |
| 16 (`--quick`) | 4 | 91 |

Le travail se fait par vagues de 10 agents en parallèle. Passe en mode accept-edits (Shift+Tab) pendant un run, sinon chaque fichier écrit dans `.arena/` demande une validation.

### Centre de réflexion

- Les runs bruts vont dans `.arena/`, ignoré par git.
- Les conclusions à garder vont dans `sujets/<AAAA-MM-JJ>-<slug>/rapport.md` (modèle : `sujets/_modele/rapport.md`), indexées dans `sujets/INDEX.md`.

### Fichiers

```
.claude/skills/arena/SKILL.md         orchestration + consignes exactes de chaque sous-agent
.claude/skills/arena/bracket.py       machine à états du tournoi (stdlib Python)
.claude/skills/arena/strategies.json  15 modes de raisonnement, 12 workflows, 12 stratégies
.claude/skills/arena/rubric.md        la grille de notation des juges
.claude/skills/arena/LICENSE          licence MIT de l'auteur
```
