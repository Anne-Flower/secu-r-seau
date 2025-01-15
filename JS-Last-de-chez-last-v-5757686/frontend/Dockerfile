FROM node:20-alpine3.20 AS base
RUN echo "Base image: node:20-alpine3.20"
COPY --chown=node:node ./package*.json ./
WORKDIR /app
RUN npm i
COPY --chown=node:node . .
EXPOSE 5173


# Étape 1 : Environnement de développement
FROM base AS development
RUN echo NODE_ENV: development
RUN npm install --only=dev
CMD ["npm", "run", "dev"]

# Étape 2 : Environnement de build
FROM base AS build
RUN echo NODE_ENV: build
CMD ["npm", "run", "build"]

FROM node:20-alpine3.20 AS production
RUN echo NODE_ENV: production
WORKDIR /app
COPY --chown=node:node .env .
COPY --from=base /app/package*.json .  
COPY --from=build /app/node_modules ./node_modules
COPY --from=build /app/dist ./dist
CMD ["npm", "run", "preview"]