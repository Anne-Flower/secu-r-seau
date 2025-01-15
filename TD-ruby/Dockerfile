#image officielle
FROM ruby:3.2

# dépendances
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs

# répertoire de travail
WORKDIR /app

# Copier les fichiers
COPY . .

# Installer les gems
RUN bundle install

# Exposer le port 3000 (ce port par défaut de Rails)
EXPOSE 3000

# Commande par défaut pour démarrer l'app
CMD ["rails", "server", "-b", "0.0.0.0"]
