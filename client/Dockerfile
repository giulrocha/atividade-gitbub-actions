# Etapa 1: Build da aplicação Angular
FROM node:18 AS build
WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

# Etapa 2: Servidor Nginx para servir os arquivos estáticos
FROM nginx:alpine
COPY --from=build /app/dist/<nome-da-pasta> /usr/share/nginx/html

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
