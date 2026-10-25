# Archivo de la Inquisición

Web de la partida de D&D en Barovia: https://pikuapequeu.github.io/inquisicion/

- La página es `index.html`. Los datos se guardan en Firebase (proyecto `inquisicion-barovia-4643`) y se actualizan en tiempo real para todos.
- Para entrar hay que usar una cuenta de Google que esté en la lista de acceso. El dueño la gestiona desde la pestaña **Resumen → Acceso**.
- `seed.json` tiene los datos originales del Excel. El dueño los importa una sola vez con el botón **Importar datos del Excel**, que solo aparece si el archivo está vacío.
- Las reglas de seguridad de Firestore no están en este repositorio; se despliegan aparte con `firebase deploy --only firestore:rules`.
