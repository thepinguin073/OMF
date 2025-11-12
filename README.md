# Framework Méthodologique OSINT

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)]()
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)]()

> **Pour une OSINT scientifique, reproductible et responsable**

Framework méthodologique open-source visant à professionnaliser les pratiques d'Open Source Intelligence par une approche rigoureuse, traçable et éthique.

---

## 📋 Table des matières

- [À propos](#-à-propos)
- [Pourquoi ce framework ?](#-pourquoi-ce-framework-)
- [Principes fondateurs](#-principes-fondateurs)
- [Architecture](#-architecture)
- [Démarrage rapide](#-démarrage-rapide)
- [Documentation](#-documentation)
- [Contribuer](#-contribuer)
- [Licence](#-licence)

---

## 🎯 À propos

Le **Framework Méthodologique OSINT** est un référentiel structuré inspiré de MITRE ATT&CK, conçu pour transformer l'Open Source Intelligence d'une pratique artisanale en discipline scientifique mature.

### Destiné aux :
- 🔍 **Enquêteurs** : journalistes d'investigation, détectives privés
- 🛡️ **Analystes** : cybersécurité, threat intelligence, corporate security
- 🎓 **Chercheurs** : académiques, fact-checkers, analystes géopolitiques
- 👥 **Citoyens engagés** : militants, ONG, défenseurs des droits humains

---

## 💡 Pourquoi ce framework ?

L'OSINT traverse une crise de légitimité causée par quatre pathologies structurelles :

### ❌ Les problèmes actuels

1. **Absence de reproductibilité** : deux analystes compétents obtiennent des conclusions contradictoires
2. **Vulnérabilité aux biais cognitifs** : biais de confirmation, erreurs d'attribution, raccourcis heuristiques
3. **Opacité décisionnelle** : les décideurs ne peuvent évaluer la solidité des conclusions
4. **Zones grises juridiques** : exposition aux risques légaux (RGPD, vie privée, proportionnalité)

### ✅ Notre solution

Un framework qui impose :
- 🔬 **Rigueur épistémologique** : falsifiabilité, reproductibilité, traçabilité
- 🧠 **Débiaisage méthodique** : ACH, devil's advocate, pre-mortem analysis
- 📊 **Transparence probatoire** : documentation exhaustive, niveaux de confiance explicites
- ⚖️ **Conformité éthique** : respect RGPD, OPSEC, proportionnalité

---

## 🏛️ Principes fondateurs

### 1. Falsifiabilité (Karl Popper)
Toute conclusion doit pouvoir être **testée, challengée et potentiellement réfutée**. Une conclusion irréfutable n'est pas une connaissance, mais une croyance.

### 2. Reproductibilité scientifique
Un tiers qualifié doit pouvoir suivre le même protocole et obtenir des résultats substantiellement comparables.

### 3. Traçabilité probatoire (Principe de Locard)
Chaque étape de l'investigation est documentée comme une **chaîne de custody intellectuelle** : métadonnées, horodatages cryptographiques, hashes SHA-256.

### 4. Explicitation des incertitudes
Utilisation d'**échelles de confiance explicites** inspirées de l'ICD 203 (Intelligence Community Directive).

### 5. Proportionnalité méthodologique
Trois niveaux d'application différenciés :
- **Quick Investigation** (80% des cas) : documentation minimale
- **Standard Professional** (15% des cas) : rapport structuré
- **Full Rigor** (5% des cas) : documentation probatoire exhaustive

---

## 🔄 Architecture

Le framework repose sur un **cycle intégré en 5 phases** :

```
┌─────────────┐
│ PLANIFICATION│──> Priority Intelligence Requirements (PIR)
│             │    Hypothèses de travail, contraintes OPSEC
└──────┬──────┘
       │
       ▼
┌─────────────┐
│  COLLECTE   │──> Taxonomie des sources, validation authenticité
│             │    Conservation probatoire (SHA-256, horodatage)
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ CORRÉLATION │──> Analyse de graphes, détection co-occurrences
│             │    Clustering thématique, structuration STIX/TAXII
└──────┬──────┘
       │
       ▼
┌─────────────┐
│   ANALYSE   │──> Analysis Ladder (5 niveaux)
│             │    ACH, Devil's Advocate, Pre-mortem
└──────┬──────┘
       │
       ▼
┌─────────────┐
│  REPORTING  │──> Synthèse exécutive, méthodologie transparente
│             │    Niveaux de confiance, hypothèses écartées
└─────────────┘
```

---

## 🚀 Démarrage rapide

### Installation

```bash
# Cloner le repository
git clone https://github.com/thepinguin073/osint-methodology-framework.git

# Accéder au dossier
cd osint-methodology-framework
```

### Première investigation

1. **Consultez le manifeste** : [`docs/manifest.md`](docs/manifest.md)
2. **Choisissez votre niveau** : 
   - Quick : [`checklists/quick-investigation.md`](checklists/quick-investigation.md)
   - Standard : [`checklists/standard-professional.md`](checklists/standard-professional.md)
   - Full Rigor : [`checklists/full-rigor.md`](checklists/full-rigor.md)
3. **Utilisez les templates** : [`templates/`](templates/)
4. **Consultez les exemples** : [`examples/`](examples/)

### Exemple d'utilisation

```markdown
# Investigation : Identification d'un compte Twitter suspect

## Phase 1 : Planification
- PIR : Identifier l'opérateur réel derrière @compte_suspect
- Périmètre : Analyse réseaux sociaux uniquement (pas de techniques invasives)
- Contraintes : Respect RGPD, pas de contact direct
- OPSEC : Navigation via VPN, pas de connexion comptes persos

## Phase 2 : Collecte
- Capture profil Twitter (SHA-256: abc123...)
- Horodatage: 2025-11-12T14:30:00Z
- Sources secondaires : mentions, retweets, abonnés
[...]
```

---

## 📚 Documentation

### Documentation complète

- 📖 **[Manifeste complet](docs/manifest.md)** : fondements épistémologiques
- 🗺️ **[Méthodologie détaillée](docs/methodology/)** : 5 phases expliquées
- 🧰 **[Frameworks analytiques](docs/frameworks/)** : ACH, Analysis Ladder, Starbursting
- ⚖️ **[Aspects légaux et éthiques](docs/legal-ethical/)** : RGPD, OPSEC, proportionnalité
- 📊 **[Études de cas](docs/case-studies/)** : exemples réels anonymisés

### Matrice des techniques

La **[matrice interactive](matrix/matrix-navigator.html)** cartographie :
- **Tactiques** : objectifs stratégiques de chaque phase
- **Techniques** : méthodes opératoires standardisées
- **Sous-techniques** : variantes et implémentations spécifiques

---

## 🤝 Contribuer

Ce framework est un **organisme méthodologique vivant** qui évolue par contributions communautaires.

### Comment contribuer ?

1. 📖 Lisez le **[Guide de contribution](CONTRIBUTING.md)**
2. 🔍 Consultez les **[Issues ouvertes](https://github.com/thepinguin073/osint-framework/issues)**
3. 💡 Proposez de nouvelles techniques via **Pull Request**
4. ✅ Participez au **peer review** des contributions

### Critères d'admission pour nouvelles techniques

- ✓ Période probatoire de **6 mois** en conditions réelles
- ✓ Validation par **au moins 2 entités indépendantes**
- ✓ Conformité épistémologique (falsifiabilité, traçabilité)
- ✓ Documentation exhaustive (description, cas d'usage, limitations, OPSEC)

---

## 🌍 Communauté

- 💬 **Discussions** : [GitHub Discussions](https://github.com/thepinguin073/OMF/discussions)
- 🌐 **Site Web** : [Site Web](https://cryptex.github.io/)
- 📧 **Contact** : your.digital.trace@gmail.com

---

## 📄 Licence

Ce projet est sous licence **Creative Commons Attribution-ShareAlike 4.0 International** (CC BY-SA 4.0).

Vous êtes libre de :
- ✓ Partager : copier, distribuer et communiquer le matériel
- ✓ Adapter : remixer, transformer et créer à partir du matériel

**Conditions** :
- Attribution : créditer l'œuvre originale
- ShareAlike : diffuser les modifications sous la même licence

[Lire la licence complète](LICENSE)

---

## 🎓 Citer ce framework

```bibtex
@misc{osint_framework_2025,
  author = {thepinguin073},
  title = {Framework Méthodologique OSINT : Pour une intelligence ouverte scientifique},
  year = {2025},
  month = {11},
  url = {https://github.com/[username]/osint-methodology-framework},
  note = {License: CC BY-SA 4.0}
}
```

---

## 🙏 Remerciements

Ce framework s'inspire des travaux de :
- **Richards Heuer** (Analysis of Competing Hypotheses)
- **Karl Popper** (Épistémologie de la falsifiabilité)
- **MITRE Corporation** (Framework ATT&CK)
- **Edmond Locard** (Principe d'échange en criminalistique)
- **Daniel Kahneman & Amos Tversky** (Biais cognitifs et heuristiques)

---

## 📊 Roadmap

- [x] Publication du manifeste fondateur
- [x] Structure du repository
- [ ] Matrice interactive (Phase 1 : Planification)
- [ ] Templates opérationnels (v1.0)
- [ ] 3 études de cas documentées
- [ ] Intégrations outils (Maltego, SpiderFoot)
- [ ] Validation par 10 entités indépendantes
- [ ] Publication académique (peer-reviewed)

---

**L'avenir de l'OSINT s'écrit maintenant, collectivement, méthodiquement.**

[📖 Lire le Manifeste](docs/manifest.md) • [🚀 Démarrer](docs/quick-start.md) • [🤝 Contribuer](CONTRIBUTING.md)
