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
cp .env-example .env
```
3 - Abra seu arquivo **.env** em seu editor favorito e configure as variáveis de ambiente para cada contêiner.

Nesse arquivo, esta todas as variáveis relacionada a cada container que foi definido em seu arquivo `docker-compose.yml`.

> *Todas as variáveis estão com um valor padrão já definido, mas você pode alterar todos os valores*.

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

**PHP_FPM_INSTALL_ZIP_ARCHIVE**: *Habilita a extensão ZIP no container do PHP-FPM*
```
PHP_FPM_INSTALL_ZIP_ARCHIVE=false
```
**PHP_FPM_INSTALL_OPCACHE**: *Habilita a extensão OPCACHE no container do PHP-FPM*
```
PHP_FPM_INSTALL_OPCACHE=true
```

**PATH_APP**: *Endereço de pasta onde fica todas suas aplicações*
```
PATH_APP=./workspace
```
