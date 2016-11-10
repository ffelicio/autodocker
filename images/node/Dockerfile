FROM node:latest

RUN npm install bower -g

# Cria um usuário não root para criação de arquivos
ARG PUID=1000
ARG PGID=1000
RUN groupadd -g $PGID autodocker && \
    useradd -u $PUID -g autodocker -m autodocker