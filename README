# Ansible Role: wordpress

Ce rôle Ansible installe et configure un site WordPress complet, avec Apache, PHP, MariaDB et les fichiers WordPress, de manière automatique et sécurisée.  
Il est compatible avec les distributions **Ubuntu/Debian** et **Rocky Linux/RedHat**.

---

## 📦 Fonctionnalités

- Installation des paquets requis (Apache, PHP, MariaDB, etc.)
- Téléchargement et déploiement de WordPress
- Configuration automatique de la base de données MariaDB
- Génération sécurisée du fichier `wp-config.php`
- Création d'un VirtualHost Apache dédié
- Compatible avec `a2ensite`, `a2enmod` (Ubuntu), ou configuration manuelle sur Rocky

---

## 🛠 Variables disponibles

### 🔧 Variables personnalisables (`defaults/main.yml`)

| Variable              | Description                                      | Valeur par défaut         |
|-----------------------|--------------------------------------------------|----------------------------|
| `db_root_password`    | Mot de passe du compte root MariaDB             | `"examplerootPW"`         |
| `db_name`             | Nom de la base de données WordPress             | `"wordpress"`             |
| `db_user`             | Utilisateur MariaDB à créer                     | `"example"`               |
| `db_user_password`    | Mot de passe de l'utilisateur MariaDB           | `"examplePW"`             |
| `wp_site_path`        | Répertoire d'installation de WordPress          | `"/var/www/html"`         |
| `wp_url`              | URL de téléchargement de l’archive WordPress    | `"https://wordpress.org/latest.zip"` |

### 📦 Variables internes (`vars/main.yml`)

Ces variables sont calculées automatiquement selon la distribution :

- `apache_service` : `apache2` (Debian) ou `httpd` (RedHat)
- `php_packages` : Liste de paquets PHP nécessaires
- `web_user` : `www-data` ou `apache`

---

## 🖥️ Plateformes compatibles

- Ubuntu 20.04 / 22.04
- Debian 11+
- Rocky Linux 8 / 9
- RHEL 8 / 9

---

## ▶️ Exemple de Playbook

```yaml
- name: Déployer WordPress
  hosts: webservers
  become: true
  roles:
    - role: wordpress
      vars:
        db_root_password: "MySecureRootPass"
        db_name: "mon_wp"
        db_user: "wpuser"
        db_user_password: "WpUserSecure123"
        wp_site_path: "/var/www/html"
