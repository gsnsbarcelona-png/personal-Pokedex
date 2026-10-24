# Proyecto 151

Colección de cartas Pokémon estilo Pokédex: los 151 de Kanto en hojas de 9 bolsillos, como un álbum real. Es un único archivo (`index.html`), sin frameworks y sin instalación.

## Qué hace

- Marca qué cartas tienes y cuáles son full art, tocando cada bolsillo (FA para full art).
- Filtra por Todas, Faltan, Tengo y Full art, y busca por nombre o número.
- Muestra el progreso total y por hoja (17 hojas de 9).
- Escanea una carta con la cámara o desde la galería. Primero recortas la carta, y el OCR lee el nombre, el número y el código de rareza (`SR`, `SAR`…). Si no reconoce el Pokémon, lo eliges tú buscando por nombre o número.
- Guarda tu foto recortada en el hueco. Marcar o no full art no cambia la imagen, solo el borde.
- En el detalle de cada carta (botón `⋯`) puedes anotar idioma, set o nota y un precio aproximado propio, que suma en el valor total.
- Descarga y carga una copia de tus datos.

## Publicarlo en GitHub Pages

1. Crea un repositorio y sube `index.html` (y este `README.md`) a la raíz.
2. Ve a **Settings → Pages**.
3. En **Source** elige **Deploy from a branch**, rama `main`, carpeta `/ (root)`.
4. Espera un minuto y abre la dirección `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`.

La cámara solo funciona con `https`, y GitHub Pages ya lo incluye.

## Cómo se usa

| Acción | Cómo |
| --- | --- |
| Marcar o desmarcar una carta | Tocar el bolsillo |
| Marcar full art | Botón `FA` del bolsillo (también marca la carta como tuya) |
| Ver o editar el detalle | Botón `⋯` del bolsillo |
| Escanear | Botón rojo **Escanear** → **Abrir cámara** o **Foto o galería** |
| Pasar los datos a otro dispositivo | **Copia y ajustes** → **Descargar copia**, y **Cargar copia** en el otro |

### Escáner

1. Elige el idioma de la carta (Español / Inglés, o Chino simplificado).
2. Encuadra una sola carta con el nombre bien visible y buena luz.
3. Elige el candidato correcto. Si no aparece, búscalo por nombre o número.
4. Marca si es full art, revisa el idioma y pulsa **Guardar como mía**.

El OCR (Tesseract.js) se descarga la primera vez que escaneas, así que necesita conexión y tarda unos segundos. No siempre acierta, por eso siempre te pide confirmar.

## Dónde se guardan los datos

Todo se guarda **solo en el navegador** donde lo uses (`localStorage`): marcas, notas, precios y fotos en miniatura. Si borras los datos del sitio o cambias de navegador, se pierden. Descarga la copia de vez en cuando.

## Datos de partida

El archivo incluye tu colección inicial (61 cartas, 7 full art). Se usa solo la primera vez. Después manda lo que haya guardado el navegador. Para empezar de cero con otros datos, edita las listas `SEED_HAVE` y `SEED_FA` al final de `index.html`.

## Servicios externos

Ninguna API de cartas ni de precios. Solo se descargan:

- **Tesseract.js** (vía jsDelivr) para leer el texto de la carta, la primera vez que escaneas.
- **Google Fonts** para las tipografías.

## Limitaciones conocidas

- Una carta por foto.
- No identifica la versión exacta ni el precio: el precio lo pones tú.
- Los nombres en chino simplificado están escritos a mano, y alguno puede fallar.
- No hay sincronización entre dispositivos, solo la copia manual.
