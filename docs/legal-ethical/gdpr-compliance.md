# Conformité RGPD en OSINT

## 📋 Table des matières

1. [Introduction](#introduction)
2. [Principes fondamentaux du RGPD](#principes-fondamentaux-du-rgpd)
3. [Application au contexte OSINT](#application-au-contexte-osint)
4. [Bases légales pour le traitement](#bases-légales-pour-le-traitement)
5. [Droits des personnes concernées](#droits-des-personnes-concernées)
6. [Obligations du praticien OSINT](#obligations-du-praticien-osint)
7. [Cas particuliers et zones grises](#cas-particuliers-et-zones-grises)
8. [Documentation et traçabilité](#documentation-et-traçabilité)
9. [Sanctions et jurisprudence](#sanctions-et-jurisprudence)
10. [Checklist de conformité](#checklist-de-conformité)
11. [Ressources complémentaires](#ressources-complémentaires)

---

## Introduction

### Contexte réglementaire

Le **Règlement Général sur la Protection des Données** (RGPD / GDPR), entré en vigueur le 25 mai 2018, constitue le cadre juridique de référence pour tout traitement de données personnelles dans l'Union Européenne. Son application extraterritoriale (Article 3) concerne également les organisations hors UE traitant des données de résidents européens.

### Problématique spécifique à l'OSINT

L'Open Source Intelligence opère dans une **zone de tension juridique** : elle exploite des informations publiquement accessibles, mais les traite de manière systématique, à des fins non prévues par les personnes concernées, créant ainsi de nouveaux risques pour la vie privée.

**Paradoxe central** : Une information légalement accessible (profil LinkedIn, photo Instagram, article de presse) peut devenir illégale à traiter dans le cadre d'une investigation OSINT si les conditions du RGPD ne sont pas respectées.

### Principe de base

> **Accessibilité publique ≠ Exploitation légitime**
> 
> La visibilité d'une donnée sur Internet ne constitue pas un consentement implicite à son traitement à des fins d'investigation.

---

## Principes fondamentaux du RGPD

Le RGPD repose sur **6 principes cardinaux** (Article 5) qui s'appliquent intégralement à l'OSINT :

### 1. Licéité, loyauté, transparence

**Définition** : Le traitement doit reposer sur une base légale explicite (voir section suivante), être effectué de manière loyale (sans tromperie), et transparent pour la personne concernée.

**Application OSINT** :
- ❌ **Illégal** : Se faire passer pour une autre personne pour accéder à des informations (violation de loyauté)
- ✅ **Légal** : Consulter des profils publics sans subterfuge
- ⚠️ **Zone grise** : Créer un faux profil pour observer sans interaction

### 2. Limitation des finalités

**Définition** : Les données doivent être collectées pour des finalités déterminées, explicites et légitimes, et ne pas être traitées ultérieurement de manière incompatible avec ces finalités.

**Application OSINT** :
- ✅ Définir clairement l'objectif de l'enquête (enquête judiciaire, due diligence, journalisme d'investigation)
- ❌ Réutiliser les données collectées pour une enquête A dans une enquête B sans nouvelle base légale
- ⚠️ La "finalité" doit être documentée **avant** la collecte (voir templates de planification)

### 3. Minimisation des données

**Définition** : Seules les données adéquates, pertinentes et limitées à ce qui est nécessaire doivent être collectées.

**Application OSINT** :
```
Exemple : Investigation sur une fraude financière d'entreprise

✅ NÉCESSAIRE :
- Profils LinkedIn des dirigeants (responsabilités, parcours)
- Registres commerciaux (structure juridique)
- Articles de presse (historique de l'entreprise)

❌ EXCESSIF :
- Photos de vacances des conjoints des dirigeants
- Localisation du domicile personnel
- Données médicales accessible via fuites de données
```

**Règle pratique** : Si vous ne pouvez pas justifier en quoi une donnée spécifique contribue à répondre à vos PIR (Priority Intelligence Requirements), ne la collectez pas.

### 4. Exactitude

**Définition** : Les données doivent être exactes et mises à jour si nécessaire.

**Application OSINT** :
- Vérifier l'authenticité des sources (métadonnées, recherche inversée d'images)
- Dater les informations collectées (un profil capturé en 2020 peut être obsolète en 2025)
- Corriger ou supprimer les informations erronées identifiées

### 5. Limitation de la conservation

**Définition** : Les données ne doivent être conservées que le temps nécessaire aux finalités du traitement.

**Application OSINT** :
```
Durées recommandées :
- Quick Investigation : 30 jours après clôture
- Standard Professional : 1 an (alignement avec prescription légale courte)
- Full Rigor / Usage judiciaire : Durée de la procédure + 5 ans (prescription pénale)
```

⚠️ **Exception** : Les données anonymisées (voir Considérant 26) peuvent être conservées indéfiniment.

### 6. Intégrité et confidentialité

**Définition** : Sécurité appropriée des données contre traitement non autorisé, perte, destruction ou dégradation accidentelle.

**Application OSINT** :
- Chiffrement des bases de données (AES-256)
- Accès restreint (authentification multi-facteurs)
- Logs d'accès traçables
- Procédures de réponse aux incidents (data breach)

---

## Application au contexte OSINT

### Qu'est-ce qu'une "donnée personnelle" ?

**Définition RGPD (Article 4.1)** : Toute information se rapportant à une personne physique identifiée ou identifiable.

**Exemples pertinents en OSINT** :
- ✅ **Donnée personnelle** : Nom, prénom, email, numéro de téléphone, adresse IP, photo identifiable, pseudonyme associable, géolocalisation, métadonnées EXIF
- ❌ **Pas une donnée personnelle** : Statistiques agrégées anonymisées, informations sur des personnes morales (entreprises), données véritablement anonymisées (impossible de ré-identifier)

### Catégories sensibles (Article 9)

Certaines données bénéficient d'une **protection renforcée** et nécessitent une base légale spécifique :

- Origine raciale ou ethnique
- Opinions politiques
- Convictions religieuses ou philosophiques
- Appartenance syndicale
- Données génétiques ou biométriques
- Données de santé
- Données concernant la vie sexuelle ou l'orientation sexuelle

**Implication OSINT** : Ces données ne peuvent être traitées que dans des cas très limités (Article 9.2) :
- Consentement explicite (rare en OSINT)
- Intérêt public substantiel avec base légale (enquête pénale officielle)
- Données manifestement rendues publiques **par la personne elle-même**

```
Exemple : Enquête sur un réseau de désinformation

✅ LICITE : Analyser les opinions politiques exprimées publiquement sur Twitter
   → La personne a manifestement rendu publique cette information (Art. 9.2.e)

❌ ILLICITE : Inférer l'orientation sexuelle via analyse comportementale
   → Même si l'information est publique, l'inférence systématique est interdite
```

### Qu'est-ce qu'un "traitement" ?

**Définition RGPD (Article 4.2)** : Toute opération appliquée à des données personnelles : collecte, enregistrement, organisation, structuration, conservation, consultation, utilisation, communication, etc.

**Implication OSINT** : Dès que vous :
- Capturez une page web contenant un nom
- Enregistrez une photo de profil
- Créez un graphe relationnel
- Corréllez des identifiants
- Rédigez un rapport mentionnant des individus

→ **Vous effectuez un traitement soumis au RGPD**

---

## Bases légales pour le traitement

Le RGPD exige qu'**au moins une** des 6 bases légales suivantes soit applicable (Article 6.1) :

### 1. Consentement (Article 6.1.a)

**Définition** : Manifestation de volonté libre, spécifique, éclairée et univoque.

**Applicabilité OSINT** : ❌ **Quasi-impossible** en pratique
- L'OSINT est par nature non-intrusive : vous n'interagissez pas avec la cible
- Le consentement obtenu rétrospectivement n'est pas valide
- Ne vous reposez jamais sur cette base pour l'OSINT

### 2. Exécution d'un contrat (Article 6.1.b)

**Applicabilité OSINT** : ⚠️ **Rare**
- Due diligence pré-contractuelle (vérification d'un futur partenaire commercial)
- Investigation RH (vérification d'un candidat avec son accord préalable)

### 3. Obligation légale (Article 6.1.c)

**Définition** : Traitement nécessaire au respect d'une obligation légale incombant au responsable.

**Applicabilité OSINT** : ✅ **Fréquente pour certaines professions**
- Obligations KYC (Know Your Customer) pour institutions financières
- Obligations de vigilance anti-blanchiment (directive LCB-FT)
- Obligations de vérification fiscale

**Exemple** : Une banque effectuant de l'OSINT sur un nouveau client dans le cadre de ses obligations réglementaires peut invoquer cette base légale.

### 4. Sauvegarde des intérêts vitaux (Article 6.1.d)

**Applicabilité OSINT** : ❌ **Très rare**
- Situations d'urgence médicale ou de danger imminent
- Localisation d'une personne disparue en danger

### 5. Mission d'intérêt public ou autorité publique (Article 6.1.e)

**Applicabilité OSINT** : ✅ **Pour acteurs publics**
- Police judiciaire, services de renseignement, administration fiscale
- Nécessite une habilitation légale explicite (Code de procédure pénale, Code de la sécurité intérieure)

⚠️ **Attention** : Cette base légale n'est pas transposable au secteur privé, même pour des "missions d'intérêt général" auto-proclamées.

### 6. Intérêt légitime (Article 6.1.f) ⭐

**Définition** : Le traitement est nécessaire aux fins des intérêts légitimes poursuivis par le responsable, sauf si les intérêts ou libertés de la personne concernée prévalent.

**C'est la base légale de référence pour l'OSINT professionnel.**

**Test de proportionnalité en 3 étapes** :

```
ÉTAPE 1 : Intérêt légitime est-il établi ?
├─ ✅ Journalisme d'investigation (liberté de la presse)
├─ ✅ Prévention de la fraude interne (protection des actifs)
├─ ✅ Protection de la réputation (diffamation prouvée)
├─ ✅ Défense en justice (préparation d'une procédure)
└─ ❌ Curiosité personnelle, surveillance arbitraire

ÉTAPE 2 : Le traitement est-il nécessaire ?
├─ Existe-t-il des moyens moins intrusifs ? (subsidiarité)
├─ Les données collectées sont-elles minimales ? (proportionnalité)
└─ L'objectif peut-il être atteint sans OSINT ? (nécessité)

ÉTAPE 3 : Équilibre intérêts / droits fondamentaux
├─ Nature des données (sensibles = balance penche vers la personne)
├─ Attentes raisonnables de la personne (contexte de publication)
├─ Impact potentiel sur la personne (risques générés)
└─ Mesures de protection mises en œuvre (pseudonymisation, sécurité)
```

**Exemple d'analyse** :

```
CAS : Enquête journalistique sur un élu soupçonné de conflit d'intérêts

ÉTAPE 1 : Intérêt légitime établi ?
✅ OUI - Liberté de la presse + transparence de la vie publique (Article 10 CEDH)

ÉTAPE 2 : Traitement nécessaire ?
✅ OUI - Impossible de démontrer le conflit d'intérêts sans corréler :
   - Registre des entreprises (participations financières)
   - Comptes-rendus de conseil municipal (décisions votées)
   - Profils LinkedIn (réseaux professionnels)

ÉTAPE 3 : Équilibre ?
✅ Les intérêts de l'élu (vie privée) sont atténués par :
   - Son statut de personne publique (attentes réduites en confidentialité)
   - La finalité d'intérêt général (transparence démocratique)
   - La limitation aux données strictement nécessaires (pas de vie familiale)

CONCLUSION : Base légale "intérêt légitime" applicable
```

---

## Droits des personnes concernées

Le RGPD confère aux individus **8 droits opposables** (Articles 15-22). Le praticien OSINT doit pouvoir y répondre.

### 1. Droit d'accès (Article 15)

**Obligation** : Fournir une copie des données traitées sous 1 mois.

**Application OSINT** :
- Préparer une procédure de réponse standardisée
- Exclure les données couvertes par le secret (enquête pénale, secret des affaires)
- Distinguer données collectées / données inférées

**Exemple de réponse** :
```
"Nous confirmons traiter les données suivantes vous concernant :
- Profil LinkedIn capturé le [date] (hash SHA-256: xxx)
- 3 articles de presse mentionnant votre nom (sources : Le Monde, Libération, Reuters)
- Graphe relationnel vous associant à 5 entités (entreprises A, B, C, D, E)

Ces données ont été collectées dans le cadre d'une enquête de due diligence 
pour notre client [X] sur base légale 'intérêt légitime' (Article 6.1.f).
Durée de conservation : 12 mois. Responsable : [Contact DPO]."
```

### 2. Droit de rectification (Article 16)

**Obligation** : Corriger les données inexactes.

**Application OSINT** :
- Si la personne prouve une erreur factuelle → correction obligatoire sous 1 mois
- Si l'erreur provient de la source (article de presse erroné) → mentionner la contestation sans nécessairement supprimer

### 3. Droit à l'effacement / "droit à l'oubli" (Article 17)

**Obligation** : Supprimer les données dans certaines conditions.

**Motifs d'effacement applicables en OSINT** :
- Données non nécessaires au regard des finalités (collecte excessive)
- Opposition légitime de la personne (voir droit d'opposition)
- Traitement illicite (absence de base légale)

**Exceptions au droit à l'effacement** (Article 17.3) :
- ✅ Liberté d'expression et d'information (journalisme)
- ✅ Constatation, exercice ou défense de droits en justice
- ✅ Intérêt public dans le domaine de la santé publique, archivage, recherche scientifique

```
Exemple : Journaliste refusant l'effacement

"Nous ne pouvons accéder à votre demande d'effacement car le traitement 
de vos données relève de l'exception 'liberté d'expression' (Article 17.3.a) 
dans le cadre d'une investigation journalistique sur [sujet d'intérêt public]."
```

### 4. Droit à la limitation (Article 18)

**Obligation** : "Geler" les données (les conserver mais ne plus les traiter) dans l'attente d'un arbitrage.

**Applicable quand** :
- Contestation de l'exactitude (le temps de vérifier)
- Traitement illicite mais personne refuse l'effacement (préfère limitation)
- Opposition en attente de décision

### 5. Droit à la portabilité (Article 20)

**Application OSINT** : ⚠️ **Peu pertinent**
- Ne concerne que les données fournies par la personne elle-même
- Exclut les données inférées ou collectées publiquement

### 6. Droit d'opposition (Article 21) ⭐

**CRITIQUE pour l'OSINT**

**Principe** : Toute personne peut s'opposer au traitement fondé sur "intérêt légitime" ou "intérêt public" pour des **raisons tenant à sa situation particulière**.

**Conséquence** :
- Le responsable doit **cesser le traitement**, sauf s'il démontre des motifs légitimes impérieux prévalant sur les intérêts de la personne.

**Analyse au cas par cas** :

```
CAS 1 : Journaliste enquêtant sur une corruption de grande ampleur
→ Motif légitime impérieux : liberté de la presse + intérêt public majeur
→ Opposition rejetée (proportionnellement)

CAS 2 : Enquête privée sur un ancien employé pour vengeance personnelle
→ Aucun motif légitime impérieux
→ Opposition acceptée → cessation immédiate du traitement
```

### 7. Droit de ne pas faire l'objet d'une décision automatisée (Article 22)

**Application OSINT** : ⚠️ **Pertinent si automatisation poussée**
- Profilage automatique via IA (scoring de risque, détection de patterns comportementaux)
- Décision produisant des effets juridiques ou significatifs

**Exemple** : Un algorithme classifiant automatiquement des individus comme "suspects" sans intervention humaine → violation potentielle.

### 8. Droit d'introduire une réclamation (Article 77)

**Principe** : Toute personne peut saisir l'autorité de contrôle (CNIL en France).

**Implication** : Vos pratiques OSINT peuvent être auditées. La documentation rigoureuse est votre meilleure défense.

---

## Obligations du praticien OSINT

### A. Documenter la conformité

**Principe de responsabilité (accountability)** : Le responsable de traitement doit être en mesure de **démontrer** sa conformité (Article 5.2).

**Documents obligatoires** :

#### 1. Registre des activités de traitement (Article 30)

**Obligatoire si** :
- Organisation > 250 employés, OU
- Traitement de données sensibles (Article 9), OU
- Traitement non occasionnel

**Contenu minimal** :
```markdown
| Finalité | Base légale | Catégories de données | Destinataires | Durée | Mesures sécurité |
|----------|-------------|----------------------|---------------|-------|------------------|
| Due diligence pré-contractuelle | Intérêt légitime (6.1.f) | Identité, parcours professionnel, réputation en ligne | Client interne (direction juridique) | 12 mois | Chiffrement AES-256, accès MFA |
```

#### 2. Analyse d'impact relative à la protection des données (AIPD / DPIA)

**Obligatoire si** (Article 35.3) :
- Évaluation systématique et approfondie basée sur traitement automatisé
- Traitement à grande échelle de données sensibles
- Surveillance systématique à grande échelle d'une zone accessible au public

**En pratique pour l'OSINT** :
- ✅ **Obligatoire** : Surveillance systématique d'un groupe de personnes (collectif, communauté en ligne)
- ❌ **Non obligatoire** : Investigation ponctuelle sur 1-5 individus

**Structure de l'AIPD** :
1. Description systématique du traitement (finalité, moyens, flux de données)
2. Évaluation de la nécessité et proportionnalité
3. Identification des risques pour les droits et libertés
4. Mesures d'atténuation des risques

#### 3. Mentions d'information (transparence)

**Principe** : Informer les personnes dont les données sont collectées (Articles 13-14).

**Exception applicable en OSINT** (Article 14.5) :
- Information impossible (collecte passive sans contact)
- Information disproportionnée (investigation discrète nécessaire)
- Information légalement interdite (secret de l'enquête)

⚠️ **Attention** : L'exception ne dispense pas de l'information **ultérieure** si la personne exerce ses droits.

### B. Nommer un DPO (Data Protection Officer) ?

**Obligatoire si** (Article 37) :
- Autorité publique
- Activités de base nécessitent suivi régulier et systématique à grande échelle
- Activités de base consistent en traitement à grande échelle de données sensibles

**Pour un praticien OSINT indépendant** : ❌ Généralement non obligatoire  
**Pour une entreprise d'investigation** : ⚠️ Probablement oui (selon échelle)

### C. Sécuriser les données (Article 32)

**Mesures techniques et organisationnelles appropriées** :

```
NIVEAU QUICK INVESTIGATION :
├─ Chiffrement du disque dur (BitLocker, FileVault)
├─ Mots de passe robustes (12+ caractères, gestionnaire)
└─ Suppression sécurisée après usage (shred, BleachBit)

NIVEAU STANDARD PROFESSIONAL :
├─ Chiffrement AES-256 des bases de données
├─ Authentification multi-facteurs (MFA)
├─ Logs d'accès horodatés
├─ Sauvegarde chiffrée (3-2-1 rule)
└─ Cloisonnement des données (enquêtes séparées)

NIVEAU FULL RIGOR :
├─ Chiffrement de bout en bout (E2EE)
├─ Infrastructure zero-knowledge
├─ Hébergement souverain (RGPD-compliant)
├─ Audits de sécurité réguliers
├─ Plan de réponse aux incidents (CSIRT)
└─ Pseudonymisation systématique
```

### D. Notifier les violations de données (Articles 33-34)

**Obligation** : Notifier la CNIL sous **72 heures** en cas de violation susceptible d'engendrer un risque pour les droits et libertés.

**Exemples de violations en OSINT** :
- Vol d'ordinateur contenant des données d'enquête non chiffrées
- Exfiltration par ransomware
- Divulgation accidentelle (envoi de rapport au mauvais destinataire)
- Piratage de compte (accès non autorisé à vos outils OSINT)

**Procédure** :
1. **Détection** : Identifier la violation (logging, alertes)
2. **Containment** : Isoler le système compromis
3. **Évaluation** : Risque pour les personnes ? (haute/moyenne/faible)
4. **Notification CNIL** : Formulaire en ligne sous 72h
5. **Notification individuelle** : Si risque élevé pour les personnes
6. **Documentation** : Registre des violations (Article 33.5)

---

## Cas particuliers et zones grises

### 1. Données publiquement accessibles

**Question** : Une information sur un site web public est-elle "libre de droits" pour l'OSINT ?

**Réponse** : ❌ Non. L'accessibilité ≠ Licéité du traitement.

**Distinction** :
```
INFORMATION MANIFESTEMENT RENDUE PUBLIQUE PAR LA PERSONNE ELLE-MÊME :
└─ Exemple : Tweet public, profil LinkedIn ouvert, interview médiatique
└─ Traitement facilité (mais toujours soumis au RGPD)

INFORMATION PUBLIQUE MAIS NON VOLONTAIREMENT EXPOSÉE :
└─ Exemple : Fuite de données (Have I Been Pwned), documents judiciaires, 
             annuaires professionnels, métadonnées EXIF
└─ Traitement strictement encadré (vérifier base légale robuste)
```

**Jurisprudence** : Arrêt CJUE "Wirtschaftsakademie" (2019) : Les données accessibles via réseaux sociaux restent protégées par le RGPD même si publiques.

### 2. Scraping et collecte automatisée

**Légalité** : ⚠️ **Zone grise juridique**

**Positions divergentes** :
- **LinkedIn c. hiQ Labs (USA, 2022)** : Scraping de profils publics autorisé sous conditions
- **CNIL (France)** : Scraping massif = traitement nécessitant base légale + respect du RGPD

**Recommandations** :
- ✅ Respecter le fichier `robots.txt`
- ✅ Limiter la fréquence de requêtes (rate limiting)
- ✅ Ne pas contourner les mesures techniques de protection
- ❌ Ne pas scraper de données manifestement sensibles (Article 9)
- ❌ Ne jamais scraper de contenus derrière authentification

### 3. Pseudonymisation et anonymisation

**Pseudonymisation** (Article 4.5) : Traitement empêchant l'identification sans information supplémentaire (conservée séparément).

**Exemple OSINT** : Remplacer noms par identifiants (`SUBJECT-001`, `SUBJECT-002`) dans les analyses préliminaires.

**Anonymisation** (Considérant 26) : Données ne permettant plus d'identifier une personne.

⚠️ **Attention** : La véritable anonymisation est **quasi-impossible** en OSINT :
- Inférence par corrélation (3-4 attributs suffisent souvent pour ré-identifier)
- Données externes disponibles publiquement (recoupement)

**Conclusion** : Présumer que vos données OSINT restent personnelles et appliquer le RGPD.

### 4. Transferts hors UE (Articles 44-50)

**Principe** : Transfert vers pays tiers uniquement si niveau de protection adéquat.

**Mécanismes** :
- ✅ **Décision d'adéquation** (Article 45) : Pays reconnus équivalents UE (UK post-Brexit, Suisse, Canada [partiel])
- ✅ **Clauses contractuelles types** (SCC) : Contrat garantissant protection équivalente
- ⚠️ **Règles d'entreprise contraignantes** (BCR) : Pour groupes multinationaux

**Impact sur outils OSINT** :
```
OUTILS HÉBERGÉS USA (pas de décision d'adéquation depuis Schrems II, 2020) :
├─ Google Sheets, Notion, Airtable → ⚠️ Vérifier SCC
├─ AWS, Azure, GCP → ✅ SCC disponibles généralement
└─ Outils SaaS inconnus → ❌ Risque de non-conformité

OUTILS HÉBERGÉS UE :
├─ OVH, Scaleway, Hetzner → ✅ Conformes
└─ Privilégier si données sensibles
```

### 5. Journalisme et liberté d'expression

**Exception de traitement** (Article 85) : Les États membres prévoient des exemptions pour :
- Traitement à des fins journalistiques
- Expression académique, artistique ou littéraire

**En France** : Article 80 de la loi Informatique et Libertés :
- Exemption des obligations de déclaration CNIL
- Application allégée du RGPD (mais pas annulation totale)
- Équilibre avec vie privée (Article 9 Code civil)

**Conditions** :
- ✅ Finalité réellement journalistique (pas prétexte)
- ✅ Respect de la déontologie professionnelle
- ✅ Intérêt public du sujet traité
- ❌ Pas d'exemption pour données sensibles sans justification impérieuse

---

## Documentation et traçabilité

### Template : Analyse de conformité RGPD pour enquête OSINT

```markdown
# Analyse RGPD - Investigation [ID-ENQUÊTE]

## 1. IDENTIFICATION
- Date : [JJ/MM/AAAA]
- Analyste : [Nom/Pseudonyme]
- Client/Mandant : [Entité]
- Finalité : [Description précise]

## 2. BASE LÉGALE (Article 6.1)
- [ ] (a) Consentement
- [ ] (b) Contrat
- [ ] (c) Obligation légale
- [ ] (d) Intérêts vitaux
- [ ] (e) Mission d'intérêt public
- [X] (f) Intérêt légitime → JUSTIFICATION : [Détailler]

## 3. TEST DE PROPORTIONNALITÉ (si 6.1.f)
**Intérêt légitime** : [Décrire]
**Nécessité** : [Pourquoi ce traitement est indispensable ?]
**Moyens alternatifs considérés** : [Liste]
**Équilibre intérêts/droits** : [Analyse]

## 4. DONNÉES TRAITÉES
**Catégories collectées** :
- [ ] Identité (nom, prénom, pseudonyme)
- [ ] Coordonnées (email, téléphone, adresse)
- [ ] Données professionnelles (emploi, parcours)
- [ ] Données de connexion (IP, logs, métadonnées)
- [ ] Données comportementales (activité en ligne, réseaux sociaux)
- [ ] Données sensibles (Article 9) → JUSTIFICATION IMPÉRATIVE : [...]

**Minimisation** : [Expliquer pourquoi chaque catégorie est nécessaire]

## 5. SOURCES DE COLLECTE
- [ ] Réseaux sociaux publics : [Lesquels ?]
- [ ] Registres officiels : [Lesquels ?]
- [ ] Articles de presse : [Lesquels ?]
- [ ] Bases de données publiques : [Lesquelles ?]
- [ ] Autres : [Préciser]

## 6. DURÉE DE CONSERVATION
- Collecte initiale : [Date]
- Durée prévue : [X mois/ans]
- Justification : [Aligner sur prescription légale pertinente]
- Destruction prévue : [Date]

## 7. MESURES DE SÉCURITÉ
- [ ] Chiffrement des données (AES-256)
- [ ] Authentification renforcée (MFA)
- [ ] Accès restreint (qui ?)
- [ ] Logs d'accès
- [ ] Sauvegarde chiffrée
- [ ] Procédure de destruction sécurisée

## 8. DESTINATAIRES
- Usage interne uniquement : [ ]
- Transmission au client : [ ] → Contractualisation RGPD
- Transmission à des tiers : [ ] → Lesquels ? Base légale ?

## 9. TRANSFERT HORS UE
- [ ] Non applicable (données UE uniquement)
- [ ] Oui → Pays : [...] → Mécanisme : [Adéquation/SCC/BCR]

## 10. DROITS DES PERSONNES
**Procédure de réponse mise en place** : [Décrire]
**Délai de réponse** : 1 mois maximum
**Contact désigné** : [Email/DPO]

## 11. AIPD (si applicable)
- [ ] Non nécessaire (traitement à échelle limitée)
- [ ] Nécessaire → AIPD réalisée : [Oui/Non] → Date : [...]

## 12. VALIDATION
- Analyste : [Signature] [Date]
- DPO (si applicable) : [Signature] [Date]
- Révision prévue : [Date]
```

---

## Sanctions et jurisprudence

### Échelle des sanctions RGPD

**Article 83 : Amendes administratives jusqu'à** :
- **Tier 1** (violations procédurales) : 10 millions € ou 2% du CA annuel mondial
- **Tier 2** (violations substantielles) : 20 millions € ou 4% du CA annuel mondial

**Critères d'aggravation** :
- Nature, gravité, durée de la violation
- Caractère intentionnel ou négligent
- Mesures d'atténuation prises
- Violations antérieures
- Coopération avec autorité de contrôle

### Jurisprudence pertinente pour l'OSINT

#### 1. Google Spain (CJUE, 2014) - "Droit à l'oubli"

**Faits** : Mario Costeja González demande déréférencement d'articles de presse anciens.

**Décision** : Les moteurs de recherche sont responsables de traitement et doivent déréférencer sous conditions.

**Impact OSINT** :
- Les agrégateurs de données publiques (moteurs de recherche, scrapers) restent soumis au RGPD
- Balance entre droit à l'oubli et liberté d'information au cas par cas
- Distinction entre "intérêt public" (personnalités publiques) et "simple curiosité"

#### 2. Wirtschaftsakademie (CJUE, 2019) - Réseaux sociaux

**Faits** : Responsabilité d'un administrateur de page Facebook pour cookies tiers.

**Décision** : Même une page fan Facebook constitue un traitement soumis au RGPD.

**Impact OSINT** :
- L'utilisation de plateformes tierces (Facebook, LinkedIn) pour collecter des données engage votre responsabilité
- Vous ne pouvez invoquer "c'est Facebook qui traite, pas moi"

#### 3. Clearview AI (Multiple autorités, 2021-2024)

**Faits** : Scraping massif de photos sur réseaux sociaux pour reconnaissance faciale.

**Sanctions** :
- France (CNIL) : 20 millions €
- Italie (Garante) : 20 millions €
- UK (ICO) : 7,5 millions £
- Grèce : 20 millions €

**Motifs** :
- Absence de base légale valide
- Collecte excessive (toutes les photos du web)
- Non-respect du droit d'opposition
- Transferts illicites vers USA

**Impact OSINT** :
- Le scraping massif est **hautement risqué juridiquement**
- L'excuse "c'est public donc libre" est rejetée
- Privilégier collecte manuelle et ciblée

#### 4. British Airways (ICO, 2020) - Violation de données

**Faits** : Piratage exposant données de 400 000 clients.

**Sanction** : 20 millions £ (réduite de 183 millions £ initialement)

**Impact OSINT** :
- La sécurité des données collectées est une **obligation de résultat**
- Votre négligence sécuritaire engage votre responsabilité même si vous êtes victime

#### 5. Bundeskartellamt c. Meta (Allemagne, 2023)

**Faits** : Collecte de données hors Facebook (sites tiers) sans consentement.

**Décision** : Pratique anticoncurrentielle ET violation RGPD.

**Impact OSINT** :
- La corrélation de données provenant de multiples sources nécessite une base légale robuste pour chaque source
- La "mosaïque de données" (data aggregation) est scrutée

---

## Checklist de conformité

### ✅ Avant de démarrer l'investigation

```
PHASE DE PLANIFICATION :
├─ [ ] Finalité clairement définie et documentée
├─ [ ] Base légale identifiée (Article 6.1) et justifiée
├─ [ ] Test de proportionnalité réalisé (si intérêt légitime)
├─ [ ] PIR (Priority Intelligence Requirements) rédigés
├─ [ ] Périmètre de collecte défini (minimisation)
├─ [ ] Durée de conservation établie
├─ [ ] Mesures de sécurité planifiées
├─ [ ] Vérification des contraintes juridiques locales
├─ [ ] AIPD réalisée si nécessaire (traitement à grande échelle)
└─ [ ] Procédure de réponse aux droits des personnes prête
```

### ✅ Pendant la collecte

```
PHASE DE COLLECTE :
├─ [ ] Sources documentées avec horodatage
├─ [ ] Captures forensiques avec hash SHA-256
├─ [ ] Métadonnées conservées (origin, timestamp, collector)
├─ [ ] Pas de collecte de données sensibles sans justification impérative
├─ [ ] Respect des robots.txt et CGU des plateformes
├─ [ ] Pas de contournement de mesures techniques de protection
├─ [ ] Pas d'usurpation d'identité ou technique déloyale
├─ [ ] Chiffrement des données collectées
└─ [ ] Log des actions réalisées
```

### ✅ Pendant l'analyse

```
PHASE D'ANALYSE :
├─ [ ] Accès aux données restreint (need-to-know)
├─ [ ] Pas de traitement automatisé produisant effets juridiques sans supervision humaine
├─ [ ] Traçabilité du raisonnement analytique
├─ [ ] Pseudonymisation si possible
├─ [ ] Distinction claire : faits / inférences / hypothèses
└─ [ ] Logs d'accès aux données conservés
```

### ✅ Après l'investigation

```
PHASE DE CLÔTURE :
├─ [ ] Rapport final conforme (voir template reporting)
├─ [ ] Données inutiles supprimées (minimisation)
├─ [ ] Registre des traitements mis à jour
├─ [ ] Destruction sécurisée prévue à échéance
├─ [ ] Documentation conservée pour audit éventuel
└─ [ ] Procédure de réponse aux droits activable sur demande
```

### ✅ Checklist spécifique : Scraping

```
SI SCRAPING ENVISAGÉ :
├─ [ ] Vérifier robots.txt du site cible
├─ [ ] Vérifier CGU/ToS du site (clause anti-scraping ?)
├─ [ ] Privilégier APIs officielles si disponibles
├─ [ ] Rate limiting implémenté (< 1 req/seconde)
├─ [ ] User-Agent identifiable et honnête
├─ [ ] Pas de contournement de CAPTCHA ou authentification
├─ [ ] Limitation du volume (pas de scraping exhaustif)
├─ [ ] Base légale robuste (journalisme, recherche académique)
└─ [ ] Consultation juridique si doute
```

---

## Pièges à éviter

### ❌ Erreur 1 : "C'est public donc légal"

**Faux raisonnement** : "Cette personne a publié sa photo sur Instagram en mode public, donc je peux l'utiliser librement."

**Réalité juridique** : L'accessibilité publique ne constitue **ni un consentement, ni une renonciation aux droits RGPD**. Vous devez quand même identifier une base légale valide.

**Solution** : Appliquer systématiquement le test de proportionnalité (intérêt légitime).

### ❌ Erreur 2 : "Je ne stocke pas, donc pas de traitement"

**Faux raisonnement** : "Je consulte juste des profils LinkedIn sans rien sauvegarder, donc le RGPD ne s'applique pas."

**Réalité juridique** : La **consultation** est un traitement (Article 4.2). Dès que vous lisez un nom dans un objectif d'investigation, vous traitez une donnée personnelle.

**Solution** : Documenter même les consultations sans capture (via logs de navigation si investigation sensible).

### ❌ Erreur 3 : "C'est pour le bien, donc exception d'intérêt public"

**Faux raisonnement** : "J'enquête sur un fraudeur présumé, c'est d'intérêt public, donc base légale automatique."

**Réalité juridique** : L'exception "intérêt public" (Article 6.1.e) nécessite une **habilitation légale explicite** (vous devez être une autorité publique mandatée). Un acteur privé ne peut l'invoquer.

**Solution** : Utiliser "intérêt légitime" (6.1.f) et justifier la proportionnalité.

### ❌ Erreur 4 : "J'anonymise donc plus de RGPD"

**Faux raisonnement** : "Je remplace les noms par des codes, c'est anonyme."

**Réalité juridique** : La pseudonymisation ≠ anonymisation. Si vous conservez une table de correspondance ou si les données sont ré-identifiables par corrélation, le RGPD s'applique intégralement.

**Solution** : Présumer que vos données restent personnelles et appliquer le RGPD.

### ❌ Erreur 5 : "Je suis hors UE donc pas concerné"

**Faux raisonnement** : "Mon entreprise est aux USA, le RGPD ne me concerne pas."

**Réalité juridique** : Le RGPD a une **portée extraterritoriale** (Article 3.2) : si vous traitez des données de résidents UE, même depuis l'étranger, vous êtes soumis.

**Solution** : Vérifier systématiquement la localisation des personnes ciblées.

### ❌ Erreur 6 : "Le journalisme excuse tout"

**Faux raisonnement** : "Je suis journaliste donc exemption totale du RGPD."

**Réalité juridique** : L'exception journalistique (Article 85) est **partielle et conditionnée** :
- Finalité réellement journalistique (pas prétexte)
- Respect de la déontologie
- Balance avec vie privée au cas par cas

**Solution** : Documenter la finalité journalistique et l'intérêt public du sujet.

### ❌ Erreur 7 : "Je collecte pour un client, c'est sa responsabilité"

**Faux raisonnement** : "Je suis sous-traitant, mon client est responsable de la conformité RGPD."

**Réalité juridique** : Le sous-traitant a des **obligations propres** (Article 28) et une responsabilité conjointe en cas de violation. Vous ne pouvez vous défausser.

**Solution** : Contractualiser les responsabilités RGPD (Data Processing Agreement) et appliquer les mêmes standards.

---

## Ressources complémentaires

### Textes de référence

**Règlementation européenne** :
- [Règlement (UE) 2016/679 - RGPD](https://eur-lex.europa.eu/legal-content/FR/TXT/?uri=CELEX%3A32016R0679) (version consolidée)
- [Directive 2016/680 - "Police-Justice"](https://eur-lex.europa.eu/legal-content/FR/TXT/?uri=CELEX%3A32016L0680) (traitement par autorités compétentes)

**Droit français** :
- [Loi Informatique et Libertés](https://www.legifrance.gouv.fr/loda/id/JORFTEXT000000886460) (version consolidée, modifiée 2018-2019)
- [Décret n°2019-536](https://www.legifrance.gouv.fr/jorf/id/JORFTEXT000038528420) (modalités d'exercice des droits)

### Guides CNIL

- [Guide RGPD du développeur](https://www.cnil.fr/fr/guide-rgpd-du-developpeur) (principes transposables à l'OSINT)
- [Guide de la sécurité des données personnelles](https://www.cnil.fr/fr/securite-des-donnees-personnelles)
- [Registre des activités de traitement](https://www.cnil.fr/fr/RGDP-le-registre-des-activites-de-traitement)
- [AIPD - Modèles de la CNIL](https://www.cnil.fr/fr/modeles-pia)

### Jurisprudence consolidée

**Base CURIA** (CJUE) :
- [Google Spain (C-131/12)](https://curia.europa.eu/juris/liste.jsf?num=C-131/12)
- [Schrems II (C-311/18)](https://curia.europa.eu/juris/liste.jsf?num=C-311/18)
- [Wirtschaftsakademie (C-210/16)](https://curia.europa.eu/juris/liste.jsf?num=C-210/16)

**Décisions CNIL** :
- [Sanctions CNIL](https://www.cnil.fr/fr/les-sanctions-prononcees-par-la-cnil) (base de données publique)
- [Délibérations](https://www.legifrance.gouv.fr/search/jorf?tab_selection=jorf&query=%7B(%40ALL%5Bt%22cnil%22%5D)%7D&isAdvancedResult=true)

### Outils pratiques

**Templates et générateurs** :
- [Générateur de mentions RGPD](https://www.cnil.fr/fr/modele/rgpd/generateur-de-mentions) (CNIL)
- [Kit de conformité RGPD](https://www.cnil.fr/fr/kit-de-conformite-rgpd) (CNIL)
- [AIPD Toolbox](https://www.cnil.fr/fr/outil-pia-telechargez-et-installez-le-logiciel-de-la-cnil) (logiciel gratuit CNIL)

**Formation** :
- [MOOC CNIL - Atelier RGPD](https://atelier-rgpd.cnil.fr/) (gratuit, 5h, certificat)
- [Ressources EDPB](https://www.edpb.europa.eu/edpb_fr) (Comité Européen de la Protection des Données)

### Pour aller plus loin

**Ouvrages spécialisés** :
- BENSOUSSAN Alain, *Informatique et libertés : Guide pratique*, 2024
- DEBET Anne, *Protection des données personnelles : Le RGPD*, Dalloz, 2023

**Articles académiques** :
- FORGUES Romain, "OSINT et protection des données personnelles : Vers un cadre juridique adapté", *Revue Lamy Droit de l'Immatériel*, 2023
- MARINO Laure, "L'Open Source Intelligence face au RGPD : Quelle conciliation ?", *Légicom*, 2022

**Veille juridique** :
- [Newsletter CNIL](https://www.cnil.fr/fr/newsletters)
- [Blog Dalloz Actualité - Informatique et libertés](https://www.dalloz-actualite.fr/chronique/informatique-et-libertes)
- [EDPS Newsletter](https://edps.europa.eu/) (Contrôleur européen)

---

## Conclusion

Le RGPD n'est pas un obstacle à l'OSINT efficace, mais le **cadre de sa légitimité**. Une investigation méthodique, documentée et proportionnée démontre votre professionnalisme et protège simultanément :

1. **Les personnes ciblées** : Respect de leurs droits fondamentaux
2. **Votre organisation** : Protection contre sanctions et contentieux
3. **La qualité de votre renseignement** : Valeur probatoire préservée

**Principe directeur** : *Si vous ne pouvez pas justifier publiquement pourquoi vous avez collecté telle donnée sur telle personne, ne la collectez pas.*

La conformité RGPD n'est pas une checklist bureaucratique à cocher pour "être tranquille". C'est une **discipline intellectuelle** qui structure votre démarche investigative, améliore votre rigueur méthodologique, et garantit l'exploitabilité de vos conclusions.

**L'OSINT éthique et légale est l'OSINT crédible.**

---

## Navigation

📖 [Retour au sommaire principal](../README.md)  
🔍 [Guide de démarrage rapide](quick-start.md)  
⚖️ [Proportionnalité méthodologique](legal-ethical/proportionality.md)  
🔒 [OPSEC et protection de l'investigateur](legal-ethical/opsec.md)  
📋 [Templates de planification](../templates/planning-template.md)

---

**Document version** : 1.0  
**Dernière mise à jour** : Novembre 2025  
**Auteur** : thepinguin073  
**Licence** : Creative Commons BY-SA 4.0  
**Contact** : your.digital.trace@gmail.com

---

**⚠️ Avertissement légal** : Ce document est fourni à titre informatif uniquement et ne constitue pas un conseil juridique. Les praticiens OSINT doivent consulter un avocat spécialisé en protection des données pour évaluer leur situation spécifique. Les auteurs déclinent toute responsabilité en cas d'interprétation erronée ou d'application inadéquate des principes exposés.