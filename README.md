# SonarQube Docker

Entorno de análisis estático de código mediante SonarQube Community Build, Docker Compose y PostgreSQL.

## Objetivo

Levantar un servidor SonarQube independiente que permita analizar la calidad y seguridad del código de distintos proyectos, especialmente aplicaciones desarrolladas con Node.js, Express, Next.js y TypeScript.

## Requisitos

- Docker
- Docker Compose
- Memoria RAM suficiente para ejecutar SonarQube y PostgreSQL

## Instalación

1. Clonar el repositorio.
2. Copiar `.env.example` a `.env`.
3. Configurar la contraseña de PostgreSQL.
4. Ejecutar `docker compose up -d`.
5. Acceder a `http://localhost:9000`.
6. Iniciar sesión con las credenciales iniciales `admin/admin` y cambiar la contraseña.

## Comandos útiles

```bash
docker compose up -d
docker compose ps
docker compose logs -f sonarqube
docker compose down
```

## Integración con otros proyectos

Para analizar un repositorio externo:

1. Crear un proyecto en la interfaz de SonarQube.
2. Generar un token de análisis.
3. Configurar SonarScanner en el repositorio que se desea analizar.
4. Ejecutar el scanner indicando la URL del servidor y el token.
5. Revisar los resultados en el dashboard.

## Arquitectura

- **SonarQube:** servidor de análisis y visualización.
- **PostgreSQL:** almacenamiento persistente de información.
- **SonarScanner:** herramienta que analiza los repositorios externos y envía los resultados al servidor.

## Consideraciones

- No almacenar contraseñas ni tokens en Git.
- Utilizar volúmenes persistentes.
- Fijar versiones de las imágenes para entornos estables.
- No utilizar `docker compose down -v` si se desea conservar la información.

# CREDENCIALES

user: admin
password: Está en el .env (default admin)
