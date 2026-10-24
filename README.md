# Proyecto 151

Colección de cartas Pokémon estilo Pokédex: los 151 de Kanto en hojas de 9 bolsillos, como un álbum real. Es un único archivo (`index.html`), sin frameworks y sin instalación.

## Qué hace

- Marca qué cartas tienes y cuáles son full art, tocando cada bolsillo (FA para full art).
- Filtra por Todas, Faltan, Tengo y Full art, y busca por nombre o número.
- Muestra el progreso total y por hoja (17 hojas de 9).
- Escanea una carta con la cámara o desde la galería. Lee con OCR el nombre y el número (`025/165`), busca la carta exacta en TCGdex y te propone candidatas para que confirmes.
- Guarda la carta real (imagen oficial, set, rareza y precio aproximado) en su hueco, y suma el valor aproximado de la colección.
- En el detalle de cada carta (botón `⋯`) puedes anotar idioma y set, actualizar el precio, y ver todas las versiones ordenadas por precio para decidir si merece la pena mejorarla. «Es la mía» fija la versión que tienes.
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

Todo se guarda **solo en el navegador** donde lo uses (`localStorage`): marcas, notas y fotos en miniatura. Si borras los datos del sitio o cambias de navegador, se pierden. Descarga la copia de vez en cuando.

## Datos de partida

El archivo incluye tu colección inicial (61 cartas, 7 full art). Se usa solo la primera vez. Después manda lo que haya guardado el navegador. Para empezar de cero con otros datos, edita las listas `SEED_HAVE` y `SEED_FA` al final de `index.html`.

## Servicios externos

- **TCGdex** (`api.tcgdex.net`, sin clave) para identificar la carta escaneada, con cartas en español, inglés, chino y japonés. No todos los sets están en todos los idiomas: si no hay en el tuyo, prueba en inglés.
- **pokemontcg.io** para la lista de versiones con precios (respaldo: TCGdex). Funciona sin clave (1.000 consultas al día). Con una clave gratuita sube a 20.000, y se pone en **Copia y ajustes**. Cubre sobre todo sets en inglés, así que cartas de otros idiomas pueden no aparecer. Los precios son orientativos (Cardmarket en euros o TCGplayer en dólares).
- **Tesseract.js** (vía jsDelivr) para leer el nombre de la carta.
- **Google Fonts** para las tipografías.

## Limitaciones conocidas

- Una carta por foto.
- Los nombres en chino simplificado están escritos a mano, y alguno puede fallar.
- No hay sincronización entre dispositivos, solo la copia manual.
