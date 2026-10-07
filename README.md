# Persona 2: Batsu (Eternal Punishment) — Traducción al español

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Ficha del proyecto, capturas y más traducciones al castellano en **[Parches en Castellano](https://parchesencastellano.com/traducciones/playstation/persona-2-batsu)**.

Traducción al **español de España** de *Persona 2: Batsu* (ペルソナ2 罰, PlayStation, 2000),
el RPG de Atlus que en Occidente se conoce como *Eternal Punishment*. Es la continuación de
[*Persona 2: Tsumi*](https://github.com/johanderohan/persona-2-tsumi-traduccion-es), que también
está traducido. Se ha traducido directamente del japonés.

La traducción se distribuye como **parche**. No incluye el juego: necesitas tu propia copia
japonesa para aplicarlo.

## Estado

Última versión: **[v1.1](../../releases/tag/v1.1)**.

| Parte | Estado |
|---|---|
| Guion de eventos y diálogos de los mapas de la ciudad | 9.853 mensajes traducidos |
| Contacto con demonios, charlas de Persona y presentaciones de las Personas | 7.153 textos traducidos |
| Menús, objetos, demonios, habilidades, avisos, tarjeta de memoria y nombres de lugar | 3.749 textos traducidos |
| Mapas de las mazmorras y de la ciudad | Traducidos |
| Respuestas que se escriben con el teclado (acertijos y nombres) | Adaptadas a letras latinas |
| Caracteres españoles | **á é í ó ú ü ñ Á É Í Ó Ú Ü Ñ ¡ ¿ « »** |
| Revisión durante una partida | Parcial (ver abajo) |

Detalles técnicos:

- Fuente proporcional nueva, con el mismo color y sombra que la original.
- Los textos se codifican con parejas de letras por celda para que quepan en la memoria de la
  consola.
- Las respuestas que hay que escribir con el teclado admiten mayúsculas y minúsculas y un
  máximo de 8 letras, como en el original.

Se quedan como en el original:

- El logotipo, «PRESS ANY BUTTON», el menú del título y demás rótulos gráficos en inglés
  («SAVE», «LOAD», «CONFIGURATION MENU», «FILE», «TIME»…).
- Los vídeos, incluido el aviso de ficción del principio.

### Comprobaciones y trabajo pendiente

Se ha probado en emulador desde una partida nueva hasta la redacción de *Coolest*:

- La pregunta sobre los datos de *Tsumi*, la tarjeta de memoria y el prólogo.
- La escena del santuario, la reunión del Nuevo Orden Mundial y la redacción de Kismet.
- El menú de campo, objetos, opciones, guardar y cargar partida.

Además, cada archivo modificado se comprueba al construir: los textos caben en su sitio,
los guiones no superan la memoria disponible y los archivos de contacto se releen enteros
tras reconstruirlos. El parche se ha aplicado sobre el BIN japonés original y el resultado se
ha comparado byte a byte con la imagen probada.

**No se ha jugado una partida completa** ni se ha probado en consola real. Los combates, el
contacto con demonios, la Velvet Room, los mapas de la ciudad y el resto de la historia no se
han recorrido en las pruebas. La traducción y su revisión se han hecho con asistencia de IA,
sin revisores humanos independientes. Si encuentras un error, abre una incidencia con una
captura.

En la v1.1 se ha revisado todo el texto: se han traducido los textos que faltaban, se han
corregido erratas y se ha unificado la terminología con la de *Persona 2: Tsumi*. Los mapas de
las mazmorras y de la ciudad y los demás textos añadidos se han comprobado en los datos del
disco, pero todavía no dentro de una partida.

## Cambios

- **v1.1** (25-09-2026):
  - Se traducen los nombres de zonas y salas del mapa de las mazmorras y los rótulos del mapa
    de la ciudad, que en la v1.0 salían como letras sin sentido.
  - Se traducen otros textos que seguían en japonés: el primer mensaje de los cofres, la lista
    de encargos de búsqueda de personas, avisos de combate y la opción «Devolver» de la Velvet
    Room, entre otros.
  - Más espacio entre «FILE» y el número de archivo en el mensaje de carga.
  - Terminología revisada frente a la traducción de *Persona 2: Tsumi* («Museo de la Ciencia
    del Cielo», «Devolver», «zoroástrico»…).
  - Unas 130 correcciones de sentido, erratas, ortotipografía y coherencia.
- **v1.0** (25-09-2026): primera versión.

## Cómo aplicar el parche

1. Descarga el parche `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia de **Persona 2: Batsu (Japón) (Disco 1)**, SLPS-02825, en formato BIN/CUE
   de una sola pista.
3. **Comprueba que tu copia es la correcta** antes de nada:

   | | |
   |---|---|
   | Archivo | `Persona 2 - Batsu - Eternal Punishment (Japan) (Disc 1).bin` |
   | Tamaño | 725.145.120 bytes |
   | MD5 | `bb9a4558e7ab72bd5e32fcdd46c2363a` |

   ```bash
   md5sum "Persona 2 - Batsu - Eternal Punishment (Japan) (Disc 1).bin"            # Linux
   md5 "Persona 2 - Batsu - Eternal Punishment (Japan) (Disc 1).bin"               # macOS
   CertUtil -hashfile "Persona 2 - Batsu - Eternal Punishment (Japan) (Disc 1).bin" MD5   # Windows
   ```

   Si no coincide, el parche fallará o dará un resultado corrupto.
4. Aplica el parche con una de estas herramientas:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**: `xdelta3 -d -s "original.bin" parche.xdelta "Persona 2 - Batsu (ES).bin"`
5. Comprueba que el BIN resultante tiene el MD5 **`8451eb2c4c12426f6fa5804ec9181d0a`** (v1.1)
   y 754.761.504 bytes (es algo más grande que el original).
6. Crea un CUE para el nuevo BIN, por ejemplo `Persona 2 - Batsu (ES).cue`:

   ```
   FILE "Persona 2 - Batsu (ES).bin" BINARY
     TRACK 01 MODE2/2352
       INDEX 01 00:00:00
   ```

7. Carga el CUE en tu emulador y empieza una partida nueva.

Aplica el parche sobre el **BIN japonés original**, no sobre una copia ya parcheada.

## Aviso

Este proyecto es una traducción hecha por afición, sin ánimo de lucro y sin relación alguna
con Atlus ni SEGA. Aquí no se distribuye el juego ni ninguna parte de él: solo un parche que
modifica una copia que ya tengas.

Si eres el titular de los derechos y quieres que retire esto, abre una incidencia y lo hago.
