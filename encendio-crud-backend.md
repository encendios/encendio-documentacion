### Documentación para Desarrolladores del Proyecto CRUD ENCENDIOS (Backend)

#### Índice

1. [Introducción](#introducción)
2. [Estructura del Proyecto](#estructura-del-proyecto)
3. [Configuración del Entorno de Desarrollo](#configuración-del-entorno-de-desarrollo)
4. [Uso de Docker](#uso-de-docker)
5. [Scripts Disponibles](#scripts-disponibles)

---

### Introducción

El proyecto **CRUD ENCENDIOS** es una aplicación backend que permite la gestión de frases, imágenes y palabras mediante operaciones CRUD (Crear, Leer, Actualizar, Eliminar). Utiliza tecnologías como Node.js, Express, MongoDB, y está estructurado en TypeScript para un desarrollo robusto y mantenible.

### Estructura del Proyecto

La estructura del proyecto está organizada de la siguiente manera:

```
.
├── compose-dev.yml
├── data/
├── dist/
├── docker-compose-dev.yml
├── docker-compose.yml
├── Dockerfile
├── jest.config.ts
├── package.json
├── README.md
├── setupTests.ts
├── src/
├── test/
├── tsconfig.json
```

- **compose-dev.yml** y **docker-compose.yml**: Archivos de configuración para Docker Compose para diferentes entornos.
- **data/**: Carpeta que contiene los archivos de datos de MongoDB.
- **dist/**: Carpeta generada tras la construcción del proyecto.
- **Dockerfile**: Archivo de configuración para construir la imagen de Docker del proyecto.
- **jest.config.ts**: Configuración para el framework de pruebas Jest.
- **package.json**: Archivo de configuración de Node.js que gestiona las dependencias y scripts.
- **src/**: Carpeta principal que contiene todo el código fuente del proyecto en TypeScript.
- **test/**: Carpeta que contiene las pruebas de integración y unitarias.
- **tsconfig.json**: Configuración de TypeScript para el proyecto.

### Configuración del Entorno de Desarrollo

1. **Copiar el archivo de configuración de entorno**:

   - Copia el archivo `.template.env` y renómbralo a `.env`.
   - Edita el archivo `.env` para agregar las variables de entorno necesarias como la conexión a MongoDB y el nombre de la base de datos.

2. **Instalación de dependencias**:
   Ejecuta el siguiente comando para instalar todas las dependencias del proyecto:

   ```bash
   npm install
   ```

3. **Iniciar el entorno de desarrollo**:
   Para iniciar el servidor en modo de desarrollo, usa el siguiente comando:
   ```bash
   npm run dev
   ```

### Uso de Docker

#### Docker Compose

El proyecto incluye varios archivos de Docker Compose para facilitar el despliegue:

- **docker-compose.yml**: Archivo de configuración principal para producción. Incluye la configuración para el servicio backend y el proxy Traefik.
- **docker-compose-dev.yml**: Archivo de configuración para desarrollo que incluye un contenedor de MongoDB.

Para iniciar los servicios usando Docker Compose:

```bash
docker-compose -f docker-compose.yml up -d
```

O para el entorno de desarrollo:

```bash
docker-compose -f docker-compose-dev.yml up -d
```

#### Dockerfile

El `Dockerfile` se utiliza para construir la imagen Docker del backend:

```bash
docker build -t backendcrud .
```

### Scripts Disponibles

Los scripts disponibles se definen en el archivo `package.json` y son los siguientes:

- **`npm run dev`**: Inicia el servidor en modo desarrollo usando `ts-node-dev`.
- **`npm run build`**: Compila el proyecto TypeScript a JavaScript en la carpeta `dist`.
- **`npm run start`**: Compila el proyecto y luego inicia el servidor desde la carpeta `dist`.
- **`npm run test`**: Ejecuta las pruebas unitarias y de integración con Jest.
- **`npm run test:watch`**: Ejecuta las pruebas en modo watch.
- **`npm run test:coverage`**: Genera un informe de cobertura de pruebas.

Para cualquier duda adicional, consulta la documentación en el archivo `README.md` o contacta con el equipo de desarrollo.
