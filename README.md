# quirogaj · Aplicaciones para Android y Android TV

Sitio estático en español. Las páginas usan HTML, una hoja de estilos compartida y un script para el año del pie. GitHub Pages sirve los archivos directamente desde la raíz.

## Vista local

Con Python 3, abre una terminal en la raíz del repositorio y ejecuta:

```sh
python -m http.server 8000 --bind 127.0.0.1
```

Abre [la portada local](http://127.0.0.1:8000/). Detén el servidor con Ctrl+C.

## Organización

| Archivo o carpeta | Contenido |
| --- | --- |
| `index.html` | Portada, tarjetas y sección de contacto |
| `photo-saver/`, `sweet-dreams-tv/` | Fichas de aplicación, cada una con una página en `privacidad/` |
| `parejas-locas/` | Ficha del juego, con páginas en `privacidad/` y `terminos/` |
| `css/styles.css`, `js/main.js` | Estilos compartidos y año dinámico |
| `assets/icons/`, `assets/images/` | Favicon, iconos e ilustraciones provisionales |
| `sitemap.xml`, `robots.txt`, `.nojekyll` | Indexación y entrega directa de los archivos |

## Editar el contenido y agregar aplicaciones

1. Actualiza la tarjeta de portada y la ficha correspondiente. Conserva el estado visible de disponibilidad y separa las funciones disponibles de las previstas.
2. Sustituye los iconos e ilustraciones por archivos oficiales cuando estén disponibles. Para capturas, usa WebP cuando convenga, actualiza dimensiones y texto alternativo y cambia la leyenda. Los iconos junto al nombre pueden conservar el atributo `alt=""`.
3. Sustituye el aviso de Google Play por un enlace cuando exista la ficha real de la aplicación. Agrega el canal de contacto verificado a la portada y a las políticas que lo usen.
4. Para agregar una aplicación, copia una carpeta de ficha con su subcarpeta de privacidad y elige un nombre de URL corto con guiones. Edita el título, descripción, contenido, metadatos Open Graph, URL canónica, recursos y enlaces. Añade la tarjeta a la portada, incorpora la ficha y su política en los pies y registra la ficha en el sitemap. Las rutas relativas dependen de la profundidad de la página.

## Finalizar las políticas de privacidad

Los borradores tienen rutas estables, etiqueta `noindex` y quedan fuera del sitemap. Antes de publicar, confirma para cada aplicación los datos que se tratan y su finalidad, permisos y sus usos, SDK, servicios externos, transferencias, publicidad, analítica, almacenamiento, retención y eliminación, además del contacto de privacidad. Actualiza el texto y la fecha de revisión. Al finalizar cada política, quita las marcas de borrador y la etiqueta `noindex`, incorpora su URL al sitemap y actualiza los enlaces que la mencionan.

## Publicar en GitHub Pages

1. Completa las políticas y revisa la navegación, los recursos, los datos de contacto y el estado de las fichas antes de publicar.
2. Crea el repositorio público `quirogajqa.github.io` en la cuenta `quirogajqa`. Si vas a subir este repositorio local por primera vez, ejecuta:

   ```sh
   git add .
   git commit -m "Crear sitio de quirogaj"
   git branch -M main
   git remote add origin https://github.com/quirogajqa/quirogajqa.github.io.git
   git push -u origin main
   ```

   Para cambios posteriores, agrega los archivos modificados, crea un commit y ejecuta `git push`.

3. En **Settings → Pages**, selecciona **Deploy from a branch** y guarda la rama `main` con la carpeta `/ (root)`.
4. Cuando GitHub muestre un despliegue correcto, comprueba la portada, las tres fichas y sus enlaces legales desde una ventana privada. En particular, abre `/parejas-locas/`, `/parejas-locas/privacidad/` y `/parejas-locas/terminos/`. Verifica los enlaces del pie y la carga de imágenes.

Si la portada también devuelve 404, confirma que la URL corresponde a la cuenta y al repositorio correctos, y que **Settings → Pages** muestra un despliegue correcto. Si la portada carga pero falla una ficha, comprueba que su carpeta y su `index.html` estén en la rama y carpeta que Pages publica.
