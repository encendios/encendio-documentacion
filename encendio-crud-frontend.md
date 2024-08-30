### Documentación para Desarrolladores del Proyecto EncendioCrudFrontend

#### Índice

1. [Introducción](#introducción)
2. [Estructura del Proyecto](#estructura-del-proyecto)
3. [Configuración del Entorno de Desarrollo](#configuración-del-entorno-de-desarrollo)
4. [Uso de Docker](#uso-de-docker)
5. [Scripts Disponibles](#scripts-disponibles)

---

### Introducción

**EncendioCrudFrontend** es la parte frontal del proyecto CRUD ENCENDIOS, desarrollado en Angular. Esta aplicación proporciona una interfaz de usuario amigable para interactuar con el backend, permitiendo la gestión de frases, imágenes y palabras.

### Estructura del Proyecto

La estructura del proyecto está organizada de la siguiente manera:

```
.
├── angular.json
├── dist/
│   └── encendio-crud-frontend/
│       ├── assets/
│       ├── index.html
│       ├── main.js
│       └── styles.css
├── docker-compose.yml
├── Dockerfile
├── package.json
├── README.md
├── src/
│   ├── app/
│   ├── assets/
│   ├── environments/
│   ├── favicon.ico
│   ├── index.html
│   ├── main.ts
│   └── styles.css
├── tsconfig.app.json
├── tsconfig.json
└── tsconfig.spec.json
```

- **angular.json**: Configuración de Angular CLI.
- **dist/**: Carpeta donde se generan los archivos después del build.
- **docker-compose.yml**: Archivo de configuración para Docker Compose.
- **Dockerfile**: Archivo de configuración para construir la imagen de Docker del frontend.
- **package.json**: Archivo de configuración de Node.js que gestiona las dependencias y scripts.
- **src/**: Carpeta principal que contiene todo el código fuente del proyecto en Angular.
- **tsconfig.json**: Configuración de TypeScript para el proyecto.

### Configuración del Entorno de Desarrollo

1. **Instalación de dependencias**:
   Ejecuta el siguiente comando para instalar todas las dependencias del proyecto:

   ```bash
   npm install
   ```

2. **Iniciar el servidor de desarrollo**:
   Para iniciar el servidor en modo de desarrollo, usa el siguiente comando:

   ```bash
   npm run start
   ```

   Esto iniciará un servidor en `http://localhost:4200/`. La aplicación se recargará automáticamente si realizas cambios en los archivos fuente.

3. **Archivo de configuración de entorno**:
   Asegúrate de que los archivos de configuración de entorno en la carpeta `src/environments/` estén configurados correctamente para tu entorno de desarrollo o producción.

### Uso de Docker

#### Docker Compose

El proyecto incluye un archivo de Docker Compose para facilitar el despliegue:

- **docker-compose.yml**: Archivo de configuración principal para producción. Incluye la configuración para el servicio frontend y el proxy Traefik.

Para iniciar los servicios usando Docker Compose:

```bash
docker-compose up -d
```

#### Dockerfile

El `Dockerfile` se utiliza para construir la imagen Docker del frontend:

```bash
docker build -t encendiocrudfront .
```

### Scripts Disponibles

Los scripts disponibles se definen en el archivo `package.json` y son los siguientes:

- **`npm run start`**: Inicia el servidor de desarrollo Angular.
- **`npm run build`**: Compila el proyecto Angular para producción.
- **`npm run watch`**: Compila el proyecto en tiempo real para desarrollo.
- **`npm run test`**: Ejecuta las pruebas unitarias con Jest.
- **`npm run test:watch`**: Ejecuta las pruebas en modo watch.
- **`npm run storybook`**: Inicia Storybook para el desarrollo de componentes.
- **`npm run build-storybook`**: Compila los archivos de Storybook para su despliegue.
