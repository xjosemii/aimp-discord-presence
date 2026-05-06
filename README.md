# AIMP Discord Presence fork de xjosemi

<p align="center">
  <img src=".github/aimp-discord-312.png" alt="AIMP Discord Presence">
</p>

Este repositorio es un fork personal del plugin original de [Exle](https://github.com/Exle/aimp-discord-presence) para [AIMP](https://aimp.ru/).

La idea de este fork es mantener el comportamiento del plugin original, pero corrigiendo los puntos que hoy daban problemas al compilarlo, cargarlo en AIMP y mostrar la actividad en Discord.

## Que hace

El plugin actualiza el Rich Presence de Discord segun lo que se este reproduciendo en AIMP.

En este fork la actividad se envia como `listening`, asi que en Discord aparece como reproduciendo en lugar de jugando.

## Mejoras de esta version

- cambia el tipo de actividad de Discord a `listening`
- corrige la carga del plugin dentro de AIMP
- recompila el proyecto sin depender del wrapper C++ que faltaba en el repo original
- integra `discord-rpc` dentro del arbol del proyecto para poder compilarlo desde cero
- anade comentarios en las zonas delicadas del codigo para que el mantenimiento sea mas simple
- actualiza el autor visible del plugin a `Exle - xjosemi`

## Cambios tecnicos importantes

- se reconstruyo la capa minima de integracion con el SDK de AIMP
- los servicios de AIMP se obtienen del `core` por `QueryInterface`
- se corrigio el puntero exportado del plugin para que AIMP reciba la interfaz correcta
- se parcheo la serializacion de `discord-rpc` para poder enviar el tipo de actividad

## Instalacion

1. Abre AIMP
2. Entra en `Opciones > Complementos`
3. Pulsa `Instalar`
4. Selecciona el archivo `.aimppack`
5. Activa el plugin
6. En Discord activa la opcion para compartir actividad si la tienes deshabilitada

## Configuracion

La configuracion se guarda en el perfil de AIMP dentro de `AIMP.ini`.

Valores por defecto:

```ini
[DiscordPresence]
ApplicationID=429559336982020107
Timestamp=0
UseAlbumArt=1
State.PlayImage=aimp_play
State.PauseImage=aimp_pause
State.RadioImage=https://raw.githubusercontent.com/Exle/aimp-discord-presence/main/.github/aimp_icons/animated/aimp_radio_v2.gif
State.UsePlay=0
State.UsePause=0
State.UseRadio=1
```

## Version actual

Version `1.1.1`

## Creditos

- plugin original por Exle
- mantenimiento de este fork y ajustes de compilacion por xjosemi
