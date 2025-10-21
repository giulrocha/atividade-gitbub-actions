# Etapa 1: Build da aplicação Angular
FROM node:18 AS build
WORKDIR /app

# Copia o package.json e instala dependências
COPY package*.json ./
RUN npm install

# Copia o restante do código e gera o build de produção
COPY . .
RUN npm run build --prod

# Etapa 2: Servidor Nginx para servir os arquivos estáticos
FROM nginx:alpine
COPY --from=build /app/dist/angular-ecommerce-app /usr/share/nginx/html

# Copia o arquivo default.conf, se quiser personalizar rotas
# COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
