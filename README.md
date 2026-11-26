# Centro Holístico Integral Amarte

Sitio estático para presentar cursos, talleres y terapias del centro.

## Consultas y reservas

Cada tarjeta incluye un enlace de WhatsApp con el nombre del servicio. Las fechas, disponibilidad y detalles se coordinan directamente con el centro. Los precios publicados corresponden a sesiones o cursos individuales; no se anuncian packs ni cobros de reserva.

## Imágenes

Las imágenes de servicios y espacios identificadas como referenciales son fotografías de stock; no representan el local, las terapeutas ni a clientes del centro. Se pueden sustituir por fotografías propias cuando estén disponibles. Fuentes: [masaje de cabeza, Pexels](https://www.pexels.com/photo/a-therapist-massaging-a-woman-s-head-5794045/), [masaje craneal, Pexels](https://www.pexels.com/photo/hands-of-a-person-massaging-a-woman-s-head-lying-on-bed-6187301/), [Reiki, Pexels](https://www.pexels.com/photo/woman-lying-on-the-floor-having-therapy-6998275/), [flores y frascos, Pexels](https://www.pexels.com/photo/healthy-relaxation-flowers-yellow-7526012/), [oficina, Pexels](https://www.pexels.com/photo/modern-office-space-with-indoor-plants-28461045/), [sala de spa, Pexels](https://www.pexels.com/photo/massage-table-in-the-room-6628473/). Biomagnetismo usa una ilustración propia claramente identificada. Ver [licencia de Pexels](https://www.pexels.com/license/).

## Reseñas

La sección “Experiencias de Clientes” muestra reseñas públicas recibidas en Firestore. El formulario registra la autorización explícita junto con cada reseña y la publica automáticamente al enviarse. Las reseñas más recientes aparecen primero. Para retirar una, cambia su `status` a `rejected` en Firebase Console → Firestore Database → base `reviews` → colección `reviews`.

La conexión usa el proyecto Firebase `centro-integral-amarte` y la base Enterprise `reviews`, en `southamerica-west1`. La configuración web está en `firebase-config.js`; las reglas e índices se mantienen en `firestore.rules` y `firestore.indexes.json`. Publicación: `npx -y firebase-tools@latest deploy --only firestore --project centro-integral-amarte`.

### Protección contra spam

Las reseñas se publican automáticamente, por lo que App Check no está aplicado todavía. El sitio ya permite configurarlo: registra la app web en Firebase App Check con reCAPTCHA Enterprise, agrega la clave pública del sitio en `appCheckSiteKey` dentro de `firebase-config.js`, publica el cambio y activa App Check para Cloud Firestore en modo de monitoreo antes de aplicar enforcement. App Check ayuda a filtrar tráfico no autorizado; no reemplaza una limitación de frecuencia del lado del servidor. La clave reCAPTCHA es pública y va en el sitio; no publiques ninguna clave secreta de Enterprise.

## Publicación

El sitio se publica en GitHub Pages al actualizar la rama `main`. Las imágenes se cargan desde `assets/`.
