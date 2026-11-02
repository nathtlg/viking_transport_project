# Projet Viking Transport

Site web de réservation de trajets en car en Normandie, développé en **HTML, CSS, JavaScript et PHP** avec une base de données **Oracle**.

> **Projet de groupe** réalisé dans le cadre de la **SAE 2.456** (fin de première année de BUT).

---

## Équipe
- [Toulorge Nathan](https://github.com/nathtlg)
- [Clement Simon](https://github.com/SimCLEMENT)
- [Munoz Paul](https://github.com/PaulMUNOZ14)
- Langlois Kylian
- Navarro Pierre
- [Wallaert-Beaugendre Noor](https://github.com/Lixmy)
- Ouasri Hamza

## Présentation 

Viking Transport est un site fictif de compagnie de transport permettant de :
 
- consulter le **réseau de lignes** sur une carte interactive, ainsi que les **horaires** et la **grille tarifaire** ;
- **créer un compte**, se connecter et gérer son profil (nom, mail, téléphone, ville) ;
- **réserver un trajet**, soit via une recherche rapide, soit en **construisant son trajet manuellement** (correspondances entre lignes, calcul de la durée et de l'heure d'arrivée) ;
- **payer** sa réservation (par carte bancaire) et obtenir une **confirmation avec un billet PDF** ;
- bénéficier d'un **programme de fidélité** (points, types de client, réductions) ;
- accéder à un **espace d'administration** : gestion des clients, des lignes et statistiques (chiffre d'affaires, répartition des clients, classements de points…).
---
## Technologies
 
- **Front :** HTML5, CSS3, JavaScript
- **Back :** PHP (PDO)
- **Base de données :** Oracle (script 'agile_5.sql')
- **Mise en page :** Bootstrap 5

## Structure du projet
 
```
viking_transport_project/
├── index.php                 # Page d'accueil
├── apropos.php               # Qui sommes-nous
├── contact.php               # Contact
├── agile_5.sql               # Script de création/remplissage de la base Oracle
├── administration/           # Espace admin (clients, lignes, statistiques)
├── auth/                     # Connexion, inscription, déconnexion
├── compte/                   # Espace client et modification du profil
├── reservation/              # Lignes, horaires, tarifs, réservation, paiement, PDF
├── JS/                       # Scripts JavaScript (affichage du mot de passe, inversion départ/arrivée)
├── PHP/                      # Fichiers communs (header, footer, connexion BDD, FPDF)
└── images/                   # Logos, bannières, arrière-plans
```
 
---
 
## Installation
 
### Prérequis
 
- PHP 8+ avec les extensions **PDO** et **PDO_OCI** (Oracle)
- Un accès à une base **Oracle**
- Un serveur web (Apache, ou serveur intégré de PHP)

### Étapes

1. **Cloner le dépôt**
```bash
   git clone https://github.com/<utilisateur>/viking_transport_project.git
   cd viking_transport_project
```
2. **Importer la base de données** en exécutant `agile_5.sql` sur votre instance Oracle.
3. **Configurer la connexion** à la base (identifiants, hôte, SID) dans `PHP/param_connexion.php`.
4. **Lancer le site** en prenant la racine du projet comme racine web (les liens utilisent des chemins absolus comme `/reservation/lignes.php`) :
```bash
   php -S localhost:8000
```
5. Ouvrir <http://localhost:8000>.
> Les identifiants de base de données ne doivent **pas** être publiés. Voir la section « Sécurité » plus bas.
 
---

## Éléments externes (non réalisés par l'équipe)
 
Pour être transparent sur l'origine du code et des ressources :
 
| Élément | Détail |
|---------|--------|
| `agile_5.sql` | Base de données Oracle (projet « VikingTransport ») générée et fournie par E. Porcq |
| `PHP/pdo_agile.php` | Fonctions utilitaires PDO fournies dans le cadre de la SAE |
| `PHP/param_connexion.php` | Modèle de paramètres de connexion Oracle/MySQL fourni (nous avons renseigné nos identifiants) |
| `PHP/connexion_pdo_5.php` | Programme d'exemple de connexion fourni |
| `PHP/traitement_form5.php` | Exemple de traitement de formulaire fourni |
| `PHP/1_1.php` | Fichier de test `phpinfo()` fourni |
 
### Bibliothèques et ressources tierces
 
| Élément | Auteur / source | Utilisation |
|---------|-----------------|-------------|
| [**FPDF 1.86**](http://www.fpdf.org/) (`PHP/fpdf.php`) | Olivier Plathey | Génération des billets de réservation en PDF |
| `PHP/font/` | Fourni avec FPDF | Polices utilisées par FPDF (Helvetica, Times, Courier, Symbol, ZapfDingbats) |
| [**Bootstrap 5.3.3**](https://getbootstrap.com/) | Équipe Bootstrap | Mise en page et composants (via CDN jsDelivr) |
| [**Bootstrap Icons 1.11.3**](https://icons.getbootstrap.com/) | Équipe Bootstrap | Icônes (via CDN jsDelivr) |
| [**Leaflet 1.9.4**](https://leafletjs.com/) | Vladimir Agafonkin et contributeurs | Carte interactive du réseau (via CDN unpkg) |
| [**OpenStreetMap**](https://www.openstreetmap.org/copyright) | Contributeurs OpenStreetMap | Fonds de carte (© OpenStreetMap contributors) |
| [**QR Server API**](https://goqr.me/api/) | goQR.me | Génération des QR codes |
 
### Images
 
| Fichier | Origine |
|---------|---------|
| `images/logo*.png` | Notre équipe |
| `images/arriere_plan_*.jpg`, `images/banniere_*.png`, `horaires.jpg`, `tarifs.jpg` | Génération IA |
| `images/carte.png` | Fourni par l'enseignant |
 
---
 
## Réalisé par l'équipe
 
- Conception et développement du site (pages, design, navigation)
- Système d'authentification, d'inscription et gestion du compte client
- Moteur de réservation (rapide et manuelle), calcul des durées et horaires
- Paiement, confirmation et mise en page du billet PDF (à partir de FPDF)
- Programme de fidélité
- Espace d'administration et statistiques
- Scripts JavaScript (`JS/`)
---
 
## Sécurité
 
Ce projet est un **projet pédagogique**. Avant toute mise en ligne ou réutilisation :
 
- ne jamais versionner de vrais identifiants de base de données (les externaliser dans un fichier non suivi par Git ou des variables d'environnement) ;
- le paiement par carte est **simulé**, aucune donnée bancaire réelle ne doit être saisie.
---
 
## Licence
 
Projet réalisé à des fins pédagogiques. Les bibliothèques tierces restent soumises à leurs licences respectives.


