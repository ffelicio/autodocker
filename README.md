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

2 - Altere o nome do arquivo **.env-example** para **.env** que esta na raiz do projeto **autodocker**
```shell
cp .env-example .env
```
3 - Abra seu arquivo **.env** em seu editor favorito e configure as variáveis de ambiente para cada contêiner.

No arquivo `.env` esta todas as variáveis relacionada a cada contêiner que foi definido em seu arquivo `docker-compose.yml`.

> *Todas as variáveis estão com um valor padrão já definidos, mas você pode alterar todos os valores*.

Segue abaixo uma descrição de cada variável em seu arquivo `.env`

**PHP_FPM_PORT**: *Aponte em qual porta o seu* **PHP-FPM** *vai ser executado.*	
```
PHP_FPM_PORT=9002
```

**PHP_FPM_INSTALL_XDEBUG**:  *Habilita a extensão do* **XDEBUG** *no container do PHP-FPM*
```
PHP_FPM_INSTALL_XDEBUG=false
```

**PHP_FPM_INSTALL_MONGO**: *Habilita a extensão do* **MONGODB** *no container do PHP-FPM*
```
PHP_FPM_INSTALL_MONGO=false
```

**PHP_FPM_INSTALL_ZIP_ARCHIVE**: *Habilita a extensão* **ZIP** *no container do PHP-FPM*
```
PHP_FPM_INSTALL_ZIP_ARCHIVE=false
```
**PHP_FPM_INSTALL_OPCACHE**: *Habilita a extensão* **OPCACHE** *no container do PHP-FPM*
```
PHP_FPM_INSTALL_OPCACHE=true
```

**USER_NAME**: *Criação de um usuário padrão para alguns contêineres*
```
USER_NAME=autodocker
```

**PATH_APP**: *Endereço de pasta onde fica todas suas aplicações*
```
PATH_APP=./workspace
```

4 - As imagens de cada contêiner esta localizado na pasta `imagens/$container`. Acesse cada uma e renomeie os arquivos de configurações.

**PHP FPM 5.6**
```
cp images/php-fpm/56/example-php.ini php.ini;
cp images/php-fpm/56/example-www.conf www.conf;
```
**PHP FPM 7.0**
```
cp images/php-fpm/70/example-php.ini php.ini;
cp images/php-fpm/70/example-www.conf www.conf;
```
**Nginx**
```
cp images/nginx/example-nginx.conf nginx.conf;
```
**Redis**
```
cp images/redis/example-redis.conf redis.conf;
```
**Mongo**
```
cp images/mongo/example-mongo.conf mongo.conf;
```
**Mysql**
```
cp images/mysql/my-example.cnf my.cnf;
```

## Comandos

Depois de fazer todas as configurações necessárias, finalmente você pode subir os contêineres = D.

Subindo todos os contêineres de uma vez:
```
docker-compose up
```

Subindo contêineres especificos:
```
docker-compose up mysql mongo
```

Visualizando contêineres que estão sendo executados:
```
docker-compose ps
```

##Licença

O **Autodocker** é um software livre distribuído sob os termos da licença do MIT.
