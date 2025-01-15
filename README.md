# secu-r-seau

- des tests
- configurer un hote virtuel sur mon mac

### commands ###
- mkdir Sites
- sudo apachectl start
- sudo nano /etc/apache2/httpd.conf
### activer ###
- LoadModule vhost_alias_module libexec/apache2/mod_vhost_alias.so
- LoadModule rewrite_module libexec/apache2/mod_rewrite.so
- Include /etc/apache2/extra/httpd-vhosts.conf

### commands ###
- sudo nano /etc/apache2/extra/httpd-vhosts.conf
<VirtualHost *:80>
    ServerName monprojet.local
    DocumentRoot "/Users/utilisateur/Sites/monprojet"
    <Directory "/Users/utilisateur/Sites/monprojet">
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>

- sudo nano /etc/hosts
- 127.0.0.1 monprojet.local

- chmod -R 755 /Users/utilisateur/Sites/monprojet

- echo "<h1>Bienvenue sur Projet 1</h1>" > /Users/utilisateur/Sites/monprojet/index.html

