# Módulo 8 - Cloud: Render con Docker

App Vite + React + TypeScript desplegada automáticamente en Render como contenedor Docker.

## Enlace

- **App desplegada:** https://modulo08-cloud-render-docker.onrender.com

> Usa el plan gratuito de Render: el servicio se suspende tras un tiempo sin visitas, así que la primera carga puede tardar alrededor de un minuto.

## Cómo se despliega

- El `Dockerfile` es multi-stage: una fase con Node construye la app (`npm ci` y `npm run build`) y una fase final con Nginx sirve el contenido de `dist`.
- El repositorio está conectado a un Web Service de Render (runtime Docker) con Auto-Deploy "On Commit" y la variable de entorno `PORT=80`.
- Cada push a `main` hace que Render construya la imagen a partir del `Dockerfile` y despliegue el nuevo contenedor.