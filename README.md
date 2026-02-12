# Projet Traitement du Signal - ESCAPE NO GAME 🎯

[![Repository](https://img.shields.io/badge/GitHub-Projet--traitement--du--signal-blue)](https://github.com/MishaD06/Projet-traitement-du-signal)

## 📋 Description du Projet

Projet académique réalisé dans le cadre d'un cours de traitement du signal. Ce projet propose une solution innovante de communication basée sur les ondes sonores pour permettre à un agent infiltré de transmettre des informations depuis un environnement isolé (sans accès réseau).

**Contexte :** L'agent K57, coincé dans une salle de conférence sans accès réseau, doit pouvoir communiquer vers l'extérieur en utilisant uniquement un microphone branché au système d'audioconférence.

**Solution proposée :** Système de communication par ondes sonores utilisant la modulation FSK (Frequency Shift Keying) dans les hautes fréquences inaudibles.

## 👥 Équipe

- **Misha DOPRE** (@MishaD06)
- **Alexis DUPONT**
- **Adem BRAHIM**

## 🎓 Contexte Académique

Ce projet s'inscrit dans le cadre du département Recherche et Développement de l'agence fictive AIL3C (Agence Indépendante de Lutte Contre la CyberCriminalité). Il a été réalisé en 4 livrables progressifs couvrant différents aspects du traitement du signal.

## 🚀 Fonctionnalités Principales

### ✅ Transmission de Données
- ✓ Conversion texte → binaire (ASCII)
- ✓ Encodage Manchester pour synchronisation
- ✓ Modulation FSK (18 kHz et 19 kHz pour bits 1 et 0)
- ✓ Alternative : Modulation ASK (35 kHz)
- ✓ Génération de signaux audio inaudibles

### ✅ Réception et Décodage
- ✓ Démodulation FSK/ASK
- ✓ Décodage Manchester
- ✓ Conversion binaire → texte (ASCII)
- ✓ Détection d'erreurs (CRC)
- ✓ Accusé de réception (liaison Half-Duplex)

### ✅ Fonctionnalités Avancées
- ✓ CRC (Cyclic Redundancy Check) pour détection d'erreurs
- ✓ Encapsulation dans trames PPP (Point-to-Point Protocol)
- ✓ Visualisation graphique des signaux
- ✓ Diagrammes de Bode pour analyse fréquentielle

## 📂 Structure du Projet

```
Projet-traitement-du-signal/
│
├── Livrable 1, Projet, Traitement du signal.ipynb  # Proposition de solution
├── Livrable 1, Projet, Traitement du signal.pdf    # Version PDF du livrable 1
├── Livrable 2, Groupe 5, Traîtement du signal.pdf  # Étude filtre analogique
├── Livrable 3, Traitement du signal.ipynb          # Chaîne de transmission complète
├── Livrable 4, Traitement du signal.ipynb          # Prototype POC fonctionnel
├── Diagramme de bode.ipynb                         # Analyse fréquentielle
├── schema émetteur-1.png                           # Schéma émetteur
├── schema récepteur-1-1.png                        # Schéma récepteur
└── README.md                                       # Ce fichier
```

## 🔧 Technologies Utilisées

### Langages & Outils
- **Python 3.12.4**
- **Jupyter Notebook** - Environnement de développement et présentation

### Bibliothèques Python
```python
import numpy as np              # Calculs numériques
import matplotlib.pyplot as plt # Visualisation de signaux
import sounddevice as sd        # Lecture/enregistrement audio
```

### Concepts de Traitement du Signal
- Modulation FSK (Frequency Shift Keying)
- Modulation ASK (Amplitude Shift Keying)
- Encodage Manchester
- CRC (Cyclic Redundancy Check)
- Protocole PPP
- Diagrammes de Bode
- Filtrage analogique (ordre 2)

## 📖 Livrables du Projet

### Livrable 1 : Proposition de Solution
**Objectif :** Proposer une solution de communication utilisant les ondes sonores

**Contenu :**
- Contexte et problématique
- Caractéristiques des ondes sonores
- Solution technique proposée
- Justifications scientifiques

### Livrable 2 : Étude de la Réponse Fréquentielle
**Objectif :** Valider la faisabilité technique par filtrage analogique

**Contenu :**
- Conception d'un filtre passe-bande (ordre 2)
- Fonction de transfert et analyse théorique
- Dimensionnement des composants
- Diagramme de Bode
- Simulation sur LTSpice/CircuitJS

### Livrable 3 : Chaîne de Transmission Complète
**Objectif :** Décrire l'ensemble de la chaîne de transmission

**Contenu :**
- Schémas émetteur/récepteur
- Détail de chaque étape de traitement
- Choix techniques justifiés (FSK, Manchester, PPP)
- Impact selon type de données (texte, fichier, son)
- Protocole de communication

### Livrable 4 : Prototype Fonctionnel (POC)
**Objectif :** Démontrer la viabilité de la solution par modélisation Python

**Fonctionnalités implémentées :**
- Transmission texte (5-10 caractères)
- Mode Simplex
- Détection d'erreurs (CRC)
- Segmentation en trames
- Accusé de réception (Half-Duplex)
- Modulation FSK et ASK
- Visualisation des signaux

## 🎯 Caractéristiques Techniques

### Paramètres de Modulation FSK
- **Fréquence d'échantillonnage** : 44 100 Hz
- **Fréquence porteuse bit 1** : 18 000 Hz (inaudible)
- **Fréquence porteuse bit 0** : 19 000 Hz (inaudible)
- **Débit** : 600 bits/s

### Paramètres de Modulation ASK
- **Fréquence d'échantillonnage** : 44 100 Hz
- **Fréquence porteuse** : 35 000 Hz (inaudible)
- **Débit** : 600 bits/s

### Protocole CRC
- **Clé CRC** : `11010` (polynôme générateur)
- **Méthode** : Division euclidienne avec XOR

## 🚀 Installation et Utilisation

### Prérequis
```bash
Python 3.12+
Jupyter Notebook ou JupyterLab
```

### Installation des Dépendances
```bash
pip install numpy matplotlib sounddevice
```

### Lancement des Notebooks
```bash
jupyter notebook
```

Ouvrir le notebook souhaité :
- **Livrable 1** pour la présentation conceptuelle
- **Livrable 3** pour comprendre la chaîne de transmission
- **Livrable 4** pour le prototype fonctionnel

### Utilisation du Prototype (Livrable 4)

#### 1️⃣ Émission d'un Message
```python
# Le notebook vous demandera d'entrer un message
Message = str(input('Entrez le message à envoyer : '))

# Exécutez les cellules dans l'ordre pour :
# - Convertir le texte en binaire
# - Encoder en Manchester
# - Moduler en FSK/ASK
# - Générer et jouer le son
```

#### 2️⃣ Réception du Message
```python
# Le notebook démodule automatiquement le signal
# et reconstruit le message original avec vérification CRC
```

## 📊 Exemple de Fonctionnement

### Message : "j'ai besoin d'aide"

1. **Conversion ASCII → Binaire**
   ```
   j'ai besoin d'aide → 01101010 00100111 01100001 01101001...
   ```

2. **Encodage CRC**
   ```
   Ajout du checksum pour détection d'erreurs
   ```

3. **Encodage Manchester**
   ```
   Chaque bit devient une paire de transitions
   0 → 01 | 1 → 10
   ```

4. **Modulation FSK**
   ```
   Bit 1 → Onde sinusoïdale 18 kHz
   Bit 0 → Onde sinusoïdale 19 kHz
   ```

5. **Émission Audio**
   ```
   Le signal est joué par les haut-parleurs (inaudible)
   ```

6. **Réception & Décodage**
   ```
   Démodulation → Décodage Manchester → Vérification CRC → Texte
   ```

7. **Résultat**
   ```
   Message décodé : j'ai besoin d'aide
   Accusé de réception envoyé (5000 Hz, 0.2s)
   ```

## 📈 Visualisations Disponibles

Le projet génère plusieurs graphiques pour analyser les signaux :

- **Signal Manchester** : Représentation binaire encodée
- **Signal modulé FSK/ASK** : Onde modulée avant émission
- **Signal démodulé** : Signal reçu après démodulation
- **Diagramme de Bode** : Analyse fréquentielle du filtre

## 🔬 Concepts Scientifiques Appliqués

### 1. Encodage Manchester
Technique d'encodage qui garantit une transition à chaque bit, facilitant la synchronisation entre émetteur et récepteur.

### 2. Modulation FSK
Modulation numérique utilisant deux fréquences distinctes pour représenter 0 et 1. Avantages :
- Robustesse au bruit
- Pas de synchronisation de phase nécessaire
- Simplicité de démodulation

### 3. Cyclic Redundancy Check (CRC)
Méthode de détection d'erreurs basée sur une division polynomiale. Permet de vérifier l'intégrité des données transmises.

### 4. Filtrage Analogique
Conception d'un filtre passe-bande pour isoler les fréquences porteuses du signal utile.

## 🎓 Apprentissages Clés

Ce projet couvre les aspects suivants du traitement du signal :

- ✅ Conversion analogique/numérique
- ✅ Techniques de modulation (FSK, ASK)
- ✅ Encodage de canal (Manchester)
- ✅ Détection d'erreurs (CRC)
- ✅ Analyse fréquentielle (Bode)
- ✅ Protocoles de communication (PPP)
- ✅ Traitement numérique du signal (Python)

## 🔮 Perspectives d'Amélioration

Le livrable 4 propose plusieurs pistes d'évolution :

1. **Chiffrement** : Ajout d'un chiffrement (Morse, César, etc.) pour sécuriser les communications
2. **Filtre numérique** : Implémentation d'un filtre passe-bande numérique à la réception
3. **Transmission de fichiers** : Support de fichiers binaires volumineux
4. **Gestion du bruit** : Amélioration de la robustesse face aux perturbations
5. **Communication bidirectionnelle** : Passage en mode Full-Duplex
6. **Correction d'erreurs** : Code de Reed-Solomon ou autres codes correcteurs

## 📝 Notes Techniques

### Fréquences Choisies
Les fréquences de 18-19 kHz (FSK) et 35 kHz (ASK) ont été sélectionnées car :
- **Inaudibles** pour l'oreille humaine (limite ~20 kHz)
- **Sous-échantillonnage** possible à 44.1 kHz (théorème de Nyquist)
- **Distinction facile** entre les deux fréquences FSK

### Débit de 600 bits/s
Ce débit permet :
- Une transmission suffisamment rapide
- Une robustesse face aux perturbations
- Un nombre d'échantillons suffisant par symbole (Ns = Fe/baud = 73.5)

## 🤝 Contribution

Ce projet est un travail académique réalisé en groupe. Les contributions sont organisées selon les livrables :

- **Livrable 1** : Conception et proposition de solution
- **Livrable 2** : Étude théorique du filtrage
- **Livrable 3** : Documentation de la chaîne de transmission
- **Livrable 4** : Implémentation du prototype
