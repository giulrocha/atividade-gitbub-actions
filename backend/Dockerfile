FROM node:18
WORKDIR /usr/src/app

# Instala dependências
COPY package*.json ./
RUN npm install --production

# Copia o restante do código
COPY . .

# Define variáveis de ambiente (ajuste conforme seu backend)
ENV PORT=5000
EXPOSE 5000

CMD ["node", "server.js"]
