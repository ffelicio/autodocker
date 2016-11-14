FROM node:latest

RUN npm install bower -g

# Cria um usuário não root para criação de arquivos
ARG USER_PUID=1000
ARG USER_PGID=1000
ARG USER_NAME=${USER_NAME}
RUN groupadd -g $USER_PGID $USER_NAME && \
    useradd -u $USER_PUID -g $USER_NAME -m $USER_NAME    