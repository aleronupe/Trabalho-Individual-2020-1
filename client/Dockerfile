FROM node:lts-alpine

# faz da pasta 'app' o diretório atual de trabalho
WORKDIR /app

# copia os arquivos 'package.json' e 'package-lock.json' (se disponível)
COPY package*.json ./

# instala dependências do projeto
RUN yarn install --all

# copia arquivos e pastas para o diretório atual de trabalho (pasta 'app')
COPY . .
