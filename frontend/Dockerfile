FROM node:lts-alpine

# Defina o diretório de trabalho
WORKDIR /app

# Copia arquivos de dependências
COPY package*.json ./

# Instale as dependênciass
RUN npm install

# Copie todo o projeto para o container
COPY . .

# Construa a aplicação
RUN npm run build

# Exponha a porta
EXPOSE 8080

# Use http-server para servir o conteúdo da pasta dist
RUN npm install -g http-server

CMD ["http-server", "dist"]