# TOTVS Protheus Dockerizado

Este projeto tem um objetivo de "dockerizar" os processos necessários para executar uma instância do ERP Protheus da TOTVS.

Você deve baixar os binários necessários para construção das imagens em https://suporte.totvs.com/download.

## Objetivos

Dockerizar:

- [x] TOTVS DBAccess 64bits
- [x] PostgreSQL 9.3 praparado para o Protheus
- [x] [DBMonitor](./dbmonitor/README.md)
- [x] TOTVS Protheus AppServer 64bits
- [ ] TOTVS License Server

## Guia rápico

Pré-requisitos:

* docker, docker-compose instalados e com acesso a um host docker;
* binários do dbaccess (ex.: 15-06-12-DBACCESS_LINUX64_20141119.TAR) para colocar na pasta `./dbaccess`.

<pre>
$ git clone https://github.com/endersonmaia/totvs-protheus-docker.git
$ cd totvs-protheus-docker
$ docker-compose up -d
...
$ docker-compose ps
             Name                           Command               State           Ports          
------------------------------------------------------------------------------------------------
totvsprotheusdocker_database_1   /docker-entrypoint.sh postgres   Up      5432/tcp               
totvsprotheusdocker_dbaccess_1   /docker-entrypoint.sh dbaccess   Up      0.0.0.0:7890->7890/tcp 
$ 

</pre>

Isso irá preparar um container com PostgreSQL 9.3 e outro com DBAccess 64bits, pronto para ser usado.

Basta abrir o TOTVS DBMonitor e apontar para o host que está rodando o Docker e a porta do dbacess (7890).

Veja [aqui](./dbmonitor/README.md) como rodar o DBMonitor dentro de um container.

## Passo a passo

__TODO__
