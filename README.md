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

## Sensor de rede (`ids-sensor`: Suricata e tcpdump)

O serviço `ids-sensor` é construído a partir do `Dockerfile` e sobe junto com o ambiente via `docker compose up --build -d` (ou `make up`), mantendo `postgres` e `redis` ativos.

- **Modo de execução:** o container inicia em modo interativo (`tail -f /dev/null`) para desenvolvimento e testes manuais, permitindo abrir um shell e executar `suricata` ou `tcpdump` sob demanda sem encerrar o container.
- **Permissões de rede:** utiliza `NET_ADMIN` e `NET_RAW` para permitir captura e análise de tráfego.
- **Diretórios mapeados:** `./suricata-logs` (`/var/log/suricata`) e `./captures` (`/captures`).

### Como acessar e testar as ferramentas

1. Abra um terminal dentro do serviço `ids-sensor`:
```bash
docker compose exec ids-sensor
```
