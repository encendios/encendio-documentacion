### Documentación para Desarrolladores del Proyecto Mobile Encendio Backend

#### Índice

1. [Introducción](#introducción)
2. [Estructura del Proyecto](#estructura-del-proyecto)
3. [Configuración del Entorno de Desarrollo](#configuración-del-entorno-de-desarrollo)
4. [Uso de Docker](#uso-de-docker)
5. [Scripts Disponibles](#scripts-disponibles)

---

### Introducción

**Mobile Encendio Backend** es el backend para la aplicación móvil de Encendio, desarrollado con Node.js y Express. Proporciona servicios API para gestionar actividades, usuarios, tareas, imágenes, frases y más, utilizando MongoDB como base de datos principal.

### Estructura del Proyecto

La estructura del proyecto está organizada de la siguiente manera:

```
.
├── app.js
├── config/
│   ├── ci_test.js
│   ├── default.js
│   ├── game_values/
│   ├── production.js
│   └── progression-settings.js
├── controllers/
│   ├── activity.controller.js
│   ├── auth.controller.js
│   ├── ...
│   └── word.controller.js
├── custom-logger.js
├── database/
│   ├── apply-game-config.js
│   ├── config.js
│   └── redis.js
├── docker-compose.yml
├── Dockerfile
├── install_temp/
│   ├── devdb.dump
│   └── ...
├── Jenkinsfile
├── jest.config.js
├── middlewares/
├── models/
│   ├── Activity.js
│   ├── ...
│   └── Word.js
├── openapi/
├── package.json
├── periodic_jobs/
│   └── league.js
├── public/
├── routes/
│   ├── activity.route.js
│   ├── ...
│   └── word.route.js
├── server.js
├── src/
│   ├── auth/
│   ├── game/
│   ├── image/
│   └── keycloak/
└── test/
    ├── activity.route.test.js
    └── ...
```

- **config/**: Contiene la configuración del entorno y ajustes específicos de la aplicación.
- **controllers/**: Contiene los controladores para las diferentes rutas y funcionalidades del backend.
- **database/**: Archivos relacionados con la configuración y conexión a la base de datos.
- **middlewares/**: Middleware personalizado para validación y manejo de peticiones.
- **models/**: Modelos de Mongoose para definir esquemas de datos y realizar operaciones CRUD.
- **openapi/**: Especificaciones OpenAPI para la documentación de la API.
- **public/**: Archivos estáticos que se sirven desde el servidor.
- **routes/**: Definición de las rutas API del backend.
- **src/**: Código fuente adicional dividido en módulos.
- **test/**: Archivos de pruebas unitarias y de integración.

### Configuración del Entorno de Desarrollo

1. **Instalación de dependencias**:
   Ejecuta el siguiente comando para instalar todas las dependencias del proyecto:

   ```bash
   npm install
   ```

   o

   ```bash
   yarn install
   ```

2. **Configuración del archivo de entorno**:
   Crea un archivo `.env` en la raíz del proyecto basado en el archivo `.env.template`. Asegúrate de configurar correctamente las variables de entorno necesarias, como las credenciales de la base de datos y las claves de API.

3. **Iniciar el servidor en modo desarrollo**:
   Utiliza el siguiente comando para iniciar el servidor en modo de desarrollo:
   ```bash
   npm run dev
   ```
   o
   ```bash
   yarn dev
   ```
   Esto iniciará el servidor en `http://localhost:4000` o en el puerto configurado en el archivo `.env`.

### Uso de Docker

#### Docker Compose

El proyecto incluye un archivo `docker-compose.yml` para facilitar el despliegue con Docker:

- **docker-compose.yml**: Configuración principal para desplegar el servicio backend junto con otros servicios necesarios, como la base de datos.

Para construir y ejecutar los servicios definidos en Docker Compose:

```bash
docker-compose up --build
```

Este comando construirá la imagen Docker definida en el `Dockerfile` y ejecutará el contenedor del backend junto con otros servicios especificados.

### Scripts Disponibles

Los scripts disponibles se definen en el archivo `package.json` y son los siguientes:

- **`npm start`** o **`yarn start`**: Inicia el servidor en modo de producción.
- **`npm run dev`** o **`yarn dev`**: Inicia el servidor en modo de desarrollo con recarga automática utilizando `nodemon`.
- **`npm run test`** o **`yarn test`**: Ejecuta las pruebas unitarias con Jest.
- **`npm run ci_test`** o **`yarn ci_test`**: Ejecuta las pruebas en modo continuo (CI).
