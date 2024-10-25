# Imagen de Docker para servidor dedicado de Counter-Strike 1.6

## Iniciar el servidor

### Configuración mínima

```bash
docker run -d -p 26900:26900/udp -p 27020:27020/udp -p 27015:27015/udp -p 27015:27015 -e ADMIN_STEAM=0:1:1234566 --name cs jpacora/cs1.6:latest
```

### Configuración completa

```bash
docker run -d -p 26900:26900/udp -p 27020:27020/udp -p 27015:27015/udp -p 27015:27015 -e MAXPLAYERS=32 -e START_MAP=de_dust2 -e SERVER_NAME="Nombre de mi servidor" -e START_MONEY=16000 -e BUY_TIME=0.25 -e FRIENDLY_FIRE=1 -e ADMIN_STEAM=0:1:1234566 --name cs jpacora/cs1.6:latest +log
```

#### Propiedades

| Nombre            | Descripción                                                                       | Valor predeterminado           |
| ----------------- | --------------------------------------------------------------------------------- | ------------------------------ |
| `MAXPLAYERS`      | Número máximo de jugadores                                                        | `32`                           |
| `START_MAP`       | Mapa inicial                                                                      | `de_dust2`                     |
| `SERVER_NAME`     | Nombre del servidor                                                               | `Servidor Counter-Strike 1.6`  |
| `START_MONEY`     | Dinero inicial                                                                    | `800`                          |
| `BUY_TIME`        | Tiempo para comprar objetos en cada ronda (*minutos*)                             | `0,25`                         |
| `FRIENDLY_FIRE`   | Activar o desactivar fuego amigo (*desactivado: 0, activado: 1*)                  | `1`                            |
| `SERVER_PASSWORD` | Contraseña del servidor (*Vacío si no tiene*)                                     | Ninguna                        |
| `RCON_PASSWORD`   | Contraseña RCON (*Vacío si no tiene*)                                             | Ninguna                        |
| `RESTART_ON_FAIL` | *Por definir*                                                                     | *Por definir*                  |
| `ADMIN_STEAM`     | *Por definir - relacionado con el mod AMX*                                        | *Por definir*                  |

## Detener el servidor

```bash
docker stop cs
```

## Iniciar un servidor existente (detenido)

```bash
docker start cs
```

## Eliminar el servidor

```bash
docker rm cs
```

## Cambios respecto al proyecto original

* Cambiado el nombre de la compilación.
* Añadidos nuevos mapas.
* Añadidos nuevos parámetros en el script de ejecución.
