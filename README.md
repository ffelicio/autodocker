## Autodocker

O `autodocker` é um ambiente de desenvolvimento para `PHP` utilizando `DOCKER`.

* [Introdução](#introducao)
* [Container](#container)
* [Requisitos](#requisitos)
* [Instalação](#instalacao)
* [Estrutura de pastas](#estrutura-de-pastas)
* [Variáveis de ambiente](#variaveis-de-ambiente)
* [Configuração](#configuracao)
	* [Acessando containeres](#acessando-container)
	* [Mapeando aplicações](#mapeando-aplicacoes)
	* [Criando virtual-hosts](#criando-virtualhost)
* [Comandos](#comandos)
* [Licensa](#licenca)


<a name="introducao"></a>
## Introdução
O `autodocker` é um ** SIMPLES ** ambiente de desenvolvimento para aplicações em `PHP`, onde as configurações são feitas por variáveis de ambiente (`.env`).

<a name="container"></a>
## Container
`php 5.6 ou 7.0 + composer ` `mysql 5.7` `nginx` `redis` `mongodb` `node + npm + bower` 

<a name="requisitos"></a>
## Requisitos
* Git
* Docker
* Docker Compose

<a name="instalacao"></a>
## Instalação
A instalação é muito facil, basta você dar um `git clonar` desse repositório em qualquer diretório do seu sistema operacional.

<a name="estrutura-de-pastas"></a>
## Estrutura de pastas
...

<a name="variaveis-de-ambiente"></a>
## Variáveis de ambiente
Para configurar as variáveis de ambiente é preciso seguir os seguites passos:

Execute o seguinte comando para gerar uma copia do arquivo `.env-example` que esta na raiz do **autodocker**: 

``` shell
cp .env-example .env
```

No arquivo `.env` esta todas as variáveis relacionada a cada container que foi definido em seu arquivo `docker-compose.yml`.

> **Nota**: Todas as configurações serão feita nesse aquivo que foi copiado (`.env`), o mesmo não é versionado.

<a name="configuracao"></a>
## Configuração
...

<a name="acessando-container"></a>
## Acessando container
...

<a name="mapeando-aplicacoes"></a>
## Mapeando aplicações
...

<a name="criando-virtualhost"></a>
## Criando virtual-host
...

<a name="comandos"></a>
## Comandos
...

<a name="licenca"></a>
## Licença

O `autodocker` é um software livre distribuído sob os termos da licença do MIT.