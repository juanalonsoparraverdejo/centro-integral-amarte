# Centro Holístico Integral Amarte

Sitio estático para presentar cursos, talleres y terapias del centro.

## Consultas y reservas

Cada tarjeta incluye un enlace de WhatsApp con el nombre del servicio. El catálogo no solicita datos personales ni administra horarios; las fechas, disponibilidad y detalles se coordinan directamente con el centro. El curso de Biomagnetismo usa el WhatsApp indicado para ese curso; las demás consultas usan el número general.

## Reseñas

La sección “Experiencias de Clientes” muestra una reseña por vez y permite recorrerlas con flechas. El formulario envía reseñas a la colección `reviews` de Cloud Firestore con estado `pending`; solo las reseñas aprobadas aparecen en el sitio. Para moderar, revisa cada documento en Firebase Console y cambia `status` a `approved` o `rejected`.

Para activar la función:

1. Registra una aplicación web en el proyecto Firebase del centro y copia sus datos en `firebase-config.js`.
2. Activa Cloud Firestore en Firebase Console.
3. Publica `firestore.rules` en las reglas de Firestore (o ejecuta `firebase deploy --only firestore:rules` desde Firebase CLI).
4. Vuelve a desplegar el sitio en GitHub Pages.

Mientras `firebase-config.js` mantenga valores `REEMPLAZAR_...`, el carrusel conserva la reseña de ejemplo, pero el formulario avisa que aún no está habilitado. Las reseñas enviadas no se publican automáticamente.

## Publicación

El sitio se publica en GitHub Pages al actualizar la rama `main`. Las imágenes del catálogo se guardan en `assets/` y se cargan desde el propio repositorio.
