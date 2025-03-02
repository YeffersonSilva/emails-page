# Backend de Envío de Emails para Landing Page

Este proyecto implementa un backend para envío de emails utilizando Node.js, Express y Nodemailer, diseñado para integrarse con una landing page.

## Características

- Servidor Express para manejar peticiones HTTP
- Envío de emails con Nodemailer
- Formulario de contacto HTML para pruebas
- Configuración mediante variables de entorno
- Soporte para CORS

## Requisitos

- Node.js (v12 o superior)
- Cuenta de correo electrónico (Gmail recomendado)

## Instalación

1. Clona este repositorio o descarga los archivos
2. Instala las dependencias:

```bash
npm install
```

3. Configura las variables de entorno:
   - Crea un archivo `.env` en la raíz del proyecto
   - Añade las siguientes variables:

```
PORT=3001
EMAIL_USER=tu_email@gmail.com
EMAIL_PASS=tu_contraseña_de_aplicacion
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_FROM=tu_email@gmail.com
EMAIL_TO=destinatario@ejemplo.com
```

> **Nota**: Si utilizas Gmail, necesitarás generar una "contraseña de aplicación" en la configuración de seguridad de tu cuenta de Google.

## Uso

1. Inicia el servidor:

```bash
node server.js
```

2. Accede al formulario de prueba en tu navegador:

```
http://localhost:3001
```

3. Para integrar con tu landing page, realiza peticiones POST a:

```
http://localhost:3001/api/send-email
```

Con el siguiente formato JSON:

```json
{
  "name": "Nombre del usuario",
  "email": "email@ejemplo.com",
  "subject": "Asunto del mensaje (opcional)",
  "message": "Contenido del mensaje"
}
```

## Integración con tu Landing Page

Para integrar este backend con tu landing page existente, puedes:

1. Utilizar fetch o axios para realizar peticiones POST desde tu frontend
2. Configurar CORS adecuadamente si tu frontend está en un dominio diferente
3. Personalizar el formato del email en el archivo `server.js`

## Despliegue

Para desplegar en producción:

1. Configura las variables de entorno en tu servidor
2. Utiliza un gestor de procesos como PM2:

```bash
npm install -g pm2
pm2 start server.js
```

3. Configura un proxy inverso (Nginx, Apache) para servir el backend

## Licencia

MIT
