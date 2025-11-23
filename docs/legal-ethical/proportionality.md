# Proportionnalité méthodologique en OSINT

> **"La rigueur n'est pas une fin en soi, mais un moyen au service d'objectifs investigatifs."**  
> — Principe fondateur du framework OMF

La **proportionnalité méthodologique** est un principe cardinal qui adapte le niveau de rigueur investigative aux enjeux réels de l'enquête. Contrairement à une approche bureaucratique où toutes les investigations suivraient le même protocole maximaliste, le framework OMF propose trois niveaux différenciés qui évitent à la fois la négligence méthodologique et la paralysie par excès de formalisme.

---

## 📋 Table des matières

- [Principe fondamental](#principe-fondamental)
- [Pourquoi la proportionnalité ?](#pourquoi-la-proportionnalité-)
- [Les trois niveaux de rigueur](#les-trois-niveaux-de-rigueur)
- [Critères de choix du niveau](#critères-de-choix-du-niveau)
- [Matrice de décision](#matrice-de-décision)
- [Exemples comparatifs](#exemples-comparatifs)
- [Éviter les pièges](#éviter-les-pièges)
- [Documentation minimale requise](#documentation-minimale-requise)

---

## 🎯 Principe fondamental

### Définition

La proportionnalité méthodologique consiste à **calibrer le niveau de rigueur investigative en fonction du contexte opérationnel**, notamment :

- **Les enjeux** : quelle est la gravité potentielle d'une erreur ?
- **L'usage prévu** : à quoi servira le renseignement produit ?
- **Les contraintes temporelles** : quel délai disponible ?
- **Les ressources** : quels moyens humains et techniques mobilisables ?

### Principe de Pareto appliqué à l'OSINT

```
80% des besoins OSINT peuvent être satisfaits par 20% de la rigueur maximale
15% des besoins nécessitent 50% de la rigueur maximale
5% des besoins exigent 100% de la rigueur (Full Rigor)
```

**Conséquence opérationnelle :** Appliquer systématiquement le protocole Full Rigor à toutes les investigations serait :
- ❌ Inefficace (gaspillage de ressources)
- ❌ Contre-productif (paralysie analytique)
- ❌ Irréaliste (délais incompatibles avec besoins opérationnels)

### Analogie médicale

```
Douleur légère (mal de tête)     → Automédication (paracétamol)
Symptômes persistants            → Consultation médecin généraliste
Pathologie complexe              → Hospitalisation + examens approfondis
```

**En OSINT :**
```
Vérification factuelle simple    → Quick Investigation (30 min)
Enquête professionnelle          → Standard Professional (2-7 jours)
Usage judiciaire/institutionnel  → Full Rigor (1-4 semaines)
```

---

## 💡 Pourquoi la proportionnalité ?

### 1. Éviter la bureaucratisation excessive

**Risque sans proportionnalité :**
```
Analyste : "Je dois vérifier si ce compte Twitter existe"
Chef : "Remplissez le formulaire PIR (Priority Intelligence Requirements), générez 5 hypothèses ACH, 
        documentez la chaîne de custody SHA-256, rédigez un 
        rapport de 15 pages avec peer review"
Analyste : "Euh... laisse tomber, je regarde pas"

→ Résultat : Paralysie analytique, démotivation, contournement des procédures
```

**Approche proportionnée :**
```
Analyste : "Quick check : compte existe, créé en 2019, 1200 followers"
Chef : "Parfait, note ça dans le log, on passe à la suite"
Temps : 3 minutes, pas de frustration, efficacité préservée
```

### 2. Optimiser les ressources

**Budget temporel limité :**
```
Scénario : Équipe de 3 analystes, 40h/semaine
Approche maximaliste : 1 investigation Full Rigor = 80h → 2 enquêtes/semaine
Approche proportionnée : 
  - 15 Quick Investigations (30 min) = 7.5h
  - 4 Standard Professional (8h) = 32h
  - 0-1 Full Rigor si nécessaire
  
→ 20 enquêtes/semaine vs 2
```

### 3. Adapter aux enjeux réels

**Conséquences d'une erreur :**

| Contexte | Enjeu | Niveau requis |
|----------|-------|---------------|
| Fact-checking article blog | Crédibilité éditoriale | Quick |
| Due diligence partenariat commercial | Risque financier moyen | Standard |
| Preuve judiciaire cybercriminalité | Liberté individuelle | Full Rigor |
| Renseignement géopolitique | Sécurité nationale | Full Rigor |

**Principe éthique :** Plus l'impact potentiel d'une erreur est grave, plus la rigueur doit être élevée.

### 4. Respecter les contraintes temporelles

**Réalité opérationnelle :**
```
Journaliste : "Article à publier dans 2h, je dois vérifier cette source"
→ Quick Investigation obligatoire (Full Rigor = impossible)

Magistrat : "Audition prévue dans 3 mois, besoin d'éléments probatoires"
→ Full Rigor possible et nécessaire

Manager : "Rapport trimestriel dans 1 semaine"
→ Standard Professional adapté
```

### 5. Maintenir la motivation et l'agilité

**Psychologie de l'analyste :**
- ✅ Protocole adapté = sentiment de compétence
- ✅ Résultats rapides quand approprié = satisfaction
- ✅ Rigueur accrue quand nécessaire = responsabilisation

**vs**

- ❌ Bureaucratie systématique = frustration
- ❌ Lenteur excessive = découragement
- ❌ Formalisme déconnecté des enjeux = cynisme

---

## 🔧 Les trois niveaux de rigueur

### Niveau 1 : Quick Investigation (80% des cas)

#### Contexte d'usage

**Quand utiliser ?**
- Vérifications factuelles simples
- Première reconnaissance (scoping initial)
- Enquêtes à enjeux faibles
- Contrainte temporelle forte (< 1h)

**Exemples typiques :**
- "Ce compte Twitter est-il vérifié ?"
- "Cette photo circule-t-elle depuis longtemps ?"
- "Ce site web est-il enregistré récemment ?"
- "Cette personne a-t-elle un profil LinkedIn ?"

#### Caractéristiques

**Durée :** 5-30 minutes  
**Documentation :** Minimale (notes brèves)  
**Outils :** Gratuits et rapides (Google, TinEye, WHOIS basique)  
**Validation :** Auto-validation par l'analyste  
**Traçabilité :** URL + date de consultation  

#### Ce qui est obligatoire

✅ **Minimal acceptable :**
- Identifier la source consultée (URL)
- Noter la date de vérification
- Documenter la conclusion (1-2 phrases)

❌ **Ce qui n'est PAS requis :**
- Hypothèses multiples (ACH)
- Captures forensiques avec hash SHA-256
- Rapport structuré multi-pages
- Validation par un pair
- Documentation juridique RGPD

#### Template Quick Investigation

```markdown
## Quick Check - [Sujet]
**Date :** 2025-11-13
**Analyste :** [Initiales]
**Durée :** 15 min

**Question :** [Formulation précise]

**Sources consultées :**
- Twitter.com/[username] (vérifié le 2025-11-13)
- Google Images reverse search

**Conclusion :**
[Réponse factuelle en 1-2 phrases]

**Niveau de confiance :** Élevé / Moyen / Faible
```

**Exemple réel :**
```markdown
## Quick Check - Authenticité compte @JohnDoe2025

**Date :** 2025-11-13  
**Analyste :** TP  
**Durée :** 8 min

**Question :** Le compte @JohnDoe2025 est-il authentique ?

**Sources consultées :**
- twitter.com/JohnDoe2025 (vérifié badge bleu présent)
- Wayback Machine (compte existe depuis 2019)

**Conclusion :**
Compte authentique, badge vérifié, historique cohérent (6 ans d'activité).

**Niveau de confiance :** Élevé
```

---

### Niveau 2 : Standard Professional (15% des cas)

#### Contexte d'usage

**Quand utiliser ?**
- Enquêtes professionnelles courantes
- Due diligence d'entreprise
- Investigations journalistiques standard
- Rapport destiné à management/client

**Exemples typiques :**
- "Profil complet d'un individu suspect"
- "Mapping d'un réseau d'influence"
- "Attribution d'une campagne de désinformation"
- "Analyse comportementale d'un groupe"

#### Caractéristiques

**Durée :** 4-40 heures (1-5 jours)  
**Documentation :** Structurée (rapport 5-15 pages)  
**Outils :** Mix gratuit/payant (Maltego, SpiderFoot, IntelX)  
**Validation :** Revue par chef d'équipe ou pair senior  
**Traçabilité :** Captures écran + métadonnées + log horodaté  

#### Ce qui est obligatoire

✅ **Exigences Standard :**
- **Planification :** PIR formalisés, scoping clair
- **Collecte :** Sources multiples, évaluation qualité (Admiralty Code)
- **Analyse :** ACH simplifié (3-5 hypothèses) OU Analysis Ladder
- **Reporting :** Rapport structuré avec méthodologie transparente
- **Traçabilité :** Captures écran + URLs + dates
- **Niveau de confiance :** Calibration explicite (ICD 203)

❌ **Ce qui reste optionnel :**
- Hashes cryptographiques SHA-256 systématiques
- Validation par 2 pairs indépendants
- Analyse de sensibilité exhaustive (tous linchpins)
- Documentation juridique probatoire complète

#### Structure de rapport Standard

```markdown
# Rapport OSINT : [Titre enquête]

## 1. Synthèse Executive (1 page)
- Conclusion principale
- Niveau de confiance
- Recommandations clés

## 2. Contexte et objectifs (0.5 page)
- PIR (Priority Intelligence Requirements)
- Périmètre de l'investigation
- Contraintes et limitations

## 3. Méthodologie (1 page)
- Sources consultées (typologie)
- Outils utilisés
- Frameworks appliqués (ACH, Analysis Ladder)

## 4. Résultats (5-10 pages)
- Découvertes factuelles structurées
- Corrélations identifiées
- Graphes relationnels (si applicable)

## 5. Analyse (2-3 pages)
- Hypothèses testées (matrice ACH simplifiée)
- Patterns comportementaux
- Attribution (si possible)

## 6. Conclusions et recommandations (1 page)
- Réponses aux PIR
- Actions recommandées
- Pistes d'approfondissement

## Annexes
- Captures écran clés (5-10)
- Timeline événements
- Liste complète des sources
```

**Longueur typique :** 8-15 pages + annexes

---

### Niveau 3 : Full Rigor (5% des cas)

#### Contexte d'usage

**Quand utiliser ?** (UN SEUL critère suffit)
- ⚖️ **Usage judiciaire** : preuve devant tribunal
- 🔐 **Sécurité nationale** : renseignement géopolitique
- 💰 **Enjeux financiers majeurs** : fraude >500K€
- 🏛️ **Décision institutionnelle critique** : sanctions diplomatiques
- 📰 **Publication médiatique à fort impact** : révélations Bellingcat-style

**Exemples typiques :**
- Attribution cyberattaque étatique
- Investigation crimes de guerre (géolocalisation bombardements)
- Enquête judiciaire cybercriminalité organisée
- Révélation réseaux d'influence étrangers

#### Caractéristiques

**Durée :** 40-200 heures (1-4 semaines)  
**Documentation :** Exhaustive (rapport 20-50 pages + annexes)  
**Outils :** Suite complète pro (Maltego XL, Recorded Future, OSINT frameworks spécialisés)  
**Validation :** Peer review par 2 analystes indépendants minimum  
**Traçabilité :** Chaîne de custody forensique complète (SHA-256, horodatage RFC 3161)  

#### Ce qui est obligatoire

✅ **Exigences Full Rigor (NON-NÉGOCIABLES) :**

**Planification :**
- PIR validés par commanditaire
- Hypothèses multiples (5-7 via Starbursting)
- Évaluation juridique préalable (RGPD, CFAA)
- Protocole OPSEC documenté

**Collecte :**
- Sources primaires privilégiées
- Validation authenticité systématique (EXIF, reverse search, forensique)
- Conservation probatoire : SHA-256 + horodatage certifié + capture complète (HTML source)
- Log horodaté de TOUTES les actions (qui, quoi, quand, où)

**Corrélation :**
- Graphes relationnels formalisés (Maltego, Gephi)
- Détection co-occurrences temporelles précises
- Structuration STIX/TAXII si cyberthreat

**Analyse :**
- **ACH complet** : matrice pondérée, analyse sensibilité exhaustive
- **Analysis Ladder** : progression niveau par niveau documentée
- **Débiaisage** : Devil's Advocate + Pre-mortem obligatoires
- **Niveaux de confiance** : ICD 203 calibrés avec justification

**Reporting :**
- Rapport structuré (template judiciaire)
- Méthodologie reproductible (auditabilité)
- Hypothèses concurrentes écartées explicitées
- Lacunes informationnelles documentées
- Annexes forensiques complètes (captures + hashes)

**Validation :**
- Peer review par 2 analystes indépendants
- Validation juridique si usage judiciaire
- Archivage sécurisé 5-10 ans

#### Structure de rapport Full Rigor

```markdown
# Rapport OSINT Full Rigor : [Titre]

## PARTIE 1 : SYNTHÈSE DÉCISIONNELLE (3 pages)

### 1.1 Executive Summary
- Conclusion principale (2 paragraphes)
- Niveau de confiance : [X%] (justification ICD 203)
- Recommandations immédiates (3-5 actions)

### 1.2 Réponses aux PIR
[Tableau structuré question-réponse]

### 1.3 Limitations et incertitudes
[Explicitation zones d'ombre]

---

## PARTIE 2 : MÉTHODOLOGIE (5 pages)

### 2.1 Contexte et périmètre
- Commanditaire et objectifs
- Contraintes juridiques/éthiques
- Délais et ressources

### 2.2 Frameworks appliqués
- ACH : 5 hypothèses testées
- Analysis Ladder : progression documentée
- Débiaisage : Devil's Advocate, Pre-mortem

### 2.3 Sources et outils
- Taxonomie sources (primaires/secondaires)
- Évaluation fiabilité (Admiralty Code)
- Stack technique utilisé

### 2.4 Protocole OPSEC
- Mesures de protection appliquées
- Évaluation risques pour enquêteur

---

## PARTIE 3 : RÉSULTATS FACTUELS (10-15 pages)

### 3.1 Timeline chronologique
[Événements clés avec horodatage précis]

### 3.2 Entités identifiées
[Personnes, organisations, infrastructures]

### 3.3 Graphes relationnels
[Visualisations Maltego/Gephi]

### 3.4 Corrélations techniques
[Métadonnées, géolocalisation, blockchain, etc.]

---

## PARTIE 4 : ANALYSE APPROFONDIE (8-12 pages)

### 4.1 Matrice ACH complète
[Hypothèses × Preuves avec pondération]

### 4.2 Analysis Ladder
[Niveau 1 → Niveau 5 avec justifications]

### 4.3 Analyse de sensibilité
[Tests linchpins, scénarios alternatifs]

### 4.4 Patterns et anomalies
[Comportements récurrents, outliers]

---

## PARTIE 5 : CONCLUSIONS ET RECOMMANDATIONS (3 pages)

### 5.1 Hypothèse retenue
[Justification détaillée]

### 5.2 Hypothèses écartées
[Pourquoi rejetées avec argumentation]

### 5.3 Niveau de robustesse
[Évaluation globale : Élevé/Moyen/Faible]

### 5.4 Indicateurs de suivi (milestones)
[Pour validation/invalidation future]

### 5.5 Recommandations opérationnelles
[Actions concrètes priorisées]

---

## ANNEXES (20-40 pages)

### A. Captures forensiques
[50-100 captures avec hash SHA-256]

### B. Log horodaté complet
[Toutes actions investigatives]

### C. Code source et métadonnées
[Dumps HTML, headers HTTP, EXIF]

### D. Validation par pairs
[Rapports reviewers indépendants]

### E. Conformité juridique
[Checklist RGPD, avis juridique si applicable]

### F. Bibliographie
[Sources académiques, références techniques]
```

**Longueur typique :** 30-50 pages + 20-40 pages d'annexes

---

## 📊 Critères de choix du niveau

### Arbre de décision

```
START : Nouvelle investigation OSINT
  │
  ├─ Usage judiciaire OU sécurité nationale ?
  │   └─ OUI → FULL RIGOR (obligatoire)
  │   └─ NON ↓
  │
  ├─ Publication médiatique majeure OU enjeux financiers >500K€ ?
  │   └─ OUI → FULL RIGOR (fortement recommandé)
  │   └─ NON ↓
  │
  ├─ Rapport professionnel avec attribution OU décision managériale ?
  │   └─ OUI → STANDARD PROFESSIONAL
  │   └─ NON ↓
  │
  ├─ Temps disponible < 1h OU simple fact-check ?
  │   └─ OUI → QUICK INVESTIGATION
  │   └─ NON → STANDARD PROFESSIONAL (par défaut)
```

### Matrice multi-critères

| Critère | Quick | Standard | Full Rigor |
|---------|-------|----------|------------|
| **Enjeu si erreur** | Faible (réputation) | Moyen (financier/professionnel) | Grave (liberté/sécurité/vie) |
| **Usage prévu** | Interne/Personnel | Client/Management | Judiciaire/Institutionnel |
| **Délai disponible** | < 1h | 1-5 jours | > 1 semaine |
| **Budget** | Gratuit (0€) | 100-1000€ | 1000-10000€ |
| **Ressources humaines** | 1 analyste solo | 1-2 analystes | Équipe 3-5 + reviewers |
| **Auditabilité requise** | Non | Oui (interne) | Oui (externe/judiciaire) |
| **Reproductibilité** | Non critique | Souhaitable | Obligatoire |

### Échelle de gravité des conséquences

**Niveau 1 - Conséquences mineures (Quick) :**
- Perte de crédibilité personnelle
- Temps perdu (réanalyse nécessaire)
- Erreur factuelle sans impact

**Niveau 2 - Conséquences modérées (Standard) :**
- Perte contrat commercial
- Dommage réputation entreprise
- Décision managériale erronée (réversible)

**Niveau 3 - Conséquences graves (Full Rigor) :**
- Condamnation judiciaire injuste
- Sanctions diplomatiques erronées
- Mise en danger physique d'individus
- Pertes financières massives (>500K€)

---

## 🎯 Matrice de décision

### Tableau récapitulatif

| Situation | Enjeu | Délai | Niveau | Justification |
|-----------|-------|-------|--------|---------------|
| Vérifier badge Twitter | Faible | 5 min | **Quick** | Fact-check simple, impact limité |
| Profil complet candidat recrutement | Moyen | 2h | **Standard** | Décision RH importante mais réversible |
| Due diligence fusion entreprises | Élevé | 1 semaine | **Standard** → **Full** | Enjeux financiers, optez pour Full si >5M€ |
| Attribution cyberattaque | Critique | 3 semaines | **Full Rigor** | Sécurité nationale, usage institutionnel |
| Fact-checking article blog | Faible | 1h | **Quick** | Publication sans portée judiciaire |
| Investigation journalistique (révélation) | Élevé | 2 semaines | **Full Rigor** | Impact public majeur, risque juridique |
| Monitoring routine réseaux sociaux | Faible | 30 min/jour | **Quick** | Surveillance continue, pas d'investigation |
| Analyse réseau influence étranger | Critique | 1 mois | **Full Rigor** | Renseignement géopolitique, usage gouvernemental |

### Cas limites (choix délicat)

#### Cas 1 : Investigation journalistique standard

```
Contexte : Article sur corruption locale (maire petite ville)
Enjeu : Moyen (impact local, pas national)
Délai : 1 semaine
Budget : Limité (média indépendant)

Hésitation : Standard ou Full Rigor ?

✅ STANDARD suffit si :
- Pas de poursuites judiciaires prévues
- Sources publiques uniquement
- Impact limité géographiquement

⚠️ FULL RIGOR si :
- Risque de plainte en diffamation élevé
- Accusations graves (détournement fonds publics)
- Précédent judiciaire dans ce média
```

#### Cas 2 : Due diligence partenariat

```
Contexte : Entreprise A veut s'associer avec entreprise B
Enjeu : Variable selon montant
Délai : 2 semaines
Budget : Moyen (10K€ disponibles)

Décision :
- < 100K€ enjeu → STANDARD
- 100-500K€ enjeu → STANDARD renforcé (ACH complet, validation interne)
- > 500K€ enjeu → FULL RIGOR

Règle : Si perte potentielle > 10% CA annuel → Full Rigor obligatoire
```

#### Cas 3 : Urgence opérationnelle

```
Contexte : Attaque cyber en cours, attribution nécessaire MAINTENANT
Enjeu : Critique (contre-mesures à déployer)
Délai : 2 heures

Conflit : Full Rigor impossible (temps), mais enjeux critiques

Solution : **Standard accéléré** ("Quick Full Rigor")
- ACH simplifié (3 hypothèses)
- Preuves techniques prioritaires uniquement
- Documentation minimale mais horodatée
- Rapport préliminaire 5 pages
- ⚠️ Mentionner explicitement "conclusions provisoires, validation complète nécessaire"
- Planifier Full Rigor post-crise (48-72h)
```

---

## 💼 Exemples comparatifs

### Exemple 1 : Vérification d'un compte Twitter suspect

#### Scénario
Un compte @MysteryBot2025 propage des infox. Trois analystes différents investiguent selon trois niveaux.

---

**Version Quick (15 minutes) :**

```markdown
## Quick Check @MysteryBot2025

**Analyste :** Analyste A  
**Date :** 2025-11-13 14:30  
**Durée :** 15 min

**Question :** Le compte est-il authentique ou bot ?

**Vérifications :**
- Twitter.com/MysteryBot2025 : créé octobre 2024, 43 followers
- Botometer score : 4.2/5 (probable bot)
- Activité : 200 tweets/jour (automatisation évidente)

**Conclusion :**
Très probablement un bot (score Botometer élevé, fréquence anormale).

**Niveau de confiance :** Moyen (pas de validation forensique)
```

**Livrables :** Note de 10 lignes  
**Temps :** 15 min  
**Coût :** 0€

---

**Version Standard (4 heures) :**

```markdown
# Analyse @MysteryBot2025 - Rapport Standard

## 1. Synthèse Executive

**Conclusion :** Compte automatisé (bot) avec coordination probable (réseau).  
**Niveau de confiance :** Élevé (75%)  
**Recommandation :** Signalement Twitter + surveillance réseau associé.

## 2. Méthodologie

**Sources :**
- Twitter API (historique 3 mois)
- Botometer Pro
- Analyse réseau (Gephi)
- WHOIS domaines liés

**Frameworks :**
- Analysis Ladder (Niveau 1 → 3)
- ACH simplifié (3 hypothèses)

## 3. Résultats

### 3.1 Identité compte
- Créé : 2024-10-15
- Bio : Générique ("News & Insights")
- Photo profil : Stock photo (TinEye: 47 usages)

### 3.2 Analyse comportementale
- Fréquence : 180-220 tweets/jour
- Timezone : Pic UTC+3 (9h-17h)
- Langue : 85% anglais, 15% russe
- Coordination : 12 comptes patterns similaires

### 3.3 Graphe réseau
[Visualisation Gephi : 12 comptes cluster]

## 4. Analyse

### ACH simplifié
| | H1 Bot solo | H2 Réseau coordonné | H3 Humain planification |
|---|---|---|---|
| Fréquence 200/j | C | C | I |
| Timezone UTC+3 | C | C | C |
| Stock photo | C | C | I |
| 12 comptes similaires | I | C | I |
| **Total I** | **1** | **0** | **3** |

**Conclusion :** H2 (réseau coordonné) la plus probable.

## 5. Recommandations
1. Signaler cluster complet à Twitter Trust & Safety
2. Monitoring actif (30 jours)
3. Analyse contenu sémantique (narratives)

## Annexes
- 15 captures écran clés
- Export Twitter API (JSON)
- Graphe Gephi (PNG)
```

**Livrables :** Rapport 8 pages + annexes  
**Temps :** 4h  
**Coût :** 150€ (Botometer Pro + analyste)

---

**Version Full Rigor (3 jours) :**

```markdown
# Attribution Réseau @MysteryBot2025 - Rapport Full Rigor

[30 pages + 40 pages annexes]

## PARTIE 1 : SYNTHÈSE (3 pages)

**Conclusion :** Réseau de 47 bots coordonnés, attribution probable acteur étatique (Russie, confiance 65%).

**Justification :** 
- Infrastructure VPS (Bulgarie/Roumanie, proxies russes)
- Narratives pro-Kremlin cohérentes
- Sophistication technique modérée (détectable mais efficace)
- Blockchain : paiements tracés vers portefeuilles russes connus

**Niveau de confiance :** Moyen-Élevé (65%)  
Dépendant de 2 linchpins : géolocalisation VPS + attribution blockchain.

## PARTIE 2 : MÉTHODOLOGIE (5 pages)

### Frameworks appliqués
- **ACH complet :** 5 hypothèses (Russie, Chine, Hacktivistes, Domestique, Mercenaires)
- **Analysis Ladder :** Niveau 1 → 5 documenté
- **Devil's Advocate :** Contradicteur désigné (Analyste B)
- **Pre-mortem :** "Pourquoi attribution Russie pourrait échouer ?"

### Stack technique
- Twitter API v2 (full archive)
- Maltego XL (graphe 500 nœuds)
- Chainalysis (blockchain)
- Shodan/Censys (infrastructure)
- IntelX (dark web mentions)

### Protocole OPSEC
- VPN triple-hop (ProtonVPN)
- VM dédiée (Whonix)
- Comptes investigation anonymes
- Pas de requêtes directes IPs russes

## PARTIE 3 : RÉSULTATS (12 pages)

### 3.1 Cartographie réseau complet
- 47 comptes identifiés (cluster principal)
- 12 comptes secondaires (amplification)
- 3 hubs centraux (coordination)

[Graphe Maltego haute résolution]

### 3.2 Infrastructure technique
**VPS identifiés :**
| IP | Localisation | Provider | WHOIS | Hash SHA-256 |
|---|---|---|---|---|
| 185.x.x.x | Bulgarie | DigitalOcean | 2024-09 | abc123... |
| 94.x.x.x | Roumanie | OVH | 2024-10 | def456... |

### 3.3 Analyse temporelle
- Pic activité : 09h-17h UTC+3 (Moscou) - 87% du volume
- Coordination : 15 min entre tweets cluster (automation)
- Réactivité événements : 2-4h après actualités majeures

### 3.4 Analyse blockchain
- 3 portefeuilles identifiés
- Chainalysis : liens vers groupes russes connus (GRU-affiliés)
- Montant estimé : $75K-120K (6 mois)

## PARTIE 4 : ANALYSE ACH COMPLÈTE (10 pages)

### 4.1 Matrice pondérée

| Preuve | Poids | H1 Russie | H2 Chine | H3 Hackti | H4 Domest | H5 Merc | Fiabilité |
|--------|-------|-----------|----------|-----------|-----------|---------|-----------|
| P1 Langue (80% EN, 15% RU) | 2 | C | I | C | C | C | A1 |
| P2 TZ UTC+3 | 3 | C | I | C | I | C | A1 |
| P3 VPS Europe Est | 2 | C | C | C | I | C | B1 |
| P4 Narratives pro-Kremlin | 4 | C | I | I | I | C | A1 |
| P5 Sophistication modérée | 2 | I | I | C | C | C | B2 |
| P6 Blockchain → RU | 4 | C | I | I | I | I | A1 |
| P7 Infrastructure budget | 2 | I | I | C | C | C | C3 |
| P8 Réactivité 2-4h | 1 | C | C | I | C | C | A2 |
| P9 Cibles OTAN | 3 | C | C | I | I | C | A1 |
| P10 Absence idéologie pure | 2 | I | I | C | I | C | B2 |
| **Score pondéré** | | **9** | **17** | **14** | **16** | **6** | |
| **Rang** | | **2** | **5** | **4** | **3** | **1** | |

**Conclusion initiale :** H5 (Mercenaires) score le plus bas (6), mais...

### 4.2 Analyse de sensibilité

**⚠️ PROBLÈME :** H5 trop générique ("mercenaires engagés par qui ?")

**Raffinement :**
- H5a : Mercenaires engagés par Russie
- H5b : Mercenaires engagés par acteur non-russe

**Nouvelle collecte (48h) :**
- P11 : Analyse linguistique (fautes typiques locuteurs RU natifs) → B2
- P12 : Metadata EXIF photos (géotag Moscou 60% cas) → A1

**Matrice mise à jour :**

| | H1 Russie directe | H5a Merc-RU | H5b Merc-autre |
|---|---|---|---|
| P1-P10 | 9 | 6 | 6 |
| P11 Linguistique | C (9) | I (7) | I (8) |
| P12 EXIF Moscou | C (9) | C (7) | I (10) |
| **Score final** | **9** | **7** | **10** |

**Conclusion révisée :** H1 (Opération étatique russe directe) privilégiée.

### 4.3 Tests linchpins

**Preuve critique #1 : P4 (Narratives pro-Kremlin)**
- Suppression P4 : H1 = 12, H5a = 10 → H5a redevient première
- **LINCHPIN CRITIQUE**
- Risque : Faux drapeau possible (acteur imitant narratives russes)
- Mitigation : Multi-sources confirmant (3 analystes indépendants)

**Preuve critique #2 : P6 (Blockchain)**
- Suppression P6 : H1 = 13, H5a = 10 → H5a première
- **LINCHPIN CRITIQUE**
- Risque : Mixeurs utilisés, attribution blockchain complexe
- Mitigation : Validation Chainalysis + expertise blockchain externe

**Niveau de robustesse :** MOYEN-FAIBLE
- Conclusion dépend de 2 preuves critiques sur 12
- Écart H1 vs H5a faible (9 vs 7 = 2 points seulement)
- Recommandation : Validation HUMINT/SIGINT urgente

## PARTIE 5 : CONCLUSIONS (3 pages)

### 5.1 Attribution privilégiée

**Hypothèse retenue :** H1 - Opération étatique russe (directe ou sous-traitée)

**Justification :**
Les preuves techniques (blockchain, infrastructure, TZ) + preuves linguistiques + narratives cohérentes pointent vers acteurs russes. Sophistication modérée cohérente avec opérations IRA (Internet Research Agency) documentées 2016-2024.

**Niveau de confiance :** 65% (Moyen-Élevé selon ICD 203)

**Facteurs d'incertitude :**
- Dépendance à 2 linchpins critiques (P4, P6)
- Hypothèse H5a (mercenaires russes) reste compétitive (écart faible)
- Absence validation HUMINT/SIGINT

### 5.2 Hypothèses écartées

**H2 (Chine) :** Éliminée (60% inconsistances)
- Timezone incompatible
- Langue russe présente
- Narratives anti-OTAN (pas priorité chinoise sur ce théâtre)

**H3 (Hacktivistes) :** Éliminée (50% inconsistances)
- Budget infrastructure trop élevé pour amateurs
- Sophistication opérationnelle inadéquate
- Absence revendication idéologique pure

**H4 (Domestique) :** Éliminée (57% inconsistances)
- Timezone incompatible avec acteurs US/EU
- Narratives pro-Russie illogiques pour acteur domestique occidental

### 5.3 Indicateurs de suivi (30 jours)

**Confirmation H1 :**
- [ ] Nouvelles campagnes mêmes tactiques/narratives
- [ ] Corrélation avec événements géopolitiques russes
- [ ] Attribution technique supplémentaire (malware, C2)

**Invalidation H1 :**
- [ ] Revendication crédible acteur non-russe
- [ ] Preuves forensiques contredisant P4/P6
- [ ] Révélation contrat mercenaire client non-russe

**Réévaluation si :**
- 0 indicateurs confirmation après 30j
- 2+ indicateurs invalidation
- Nouvelles preuves majeures

**Prochaine revue :** 2025-12-13

### 5.4 Recommandations opérationnelles

**Immédiat (72h) :**
1. Signalement coordonné Twitter/Meta/Telegram (47 comptes)
2. Alerte partenaires OTAN (réseau actif, ciblage institutions)
3. Briefing décideurs avec niveau confiance calibré

**Court terme (2 semaines) :**
4. Validation HUMINT sur groupes identifiés (si accès sources)
5. Partage indicateurs techniques (IoC) avec CERT nationaux
6. Surveillance H5a en parallèle (si H1 invalide)

**Moyen terme (1-3 mois) :**
7. Monitoring continu (détection nouvelles campagnes)
8. Analyse narratives (évolution discours)
9. Collaboration Bellingcat/DFRLab (open source)

## ANNEXES (40 pages)

### A. Captures forensiques (100 captures)
[Chaque capture avec hash SHA-256, timestamp, source URL]

### B. Log horodaté complet (15 pages)
```
2025-11-10 09:23:15 - Analyste A - Requête Twitter API @MysteryBot2025
2025-11-10 09:45:32 - Analyste A - Botometer scan (score: 4.2/5)
2025-11-10 10:12:44 - Analyste B - WHOIS 185.x.x.x (Bulgarie, DigitalOcean)
[... 200 entrées ...]
```

### C. Code source et métadonnées
- Dumps HTML (50 pages)
- Headers HTTP complets
- EXIF metadata (12 photos analysées)

### D. Validation par pairs
**Reviewer 1 (Analyste Senior C) :**
"Méthodologie rigoureuse, conclusions prudentes. Accord avec H1 mais niveau confiance 60% (vs 65% auteur) car linchpins fragiles. Recommande validation HUMINT avant diffusion large."

**Reviewer 2 (Expert Blockchain D) :**
"Attribution blockchain solide (P6), Chainalysis confirmé. Cependant, mixeurs possibles non détectés. Confiance P6 : B1 (vs A1 auteur). Reste robuste mais prudence."

### E. Conformité juridique
**Checklist RGPD :**
- [x] Minimisation données (uniquement publiques)
- [x] Finalité légitime (sécurité publique)
- [x] Durée conservation justifiée (5 ans)
- [x] Pas de données sensibles (santé, religion, etc.)

**Avis juridique :**
Investigation conforme RGPD (données publiques, finalité légitime). Usage judiciaire possible avec compléments HUMINT.

### F. Bibliographie
- Heuer, R. J. (1999). *Psychology of Intelligence Analysis*. CIA.
- DiResta, R. et al. (2019). *The Tactics & Tropes of the Internet Research Agency*. Stanford/NYU.
- Chainalysis (2024). *Cryptocurrency Attribution Methodology*.
```

**Livrables :** Rapport 70 pages complet  
**Temps :** 3 jours (24h analyste)  
**Coût :** 3500€ (stack pro + 2 reviewers + expert blockchain)

---

### Comparaison finale

| Aspect | Quick | Standard | Full Rigor |
|--------|-------|----------|------------|
| **Temps** | 15 min | 4h | 3 jours |
| **Coût** | 0€ | 150€ | 3500€ |
| **Pages** | 10 lignes | 8 pages | 70 pages |
| **Hypothèses** | 1 (intuitive) | 3 (ACH simplifié) | 5 (ACH complet) |
| **Validation** | Auto | Chef équipe | 2 pairs + expert |
| **Confiance** | 60% | 75% | 65%* |
| **Utilisable pour** | Screening initial | Rapport client | Usage judiciaire |

**Paradoxe confiance Full Rigor* :** Confiance calibrée PLUS BASSE car analyse sensibilité révèle fragilités (linchpins). Standard sur-confiant par manque de tests robustesse.

---

## ⚠️ Éviter les pièges

### Piège #1 : Sur-rigueur systématique

**Erreur :**
```
Manager : "Toutes nos investigations doivent être Full Rigor, on est une boîte sérieuse"

Conséquence : 
- Analyste passe 3 jours sur "Vérifier si ce domaine est enregistré"
- Paralysie, frustration, turnover
- Coûts explosent, délais intenables
```

**Solution :** Accepter que 80% des besoins = Quick/Standard suffit.

### Piège #2 : Sous-rigueur dangereuse

**Erreur :**
```
Analyste : "C'est juste pour un article, pas besoin de tout checker"
Publication : "M. X est lié à un réseau mafieux" (Quick Investigation 20 min)
Réalité : Homonymie, M. X innocent
Résultat : Procès diffamation, média condamné 50K€
```

**Solution :** Si impact potentiel grave, TOUJOURS Standard minimum.

### Piège #3 : Confusion niveau/qualité

**Erreur :**
```
Croyance : "Quick Investigation = mauvais travail"
Réalité : "Quick bien fait > Full Rigor bâclé"
```

**Principe :** Chaque niveau a ses standards de qualité propres.

**Quick bien fait :**
- Sources fiables consultées
- Conclusion factuelle précise
- Niveau confiance honnête
- Timing respecté

**Full Rigor bâclé :**
- 50 pages de remplissage
- ACH théorique (preuves faibles)
- Validation pro forma (copinage)
- Rapport illisible

### Piège #4 : Escalade automatique

**Erreur :**
```
Analyste : "Je commence Quick, mais finalement c'est complexe, 
            je passe Standard... ah non Full Rigor tant qu'à faire"
            
3 semaines plus tard : "J'ai rien fini"
```

**Solution :** Fixer le niveau AU DÉPART basé sur critères objectifs, pas improviser.

### Piège #5 : Déclassement par flemme

**Erreur :**
```
Analyste : "Le client demande Standard, mais j'ai la flemme, 
            je fais Quick et j'emballe ça dans 10 pages de blabla"
```

**Conséquence :** Rapport apparemment Standard, mais méthodologiquement Quick = tromperie.

**Solution :** Si niveau requis impossible (temps/ressources), négocier AVANT livraison.

### Piège #6 : Obsession outillage

**Erreur :**
```
Croyance : "Full Rigor = utiliser Maltego XL + 10 outils payants"
Réalité : "Full Rigor = MÉTHODOLOGIE rigoureuse (outils = moyens)"
```

**Principe :** On peut faire du Full Rigor avec outils gratuits si méthodologie respectée.

**Hiérarchie :**
```
1. Méthodologie (ACH, Analysis Ladder, traçabilité) ← CRITIQUE
2. Validation (peer review, sensibilité) ← CRITIQUE
3. Outils (Maltego vs gratuit) ← SECONDAIRE
```

### Piège #7 : Pseudo-proportionnalité

**Erreur :**
```
"On fait du Standard-", "Standard+", "Quick Premium", etc.

Résultat : 12 niveaux informels, aucune standardisation
```

**Solution :** S'en tenir aux 3 niveaux définis. Si besoin intermédiaire, choisir niveau supérieur et adapter (ex: "Standard léger").

---

## 📝 Documentation minimale requise

### Quick Investigation

**Obligatoire (5-10 lignes) :**
```markdown
**Sujet :** [Question précise]
**Date :** YYYY-MM-DD
**Sources :** [URLs consultées]
**Conclusion :** [Réponse factuelle]
**Confiance :** [Élevé/Moyen/Faible]
```

**Optionnel :**
- Captures écran (si facilement disponibles)
- Note de limitations

### Standard Professional

**Obligatoire (5-15 pages) :**
1. Synthèse executive (1 page)
2. Méthodologie (sources, outils, frameworks) (1-2 pages)
3. Résultats structurés (5-10 pages)
4. Analyse (ACH/Ladder) (2-3 pages)
5. Conclusions + recommandations (1 page)
6. Annexes : captures clés (10-20)

**Optionnel :**
- Graphes relationnels (Maltego/Gephi)
- Timeline détaillée
- Analyse sensibilité (linchpins)

### Full Rigor

**Obligatoire (20-50 pages + annexes) :**
1. Synthèse décisionnelle (2-3 pages)
2. Méthodologie exhaustive (4-6 pages)
3. Résultats factuels (10-15 pages)
4. Analyse approfondie (8-12 pages)
   - ACH complet pondéré
   - Analysis Ladder documenté
   - Sensibilité exhaustive
   - Débiaisage (Devil's Advocate, Pre-mortem)
5. Conclusions + indicateurs suivi (3 pages)
6. Annexes probatoires (20-40 pages)
   - Captures forensiques (hash SHA-256)
   - Logs horodatés complets
   - Dumps techniques (HTML, EXIF)
   - Validation pairs (2 reviewers minimum)
   - Conformité juridique (RGPD checklist)

**Non-négociable :**
- Hashes cryptographiques (SHA-256)
- Horodatage certifié (RFC 3161 si judiciaire)
- Peer review par 2 analystes indépendants
- Reproductibilité méthodologique

---

## 🔄 Escalade et déclassement

### Quand escalader (passer à niveau supérieur) ?

**Signaux d'alerte :**

```
Situation initiale : Quick Investigation prévue

⚠️ ESCALADE vers Standard si :
- Complexité inattendue (multiples hypothèses émergent)
- Sources contradictoires (nécessite ACH)
- Enjeux réévalués (décision managériale finalement)
- Client demande rapport structuré

⚠️ ESCALADE vers Full Rigor si :
- Risque juridique identifié (procès possible)
- Usage institutionnel finalement prévu
- Enjeux financiers >500K€ découverts
- Attribution étatique potentielle (géopolitique)
```

**Procédure d'escalade :**
1. **STOPPER** l'investigation en cours
2. **DOCUMENTER** ce qui a été fait (même si incomplet)
3. **NÉGOCIER** nouveaux délais/budget avec client
4. **REDÉMARRER** avec méthodologie niveau supérieur
5. **INTÉGRER** travail préliminaire dans nouveau protocole

### Quand déclasser (passer à niveau inférieur) ?

**Situations légitimes :**

```
Situation initiale : Standard ou Full Rigor planifié

✅ DÉCLASSEMENT acceptable si :
- Hypothèse éliminée rapidement (ACH initial: 1 hypothèse évidemment fausse)
- Données insuffisantes (sources taries, impossible aller plus loin)
- Changement priorités client (urgence autre dossier)
- Budget/délai révisés (contraintes externes)

⚠️ OBLIGATIONS si déclassement :
- Informer client/management AVANT livraison
- Documenter raisons (transparence)
- Indiquer clairement niveau réel dans rapport
- Mentionner limitations méthodologiques
- Proposer complément ultérieur si nécessaire
```

**Procédure de déclassement :**
1. **JUSTIFIER** auprès commanditaire (email/note)
2. **OBTENIR** validation écrite (couvrir responsabilité)
3. **ADAPTER** livrables au nouveau niveau
4. **MENTIONNER** explicitement dans rapport : "Investigation initialement Standard, ramenée à Quick en raison de [X]"
5. **ARCHIVER** documentation niveau initial (audit trail)

---

## 🎓 Cas d'usage par secteur

### Journalisme

| Type article | Niveau | Justification |
|-------------|--------|---------------|
| Brève actualité | Quick | Fact-checking rapide, vérification source |
| Article fond (hebdo) | Standard | Investigation structurée, multi-sources |
| Investigation Pulitzer | Full Rigor | Révélations majeures, risque diffamation |

### Cybersécurité

| Scénario | Niveau | Justification |
|----------|--------|---------------|
| IOC lookup | Quick | Base de données threat intelligence |
| Incident response | Standard | Attribution tactique, rapport post-mortem |
| APT attribution | Full Rigor | État-nation, implications géopolitiques |

### Finance/Business

| Contexte | Niveau | Justification |
|----------|--------|---------------|
| Screening KYC | Quick | Vérification identité, listes sanctions |
| Due diligence M&A | Standard | Réputation, risques, conflits intérêt |
| Fraude >1M€ | Full Rigor | Usage judiciaire, preuves probatoires |

### Forces de l'ordre

| Investigation | Niveau | Justification |
|--------------|--------|---------------|
| Renseignement territorial | Quick/Standard | Surveillance routine, profils suspects |
| Enquête préliminaire | Standard | Constitution dossier, mandat possible |
| Instruction judiciaire | Full Rigor | Preuves devant tribunal, chaîne custody |

### Think tanks / Recherche

| Produit | Niveau | Justification |
|---------|--------|---------------|
| Veille quotidienne | Quick | Monitoring, alertes |
| Rapport thématique | Standard | Analyse structurée, publication |
| Rapport attribution | Full Rigor | Crédibilité académique, peer review |

---

## 📚 Ressources complémentaires

### Templates téléchargeables

- [📄 Template Quick Investigation](../../templates/quick-investigation-template.md)
- [📊 Template Standard Professional](../../templates/standard-professional-template.md)
- [📑 Template Full Rigor](../../templates/full-rigor-template.md)

### Checklists décisionnelles

- [✅ Checklist choix niveau de rigueur](../../checklists/proportionality-decision.md)
- [⚠️ Checklist escalade/déclassement](../../checklists/escalation-checklist.md)

### Guides méthodologiques

- [📖 Quick Start Guide](../quick-start.md) - 30 min pour démarrer
- [🔬 Guide Full Rigor](../methodology/full-rigor-guide.md) - Protocole complet
- [⚖️ Guide conformité juridique](./gdpr-compliance.md) - RGPD, CFAA

### Frameworks analytiques

- [📊 Analysis Ladder](../frameworks/analysis-ladder.md) - Progression Raw Data → Insights
- [🔄 ACH](../frameworks/ach.md) - Analysis of Competing Hypotheses
- [⭐ Starbursting](../frameworks/starbursting.md) - Génération questions

---

## 🎯 Checklist rapide : Quel niveau choisir ?

```
[ ] Usage judiciaire prévu ? → OUI = Full Rigor OBLIGATOIRE
[ ] Sécurité nationale / géopolitique ? → OUI = Full Rigor
[ ] Publication médiatique majeure ? → OUI = Full Rigor
[ ] Enjeux financiers >500K€ ? → OUI = Full Rigor
[ ] Décision managériale importante ? → OUI = Standard minimum
[ ] Rapport client professionnel ? → OUI = Standard
[ ] Attribution technique requise ? → OUI = Standard minimum
[ ] Temps disponible <1h ? → OUI = Quick maximum
[ ] Simple fact-check ? → OUI = Quick suffit
[ ] Screening initial ? → OUI = Quick suffit

SI DOUTE : Choisir niveau supérieur (on peut déclasser, difficilement escalader)
```

---

## 💡 Principes directeurs

**1. La rigueur est un moyen, pas une fin**
> Adaptez le protocole aux enjeux réels, pas à vos préférences.

**2. Mieux vaut un Quick bien fait qu'un Full Rigor bâclé**
> La qualité méthodologique prime sur la quantité documentaire.

**3. Transparence > Perfection**
> Si vous faites Quick, dites-le. N'emballez pas du Quick dans du papier Full Rigor.

**4. L'escalade est normale**
> 20% des Quick deviennent Standard. C'est le signe d'une investigation rigoureuse, pas d'un échec.

**5. Le niveau ne détermine pas la valeur**
> Un Quick peut être plus précieux qu'un Full Rigor si c'est la bonne réponse au bon moment.

---

## 📌 Rappel

**La rigueur n’est efficace que si elle est utile et adaptée.**
Une investigation trop lourde sur un enjeu mineur est une perte de ressources; une investigation trop légère sur un enjeu critique est un risque inacceptable. La proportionnalité méthodologique est l’équilibre stratégique entre efficacité et fiabilité.

---

[📖 Retour aux Legal/Ethical](./README.md) | [🏠 Accueil OMF](../../README.md) | [🚀 Quick Start](../quick-start.md)

---

**Dernière mise à jour :** Novembre 2025  
**Auteur :** thepinguin073  
**Licence :** Creative Commons BY-SA 4.0  
**Pour contribuer :** [CONTRIBUTING.md](../../CONTRIBUTING.md)
