# Technique du Starbursting en OSINT

Le **Starbursting** est une technique de planification qui privilégie la génération systématique de questions plutôt que la production immédiate de réponses. En OSINT, elle constitue la colonne vertébrale de la phase de planification, empêchant les investigations erratiques et les angles morts analytiques.

---

## 📋 Table des matières

- [Principe fondamental](#principe-fondamental)
- [Pourquoi l'utiliser en OSINT ?](#pourquoi-lutiliser-en-osint-)
- [Comment l'appliquer ?](#comment-lappliquer-)
- [Exemple appliqué à l'OSINT](#exemple-appliqué-à-losint)
- [Pièges à éviter](#pièges-à-éviter)
- [Combinaison avec d'autres frameworks](#combinaison-avec-dautres-frameworks)

---

## 🎯 Principe fondamental

> **"Mieux vaut poser les bonnes questions que de chercher les mauvaises réponses."**

Le Starbursting inverse le processus cognitif habituel :
- ❌ **Approche classique** : Collecter → Analyser → Se poser des questions (trop tard)
- ✅ **Starbursting** : Se poser toutes les questions → Collecter méthodiquement → Analyser

### L'étoile à 6 branches

```
                    QUAND ?
                       │
                       │
        QUI ? ─────────┼───────── OÙ ?
                  \    │    /
                   \   │   /
                    \  │  /
                     \ │ /
                   [SUJET]
                     / │ \
                    /  │  \
                   /   │   \
                  /    │    \
      COMMENT ? ───────┼───────── QUOI ?
                       │
                       │
                   POURQUOI ?
```

---

## 💡 Pourquoi l'utiliser en OSINT ?

### 1. Prévenir le *framing bias*

Le framing bias, où 80% des défaillances analytiques trouvent leur origine, survient lorsqu'on définit mal le problème initial. Le Starbursting force une exploration exhaustive avant toute collecte.

**Exemple concret :**
Sans Starbursting, vous cherchez "qui est @JohnDoe ?"
Avec Starbursting, vous explorez :
- QUI : Personne physique ? Organisation ? Bot ? Collectif ?
- QUOI : Identité réelle ? Motivations ? Affiliations ?
- OÙ : Sur quelles plateformes chercher ?
- QUAND : Période d'activité ? Création du compte ?
- POURQUOI : Objectif de l'investigation ? Usage des résultats ?
- COMMENT : Méthodes autorisées ? Contraintes légales ?

### 2. Éviter les angles morts

En OSINT, les informations manquantes sont souvent dues à des questions non posées plutôt qu'à des réponses introuvables.

**Statistique clé :** Les questions les plus originales surgissent généralement seulement après avoir posé toutes les questions évidentes.

### 3. Structurer les Priority Intelligence Requirements (PIR)

Le Starbursting transforme une intention vague en PIR actionnables :

**Intention vague :** "Enquêter sur cette entreprise suspecte"

**PIR après Starbursting :**
1. QUI contrôle légalement l'entreprise ? (actionnaires, dirigeants)
2. QUOI fait réellement cette entreprise ? (activités vs. communication)
3. OÙ opère-t-elle ? (juridictions, implantations physiques)
4. QUAND a-t-elle été créée ? Changements de structure ?
5. POURQUOI cette structure juridique complexe ?
6. COMMENT finance-t-elle ses opérations ?

### 4. Anticiper les questions des décideurs

Si vous préparez un rapport OSINT pour un magistrat, un journaliste ou un RSSI, le Starbursting prédit les questions qu'ils poseront inévitablement.

---

## 🔧 Comment l'appliquer ?

### Étape 1 : Dessiner l'étoile (2 min)

**Support physique ou numérique :**
- Tableau blanc / paperboard (travail en équipe)
- Outil de mind mapping (XMind, Miro, Excalidraw)
- Simple document texte avec sections

**Au centre :** Formulez votre sujet en UNE phrase claire

**Exemple :**
```
        SUJET CENTRAL :
"Identifier l'opérateur réel
   du compte Twitter
      @mysterytech"
```

### Étape 2 : Générer les questions systématiquement (15-30 min)

**⚠️ RÈGLE CRITIQUE** : N'allez pas trop vite et évitez l'écueil courant de répondre aux questions au fur et à mesure qu'elles vous viennent à l'esprit.

#### 🔴 Branche "QUI ?" (Who)

*Questions sur les acteurs impliqués*

- Qui est la cible principale ?
- Qui sont les acteurs secondaires (associés, contacts fréquents) ?
- Qui a créé les comptes/contenus analysés ?
- Qui bénéficie de l'information recherchée ?
- Qui pourrait avoir des informations sur la cible ?
- Qui sont les témoins potentiels ?
- Qui a intérêt à cacher cette information ?

**En OSINT avancé :**
- Qui valide/contredit les informations trouvées ?
- Qui sont les sources primaires vs secondaires ?
- Qui a l'autorité légale sur ces données ?

#### 🟠 Branche "QUOI ?" (What)

*Questions sur la nature de l'investigation*

- Quoi exactement cherchons-nous ? (définition précise)
- Quelles informations sont nécessaires vs suffisantes ?
- Quelles données sont publiques vs privées ?
- Quelles preuves constitueraient une validation ?
- Quels sont les indicateurs de succès ?
- Quelles métadonnées sont exploitables ?
- Quelles connexions/relations cherchons-nous ?

**En OSINT avancé :**
- Quels biais cognitifs pourraient nous affecter ?
- Quelles hypothèses alternatives devons-nous tester ?
- Quels niveaux de confiance visons-nous ?

#### 🟡 Branche "OÙ ?" (Where)

*Questions sur la localisation des informations*

- Où chercher en priorité ? (plateformes, sources)
- Où les données sont-elles hébergées ? (juridiction)
- Où la cible est-elle active en ligne ?
- Où les informations sont-elles archivées ?
- Où trouver des sources primaires ?
- Où sont les angles morts probables ?
- Où les données peuvent-elles être croisées ?

**En OSINT géospatial :**
- Où la cible se situe-t-elle physiquement ?
- Où les images/vidéos ont-elles été prises ?
- Où chercher des métadonnées de localisation ?

#### 🟢 Branche "QUAND ?" (When)

*Questions sur la temporalité*

- Quand l'investigation doit-elle être terminée ? (deadline)
- Quand les événements étudiés ont-ils eu lieu ?
- Quand les comptes/contenus ont-ils été créés ?
- Quand les informations ont-elles été publiées/modifiées ?
- Quand vérifier les sources (évolution rapide) ?
- Quand planifier les phases de collecte ?
- Quand effectuer les validations croisées ?

**En OSINT temporel :**
- Quand les archives web ont-elles été capturées ?
- Quand les métadonnées EXIF indiquent-elles ?
- Quand les corrélations temporelles émergent-elles ?

#### 🔵 Branche "POURQUOI ?" (Why)

*Questions sur les objectifs et motivations*

- Pourquoi cette investigation est-elle nécessaire ?
- Pourquoi ces PIR spécifiques ont-ils été définis ?
- Pourquoi la cible agit-elle ainsi ?
- Pourquoi certaines informations sont-elles cachées ?
- Pourquoi ces sources sont-elles fiables/douteuses ?
- Pourquoi privilégier cette méthode vs une autre ?
- Pourquoi ce niveau de rigueur est-il requis ?

**En analyse comportementale :**
- Pourquoi ce pattern de comportement en ligne ?
- Pourquoi ces connexions/relations existent-elles ?
- Pourquoi ces incohérences dans les données ?

#### 🟣 Branche "COMMENT ?" (How)

*Questions sur les méthodes et moyens*

- Comment collecter les données ? (techniques, outils)
- Comment garantir la légalité de l'investigation ?
- Comment préserver l'OPSEC ?
- Comment valider l'authenticité des sources ?
- Comment documenter la chaîne probatoire ?
- Comment gérer les données sensibles (RGPD) ?
- Comment structurer le rapport final ?

**En OSINT technique :**
- Comment contourner les restrictions d'accès (légalement) ?
- Comment automatiser sans perdre la traçabilité ?
- Comment croiser les sources disparates ?

### Étape 3 : Catégoriser et hiérarchiser (10 min)

Une fois TOUTES les questions générées, organisez-les :

#### A. Par priorité

```
🔴 CRITIQUE (réponse obligatoire avant de continuer)
🟠 IMPORTANTE (réponse nécessaire pour conclusions solides)
🟢 SOUHAITABLE (améliorerait la qualité mais pas essentielle)
⚪ OPTIONNELLE (nice-to-have)
```

#### B. Par dépendances

Certaines questions ne peuvent être répondues qu'après d'autres :

```
QUOI cherchons-nous ?
    ↓
OÙ le chercher ?
    ↓
COMMENT y accéder ?
    ↓
QUAND effectuer la collecte ?
```

#### C. Par phase du cycle OSINT

```
📋 PLANIFICATION : Pourquoi ? Quoi ? (définition)
🔍 COLLECTE : Où ? Comment ? (acquisition)
🔗 CORRÉLATION : Qui ? Quand ? (relations)
🧠 ANALYSE : Pourquoi ? (causalité)
📊 REPORTING : Comment ? (communication)
```

### Étape 4 : Élaborer le plan d'action (15 min)

Pour chaque question priorisée :

**Type A - Réponse immédiate**
→ Répondez directement si trivial

**Type B - Recherche rapide**
→ Google, consultation expert, 5-15 min

**Type C - Investigation approfondie**
→ Devient un sous-objectif avec son propre mini-Starbursting

**Type D - Question sans réponse**
→ Documentez l'impossibilité et son impact sur les conclusions

---

## 📘 Exemple appliqué à l'OSINT

### Cas : Investigation sur une campagne de désinformation

**Sujet central :** *"Analyser l'origine et les opérateurs de la campagne de désinformation #FakeNewsX"*

#### Génération de questions (extrait)

**QUI ?**
- Qui a lancé le hashtag initial ?
- Qui sont les 10 comptes les plus actifs ?
- Qui sont les early adopters (premiers relais) ?
- Qui bénéficie de cette campagne ? (cui bono)
- Qui finance potentiellement cette opération ?
- Qui sont les cibles de la désinformation ?

**QUOI ?**
- Quelle est la narration centrale diffusée ?
- Quels éléments de contenu sont récurrents ?
- Quels médias (images, vidéos) sont utilisés ?
- Quelles techniques de manipulation sont employées ?
- Quels sont les indicateurs de coordination (bots, timing) ?

**OÙ ?**
- Où la campagne a-t-elle émergé (plateforme d'origine) ?
- Où se propage-t-elle (Twitter, Facebook, Telegram, forums) ?
- Où les comptes suspects sont-ils enregistrés (géolocalisation) ?
- Où les serveurs hébergeant les contenus sont-ils localisés ?

**QUAND ?**
- Quand la campagne a-t-elle débuté (date/heure précise) ?
- Quand les pics d'activité surviennent-ils (analyse temporelle) ?
- Quand les contenus ont-ils été créés (métadonnées) ?
- Quand planifier la collecte pour capturer l'activité maximale ?

**POURQUOI ?**
- Pourquoi cette narration spécifique (objectif stratégique) ?
- Pourquoi ce timing (contexte géopolitique, élections) ?
- Pourquoi ces plateformes ont-elles été choisies ?
- Pourquoi certains contenus sont supprimés puis republiés ?

**COMMENT ?**
- Comment identifier les comptes automatisés (bots) ?
- Comment tracer la propagation (analyse de réseau) ?
- Comment valider l'attribution (preuves forensiques) ?
- Comment documenter sans violer les CGU des plateformes ?
- Comment protéger l'OPSEC (éviter d'alerter les opérateurs) ?

#### Hiérarchisation

```
🔴 CRITIQUE
1. Qui a lancé le hashtag initial ? (point d'origine)
2. Quand la campagne a-t-elle débuté ? (temporalité)
3. Comment identifier les bots ? (fiabilité des données)

🟠 IMPORTANTES
4. Où les serveurs hébergeant les contenus sont localisés ? (attribution)
5. Quels sont les indicateurs de coordination ? (preuve d'opération)
6. Pourquoi ce timing ? (mobile)

🟢 SOUHAITABLES
7. Qui finance cette opération ? (complexe, temps long)
8. Comment tracer la propagation complète ? (volume élevé)
```

#### Plan d'action résultant

```markdown
## Phase 1 : Réponses immédiates (Jour 1)
- Q1 (QUI lancé) → Recherche Twitter API + archive.org
- Q2 (QUAND débuté) → Analyse timestamps premiers tweets
- Q3 (COMMENT identifier bots) → Utiliser Botometer + analyse pattern

## Phase 2 : Investigation approfondie (Jours 2-5)
- Q4 (OÙ serveurs) → WHOIS, traceroute, analyse DNS
- Q5 (QUELS indicateurs) → Graphe social Gephi, analyse co-tweets
- Q6 (POURQUOI timing) → Recherche contexte géopolitique

## Phase 3 : Optionnel (si temps/ressources)
- Q7 (QUI finance) → Nécessite sources HUMINT, hors scope OSINT
- Q8 (COMMENT propagation) → Volume trop élevé, échantillonnage uniquement
```

---

## ⚠️ Pièges à éviter

### 1. Répondre immédiatement aux questions

**❌ Erreur fréquente :**
```
QUI est derrière @compte_suspect ?
→ "C'est probablement un bot russe !"
```

**✅ Bonne pratique :**
Évitez l'écueil courant de répondre aux questions au fur et à mesure qu'elles vous viennent à l'esprit. Générez d'ABORD toutes les questions, répondez ENSUITE.

### 2. Se limiter aux questions évidentes

**❌ Questions superficielles :**
- Qui est cette personne ?
- Où habite-t-elle ?

**✅ Questions approfondies :**
- Qui valide/contredit les informations trouvées ?
- Où sont les angles morts de notre investigation ?
- Pourquoi certaines sources sont-elles absentes ?

**Rappel :** Les questions les plus originales surgissent généralement seulement après avoir posé toutes les questions évidentes.

### 3. Oublier les questions méthodologiques

Ne vous concentrez pas uniquement sur le SUJET, mais aussi sur le PROCESSUS :

- Comment garantir la reproductibilité ?
- Quand effectuer les validations croisées ?
- Pourquoi choisir ce niveau de rigueur ?

### 4. Ignorer les contraintes légales/éthiques

**Questions obligatoires :**
- Quoi est légal dans cette juridiction ?
- Comment respecter le RGPD ?
- Pourquoi cette méthode est-elle proportionnée ?
- Où s'arrête le périmètre légitime ?

### 5. Ne pas documenter les "questions sans réponse"

Certaines questions resteront sans réponse. C'est normal et informatif.

**Documentez-les :**
```markdown
## Questions non résolues
- QUI finance l'opération ? → Impossible à déterminer avec OSINT seule
  Impact : Limite la compréhension de l'attribution complète
```

---

## 🔗 Combinaison avec d'autres frameworks

### Starbursting → ACH (Analysis of Competing Hypotheses)

Le Starbursting génère les questions ; l'ACH structure les réponses concurrentes.

**Workflow :**
```
1. Starbursting → "Qui est derrière @compte_suspect ?"
2. Génération d'hypothèses concurrentes :
   - H1 : Bot automatisé russe
   - H2 : Militant individuel français
   - H3 : Campagne coordonnée multi-acteurs
3. ACH → Tester chaque hypothèse contre les preuves
```

### Starbursting → Analysis Ladder

Les questions du Starbursting guident la montée progressive de l'échelle analytique.

**Exemple :**
```
Niveau 1 (Raw Data) → Répondre aux QUOI/OÙ/QUAND factuels
Niveau 2 (Identifiers) → Répondre aux QUI basiques
Niveau 3 (Contextual) → Répondre aux POURQUOI contextuels
Niveau 4 (Patterns) → Répondre aux COMMENT comportementaux
Niveau 5 (Insights) → Synthétiser toutes les réponses
```

### Starbursting → OPSEC Planning

Les questions "COMMENT ?" alimentent directement les protocoles OPSEC.

**Exemple :**
```
COMMENT éviter d'alerter la cible ?
→ Protocole OPSEC :
  - VPN + navigation privée
  - Pas d'engagement direct
  - Collecte par scraping passif
```

---

## 📊 Métriques de succès

Une session Starbursting réussie génère :

- ✅ **20-50 questions** (selon complexité du sujet)
- ✅ **Au moins 3 questions par branche** (équilibre)
- ✅ **10-20% de questions "non évidentes"** (profondeur)
- ✅ **100% des questions priorisées** (hiérarchie claire)
- ✅ **Plan d'action pour chaque question critique** (actionnable)

---

## 📚 Ressources complémentaires

### Documentation du framework
- [Phase 1 : Planification complète](../methodology/01-planning.md)
- [Priority Intelligence Requirements (PIR)](../methodology/01-planning.md#pir)
- [Analysis of Competing Hypotheses (ACH)](ach.md)

### Lectures externes
- **NATO ALTA Handbook** - Source originale de la technique
- *Structured Analytic Techniques for Intelligence Analysis* (Heuer & Pherson, 2010)
- *Psychology of Intelligence Analysis* (Richards Heuer, 1999) - Chapitre sur le framing bias

---

## ✅ Checklist Starbursting

Avant de démarrer une investigation, vérifiez :

- [ ] J'ai formulé mon sujet central en UNE phrase claire
- [ ] J'ai dessiné l'étoile à 6 branches (physique ou numérique)
- [ ] J'ai généré au moins 3 questions par branche
- [ ] Je n'ai PAS répondu aux questions pendant la génération
- [ ] J'ai exploré au-delà des questions évidentes
- [ ] J'ai catégorisé les questions par priorité (🔴🟠🟢⚪)
- [ ] J'ai identifié les dépendances entre questions
- [ ] J'ai créé un plan d'action pour les questions critiques
- [ ] J'ai documenté les questions probablement sans réponse
- [ ] J'ai partagé avec l'équipe (si travail collaboratif)

---

## 🎓 Exercice pratique

**Sujet :** *"Vérifier la légitimité d'une collecte de fonds en ligne suspecte"*

**À vous de jouer :**
1. Prenez 15 minutes
2. Générez au moins 18 questions (3 par branche)
3. Hiérarchisez-les en 🔴🟠🟢
4. Créez un mini-plan d'action

**Correction suggestive disponible :** [examples/starbursting-exercise.md](../../examples/starbursting-exercise.md)

---

**"Une investigation méthodique commence par les bonnes questions."**

[📖 Retour Frameworks](../frameworks/) • [🎯 Phase Planification](../methodology/01-planning.md) • [🧠 ACH](ach.md)