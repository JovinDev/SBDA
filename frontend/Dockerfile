FROM node:lts-alpine

# Defina o diretório de trabalho
WORKDIR /app

# Copia arquivos de dependências
COPY app/package*.json ./

# Instale as dependênciass
RUN npm install

# Copie todo o projeto para o container
COPY /app .

# Construa a aplicação
RUN npm run build

# Exponha a porta
EXPOSE 3000:3000

# Use http-server para servir o conteúdo da pasta dist
RUN npm install -g http-server

CMD ["http-server", "dist"]