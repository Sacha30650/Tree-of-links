---
name: arena
description: Confronte une idée, un problème ou un axe de réflexion à 100 agents aux perspectives opposées (Arena). À utiliser quand l'utilisateur veut challenger une idée, stress-tester une décision, explorer un dilemme, ou dit « arena », « confronte », « 100 agents ».
---

# Arena : 100 agents, 1 sujet

## Principe
Une idée seule est fragile. L'Arena la soumet à 100 personas réparties en 10 familles de 10 (voir `roster.md`). Chaque persona a des valeurs et des angles morts différents. La valeur est dans les **clivages**, pas dans la moyenne.

## Protocole

### 0. Cadrage
Reformule le sujet en question tranchable. Si le sujet est trop vague pour être débattu, pose UNE question de clarification, pas plus. Donne le contexte du dépôt si utile (ex. projet HistoireDuDodo : livre + TikTok).

### 1. Round 1 : positions (100 agents)
Pour chaque famille du roster, lance 10 appels `Agent` (subagent_type `arena-debater`) **dans un seul message** (parallèles). Prompt type :

> Persona : <nom> — <description>. Sujet : <question>. Contexte : <contexte>. Donne ton avis au format imposé.

Lance les familles une à une (10 agents par lot) pour rester maîtrisable. Conserve les réponses.

### 2. Round 2 : duel (10 agents)
Pour chaque famille, prépare un condensé : les 3 positions les plus fortes des *autres* familles (une POUR, une CONTRE, une surprenante). Un agent `arena-debater` par famille, incarnant le « porte-parole » de la famille, réagit et peut réviser sa position.

### 3. Round 3 : verdict
Calcule toi-même (sans agent) :
- répartition POUR / CONTRE / NUANCÉ, conviction moyenne, par famille et globale ;
- les 3 clivages les plus nets entre familles ;
- les angles morts : risques cités par un seul agent mais potentiellement fatals ;
- changements d'avis entre rounds 1 et 2.

### 4. Rapport
Écris `sujets/<AAAA-MM-JJ>-<slug>/rapport.md` depuis `sujets/_modele/rapport.md`, ajoute une ligne à `sujets/INDEX.md`.

## Règles d'intégrité
- Ne jamais inventer un avis d'agent : tout ce qui est cité provient d'un retour réel.
- Rapporter les minorités, même à 3 %.
- Séparer clairement ce que disent les agents de la recommandation propre de Claude.
- Si des agents échouent, le dire et indiquer le nombre réel de votants.
