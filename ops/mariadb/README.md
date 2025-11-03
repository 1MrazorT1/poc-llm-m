# Configuration MariaDB - POC Murata

## INFORMATIONS DE CONNEXION
- Host: 127.0.0.1
- Port: 3307  
- Database: poc_murata
- User: openmetadata
- Password: openmetadata_password
- Root access: sudo mysql -u root

## COMMANDES ESSENTIELLES

### Gestion du service
sudo systemctl status mariadb
sudo systemctl restart mariadb
sudo systemctl stop mariadb

### Connexion
mysql -h 127.0.0.1 -P 3307 -u openmetadata -p poc_murata
sudo mysql -u root

### Verification
ss -tlnp | grep 3307
sudo journalctl -u mariadb -f
mysql -h 127.0.0.1 -P 3307 -u openmetadata -p -e "SELECT 1;"

## INTEGRATION OPENMETADATA
Type: mysql
Host: 127.0.0.1
Port: 3307  
Database: poc_murata
Username: openmetadata
Password: openmetadata_password

## DEPANNAGE
- Erreur connexion: sudo systemctl status mariadb
- Port utilise: ss -tlnp | grep 3307  
- Logs: sudo journalctl -u mariadb
- Permission: sudo mysql -u root

## CONFIGURATION
- Fichier: /etc/mysql/mariadb.conf.d/50-server.cnf
- Port 3307 pour eviter conflit avec OpenMetadata (3306)
- Donnees: /var/lib/mysql/
