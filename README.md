# Ambiente de Desenvolvimento - IDS 4

Este repositório contém a configuração do Docker Compose e do Dockerfile para rodar um ambiente local contendo ferramentas de monitoramento de rede (**Suricata** e **tcpdump**), sem depender de uma VPS.

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

3. Construa a imagem e suba os serviços em segundo plano com o Docker Compose:
```bash
docker compose up --build -d
```

4. Como acessar o container para usar as ferramentas (Suricata / tcpdump):
```bash
docker exec -it ids4-projeto-docker bash
```

5. Para parar os serviços quando terminar:
```bash
docker compose down
```