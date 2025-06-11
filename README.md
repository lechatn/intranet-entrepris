# Projet : Intranet d'Entreprise

## 📌 Présentation

Ce projet vise à mettre en place une infrastructure complète pour un intranet d'entreprise auto-hébergé. Il inclut un ensemble de services essentiels accessibles via un portail interne sécurisé :

- **Annuaire LDAP** pour la gestion centralisée des utilisateurs et groupes
- **phpLDAPadmin** pour l'administration graphique de l'annuaire
- **Nextcloud** comme cloud privé pour le partage de fichiers, la gestion d’agenda et de contacts
- **Serveur mail** (Postfix + Dovecot) avec envoi et réception
- **Serveur web Apache2** pour héberger les pages internes (dont la page de management)
- **Gestion d’accès PAM** intégrée à LDAP (authentification centralisée)
- **Portail de management** interface d'accès simplifiée

---

## 🛠️ Technologies utilisées

| Composant         | Outils / Services              |
|-------------------|-------------------------------|
| **Web Server**    | Apache2                       |
| **Cloud Privé**   | Nextcloud                     |
| **Annuaire LDAP** | OpenLDAP                      |
| **Interface LDAP**| phpLDAPadmin                  |
| **Mail Server**   | Postfix (SMTP), Dovecot (IMAP)|
| **Base de données** | MariaDB                     |
| **Sécurité**      | SSH (clé uniquement)          |

---

## 🧩 Arborescence des services

/var/www/html/management => Page centrale de gestion
/var/www/nextcloud => Cloud personnel (Nextcloud)

---

## 🔐 Sécurité mise en place

- Connexion SSH uniquement par clé
- Permissions strictes sur les fichiers sensibles

---

## 🚀 Lancer l’infrastructure

1. Démarrer tous les services :
   ```bash
   sudo systemctl start apache2
   sudo systemctl start slapd
   sudo systemctl start postfix dovecot
   sudo systemctl start nginx

2. Accéder aux services :

http://localhost:8080/management : Portail de gestion

http://localhost:8080 : Cloud personnel

http://localhost:8080/phpldapadmin : Interface LDAP