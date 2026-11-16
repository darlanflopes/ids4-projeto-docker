# Ambiente de Desenvolvimento - IDS 4

Este repositório contém a configuração do Docker Compose para rodar os serviços locais do projeto sem depender de uma VPS

## Pré-requisitos
- Ter o [Docker Desktop](https://www.docker.com/) e rodando com WSL 2.

## Como rodar o ambiente

1. Clone o repositório em sua máquina:
```bash
git clone <url-do-repositorio>
```
2. Abra o terminal na pasta do projeto:
```bash
cd ids4-projeto-docker 
```
3. Suba os serviços localmente com o Docker Compose:
```bash
docker compose up -d
```
4. Para parar os serviços quando terminar:
```bash
docker compose down
```