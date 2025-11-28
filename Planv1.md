# PLAN.md

⚠️ **Disclaimer** : Ce plan est un "living plan" il est voué à changer/s'améliorer ⚠️

## Plan d’action – Déploiement Grafana, Prometheus, Stack LAMP & Grafonnet

## 1. Objectifs du projet
- Mettre en place une stack de supervision utilisant **Prometheus** et **Grafana**.  
- Déployer une infrastructure **LAMP (Linux, Apache, MySQL, PHP)**.  
- Industrialiser la création de dashboards Grafana via **Grafonnet**.

---

## 2. Architecture cible
1. Une machine/VM pour la stack LAMP.  
2. Une machine/VM dédiée à Prometheus.  
3. Une machine/VM dédiée à Grafana.  
4. (Optionnel) Un dépôt Git pour gérer les dashboards Jsonnet (Grafonnet).

---

## 3. Étapes du projet

### 3.1 Préparation de l’environnement
- Définir les ressources nécessaires (CPU, RAM, stockage).  
- Installer l’OS (Ubuntu/Debian/CentOS).  
- Mettre à jour les paquets.  
- Sécuriser l’accès SSH.

---

### 3.2 Déploiement de la stack LAMP
- Installer Apache2.  
- Installer et configurer MySQL/MariaDB.  
- Installer PHP et modules associés.  
- Déployer une application de test (phpinfo, mini-site).  
- Vérifications de bon fonctionnement.

---

### 3.3 Installation et configuration de Prometheus
- Installer Prometheus sur une VM dédiée.  
- Installer et configurer :
  - `node_exporter` (VM LAMP)  
  - `apache_exporter`  
  - `mysqld_exporter`  
- Configurer `prometheus.yml` pour scraper les cibles.  
- Vérifier la collecte via l'interface Prometheus.

---

### 3.4 Installation et configuration de Grafana
- Installer Grafana sur une VM dédiée.  
- Configurer la datasource Prometheus.  
- Vérifier la connexion Grafana → Prometheus.

---

### 3.5 Industrialisation des dashboards avec Grafonnet
- Installer Jsonnet et Grafonnet.  
- Créer un dépôt Git pour les dashboards.  
- Développer un premier dashboard Jsonnet (CPU, RAM, Apache, MySQL).  
- Générer les dashboards JSON à partir des sources Jsonnet.  
- Automatiser le déploiement des dashboards :  
  - via API Grafana  
  - ou via GitOps (optionnel).

---

### 3.6 Tests & validation
- Vérifier la remontée des métriques Prometheus.  
- Vérifier l’affichage des dashboards Grafana.  
- Tester une montée en charge (ex : `ab`, `stress`).  
- Contrôler les variations visibles sur les graphiques.

---

### 3.7 Documentation finale
- Rédiger un README complet.  
- Décrire l’installation, la configuration et les automatisations Grafonnet.  
- Documenter la procédure d’ajout/modification de dashboards.

---

## 4. Livrables
- `PLAN.md`  
- Infrastructure LAMP opérationnelle  
- Instances Prometheus et Grafana fonctionnelles  
- Exporters configurés  
- Dashboards Grafonnet + sources Jsonnet  
- Documentation finale

