# Analysis of Competing Hypotheses (ACH)

> **"L'analyste ne doit pas chercher à confirmer son hypothèse, mais à la réfuter activement."**  
> — Richards J. Heuer Jr., *Psychology of Intelligence Analysis* (1999)

L'**Analysis of Competing Hypotheses** (ACH) est une méthodologie développée par Richards J. Heuer Jr. pour la CIA dans les années 1970. Elle vise à surmonter les biais cognitifs en forçant l'analyste à tester simultanément **toutes les hypothèses concurrentes** plutôt que de chercher à confirmer une seule hypothèse privilégiée.

---

## 📋 Table des matières

- [Principe fondamental](#principe-fondamental)
- [Pourquoi l'ACH en OSINT ?](#pourquoi-lach-en-osint-)
- [Les 8 étapes de l'ACH](#les-8-étapes-de-lach)
- [Construction de la matrice ACH](#construction-de-la-matrice-ach)
- [Exemple complet](#exemple-complet)
- [Interprétation des résultats](#interprétation-des-résultats)
- [Forces et limites](#forces-et-limites)
- [Variantes et extensions](#variantes-et-extensions)
- [Outils et templates](#outils-et-templates)

---

## 🎯 Principe fondamental

### Le problème du biais de confirmation

L'esprit humain est naturellement biaisé : lorsqu'un analyste privilégie une hypothèse, il cherche inconsciemment des preuves qui la **confirment** tout en ignorant ou minimisant celles qui la **contredisent**.

**Exemple classique :**
```
Hypothèse initiale : "Ce compte Twitter est un bot russe"

❌ Approche biaisée :
→ Cherche des indices de langue russe → Trouvé !
→ Cherche des patterns automatisés → Trouvé !
→ Conclusion : "C'est bien un bot russe" (confiance excessive)

✅ Approche ACH :
→ Teste simultanément 4 hypothèses :
   H1 : Bot russe
   H2 : Bot chinois
   H3 : Compte automatisé légitime (entreprise)
   H4 : Humain réel utilisant des outils de planification
→ Compare chaque preuve contre TOUTES les hypothèses
→ Conclusion nuancée avec degré de confiance calibré
```

### Inversion méthodologique

L'ACH inverse le processus analytique habituel :

| Approche traditionnelle | ACH |
|------------------------|-----|
| 1. Choisir une hypothèse probable | 1. Lister **toutes** les hypothèses possibles |
| 2. Chercher des preuves qui la confirment | 2. Lister **toutes** les preuves disponibles |
| 3. Ignorer/minimiser les preuves contradictoires | 3. Tester chaque preuve contre **chaque** hypothèse |
| 4. Conclure avec sur-confiance | 4. Éliminer les hypothèses les plus inconsistantes |
| 5. Risque élevé d'erreur analytique | 5. Retenir l'hypothèse la moins réfutable |

**Principe cardinal :** L'ACH ne cherche pas à prouver quelle hypothèse est vraie, mais à **éliminer celles qui sont fausses**.

---

## 💡 Pourquoi l'ACH en OSINT ?

### 1. Neutralisation des biais cognitifs

L'ACH vise à aider l'analyste à surmonter, ou au moins minimiser, certaines limitations cognitives qui rendent difficile l'analyse de renseignement perspicace.

**Biais neutralisés :**
- **Biais de confirmation** : chercher uniquement ce qui confirme
- **Ancrage** : première hypothèse disproportionnellement influente
- **Disponibilité** : surestimation des informations facilement accessibles
- **Cohérence narrative** : privilégier les histoires "qui font sens"

### 2. Traçabilité et reproductibilité

La matrice ACH permet de retracer les preuves et hypothèses (backtracking). Cela permet au décideur ou à d'autres analystes de voir la séquence de règles et de données qui ont conduit à la conclusion.

**Avantages opérationnels :**
- ✅ Audit externe possible
- ✅ Validation par les pairs facilitée
- ✅ Documentation probatoire solide
- ✅ Reproductibilité scientifique

### 3. Gestion de l'incertitude

En OSINT, les données sont souvent :
- Incomplètes (lacunes informationnelles)
- Contradictoires (sources conflictuelles)
- Ambiguës (interprétations multiples)
- Manipulées (désinformation intentionnelle)

L'ACH fournit un **cadre structuré pour naviguer dans cette incertitude** sans tomber dans la paralysie analytique.

### 4. Communication avec les décideurs

La matrice ACH produit un livrable visuel et compréhensible qui :
- Montre **toutes** les hypothèses considérées (pas seulement celle retenue)
- Explicite **pourquoi** certaines ont été écartées
- Calibre le **niveau de confiance** de manière transparente
- Identifie les **preuves diagnostiques** les plus critiques

---

## 🔧 Les 8 étapes de l'ACH

### Étape 1 : Identifier les hypothèses

La première étape du processus consiste à identifier toutes les hypothèses potentielles, de préférence en utilisant un groupe d'analystes avec différentes perspectives pour réfléchir aux possibilités.

#### Règles de génération

**✅ Bonnes pratiques :**
- Générer 3 à 7 hypothèses (plus = dilution, moins = biais)
- Utiliser le **brainstorming collectif** (diversité de perspectives)
- Inclure des hypothèses "improbables mais pas impossibles"
- Formuler des hypothèses **mutuellement exclusives** (non redondantes)

**❌ Pièges à éviter :**
- Se limiter à 2 hypothèses (fausse dichotomie)
- Inclure des hypothèses vagues ("c'est compliqué")
- Formuler des hypothèses non testables ("c'est la volonté divine")

#### Techniques de génération

**1. Starbursting inversé**
```
POURQUOI ce comportement ?
→ H1 : Motivation financière
→ H2 : Motivation idéologique
→ H3 : Motivation personnelle/vengeance
→ H4 : Absence de motivation (hasard)
```

**2. Spectre d'intensité**
```
Pour un compte suspect :
→ H1 : Innocent (aucune malveillance)
→ H2 : Naïf manipulé (complice involontaire)
→ H3 : Acteur organisé (coordination active)
→ H4 : Opération étatique (ressources importantes)
```

**3. Sources alternatives**
```
QUI est derrière cette campagne ?
→ H1 : État-nation (Russie)
→ H2 : État-nation (Chine)
→ H3 : Groupe hacktiviste non-étatique
→ H4 : Entreprise privée (mercenaires)
→ H5 : Individu isolé (hacker solitaire)
```

#### Template de formulation

```markdown
## Hypothèses générées

**H1 - [Titre court]**
Description : [1-2 phrases explicatives]
Plausibilité initiale : [Élevée/Moyenne/Faible]

**H2 - [Titre court]**
Description : [1-2 phrases explicatives]
Plausibilité initiale : [Élevée/Moyenne/Faible]

[...]

**Total hypothèses : 5**
**Mutuellement exclusives : OUI**
**Source : Brainstorming équipe + Starbursting**
```

---

### Étape 2 : Lister les preuves

L'analyste liste ensuite les preuves et arguments (y compris les hypothèses et déductions logiques) pour et contre chaque hypothèse.

#### Types de preuves

**1. Preuves factuelles directes**
- Observations vérifiables
- Métadonnées extraites
- Documents authentifiés
- Témoignages corroborés

**2. Preuves circonstancielles**
- Corrélations temporelles
- Proximité géographique
- Patterns comportementaux
- Indices indirects

**3. Déductions logiques**
- Inférences basées sur des faits établis
- Implications nécessaires d'une situation
- Exclusions par contradiction

**4. Absences significatives**
- Informations attendues mais manquantes
- Comportements normaux non observés
- Preuves que l'on devrait trouver

#### Évaluation de la qualité des preuves

Chaque preuve doit être évaluée selon deux dimensions :

**Fiabilité de la source** (Admiralty Code) :
- A : Complètement fiable
- B : Généralement fiable
- C : Assez fiable
- D : Généralement peu fiable
- E : Peu fiable
- F : Fiabilité inconnue

**Crédibilité de l'information** :
- 1 : Confirmée par d'autres sources
- 2 : Probablement vraie
- 3 : Possiblement vraie
- 4 : Douteuse
- 5 : Improbable
- 6 : Véracité inconnue

**Exemple :**
```
Preuve #1 : Tweet mentionnant "Moscou"
- Source : A1 (Twitter vérifié, multi-sources confirmant)
- Diagnosticité : Faible (mention ne prouve pas la localisation)

Preuve #2 : Métadonnées EXIF montrant Moscou
- Source : B1 (Métadonnées techniques, validées)
- Diagnosticité : Élevée (preuve technique objective)
```

#### Template de collecte

```markdown
## Preuves collectées

**P1 - [Description courte]**
- Type : Factuelle directe / Circonstancielle / Déduction logique
- Source : [Origine + URL]
- Fiabilité : [A-F][1-6]
- Date de collecte : [YYYY-MM-DD]
- Hash : [SHA-256 si applicable]

**P2 - [Description courte]**
[...]

**Total preuves : 12**
**Preuves de haute qualité (A1, A2, B1) : 7**
**Preuves douteuses (D4, E5) : 2**
```

---

### Étape 3 : Construction de la matrice (Diagnosticité)

En utilisant une matrice, l'analyste applique les preuves contre chaque hypothèse dans une tentative de réfuter autant de théories que possible. Certaines preuves auront une plus grande "diagnosticité" que d'autres—c'est-à-dire qu'elles seront plus utiles pour juger de la probabilité relative des hypothèses alternatives.

#### Structure de la matrice

```
         │  H1   │  H2   │  H3   │  H4   │  H5
─────────┼───────┼───────┼───────┼───────┼──────
Preuve 1 │   C   │   C   │   I   │   I   │  N/A
Preuve 2 │   I   │   C   │   C   │   I   │   C
Preuve 3 │   C   │   I   │   I   │   C   │   I
Preuve 4 │   I   │   I   │   C   │   C   │   C
[...]
─────────┼───────┼───────┼───────┼───────┼──────
Total I  │   6   │   4   │   2   │   5   │   3
```

**Légende :**
- ✅ = Hypothèse retenue (score le plus bas)
- ⚠️ = Hypothèse secondaire (à surveiller)
- ❌ = Hypothèse éliminée (score trop élevé)

#### Matrice pondérée (avancée)

Pour les investigations Full Rigor, chaque preuve reçoit un poids selon sa diagnosticité :

```
         │  H1   │  H2   │  H3   │  H4   │ Poids │ Fiabilité
─────────┼───────┼───────┼───────┼───────┼───────┼──────────
P1       │   C   │   C   │   I   │   I   │   2   │   A1
P2       │   I   │   C   │   C   │   I   │   1   │   B2
P3       │   C   │   I   │   I   │   C   │   3   │   A1
P4       │   I   │   I   │   C   │   C   │   2   │   B1
P5       │   C   │   C   │   C   │   I   │   1   │   C2
─────────┼───────┼───────┼───────┼───────┼───────┼──────────
Score    │  5    │  4    │ **2** │  6    │       │
```

**Calcul :**
```
H1 : (0×2) + (1×1) + (0×3) + (1×2) + (0×1) = 5
H2 : (0×2) + (0×1) + (1×3) + (1×2) + (0×1) = 4
H3 : (1×2) + (0×1) + (1×3) + (0×2) + (0×1) = 2 ← Meilleur
H4 : (1×2) + (1×1) + (0×3) + (0×2) + (1×1) = 6
```

### Conseils de mise en forme

**Couleurs recommandées (Excel/Sheets) :**
- 🟢 Vert : C (Consistent)
- 🔴 Rouge : I (Inconsistent)
- ⚪ Gris : N/A (Non applicable)

**Mise en évidence :**
- Ligne Total I : police grasse
- Hypothèse retenue : surlignage jaune
- Preuves critiques (linchpins) : bordure épaisse

---

## 💼 Exemple complet

### Scénario : Campagne de désinformation sur Twitter

**Contexte :** Une campagne virale #FakeNews2025 propage de fausses informations sur les élections. Vous devez identifier l'origine.

#### Étape 1 : Génération des hypothèses

```markdown
## Hypothèses

**H1 - Opération étatique russe**
Description : Campagne orchestrée par des agences de renseignement russes (IRA, GRU)
Plausibilité initiale : Moyenne (précédents connus)

**H2 - Opération étatique chinoise**
Description : Campagne menée par acteurs chinois (APT, 50 Cent Army)
Plausibilité initiale : Faible (moins de précédents sur ce type de cible)

**H3 - Groupe hacktiviste non-étatique**
Description : Collectif indépendant (style Anonymous, LulzSec)
Plausibilité initiale : Moyenne (capacités techniques suffisantes)

**H4 - Campagne partisane domestique**
Description : Acteurs politiques locaux (partis, groupes d'intérêt)
Plausibilité initiale : Élevée (motivation claire, accès facile)

**H5 - Manipulation commerciale**
Description : Entreprise de désinformation-as-a-service (mercenaires)
Plausibilité initiale : Moyenne (marché connu mais opaque)
```

#### Étape 2 : Collecte des preuves

```markdown
## Preuves

**P1 - Langue des tweets : 80% anglais, 15% russe, 5% autres**
Source : Analyse NLP de 10,000 tweets | Fiabilité : A1

**P2 - Timezone principale : UTC+3 (Moscou)**
Source : Métadonnées Twitter API | Fiabilité : A1

**P3 - Infrastructure : Serveurs VPS en Bulgarie et Roumanie**
Source : Analyse IP + WHOIS | Fiabilité : B1

**P4 - Coordination temporelle : Pics d'activité 9h-17h UTC+3**
Source : Analyse temporelle (30 jours) | Fiabilité : A1

**P5 - Sophistication technique : Modérée (bots détectables)**
Source : Analyse Botometer + patterns | Fiabilité : B2

**P6 - Budget apparent : $50K-100K estimé**
Source : Coût VPS + comptes achetés | Fiabilité : C3

**P7 - Narratives : Anti-OTAN, pro-Russie**
Source : Analyse de contenu sémantique | Fiabilité : A1

**P8 - Réactivité : 2-4h après événements majeurs**
Source : Timeline corrélation avec actualités | Fiabilité : A2

**P9 - Cibles : Médias occidentaux + think tanks**
Source : Analyse mentions et hashtags | Fiabilité : A1

**P10 - Absence d'idéologie cohérente au-delà de narratives**
Source : Analyse approfondie contenu | Fiabilité : B2
```

#### Étape 3 : Matrice ACH

```
           │  H1    │  H2    │  H3    │  H4    │  H5    │ Diagnosticité
           │ Russie │ Chine  │Hackti- │Domes-  │Merce-  │
           │        │        │viste   │tique   │naire   │
───────────┼────────┼────────┼────────┼────────┼────────┼──────────────
P1 Langue  │   C    │   I    │   C    │   C    │   C    │   Moyenne
P2 TZ UTC+3│   C    │   I    │   C    │   I    │   C    │   Élevée
P3 VPS Est │   C    │   C    │   C    │   I    │   C    │   Faible
P4 Coordin │   C    │   C    │   I    │   C    │   C    │   Faible
P5 Sophist │   I    │   I    │   C    │   C    │   C    │   Moyenne
P6 Budget  │   I    │   I    │   C    │   C    │   C    │   Moyenne
P7 Narrativ│   C    │   I    │   I    │   I    │   C    │   Très élevée
P8 Réactiv │   C    │   C    │   I    │   C    │   C    │   Faible
P9 Cibles  │   C    │   C    │   I    │   I    │   C    │   Moyenne
P10 Idéolo │   I    │   I    │   C    │   I    │   C    │   Élevée
───────────┼────────┼────────┼────────┼────────┼────────┼──────────────
Total I    │   3    │   6    │   5    │   5    │   0    │
% Incons   │  30%   │  60%   │  50%   │  50%   │  **0%**│
───────────┼────────┼────────┼────────┼────────┼────────┼──────────────
Rang       │   2    │   5    │   3    │   4    │ **1**  │
Statut     │  ⚠️    │   ❌   │   ❌   │   ❌   │  ✅    │
```

#### Étape 4 : Raffinement

```markdown
## Analyse initiale

H5 (Mercenaire) : 0 inconsistance ← Score paradoxalement parfait
H1 (Russie) : 3 inconsistances ← Deuxième position

⚠️ PROBLÈME : H5 est "trop parfait"
→ Hypothèse générique compatible avec tout
→ Nécessite raffinement pour départager H5 et H1

## Lacune identifiée

Aucune preuve ne permet de distinguer :
- H5 : Mercenaires engagés (par qui ?)
- H1 : Opération étatique russe directe

## Collecte complémentaire (48h)

**P11 - Analyse linguistique approfondie**
Détection de fautes grammaticales typiques de locuteurs russes natifs
Source : Expert linguiste | Fiabilité : B2

**P12 - Analyse financière blockchain**
Paiements tracés vers portefeuilles liés à groupes hackers russes connus
Source : Chainalysis | Fiabilité : A1

## Matrice mise à jour

           │  H1    │  H5    │
───────────┼────────┼────────┼
P1-P10     │   3I   │   0I   │
P11 Linguis│   C    │   I    │ ← Nouveau
P12 Finance│   C    │   I    │ ← Nouveau
───────────┼────────┼────────┼
Total I    │   3    │   2    │
% Incons   │  25%   │  17%   │
───────────┼────────┼────────┼
Statut     │ **✅** │  ⚠️    │
```

**Conclusion révisée :** H1 (Opération étatique russe) devient l'hypothèse privilégiée après raffinement.

#### Étape 5-6 : Sensibilité

```markdown
## Preuves critiques (linchpins)

**P7 (Narratives pro-Russie) :**
- Suppression : H1 passe de 3I à 2I, H5 passe de 2I à 1I
- Impact : H5 redevient première → **LINCHPIN CRITIQUE**
- Fiabilité : A1 (analyse sémantique robuste)
- Risque : FAIBLE (multi-sources confirmant)

**P12 (Blockchain) :**
- Suppression : H1 passe de 3I à 4I, H5 passe de 2I à 1I
- Impact : H5 redevient première → **LINCHPIN CRITIQUE**
- Fiabilité : A1 (preuve cryptographique)
- Risque : MOYEN (attribution blockchain complexe)

## Scénarios alternatifs

**Scénario 1 : Si P7 était trompeur (faux drapeau)**
→ Acteurs non-russes imitant narratives russes pour attribuer faussement
→ H5 (Mercenaires) redevient probable
→ Besoin validation HUMINT/SIGINT

**Scénario 2 : Si P12 blockchain était manipulation**
→ Mixeurs utilisés pour brouiller les pistes
→ Attribution financière non fiable
→ Retour à H5

## Niveau de robustesse

**MOYEN-FAIBLE**
- Dépendance à 2 preuves critiques (P7, P12)
- Hypothèse H5 reste compétitive (écart de seulement 1 inconsistance)
- Recommandation : Validation par sources SIGINT/HUMINT urgente
```

#### Étape 7 : Rapport final

```markdown
# Rapport ACH : Origine campagne #FakeNews2025

## Synthèse Executive

**Conclusion privilégiée :** H1 - Opération étatique russe
**Niveau de confiance :** MOYEN (65%)

**Justification :** 
Les preuves linguistiques et financières pointent vers des acteurs russes connus, 
combinées à des narratives pro-Kremlin et infrastructure compatible. Cependant, 
l'hypothèse H5 (mercenaires) reste possible (2 inconsistances vs 3 pour H1).

**Alternatives rejetées :**
- H2 (Chine) : Éliminée (60% inconsistances - timezone, langue)
- H3 (Hacktivistes) : Éliminée (50% inconsistances - sophistication, budget)
- H4 (Domestique) : Éliminée (50% inconsistances - narratives, cibles)

**Recommandations :**
1. **Immédiat** : Signalement plateformes + alerte partenaires OTAN
2. **Court terme** : Validation HUMINT sur groupes identifiés
3. **Moyen terme** : Surveillance H5 en parallèle (si H1 invalide)

## [Sections détaillées : Méthodologie, Matrice, Sensibilité...]

## Indicateurs de suivi

**Confirmation H1 (30 jours) :**
- Nouvelles campagnes avec mêmes tactiques/narratives
- Corrélation avec événements géopolitiques russes
- Attribution technique supplémentaire (malware, domaines)

**Invalidation H1 :**
- Revendication crédible par acteur non-russe
- Preuves forensiques contredisant P7/P12
- Révélation contrat mercenaire avec client non-russe

**Réévaluation si :**
- 0 indicateurs de confirmation après 30j
- 2+ indicateurs d'invalidation observés
- Nouvelles preuves majeures émergent

**Prochaine revue : 2025-12-15**
```

---

## 📈 Interprétation des résultats

### Règles d'interprétation

#### 1. Score d'inconsistance

**Seuils indicatifs :**
- **0-20%** : Hypothèse très probable (mais vérifier si pas trop générique)
- **20-35%** : Hypothèse plausible
- **35-50%** : Hypothèse peu probable
- **>50%** : Hypothèse éliminée

**⚠️ Attention au "zéro parfait" :**
Un score de 0% peut indiquer une hypothèse trop vague/générique qui s'adapte à tout.

**Exemple :**
```
H1 : "Le compte est géré par un humain"
→ Compatible avec presque toutes les preuves
→ Score : 0% mais hypothèse non informative

Solution : Raffiner en sous-hypothèses plus précises
- H1a : Humain professionnel (organisation)
- H1b : Humain amateur (individu isolé)
```

#### 2. Écart entre hypothèses

**Si écart < 10% entre les deux premières :**
```
H1 : 25% inconsistances
H2 : 30% inconsistances
→ Écart = 5% (trop faible)

Recommandation :
- Collecte ciblée pour départager
- Conserver les deux hypothèses actives
- Niveau de confiance : FAIBLE à MOYEN maximum
```

**Si écart > 20% :**
```
H1 : 20% inconsistances
H2 : 45% inconsistances
→ Écart = 25% (significatif)

Recommandation :
- H1 clairement privilégiée
- H2 surveillée mais secondaire
- Niveau de confiance : MOYEN à ÉLEVÉ possible
```

#### 3. Distribution des inconsistances

**Pattern idéal (conclusion robuste) :**
```
H1 : ██ 15%
H2 : ████████ 45%
H3 : ██████ 35%
H4 : ████████████ 60%
H5 : ███████ 40%

→ H1 clairement isolée
→ Conclusion robuste
```

**Pattern problématique (indécidable) :**
```
H1 : ████ 25%
H2 : ████ 25%
H3 : █████ 30%
H4 : ████ 28%
H5 : ████ 27%

→ Toutes les hypothèses groupées
→ Collecte insuffisante ou preuves peu diagnostiques
```

### Calibration du niveau de confiance

**Formule empirique :**

```
Niveau de confiance = f(Score, Écart, Robustesse, Qualité)

Où :
- Score : % inconsistances de l'hypothèse retenue
- Écart : Différence avec la deuxième hypothèse
- Robustesse : Nombre de linchpins
- Qualité : % de preuves A1/A2/B1
```

**Table de conversion :**

| Score H1 | Écart avec H2 | Linchpins | Qualité preuves | Confiance |
|----------|---------------|-----------|-----------------|-----------|
| 0-15% | >30% | ≤1 | >80% A/B | TRÈS ÉLEVÉ (85-95%) |
| 15-25% | 20-30% | ≤2 | >70% A/B | ÉLEVÉ (70-85%) |
| 25-35% | 10-20% | ≤3 | >60% A/B | MOYEN (55-70%) |
| 35-45% | <10% | >3 | <60% A/B | FAIBLE (40-55%) |
| >45% | N/A | N/A | N/A | TRÈS FAIBLE (<40%) |

**Exemple d'application :**
```
Investigation #FakeNews2025 :
- Score H1 : 25% (3/12 inconsistances)
- Écart avec H5 : 8% (H5 = 17%)
- Linchpins : 2 (P7, P12)
- Qualité : 75% A1/A2/B1

→ Niveau de confiance : MOYEN (65%)
```

---

## ⚖️ Forces et limites

### ✅ Forces de l'ACH

#### 1. Auditabilité et traçabilité

L'ACH est auditable. Puisque l'ACH exige que l'analyste construise une matrice, les preuves et hypothèses peuvent faire l'objet d'un backtracking. Cela permet au décideur ou à d'autres analystes de voir la séquence de règles et de données qui ont conduit à la conclusion.

**Avantages pratiques :**
- Documentation probatoire pour usage judiciaire
- Validation par les pairs facilitée
- Apprentissage organisationnel (capitalisation d'expérience)

#### 2. Neutralisation des biais cognitifs

Il est largement admis que l'ACH aide à surmonter les biais cognitifs, notamment :

- **Biais de confirmation** : La méthode force à considérer les preuves contredisant l'hypothèse privilégiée
- **Ancrage** : Toutes les hypothèses sont traitées équitablement dès le départ
- **Disponibilité** : La collecte systématique réduit la dépendance aux informations facilement accessibles

#### 3. Structuration de la pensée analytique

L'ACH fournit un **cadre rigoureux** qui :
- Évite les sauts inférentiels non justifiés
- Impose une documentation exhaustive
- Facilite la communication avec les décideurs

#### 4. Gestion de l'incertitude

En produisant un **classement d'hypothèses** plutôt qu'une conclusion binaire, l'ACH :
- Permet de garder des hypothèses alternatives actives
- Facilite le monitoring d'indicateurs multiples
- Réduit le risque de "surprise stratégique"

### ❌ Limites de l'ACH

#### 1. Temps et ressources

Le processus de création d'une ACH est chronophage.

**Impact opérationnel :**
- Quick Investigation : ACH complète souvent impossible (30 min disponibles)
- Standard Professional : ACH simplifié (3-5 hypothèses max)
- Full Rigor : ACH complète possible (1-3 jours)

**Solutions :**
- ACH "express" avec 3 hypothèses + 8 preuves (1h)
- ACH collaborative (équipe parallélise la collecte)
- ACH itérative (matrice mise à jour progressivement)

#### 2. Complexité à grande échelle

La matrice ACH peut être problématique lors de l'analyse d'un projet complexe. Il peut être lourd pour un analyste de gérer une grande base de données avec de multiples éléments de preuve.

**Exemple :**
```
10 hypothèses × 50 preuves = 500 cellules à évaluer
→ Temps estimé : 8-12 heures
→ Risque d'erreurs, fatigue cognitive
```

**Solutions :**
- Limiter à 5-7 hypothèses maximum
- Filtrer les preuves (garder les plus diagnostiques)
- Utiliser des outils automatisés (PARC ACH, Excel avec macros)

#### 3. Qualité des preuves

Les preuves posent également problème si elles ne sont pas fiables. Les preuves utilisées dans la matrice sont statiques et donc peuvent être un instantané dans le temps.

**Problèmes :**
- Preuves contradictoires (sources conflictuelles)
- Preuves évolutives (ce qui est vrai aujourd'hui change demain)
- Preuves manipulées (désinformation, faux drapeaux)

**Solutions :**
- Évaluation Admiralty Code systématique (A1-F6)
- Mise à jour régulière de la matrice (snapshot daté)
- Analyse de sensibilité pour identifier les preuves critiques

#### 4. Génération initiale des hypothèses

Selon les critiques constructivistes sociaux, l'ACH ne met pas suffisamment l'accent (ou n'aborde pas en tant que méthode) la nature problématique de la formation initiale des hypothèses utilisées pour créer sa grille. Il existe des preuves considérables, par exemple, qu'en plus de tout biais bureaucratique, psychologique ou politique pouvant affecter la génération d'hypothèses, il y a également des facteurs de culture et d'identité à l'œuvre.

**Risque :** Si les "vraies" hypothèses ne sont pas générées initialement, l'ACH ne peut pas les identifier.

**Solutions :**
- Brainstorming diversifié (perspectives multiples)
- Techniques de génération (Starbursting, spectre d'intensité)
- Révision périodique (nouvelles hypothèses ajoutées si nécessaire)
- Red teaming (adversaire génère des hypothèses alternatives)

#### 5. Hypothèses "plates" (non hiérarchiques)

L'ACH traite l'ensemble d'hypothèses comme "plat", c'est-à-dire une simple liste, et est donc incapable de relier les preuves aux hypothèses aux niveaux d'abstraction appropriés

**Problème :**
```
H1 : Opération étatique
  └─ H1a : Russie
  └─ H1b : Chine
  └─ H1c : Iran

→ ACH standard ne gère pas cette hiérarchie
→ Nécessite SACH (Structured ACH) pour subdivisions
```

**Solution : SACH** (voir section Variantes)

---

## 🔄 Variantes et extensions

### 1. SACH (Structured ACH)

L'analyse structurée des hypothèses concurrentes offre aux analystes une amélioration par rapport aux limitations de l'ACH original. Le SACH maximise les hypothèses possibles en permettant à l'analyste de diviser une hypothèse en deux complexes.

#### Principe de subdivision

```
NIVEAU 1 (général) :
H1 : L'Irak possède des ADM

NIVEAU 2 (géographique) :
H1a : ADM à Bagdad
H1b : ADM à Mossoul

NIVEAU 3 (typologie) :
H1a1 : ADM biologiques à Bagdad
H1a2 : ADM chimiques à Bagdad
H1a3 : ADM nucléaires à Bagdad
```

#### Workflow SACH

1. Matrice ACH initiale (niveau 1)
2. Hypothèse H1 ressort comme la plus probable
3. Subdivision de H1 en H1a, H1b, H1c
4. Nouvelle matrice ACH (niveau 2) avec preuves supplémentaires
5. Itération jusqu'à niveau de granularité souhaité

**Avantages :**
- Permet d'affiner progressivement
- Gère la complexité par niveaux
- Fournit des estimations nuancées

### 2. ACH Bayésien

Une méthode, par Valtorta et collègues, utilise des méthodes probabilistes, ajoute l'analyse bayésienne à l'ACH.

#### Principe

Au lieu de compter les inconsistances (C/I), calculer des probabilités conditionnelles :

```
P(H|E) = P(E|H) × P(H) / P(E)

Où :
P(H|E) = Probabilité de l'hypothèse sachant les preuves
P(E|H) = Vraisemblance de la preuve si l'hypothèse est vraie
P(H) = Probabilité a priori de l'hypothèse
P(E) = Probabilité marginale de la preuve
```

**Exemple simplifié :**
```
Hypothèse : "Le compte est un bot" (probabilité a priori = 30%)
Preuve : "Publication à intervalles fixes" (vraisemblance si bot = 90%, si humain = 10%)

P(Bot|Intervalles) = (0.9 × 0.3) / [(0.9 × 0.3) + (0.1 × 0.7)]
                   = 0.27 / 0.34
                   = 79%

→ Après cette preuve, probabilité que ce soit un bot = 79%
```

**Outils :**
- CACHE (Collaborative ACH Environment) qui a introduit le concept de communauté Bayes
- Sheba technology utilisée dans le logiciel d'évaluation du renseignement de Veriluma

### 3. ACH avec Subjective Logic

Le travail de Pope et Jøsang utilise la logique subjective, une méthodologie mathématique formelle qui traite explicitement de l'incertitude.

#### Principe

Au lieu de C/I binaire, utiliser des opinions subjectives avec :
- Croyance (belief)
- Incrédulité (disbelief)
- Incertitude (uncertainty)
- Probabilité de base (base rate)

**Représentation :**
```
Opinion = (b, d, u, a)
Où : b + d + u = 1

Exemple :
Preuve #3 supporte H1 avec :
- Croyance : 0.7
- Incrédulité : 0.1
- Incertitude : 0.2
- Base rate : 0.5
```

### 4. Hypothesis Mapping (Alternative)

Le philosophe et théoricien de l'argumentation Tim van Gelder a proposé la cartographie d'hypothèses (similaire à la cartographie d'arguments) comme alternative à l'ACH.

#### Critiques de van Gelder

L'ACH exige que l'analyste fasse trop de jugements discrets, dont un grand nombre contribuent peu ou rien à discerner la meilleure hypothèse. L'ACH conçoit mal la nature de la relation entre les éléments de preuve et les hypothèses en supposant que les éléments de preuve sont, par eux-mêmes, cohérents ou incohérents avec les hypothèses.

#### Principe du Hypothesis Mapping

Créer un graphe argumentatif visuel montrant :
- Les hypothèses (nœuds principaux)
- Les preuves (nœuds secondaires)
- Les relations de soutien/réfutation (arêtes orientées)
- Les arguments subordonnés (hiérarchie)

**Exemple :**
```
[H1 : Bot russe]
    ↑ (soutient)
    │
[P1 : Langue russe] ← [P1a : 80% des tweets en russe]
    ↓ (contredit)
    │
[Objection : Russophones hors Russie nombreux]
```

**Outil :** Rationale, bCisive (logiciels de cartographie d'arguments)

---

## 🛠️ Outils et templates

### Templates Excel/Google Sheets

#### Template de base (téléchargeable)

**Disponible :** [`templates/ach-matrix-template.xlsx`](../../templates/ach-matrix-template.xlsx)

**Contenu :**
1. Feuille "Hypothèses" : génération et descriptions
2. Feuille "Preuves" : collecte et évaluation qualité
3. Feuille "Matrice" : grille C/I/N/A avec calculs automatiques
4. Feuille "Sensibilité" : tests linchpins
5. Feuille "Rapport" : synthèse executive auto-générée

**Formules automatiques :**
```excel
// Comptage inconsistances
=COUNTIF(B2:B11,"I")

// Pourcentage
=B12/COUNTA(B2:B11)*100

// Classement
=RANK(B13,$B$13:$F$13,1)

// Formatage conditionnel
Si % > 50% → Rouge (éliminé)
Si % < 20% → Vert (retenu)
Sinon → Orange (à surveiller)
```

**Macros VBA (avancé) :**
- Génération automatique de graphiques radar
- Export PDF du rapport complet
- Calcul pondéré avec coefficients de diagnosticité

---

### Logiciels spécialisés

#### PARC ACH (Palo Alto Research Center)

**Description :** Logiciel dédié développé par le Palo Alto Research Center pour automatiser la méthode ACH de Heuer.

**Fonctionnalités :**
- Interface graphique pour construction matricielle
- Calculs automatiques d'inconsistances
- Analyse de sensibilité intégrée (tests linchpins)
- Export de rapports standardisés

**Limitations :**
- Logiciel propriétaire (coût élevé)
- Courbe d'apprentissage importante
- Peu adapté aux investigations rapides (Quick)

**Usage recommandé :** Full Rigor uniquement (enquêtes majeures, usage judiciaire)

#### CACHE (Collaborative ACH Environment)

**Description :** Plateforme collaborative permettant à plusieurs analystes de travailler simultanément sur une même matrice ACH.

**Avantages :**
- Travail en équipe distribué
- Versioning des hypothèses et preuves
- Intégration Bayésienne (probabilités conditionnelles)
- Audit trail complet (traçabilité)

**Cas d'usage :** Investigations complexes nécessitant expertise multidisciplinaire (cyber + géopolitique + finance)

---

### Outils de visualisation

#### Graphiques radar (Spider charts)

**Principe :** Visualiser les scores d'inconsistance de chaque hypothèse sur un graphique circulaire.

```
        Complétude
            │
            │
   H1 ●─────┼─────● H5
       ╲    │    ╱
        ╲   │   ╱
         ╲  │  ╱
Qualité───●─┼─●───Diagnosticité
         ╱  │  ╲
        ╱   │   ╲
       ╱    │    ╲
   H2 ●─────┼─────● H4
            │
         Cohérence
```

**Outil recommandé :** Plotly, Chart.js, ou Excel natif

#### Cartes de chaleur (Heatmaps)

**Principe :** Matrice ACH colorée selon l'intensité des (in)cohérences.

```
         H1    H2    H3    H4    H5
P1    [ 🟢 ] [ 🟢 ] [ 🔴 ] [ 🔴 ] [ ⚪ ]
P2    [ 🔴 ] [ 🟢 ] [ 🟢 ] [ 🔴 ] [ 🟢 ]
P3    [ 🟢 ] [ 🔴 ] [ 🔴 ] [ 🟢 ] [ 🔴 ]
P4    [ 🔴 ] [ 🔴 ] [ 🟢 ] [ 🟢 ] [ 🟢 ]
```

**Bibliothèques :**
- Python : `seaborn.heatmap()`
- R : `ggplot2 + geom_tile()`
- JavaScript : `D3.js heatmap`

---

## ⚠️ Pièges à éviter

### 1. Générer trop peu d'hypothèses (fausse dichotomie)

**Erreur :** Se limiter à "c'est un bot" vs "c'est un humain"  
**Conséquence :** Biais binaire, hypothèses intermédiaires ignorées (bot partiellement automatisé, équipe humaine utilisant automation)  
**Solution :** Minimum 3-4 hypothèses, utiliser un spectre d'intensité ou de motivation

### 2. Confondre "absence de preuve" et "preuve d'absence"

**Erreur :** Marquer "I" (inconsistant) quand une preuve attendue est manquante  
**Conséquence :** Élimination abusive d'hypothèses viables (manque de données ≠ réfutation)  
**Solution :** Utiliser "N/A" si la preuve n'est pas applicable, documenter les lacunes informationnelles

**Exemple :**
```
Hypothèse : "Acteur étatique chinois"
Preuve manquante : Aucune IP chinoise détectée

❌ Mauvais : Marquer "I" → Élimine H2
✅ Correct : Marquer "N/A" + noter "Absence preuve ≠ preuve absence (VPN possible)"
```

### 3. Sur-pondérer les preuves facilement accessibles

**Erreur :** Accorder plus d'importance aux preuves OSINT faciles (tweets, photos publiques) qu'aux preuves techniques difficiles (blockchain, forensique)  
**Conséquence :** Biais de disponibilité, conclusions superficielles  
**Solution :** Évaluer chaque preuve selon **diagnosticité objective**, pas facilité d'accès

### 4. Traiter toutes les inconsistances comme égales

**Erreur :** Compter "langue russe détectée" (faible diagnosticité) au même niveau que "géolocalisation EXIF confirmée à Moscou" (haute diagnosticité)  
**Conséquence :** Scores d'inconsistance trompeurs  
**Solution :** Utiliser la pondération pour les investigations Standard/Full Rigor

### 5. Ne pas documenter les hypothèses écartées

**Erreur :** Rapport final mentionnant uniquement l'hypothèse retenue  
**Conséquence :** Décideur ne comprend pas le raisonnement, impossible de challenger  
**Solution :** Toujours inclure tableau des hypothèses avec scores et justifications d'élimination

### 6. Ignorer l'analyse de sensibilité

**Erreur :** Conclure sans tester la robustesse (linchpins)  
**Conséquence :** Conclusions fragiles, vulnérables à une seule preuve falsifiée  
**Solution :** Tests systématiques : "Si je supprime cette preuve, la conclusion change-t-elle ?"

### 7. Confondre corrélation et causalité

**Erreur :** "Le compte tweete toujours après minuit UTC+3 → C'est forcément un Russe à Moscou"  
**Conséquence :** Attribution erronée (peut être un insomniac à Paris utilisant automation)  
**Solution :** Croiser plusieurs types de preuves (technique + comportementale + linguistique)

---

## 🔗 Intégration dans le cycle OSINT

L'ACH s'insère principalement dans la **Phase 4 (Analyse)** du cycle OSINT, mais influence également les autres phases :

### Phase 1 - Planification

**Rôle de l'ACH :** Génération des hypothèses initiales via Starbursting

```
Question PIR : "Qui est derrière cette campagne de désinformation ?"

Starbursting → 6 branches (Qui/Quoi/Où/Quand/Pourquoi/Comment)
      ↓
Génération hypothèses ACH (H1 à H5)
      ↓
Identification des preuves nécessaires pour départager
```

**Livrable :** Liste d'hypothèses mutuellement exclusives + plan de collecte ciblé

### Phase 4 - Analyse (CŒUR DE L'ACH)

**Rôle de l'ACH :** Framework analytique central pour tester toutes les hypothèses concurrentes

```
Collecte terminée (Phase 2-3) → Preuves disponibles
      ↓
Construction matrice ACH (Preuves × Hypothèses)
      ↓
Évaluation C/I/N/A pour chaque cellule
      ↓
Calcul scores d'inconsistance
      ↓
Analyse de sensibilité (linchpins)
      ↓
Conclusion avec niveau de confiance calibré
```

**Synergie avec autres frameworks :**
- **Analysis Ladder** : Vérifier que chaque preuve a atteint le bon niveau (ne pas utiliser Raw Data non vérifiée)
- **Devil's Advocate** : Challenger systématiquement les évaluations C/I
- **Pre-mortem** : Imaginer pourquoi l'hypothèse retenue pourrait échouer

### Phase 5 - Reporting

**Rôle de l'ACH :** Livrable visuel pour décideurs

```
Matrice ACH complète (Excel/PDF)
      +
Synthèse executive (hypothèse retenue + alternatives écartées)
      +
Justification méthodologique (traçabilité)
      ↓
Rapport transparent et auditable
```

**Format recommandé :**
- **Quick Investigation** : Matrice simplifiée (3 hypothèses, 5-8 preuves) en annexe
- **Standard Professional** : Matrice complète + analyse sensibilité
- **Full Rigor** : Matrice pondérée + scénarios alternatifs + validation par pair

### Cycle itératif

L'ACH n'est pas linéaire : chaque raffinement (Étape 4) relance une mini-boucle :

```
Matrice initiale → Lacune identifiée → Collecte ciblée → Matrice mise à jour
         ↑                                                       │
         └───────────────────────────────────────────────────────┘
                    (Itération jusqu'à conclusion robuste)
```

---

## 📚 Ressources complémentaires

### Lectures recommandées

**Ouvrages fondateurs :**
- **Richards J. Heuer Jr.**, *Psychology of Intelligence Analysis* (1999) - CIA [Disponible gratuitement sur cia.gov]
- **Randolph H. Pherson & Richards J. Heuer Jr.**, *Structured Analytic Techniques for Intelligence Analysis* (3e éd., 2020)

**Articles académiques :**
- Heuer, R. J. (2005). "How Does Analysis of Competing Hypotheses (ACH) Improve Intelligence Analysis?" - *Studies in Intelligence*
- Schum, D. A. (1987). "Evidence and Inference for the Intelligence Analyst" - University Press of America

**Ressources en ligne :**
- [Intelligence Community Directive 203](https://www.dni.gov/files/documents/ICD/ICD%20203%20Analytic%20Standards.pdf) - Standards analytiques US
- [CIA Library - ACH Chapter](https://www.cia.gov/resources/csi/books-monographs/psychology-of-intelligence-analysis/)
- [Bellingcat - Digital Forensics](https://www.bellingcat.com/category/resources/how-tos/) - Cas d'usage OSINT

### Autres frameworks analytiques

**Complémentaires à l'ACH :**
- [📊 Analysis Ladder](./analysis-ladder.md) - Progression Raw Data → Insights (éviter sauts inférentiels)
- [⭐ Starbursting](./starbursting.md) - Génération de questions (préparation Phase 1)
- [🔴 Devil's Advocate](./devils-advocate.md) - Contradicteur méthodique (débiaisage)
- [⏪ Pre-mortem Analysis](./pre-mortem.md) - Imaginer l'échec rétrospectivement

**Alternatives/Extensions :**
- **SACH** (Structured ACH) : Pour hypothèses hiérarchiques
- **ACH Bayésien** : Avec probabilités conditionnelles (CACHE software)
- **Hypothesis Mapping** (Tim van Gelder) : Graphes argumentatifs visuels

### Templates et outils

**Templates téléchargeables :**
- [📊 Matrice ACH Excel](../../templates/ach-matrix-template.xlsx) - Avec formules automatiques
- [📋 Checklist ACH Standard](../../templates/ach-checklist.md) - 8 étapes détaillées
- [📄 Template Rapport ACH](../../templates/report-template.md) - Structure complète

**Checklists par niveau de rigueur :**
- [⚡ Quick Investigation](../../checklists/quick-investigation.md) - ACH simplifié (3H, 8P)
- [🎯 Standard Professional](../../checklists/standard-professional.md) - ACH complet (5H, 12P)
- [🔬 Full Rigor](../../checklists/full-rigor.md) - ACH pondéré + Bayésien

### Formations et communautés

**Formations certifiantes :**
- **SANS FOR578** - Cyber Threat Intelligence (module ACH)
- **Mercyhurst University** - Applied Intelligence Analysis Program
- **Catalyst Partners** - Structured Analytic Techniques Workshop

**Communautés OSINT :**
- [r/OSINT](https://reddit.com/r/OSINT) - Subreddit actif (120k+ membres)
- [OSINT Curious](https://osintcurio.us/) - Webinaires mensuels
- [OSINT Framework Discord](https://discord.gg/osint) - Entraide praticiens

---

[📖 Retour aux Frameworks](./README.md) | [🏠 Accueil OMF](../../README.md) | [🚀 Quick Start](../quick-start.md)

---

**Dernière mise à jour :** Novembre 2025  
**Auteur :** thepinguin073  
**Licence :** Creative Commons BY-SA 4.0  
**Pour contribuer :** [CONTRIBUTING.md](../../CONTRIBUTING.md)