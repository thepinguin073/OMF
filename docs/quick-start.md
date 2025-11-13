# Guide de Démarrage Rapide

Bienvenue dans le Framework Méthodologique OSINT ! Ce guide vous permettra de démarrer votre première investigation en moins de 30 minutes.

---

## 📋 Table des matières

- [Prérequis](#prérequis)
- [Votre première investigation en 5 étapes](#votre-première-investigation-en-5-étapes)
- [Choisir votre niveau de rigueur](#choisir-votre-niveau-de-rigueur)
- [Exemple concret pas à pas](#exemple-concret-pas-à-pas)
- [Outils essentiels](#outils-essentiels)
- [Ressources pour aller plus loin](#ressources-pour-aller-plus-loin)

---

## 🎯 Prérequis

### Connaissances minimales

- ✅ Compréhension basique de l'OSINT (collecte d'informations publiques)
- ✅ Utilisation d'Internet et des moteurs de recherche
- ✅ Notions de vie privée et de légalité (RGPD)

### Outils de base

- ✅ Navigateur web (Firefox ou Chrome recommandé)
- ✅ VPN pour l'OPSEC (ProtonVPN, Mullvad, etc.)
- ✅ Éditeur de texte (VS Code, Notepad++, ou simple bloc-notes)
- ✅ Outil de capture d'écran (intégré au système ou ShareX)

### Temps nécessaire

- ⏱️ **Quick Investigation** : 15-30 minutes
- ⏱️ **Standard Professional** : 2-4 heures
- ⏱️ **Full Rigor** : 1-3 jours

---

## 🚀 Votre première investigation en 5 étapes

### Étape 1️⃣ : PLANIFICATION (5 min)

**Définissez clairement votre objectif.**

Utilisez la technique du **Starbursting** (les 6 questions fondamentales) :

```
┌─────────────────────────────────────┐
│  QUI ? → Qui est la cible ?         │
│  QUOI ? → Quelle info cherchez-vous ?│
│  OÙ ? → Sur quelles plateformes ?   │
│  QUAND ? → Période temporelle ?     │
│  POURQUOI ? → Objectif final ?      │
│  COMMENT ? → Méthodes autorisées ?  │
└─────────────────────────────────────┘
```

**✏️ Notez vos réponses** dans un fichier texte simple :

```markdown
## Investigation : [Titre court]
Date : 2025-11-12
Niveau : Quick Investigation

### Priority Intelligence Requirements (PIR)
1. Quelle est l'identité réelle derrière le pseudo @exemple ?
2. Quels sont les liens avec l'organisation X ?

### Périmètre
- Plateformes : Twitter, LinkedIn, sites publics
- Période : 2020-2025
- Limitations : Pas de contact direct, respect RGPD

### Contraintes OPSEC
- Navigation via VPN
- Pas de connexion avec comptes personnels
```

### Étape 2️⃣ : COLLECTE (10 min)

**Rassemblez les données de manière méthodique.**

#### Checklist de collecte :

✅ **Identifier les sources primaires**
- Profils réseaux sociaux officiels
- Sites web personnels
- Articles de presse mentionnant la cible

✅ **Documenter chaque source**
```markdown
### Source 1
- URL : https://twitter.com/exemple
- Date de capture : 2025-11-12 14:30 UTC
- Hash SHA-256 : [générer avec outil]
- Capture d'écran : source1_twitter.png
- Évaluation : Source primaire, fiable
```

✅ **Capturer les preuves**
- Screenshot complet (incluant URL et date)
- Sauvegarder la page HTML (`Ctrl+S`)
- Copier-coller du texte important
- Noter les métadonnées visibles

⚠️ **Évitez :**
- Les screenshots partiels sans contexte
- Les captures sans horodatage
- Les informations non vérifiées

### Étape 3️⃣ : CORRÉLATION (5 min)

**Reliez les informations entre elles.**

Créez un mini-graphe relationnel (même sur papier) :

```
    [Cible : @exemple]
         │
    ┌────┼────┬─────────┐
    │    │    │         │
[Twitter] [LinkedIn] [Site web] [Article blog]
    │         │         │
    └─────────┴─────────┴──> Mêmes dates
                             Mêmes thématiques
                             Email identique ?
```

**Questions clés :**
- Retrouvez-vous le même username ailleurs ?
- Y a-t-il des dates qui se recoupent ?
- Les informations biographiques concordent-elles ?
- Détectez-vous des incohérences ?

### Étape 4️⃣ : ANALYSE (5 min)

**Montez progressivement l'échelle analytique.**

Utilisez l'**Analysis Ladder** simplifié :

```
Niveau 5 : CONCLUSION
↑         "L'identité est probablement X car..."
│         Niveau de confiance : MOYEN (60-70%)
│
Niveau 4 : PATTERN
↑         "Tous les comptes utilisent le même email pattern"
│
Niveau 3 : CONTEXTE
↑         "Le compte Twitter mentionne travailler chez Y"
│
Niveau 2 : IDENTIFIANTS
↑         "Username @exemple trouvé sur 3 plateformes"
│
Niveau 1 : DONNÉES BRUTES
          "Tweet du 12/11/2025 : '...'"
```

**✋ ATTENTION aux biais cognitifs :**
- ❌ Biais de confirmation : cherchez activement ce qui contredit votre hypothèse
- ❌ Saut inférentiel : ne passez pas directement du niveau 1 au niveau 5
- ✅ Formulez au moins **2 hypothèses alternatives** :
  - Hypothèse A : La cible est X
  - Hypothèse B : La cible est Y (sosie numérique)
  - Hypothèse C : Compte abandonné/usurpé

### Étape 5️⃣ : REPORTING (5 min)

**Documentez vos conclusions de manière claire.**

**Template minimal :**

```markdown
# Rapport d'Investigation : [Titre]

## 📊 Synthèse Executive
[2-3 phrases résumant les conclusions principales]

## 🎯 Objectif de l'investigation
[Reprise des PIR]

## 🔍 Méthodologie
- Niveau : Quick Investigation
- Sources consultées : 5 (3 primaires, 2 secondaires)
- Techniques : Recherche username, analyse de graphe social
- Durée : 30 minutes

## ✅ Conclusions

**Conclusion principale**
[Votre conclusion avec niveau de confiance]
- Niveau de confiance : MOYEN (60-70%)
- Justification : [Arguments principaux]

**Hypothèses alternatives écartées**
1. Hypothèse B : écartée car [raison]
2. Hypothèse C : peu probable car [raison]

## ⚠️ Limitations
- Pas d'accès aux sources privées (groupes fermés)
- Période limitée (uniquement 2020-2025)
- Pas de validation par sources indépendantes

## 📎 Annexes
- Capture 1 : [description]
- Capture 2 : [description]
```

---

## 📊 Choisir votre niveau de rigueur

Le framework propose **3 niveaux d'application** selon vos besoins :

### 🟢 Niveau 1 : Quick Investigation (80% des cas)

**Quand l'utiliser ?**
- Vérification factuelle rapide
- Première exploration d'une cible
- Enjeux faibles
- Usage personnel

**Ce qui est requis :**
- ✅ Définir un objectif clair
- ✅ Noter les sources principales
- ✅ Documenter la conclusion
- ⏭️ Pas de validation externe nécessaire

**Checklist** : [`checklists/quick-investigation.md`](../checklists/quick-investigation.md)

### 🟡 Niveau 2 : Standard Professional (15% des cas)

**Quand l'utiliser ?**
- Investigation professionnelle
- Rapport pour un client/supérieur
- Enjeux moyens (réputation, argent)
- Usage journalistique ou académique

**Ce qui est requis :**
- ✅ Tout ce qui précède +
- ✅ Validation croisée des sources
- ✅ Application de l'ACH (Analysis of Competing Hypotheses)
- ✅ Documentation probatoire (hashes, captures horodatées)
- ✅ Rapport structuré avec méthodologie

**Checklist** : [`checklists/standard-professional.md`](../checklists/standard-professional.md)

### 🔴 Niveau 3 : Full Rigor (5% des cas)

**Quand l'utiliser ?**
- Usage judiciaire ou légal
- Enjeux majeurs (sécurité, vie privée)
- Investigation sensible
- Publication académique peer-reviewed

**Ce qui est requis :**
- ✅ Tout ce qui précède +
- ✅ Validation par pairs (au moins 2 personnes)
- ✅ Chaîne de custody complète
- ✅ Analyse forensique si nécessaire
- ✅ Revue juridique et éthique
- ✅ Documentation exhaustive (reproductibilité totale)

**Checklist** : [`checklists/full-rigor.md`](../checklists/full-rigor.md)

---

## 💡 Exemple concret pas à pas

### Scénario : Vérifier l'authenticité d'un compte Twitter

**Contexte :** Un compte Twitter @expert_tech prétend être un expert en cybersécurité. Vous devez vérifier cette affirmation.

#### Phase 1 : Planification (5 min)

```markdown
## PIR
1. Le compte @expert_tech est-il géré par un véritable expert ?
2. Y a-t-il des red flags d'usurpation/bot ?

## Périmètre
- Twitter uniquement (première phase)
- Recherches publiques sans engagement
- Pas de reverse image search si photos personnelles

## OPSEC
- VPN activé
- Navigation privée
- Pas de like/retweet
```

#### Phase 2 : Collecte (10 min)

**Actions effectuées :**

1. **Profil Twitter**
   - Date de création : Mars 2018 ✅ (compte ancien = +crédibilité)
   - Nombre de followers : 3,200
   - Nombre de tweets : 1,847
   - Bio : "Cybersecurity expert | Speaker | CISSP"
   - Capture : `twitter_profile_20251112.png`
   - Hash : `e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855`

2. **Contenu des tweets**
   - Tweets techniques cohérents ✅
   - Quelques retweets de sources reconnues ✅
   - Pas de spam/automatisation apparente ✅

3. **Recherches complémentaires**
   - Google : "expert_tech cybersecurity" → aucun résultat ⚠️
   - LinkedIn : pas de profil trouvé avec ce pseudo ⚠️
   - Conférences : aucune mention publique ⚠️

#### Phase 3 : Corrélation (5 min)

**Observations :**

```
RED FLAGS détectés :
❌ Aucune présence digitale hors Twitter
❌ Bio mentionne "Speaker" mais aucune trace de conférence
❌ CISSP mentionné mais pas de validation possible
✅ Contenu technique semble cohérent
✅ Engagement organique (pas de bot pattern)
```

#### Phase 4 : Analyse (5 min)

**Application de l'Analysis Ladder :**

- **Niveau 1** : Compte Twitter existe, bio professionnelle
- **Niveau 2** : Username unique, pas de sosies évidents
- **Niveau 3** : Aucune validation externe trouvée
- **Niveau 4** : Pattern "expert solitaire" (seul sur Twitter)
- **Niveau 5** : **Conclusion** → Probablement pas un expert reconnu

**Hypothèses concurrentes :**

1. **Hypothèse A (privilégiée)** : Professionnel réel mais peu visible publiquement
   - Pour : Contenu cohérent, pas de spam
   - Contre : Aucune trace externe, bio non vérifiable
   - Probabilité : 40%

2. **Hypothèse B** : Enthousiate/amateur se présentant comme expert
   - Pour : Absence totale de validation externe
   - Contre : Qualité du contenu technique
   - Probabilité : 50%

3. **Hypothèse C** : Bot/compte automatisé
   - Pour : /
   - Contre : Engagement humain visible, pas de pattern automatique
   - Probabilité : 10%

**Niveau de confiance final : FAIBLE à MOYEN (40-50%)**

#### Phase 5 : Reporting (5 min)

```markdown
# Rapport : Vérification compte @expert_tech

## Conclusion
Le compte @expert_tech **ne peut pas être confirmé** comme expert reconnu 
en cybersécurité. Absence de validation externe (LinkedIn, conférences, 
publications). Le contenu semble cohérent mais pourrait être celui d'un 
amateur compétent plutôt qu'un professionnel établi.

**Niveau de confiance : FAIBLE (40%)**

## Recommandations
- Ne pas citer comme source experte sans validation additionnelle
- Enquête complémentaire recommandée si usage critique
- Possibilité de contact direct pour vérification (hors scope actuel)

## Limitations
- Investigation limitée à 30 minutes
- Pas d'accès aux contenus privés
- Pas de vérification certification CISSP
```

---

## 🛠️ Outils essentiels

### Pour débuter (gratuits)

| Outil | Usage | Lien |
|-------|-------|------|
| **Google Dorking** | Recherches avancées | [Guide](https://www.google.com/advanced_search) |
| **Wayback Machine** | Archives web historiques | [archive.org](https://archive.org) |
| **TinEye / Google Images** | Recherche inversée d'images | [tineye.com](https://tineye.com) |
| **Have I Been Pwned** | Vérification email/breach | [haveibeenpwned.com](https://haveibeenpwned.com) |
| **WhoisXML** | Informations domaines | [whois.com](https://whois.com) |

### Pour le niveau intermédiaire

| Outil | Usage | Prix |
|-------|-------|------|
| **Maltego** | Graphes relationnels | Gratuit (limité) |
| **SpiderFoot** | Automation OSINT | Gratuit (open source) |
| **Shodan** | Recherche d'appareils IoT | Gratuit (limité) |
| **IntelligenceX** | Moteur de recherche OSINT | Gratuit (limité) |

### Pour l'OPSEC

- 🔒 **VPN** : ProtonVPN (gratuit), Mullvad
- 🌐 **Navigateur** : Tor Browser (anonymat maximal)
- 📱 **Numéro virtuel** : Burner, MySudo
- 🖥️ **VM** : VirtualBox + Tails OS

**Liste complète** : [`resources/tools-list.md`](../resources/tools-list.md)

---

## 📚 Ressources pour aller plus loin

### Documentation du framework

1. **[Manifeste complet](manifest.md)** → Comprendre la philosophie (30 min) ⭐
2. **[Méthodologie détaillée](methodology/)** → Approfondir les 5 phases (2h)
3. **[Frameworks analytiques](frameworks/)** → ACH, Analysis Ladder (1h)
4. **[Études de cas](case-studies/)** → Apprendre par l'exemple (variable)

### Lectures externes recommandées

📖 **Débutants :**
- [OSINT Framework](https://osintframework.com/) - Carte interactive des outils
- [Bellingcat's Online Investigation Toolkit](https://bit.ly/bcattools)

📖 **Intermédiaires :**
- *Open Source Intelligence Techniques* par Michael Bazzell
- [Awesome OSINT (GitHub)](https://github.com/jivoi/awesome-osint)

📖 **Avancés :**
- *Psychology of Intelligence Analysis* par Richards Heuer (CIA)
- [MITRE ATT&CK](https://attack.mitre.org/) - Inspiration méthodologique

### Formation continue

- 🎓 [Bellingcat's Investigation Workshops](https://www.bellingcat.com/workshops/)
- 🎓 [SANS SEC487: Open-Source Intelligence Gathering](https://www.sans.org/cyber-security-courses/open-source-intelligence-gathering/)
- 🎓 [Trace Labs - OSINT CTF](https://www.tracelabs.org/)

---

## ❓ Besoin d'aide ?

### Problèmes fréquents

**Q : Je ne trouve rien sur ma cible, est-ce normal ?**  
R : Oui ! Absence d'information = information. Documentez cette absence et ajustez vos PIR.

**Q : Mes deux hypothèses sont équiprobables, que faire ?**  
R : C'est acceptable. Indiquez "INCERTAIN" dans votre rapport avec les deux scénarios. Ne forcez pas une conclusion.

**Q : Est-ce légal de faire ça ?**  
R : Si vous utilisez uniquement des sources publiques sans contourner de protections, généralement oui. Mais consultez [`docs/legal-ethical/gdpr-compliance.md`](legal-ethical/gdpr-compliance.md) pour votre juridiction.

**Q : Combien de temps dois-je passer ?**  
R : Pour une Quick Investigation : 15-30 min max. Si vous n'avez rien trouvé, documentez l'échec et arrêtez. Ne tombez pas dans le "rabbit hole" sans fin.

### Support communautaire

- 💬 [GitHub Discussions](https://github.com/OMF/discussions)
- 🐛 [Signaler un problème](https://github.com/OMF/issues)
- 📧 Contact : your.digital.trace@gmail.com

---

## ✅ Checklist avant de commencer

Avant votre première investigation, vérifiez :

- [ ] J'ai lu ce guide en entier (15 min)
- [ ] J'ai défini un objectif clair (PIR)
- [ ] J'ai choisi mon niveau de rigueur (Quick/Standard/Full)
- [ ] J'ai activé mon VPN/OPSEC
- [ ] J'ai préparé mes outils de capture (screenshots)
- [ ] J'ai un document pour prendre des notes
- [ ] Je connais mes limites légales (RGPD, vie privée)
- [ ] J'ai fixé une limite de temps (30 min pour Quick)

---

**Prêt à démarrer votre première investigation ?**

[📖 Voir les templates](../templates/) • [✅ Checklists détaillées](../checklists/) • [🎓 Exemples](../examples/)

---

*"Une investigation méthodique vaut mieux qu'une intuition brillante."*
