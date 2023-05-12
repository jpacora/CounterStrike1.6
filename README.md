# Imagem do Docker para servidor dedicado Counter Strike 1.6

## Iniciar o servidor

### Configuração de propriedades mínimas

```bash
docker run -d -p 26900:26900/udp -p 27020:27020/udp -p 27015:27015/udp -p 27015:27015 -e ADMIN_STEAM=0:1:1234566 --name cs cs16ds/server:latest
```

### Configuração de todas as propriedades
```bash
docker run -d -p 26900:26900/udp -p 27020:27020/udp -p 27015:27015/udp -p 27015:27015 -e MAXPLAYERS=32 -e START_MAP=de_dust2 -e SERVER_NAME="Nome do meu servidor" - e START_MONEY=16000 -e BUY_TIME=0.25 -e FRIENDLY_FIRE=1 -e ADMIN_STEAM=0:1:1234566 --name cs cs16ds/server:latest +log
```

#### Propriedades

| Nome | Descrição | Valor padrão |
| --- | --- | --- |
| `MAXPLAYERS` | O número máximo de jogadores | `32` |
| `START_MAP` | O mapa inicial | `de_dust2` |
| `SERVER_NAME` | O nome do servidor | `Servidor Counter-Strike 1.6` |
| `START_MONEY` | O dinheiro inicial | `800` |
| `BUY_TIME` | O tempo permitido para comprar itens em cada rodada (*minutos*) | `0,25` |
| `FRIENDLY_FIRE` | Ative ou desative o fogo amigo. (*desligado: 0, ligado: 1*) | `1` |
| `SERVER_PASSWORD` | A senha do servidor. (*Vazio para nenhuma senha do servidor*) | Nenhum |
| `RCON_PASSWORD` | A senha rcon. (*Vazio para senha sem rcon*) | Nenhum |
| `RESTART_ON_FAIL` | *A definir* | *A definir* |
| `ADMIN_STEAM` | *A ser definido - relacionado ao mod amx*| *A definir* |

## Pare o servidor

```bash
docker stop cs
```

## Iniciar servidor existente (parado)

```bash
docker start cs
```

## Remova o servidor

```bash
docker rm cs
```

## Alterações do projeto original

* Mudou o nome da compilação.
* Adicionado novos mapas.
* Adicionado novos parâmetros no script de execução.
