# centro-integral-amarte

## Activar disponibilidad compartida

La página funciona como formulario de solicitud aunque Firebase no esté configurado. Para activar el bloqueo compartido de horarios:

1. Crea un proyecto Firebase y una base de datos Cloud Firestore.
2. En Firebase Authentication, habilita el proveedor de acceso anónimo.
3. Registra una aplicación web en Firebase y copia su configuración pública en `firebase-config.js`. No uses una clave de cuenta de servicio en el navegador.
4. Publica las reglas de `firestore.rules` desde Firebase Console o con `firebase deploy --only firestore:rules`.
5. Activa FormSubmit para `integralamarte@gmail.com` al recibir su primer correo de confirmación.

Los documentos de `bookingSlots` contienen solo metadatos del horario, nunca nombre, correo ni teléfono. Una solicitud retenida queda como `pending`; hasta que exista una pantalla administrativa, el centro debe eliminar su documento desde Firestore para liberar ese horario si no se confirma.