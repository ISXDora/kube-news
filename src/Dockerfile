#importância do versionamento da imagem base para garantir idempotência
FROM node:20.10.0-alpine3.18
RUN adduser -D isadoraxavier
WORKDIR /app
# Aproveitando os recursos de construção de camadas da imagem, vamos copiar e instalar primeiro as depêndencias do projeto
COPY package*.json .
# Só vai executar a instalação dos pacotes, se houver alteração das dependencias de pacotes
RUN npm install 
COPY . .
EXPOSE 8080
# non-user root
USER isadoraxavier
CMD [ "node", "server.js" ]