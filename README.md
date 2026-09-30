# Tree-of-links : centre de réflexion

Landing page HistoireDuDodo (`index.html`) + centre de réflexion basé sur le plugin **Arena**.

## Arena
Confronte une idée, un problème ou un axe de réflexion à **100 agents** : 10 familles (stratèges, sceptiques, visionnaires, utilisateurs, techniciens, éthique, finance, communication, savoirs, jokers) x 10 personas.

### Installation
```
/plugin marketplace add Sacha30650/Tree-of-links
/plugin install arena@tree-of-links-think-tank
```
(ou en local depuis le dépôt : `/plugin marketplace add ./`)

### Usage
```
/arena Faut-il lancer une version audio du livre avant la sortie papier ?
/arena --rapide <sujet>          # 50 agents
/arena --famille=sceptiques <sujet>   # 10 agents
```

### Déroulé
1. **Positions** : 100 avis tranchés (verdict, argument, risque, action).
2. **Duel** : chaque famille réagit aux meilleurs arguments des autres.
3. **Verdict** : clivages, angles morts, minorités, recommandation.

Les rapports sont rangés dans `sujets/` (modèle : `sujets/_modele/rapport.md`).

### Contenu
- `plugins/arena/commands/arena.md` : la commande
- `plugins/arena/agents/arena-debater.md` : l'agent débatteur
- `plugins/arena/skills/arena/` : protocole + `roster.md` (les 100 personas)
