## Autodocker

### O que é Autodocker ?

Autodocker é um **SIMPLES** ambiente de desenvolvimento em **PHP** utilizando **docker**.

### Contêineres

- PHP-FPM (5.6, 7.0)
    - Composer
    - PHPUnit
- Node
    - NPM
    - Bower
- Nginx
- Mysql
- Redis
- Mongo


### Requisitos
- Git
- Docker
- Docker Composer


### Instalação e configuração do ambiente
1 - Clone esse repositório para qualquer diretório da sua maquina.
```shell
git clone git@github.com:danilosilva87/autodocker.git
```
2 - Altere o nome do arquivo **.env-example** para **.env** que esta na raiz do projeto **autodocker**
```shell
mv .env-example .env
```
3 - Abra seu arquivo **.env** em seu editor favorito e configure as variáveis de ambiente para cada contêiner.

Exemplo:

*Apontando em qual porta seu php-fpm vai ser executada na sua maquina.*

```
PHP_FPM_PORT=9002
```

*Por padrão esse endereço esta apontando para a pasta workspace que fica dentro da pasta do **autodocker**, mas você pode colocar seu próprio endereço.
*
```
PATH_APP=./workspace
```

As extensões também podem ser habilitada aqui.
```
PHP_FPM_INSTALL_XDEBUG=false
PHP_FPM_INSTALL_MONGO=false
PHP_FPM_INSTALL_ZIP_ARCHIVE=false
PHP_FPM_INSTALL_MEMCACHED=false
PHP_FPM_INSTALL_OPCACHE=true
```