# Archivo de la Inquisición — cómo publicarlo en GitHub Pages

Archivos de esta carpeta:

| Archivo | Para qué sirve |
|---|---|
| `index.html` | La página |
| `firebase-config.js` | Los datos de tu proyecto de Firebase (hay que rellenarlo) |
| `seed.json` | Los datos del Excel, para importarlos una vez |
| `firestore.rules` | Las reglas de seguridad (se pegan en Firebase, no hace falta subirlas) |

## 1. Firebase (la base de datos)

1. Entra en https://console.firebase.google.com y pulsa **Crear un proyecto** (por ejemplo `inquisicion`). Google Analytics no hace falta.
2. Menú **Compilación → Firestore Database → Crear base de datos**. Elige una ubicación en Europa y el **modo de producción**.
3. En Firestore, pestaña **Reglas**: borra lo que haya, pega el contenido de `firestore.rules`, cambia `tu-correo@gmail.com` por tu correo de Google y pulsa **Publicar**.
4. Menú **Compilación → Authentication → Comenzar**. En **Método de acceso**, activa **Google**.
5. Rueda dentada → **Configuración del proyecto** → abajo, **Tus apps** → icono `</>` (web). Ponle un nombre y, sin marcar Hosting, pulsa **Registrar app**. Copia los valores de `firebaseConfig`.
6. Abre `firebase-config.js` con el Bloc de notas, pega esos valores y pon tu correo en `window.DUENO`.

## 2. GitHub Pages (la web)

1. En https://github.com pulsa **New repository**. Ponle un nombre (por ejemplo `inquisicion`), márcalo como **Public** y pulsa **Create repository**.
2. Pulsa **uploading an existing file** y arrastra `index.html`, `firebase-config.js` y `seed.json`. Pulsa **Commit changes**.
3. En el repositorio: **Settings → Pages**. En *Branch*, elige `main` y la carpeta `/ (root)`, y pulsa **Save**. En uno o dos minutos la web estará en `https://TU-USUARIO.github.io/inquisicion/`.
4. Vuelve a Firebase → **Authentication → Configuración → Dominios autorizados → Agregar dominio** y añade `TU-USUARIO.github.io`.

## 3. Primera vez

1. Abre tu web y pulsa **Entrar con Google** con tu correo (el de dueño).
2. En la pestaña **Resumen** verás el panel **Acceso** con el botón **Importar datos del Excel**. Púlsalo dos veces para confirmarlo. Solo se hace una vez.
3. En ese mismo panel, escribe los correos de Google de tus amigos, uno por línea, y pulsa **Guardar lista**.
4. Mándales el enlace. Entran con su cuenta de Google y ya pueden editar.

## Cosas a saber

- La página la puede abrir cualquiera, pero sin estar en la lista solo verá el botón de entrar: no podrá leer ni cambiar nada.
- El plan gratuito de Firebase (Spark) da de sobra para un grupo de amigos.
- Para cambiar la página más adelante, sube el `index.html` nuevo al repositorio (Add file → Upload files) y sustituye el antiguo. Los datos no se tocan.
