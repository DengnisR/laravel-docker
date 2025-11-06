# 📄 Documentación para el Deploy de la Aplicación Laravel 12 con Inertia y Vue3

## 🇪🇸 Español

Este documento proporciona instrucciones para desplegar una aplicación Laravel 12, configurada con Inertia y Vue3, utilizando Docker.

### ⚙️ Configuración del Entorno

1. **📄 Copiar y configurar el archivo `.env`:**

   ```bash
   cp src/.env.example src/.env
   ```

2. **🐳 Construir la imagen de Docker:**

   ```bash
   docker-compose up -d --build
   ```

### 🚀 Hacer Deploy

Para realizar el deploy, puedes usar los siguientes comandos:

- **Opción 1:** Acceder al contenedor y ejecutar los comandos:

   ```bash
   docker exec -it laravel-app bash
   composer install
   npm install
   npm run dev
   ```

- **Opción 2:** Ejecutar los comandos directamente en el contenedor:

   ```bash
   docker exec -it laravel-app composer install
   docker exec -it laravel-app npm install
   docker exec -it laravel-app npm run dev
   ```

### 🗄️ Configuración de la Base de Datos

Para migrar la base de datos, ejecuta el siguiente comando:

```bash
docker exec -it laravel-app php artisan migrate
```

### 🗺️ Mapa de Distribución del Proyecto

A continuación se presenta la distribución básica del proyecto:

```plaintext
project-root/
│
├── app/                   # Código de la aplicación
│   ├── Http/              # Controladores
│   ├── Models/            # Modelos
│   └── ...
│
├── config/                # Configuración de la aplicación
│
├── database/              # Base de datos
│   ├── migrations/        # Migraciones
│   └── seeders/          # Seeds
│
├── public/                # Archivos públicos (CSS, JS, imágenes)
│
├── resources/             # Recursos
│   ├── js/                # Archivos de JavaScript
│   ├── views/             # Vistas
│   └── ...
│
├── routes/                # Rutas de la aplicación
│
├── storage/               # Archivos generados, logs
│
└── tests/                 # Pruebas
```

---

## 🇺🇸 English

This document provides instructions for deploying a Laravel 12 application configured with Inertia and Vue3, using Docker.

### ⚙️ Environment Setup

1. **📄 Copy and configure the `.env` file:**

   ```bash
   cp .env.example .env
   ```

2. **🐳 Build the Docker image:**

   ```bash
   docker-compose up -d --build
   ```

### 🚀 Deploying

To deploy, you can use the following commands:

- **Option 1:** Access the container and run the commands:

   ```bash
   docker exec -it laravel-app bash
   composer install
   npm install
   npm run dev
   ```

- **Option 2:** Run commands directly in the container:

   ```bash
   docker exec -it laravel-app composer install
   docker exec -it laravel-app npm install
   docker exec -it laravel-app npm run dev
   ```

### 🗄️ Database Setup

To migrate the database, run the following command:

```bash
docker exec -it laravel-app php artisan migrate
```

### 🗺️ Project Directory Map

Below is the basic distribution of the project:

```plaintext
project-root/
│
├── app/                   # Application code
│   ├── Http/              # Controllers
│   ├── Models/            # Models
│   └── ...
│
├── config/                # Application configuration
│
├── database/              # Database
│   ├── migrations/        # Migrations
│   └── seeders/           # Seeds
│
├── public/                # Public files (CSS, JS, images)
│
├── resources/             # Resources
│   ├── js/                # JavaScript files
│   ├── views/             # Views
│   └── ...
│
├── routes/                # Application routes
│
├── storage/               # Generated files, logs
│
└── tests/                 # Tests
```
```