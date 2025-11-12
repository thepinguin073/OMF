# Guide de Contribution

Merci de votre intérêt pour le Framework Méthodologique OSINT ! Ce document explique comment contribuer efficacement au projet.

---

## 📋 Table des matières

- [Code de conduite](#code-de-conduite)
- [Comment contribuer ?](#comment-contribuer-)
- [Types de contributions](#types-de-contributions)
- [Processus de validation](#processus-de-validation)
- [Standards de qualité](#standards-de-qualité)
- [Gouvernance distribuée](#gouvernance-distribuée)

---

## 📜 Code de conduite

En participant à ce projet, vous acceptez de respecter notre [Code de Conduite](CODE_OF_CONDUCT.md). Nous nous engageons à maintenir un environnement ouvert, accueillant et respectueux pour tous.

---

## 🤝 Comment contribuer ?

### 1. Avant de commencer

- ✅ Lisez le [Manifeste](docs/manifest.md) pour comprendre la philosophie du projet
- ✅ Consultez les [Issues existantes](https://github.com/thepinguin073/OMF/issues) pour éviter les doublons
- ✅ Rejoignez les [Discussions](https://github.com/thepinguin073/OMF/discussions) pour échanger avec la communauté

### 2. Workflow de contribution

```bash
# 1. Forker le repository
# Cliquez sur "Fork" en haut à droite de la page GitHub

# 2. Cloner votre fork
git clone https://github.com/[votre-username]/osint-methodology-framework.git
cd osint-methodology-framework

# 3. Créer une branche pour votre contribution
git checkout -b feature/ma-nouvelle-technique

# 4. Faire vos modifications
# ... editez les fichiers ...

# 5. Commiter vos changements
git add .
git commit -m "feat: ajout technique de géolocalisation par métadonnées EXIF"

# 6. Pousser vers votre fork
git push origin feature/ma-nouvelle-technique

# 7. Créer une Pull Request
# Allez sur GitHub et cliquez sur "New Pull Request"
```

### 3. Format des commits

Nous utilisons la convention [Conventional Commits](https://www.conventionalcommits.org/) :

```
<type>(<scope>): <description>

[corps optionnel]

[footer optionnel]
```

**Types autorisés :**
- `feat`: nouvelle fonctionnalité ou technique
- `fix`: correction de bug ou erreur
- `docs`: modification de documentation
- `style`: changements de formatage (pas de code)
- `refactor`: refactoring de code
- `test`: ajout ou modification de tests
- `chore`: tâches de maintenance

**Exemples :**
```
feat(matrix): ajout technique T0042 - analyse de géolocalisation
docs(methodology): clarification phase de corrélation
fix(templates): correction template ACH Excel
```

---

## 🎯 Types de contributions

### 1. Proposer une nouvelle technique

**Critères d'admission stricts** (voir Manifeste section V) :

✅ **Période probatoire** : 6 mois d'utilisation en conditions réelles
✅ **Validation indépendante** : au moins 2 entités différentes doivent confirmer la reproductibilité
✅ **Conformité épistémologique** : respect de la falsifiabilité, traçabilité, explicitation des incertitudes
✅ **Documentation exhaustive** : voir template ci-dessous

#### Template de proposition

```markdown
## Nouvelle Technique : [Nom de la technique]

### Informations générales
- **ID proposé** : T00XX
- **Tactique** : [Planning/Collecte/Corrélation/Analyse/Reporting]
- **Auteur** : @votre-username
- **Date de première utilisation** : YYYY-MM-DD

### Description
[Description détaillée de la technique en 200-500 mots]

### Cas d'usage
1. **Scénario 1** : [Description]
   - Contexte : [...]
   - Résultat : [...]
2. **Scénario 2** : [Description]
   - Contexte : [...]
   - Résultat : [...]

### Prérequis techniques
- Compétences requises : [...]
- Outils nécessaires : [...]
- Ressources : [...]

### Procédure étape par étape
1. [Étape 1]
2. [Étape 2]
3. [...]

### Validation de reproductibilité
- **Entité 1** : [Nom] - Date : [YYYY-MM-DD] - Résultat : [Succès/Échec]
- **Entité 2** : [Nom] - Date : [YYYY-MM-DD] - Résultat : [Succès/Échec]

### Limitations connues
- [Limitation 1]
- [Limitation 2]

### Considérations OPSEC
- Risques de détection : [...]
- Contre-mesures recommandées : [...]

### Conformité légale et éthique
- **RGPD** : [Impact et mesures]
- **Proportionnalité** : [Évaluation]
- **Juridictions** : [Restrictions par pays]

### Références
- [Source 1]
- [Source 2]
```

### 2. Améliorer la documentation

**Contributions bienvenues :**
- ✏️ Corriger des fautes d'orthographe/grammaire
- 📚 Clarifier des explications complexes
- 🌍 Traduire en d'autres langues
- 📖 Ajouter des exemples pratiques
- 🎨 Améliorer les schémas et visualisations

**Processus simplifié** : Pull Request directe sans période probatoire

### 3. Créer des templates et outils

**Besoins prioritaires :**
- Templates pour les 5 phases du cycle
- Scripts de validation (Python, Bash)
- Intégrations outils (Maltego, SpiderFoot, Shodan)
- Générateurs de rapports automatiques

**Exigences :**
- ✅ Code commenté et documenté
- ✅ Licence compatible (MIT, Apache 2.0, GPL)
- ✅ Exemples d'utilisation fournis

### 4. Partager des études de cas

**Format requis :**
- ❌ **Anonymisation complète** : pas de données personnelles réelles
- ✅ Méthodologie détaillée (cycle complet)
- ✅ Leçons apprises et limitations rencontrées
- ✅ Conformité légale du cas présenté

**Soumettre via** : `examples/case-studies/[nom-du-cas].md`

### 5. Signaler des problèmes

**Créer une Issue pour :**
- 🐛 Erreurs factuelles dans la documentation
- ⚠️ Techniques obsolètes ou risquées
- 💡 Suggestions d'amélioration
- ❓ Questions méthodologiques

**Template d'Issue :**
```markdown
## Type
- [ ] Bug
- [ ] Question
- [ ] Amélioration
- [ ] Nouvelle technique

## Description
[Décrivez le problème ou la suggestion]

## Contexte
[Informations supplémentaires pertinentes]

## Solution proposée (optionnel)
[Votre idée de solution]
```

---

## ✅ Processus de validation

### Pour les techniques majeures (nouvelles tactiques/techniques)

#### Phase 1 : Proposition initiale (semaine 1)
1. Créer une **Issue** avec le label `technique-proposal`
2. Présenter la technique avec le template complet
3. Discussion communautaire pendant **7 jours minimum**

#### Phase 2 : Période probatoire (6 mois)
1. La technique est ajoutée avec le statut `[EXPERIMENTAL]`
2. Appel à validation par entités indépendantes
3. Collecte de retours d'expérience
4. Documentation des cas d'usage réels

#### Phase 3 : Validation par les pairs (2 semaines)
1. **Au moins 2 entités indépendantes** confirment la reproductibilité
2. Review par les mainteneurs du projet
3. Vérification de la conformité épistémologique
4. Validation juridique et éthique

#### Phase 4 : Intégration (semaine finale)
1. Statut changé de `[EXPERIMENTAL]` à `[VALIDATED]`
2. Intégration dans la matrice principale
3. Mise à jour de la documentation
4. Annonce communautaire

### Pour les contributions mineures (docs, corrections)

**Processus accéléré :**
1. Pull Request directe
2. Review par un mainteneur (72h max)
3. Merge si approuvé

---

## 📊 Standards de qualité

### Documentation

- ✅ Français correct (grammaire, orthographe)
- ✅ Structure markdown propre
- ✅ Liens fonctionnels
- ✅ Exemples concrets
- ✅ Références vérifiables

### Code

- ✅ Commentaires en français
- ✅ Style PEP 8 (Python) ou équivalent
- ✅ Pas de dépendances propriétaires
- ✅ Tests unitaires si applicable
- ✅ README dans le dossier du script

### Techniques

- ✅ Reproductibilité démontrée
- ✅ Limitations explicitées
- ✅ Considérations OPSEC documentées
- ✅ Conformité légale vérifiée
- ✅ Niveau de confiance calibré

---

## 🏛️ Gouvernance distribuée

### Principes

Le framework OSINT repose sur une **gouvernance anti-centralisée** :

- ❌ Aucune entité ne décide arbitrairement
- ✅ Décisions collectives par consensus
- ✅ Transparence totale des processus
- ✅ Droit de fork en cas de désaccord fondamental

### Rôles dans la communauté

#### Contributeurs
- Toute personne ayant soumis au moins une contribution acceptée
- Droit de vote sur les discussions non-techniques
- Reconnaissance publique dans le fichier CONTRIBUTORS.md

#### Reviewers
- Contributeurs ayant validé 5+ contributions majeures
- Pouvoir de review sur les Pull Requests
- Participation aux décisions méthodologiques

#### Mainteneurs
- Reviewers ayant démontré une compréhension approfondie du framework
- Accès en écriture au repository principal
- Responsabilité de maintenir la cohérence épistémologique

**Devenir mainteneur** : nomination par les mainteneurs existants après 6 mois de contributions soutenues

### Résolution de conflits

1. **Discussion ouverte** : GitHub Discussions (14 jours)
2. **Vote communautaire** : si pas de consensus (contributeurs actifs)
3. **Médiation** : mainteneurs comme arbitres
4. **Fork** : en dernier recours si désaccord irréconciliable

---

## 🎓 Ressources pour contributeurs

### Lectures recommandées

- 📖 [Manifeste complet](docs/manifest.md)
- 🧠 [Richards Heuer - Psychology of Intelligence Analysis](https://www.cia.gov/resources/csi/books-monographs/psychology-of-intelligence-analysis/)
- 🔬 [Karl Popper - La logique de la découverte scientifique](https://fr.wikipedia.org/wiki/La_Logique_de_la_d%C3%A9couverte_scientifique)
- ⚖️ [RGPD - Texte officiel](https://eur-lex.europa.eu/eli/reg/2016/679/oj)

### Outils utiles

- **Markdown** : [Guide complet](https://www.markdownguide.org/)
- **Git** : [Pro Git Book (gratuit)](https://git-scm.com/book/fr/v2)
- **Diagrammes** : [Mermaid.js](https://mermaid.js.org/)
- **Validation JSON** : [JSONLint](https://jsonlint.com/)

---

## 💬 Questions ?

- 💡 **Discussions générales** : [GitHub Discussions](https://github.com/[username]/OMF/discussions)
- 🐛 **Problèmes techniques** : [GitHub Issues](https://github.com/thepinguin073/OMF/issues)
- 📧 **Contact direct** : your.digital.trace@gmail.com

---

## 🙏 Remerciements

Merci à tous les contributeurs qui font vivre ce projet ! Votre expertise et votre temps sont précieux.

Chaque contribution, aussi petite soit-elle, participe à la professionnalisation de l'OSINT.

---

**L'avenir de l'OSINT s'écrit collectivement, méthodiquement.**

[📖 Retour au README](README.md) • [📜 Code de Conduite](CODE_OF_CONDUCT.md)