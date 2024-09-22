# Étape 1 : Utilisation d'une image Node.js pour builder l'application Angular
FROM node:18 AS build
WORKDIR /app
COPY . .
RUN npm install --legacy-peer-deps
RUN npm run build --prod


# Étape 2 : Utilisation de Nginx pour servir les fichiers Angular générés
FROM nginx:alpine
COPY --from=build /app/dist/angular-app /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
