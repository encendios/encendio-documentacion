### Documentación para Desarrolladores del Proyecto Encendio Frontend

#### Índice

1. [Introducción](#introducción)
2. [Estructura del Proyecto](#estructura-del-proyecto)
3. [Configuración del Entorno de Desarrollo](#configuración-del-entorno-de-desarrollo)
4. [Uso de Docker](#uso-de-docker)
5. [Scripts Disponibles](#scripts-disponibles)

---

### Introducción

**Encendio Frontend** es la interfaz de usuario para el dashboard de Encendio. Esta aplicación proporciona herramientas y visualizaciones para gestionar y analizar datos a través de un entorno de usuario moderno, utilizando React como framework de desarrollo.

### Estructura del Proyecto

La estructura del proyecto está organizada de la siguiente manera:

```
.
├── base_keycloak.json
├── build/
├── custom-nginx.template
├── docker-compose-dev.yml
├── docker-compose.yml
├── Dockerfile
├── generate-config.sh
├── jest.config.js
├── jsconfig.json
├── LICENSE
├── package.json
├── public/
│   ├── favicon.ico
│   ├── index.html
│   └── manifest.json
├── README.md
├── src/
│   ├── assets/
│   ├── components/
│   ├── consts/
│   ├── layout/
│   ├── scss/
│   ├── views/
│   ├── App.js
│   ├── index.js
│   ├── routes.js
│   └── store.js
├── webpack.config.js
```

- **base_keycloak.json**: Configuración base para Keycloak.
- **build/**: Carpeta donde se generan los archivos después del build.
- **docker-compose-dev.yml** y **docker-compose.yml**: Archivos de configuración para Docker Compose para diferentes entornos.
- **Dockerfile**: Archivo de configuración para construir la imagen Docker del frontend.
- **jest.config.js**: Configuración para el framework de pruebas Jest.
- **package.json**: Archivo de configuración de Node.js que gestiona las dependencias y scripts.
- **public/**: Carpeta que contiene archivos estáticos como `index.html`.
- **src/**: Carpeta principal que contiene todo el código fuente del proyecto en React.
- **webpack.config.js**: Configuración para el empaquetador de módulos Webpack.

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

2. **Iniciar el servidor de desarrollo**:
   Para iniciar el servidor en modo de desarrollo, usa el siguiente comando:

   ```bash
   npm start
   ```

   o

   ```bash
   yarn start
   ```

   Esto iniciará un servidor en `http://localhost:3000/`. La aplicación se recargará automáticamente si realizas cambios en los archivos fuente.

3. **Archivo de configuración de entorno**:
   Asegúrate de definir un archivo `.env` basado en `.env.sample` para configurar las variables de entorno necesarias.

### Uso de Docker

#### Docker Compose

El proyecto incluye varios archivos de Docker Compose para facilitar el despliegue:

- **docker-compose.yml**: Archivo de configuración principal para producción que incluye el servicio del dashboard.
- **docker-compose-dev.yml**: Archivo de configuración para desarrollo que incluye un contenedor de Keycloak.

Para iniciar los servicios usando Docker Compose en modo desarrollo:

```bash
docker-compose -f docker-compose-dev.yml up --build -d
```

### Scripts Disponibles

Los scripts disponibles se definen en el archivo `package.json` y son los siguientes:

- **`npm start`** o **`yarn start`**: Inicia el servidor de desarrollo con recarga en caliente.
- **`npm run build`** o **`yarn build`**: Compila el proyecto React para producción con minificación.
- **`npm test`** o **`yarn test`**: Ejecuta las pruebas unitarias con Jest.
