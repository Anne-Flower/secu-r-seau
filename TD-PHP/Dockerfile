FROM php:7.2-apache

RUN apt-get update -qq && apt-get install -y build-essential libpq-dev

# répertoire de travail
WORKDIR /var/www/html

# Copier les fichiers
COPY src/ /var/www/html/
#COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

# Installer le module Apache mod_rewrite 
#RUN a2enmod rewrite

#droits
#RUN chown -R www-data:www-data /var/www/html

# Exposer le port 80 => apache 443 => SSL
EXPOSE 80
EXPOSE 443

# Commande par défaut pour démarrer l'app
CMD ["apache2-foreground"]
