# Centro Holístico Integral Amarte

Sitio estático para presentar cursos, talleres y terapias del centro.

## Consultas y reservas

Cada tarjeta incluye un enlace de WhatsApp con el nombre del servicio. El catálogo no solicita datos personales ni administra horarios; las fechas, disponibilidad y detalles se coordinan directamente con el centro. El curso de Biomagnetismo usa el WhatsApp indicado para ese curso; las demás consultas usan el número general.

## Reseñas

La sección “Experiencias de Clientes” muestra una reseña por vez y permite recorrerlas con flechas. El formulario envía reseñas a la colección `reviews` de Cloud Firestore con estado `pending`; solo las reseñas aprobadas aparecen en el sitio. Para moderar, revisa cada documento en Firebase Console y cambia `status` a `approved` o `rejected`.

La conexión está configurada con el proyecto Firebase `centro-integral-amarte` y la base Enterprise `reviews`, alojada en Santiago (`southamerica-west1`). La configuración web está en `firebase-config.js`; las reglas e índices se mantienen en `firestore.rules` y `firestore.indexes.json`. Para volver a publicar reglas e índices, ejecuta `npx -y firebase-tools@latest deploy --only firestore --project centro-integral-amarte`.

Las reseñas nuevas se guardan como `pending` y no aparecen públicamente hasta que se aprueban. Para moderarlas, abre Firebase Console → Firestore Database → `reviews` → colección `reviews`, y cambia `status` a `approved` o `rejected`.

## Publicación

El sitio se publica en GitHub Pages al actualizar la rama `main`. Las imágenes del catálogo se guardan en `assets/` y se cargan desde el propio repositorio.
