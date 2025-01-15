#image officielle
FROM ruby:2.6

# dépendances
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs
RUN gem install rails
# répertoire de travail
 WORKDIR /app

# Copier les fichiers
COPY . .

# Installer les gems
# RUN bundle install

# Exposer le port 3000 (ce port par défaut de Rails)
EXPOSE 3000

# Commande par défaut pour démarrer l'app
CMD ["rails", "server", "-b", "0.0.0.0"]
# CMD ["sh", "-c", "while true; do sleep 1000; done"]