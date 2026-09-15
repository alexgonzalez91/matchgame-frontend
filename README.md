# MatchGame - Frontend

MatchGame es una aplicación web Full Stack orientada al descubrimiento de videojuegos.

El frontend permite explorar un catálogo propio de videojuegos, realizar búsquedas, aplicar filtros, ordenar resultados, consultar fichas detalladas y descubrir recomendaciones editoriales mediante la sección Selección MatchGame.

Este repositorio contiene exclusivamente el frontend de la aplicación, desarrollado con Astro y React.

## Tecnologías utilizadas

- Astro
- React
- JavaScript
- HTML
- CSS
- Fetch API
- pnpm

## Funcionalidades

- Página de inicio con videojuegos destacados.
- Buscador de videojuegos.
- Catálogo completo.
- Búsqueda por título.
- Filtro por género.
- Filtro por plataforma.
- Ordenación de resultados.
- Paginación real conectada a la API.
- Página de detalle de cada videojuego.
- Información de género, plataformas, fecha de lanzamiento y puntuación.
- Reseñas editoriales.
- Selección MatchGame con filtro por etiquetas.
- Página Sobre MatchGame.
- Formulario de contacto con validación mediante React.
- Navegación responsive.
- Menú hamburguesa para tablet y móvil.
- Estados de carga, error y resultados vacíos.
- Diseño responsive para escritorio, tablet y móvil.

## Páginas

```text
/
├── Inicio
├── /catalogo
├── /juegos/[id]
├── /seleccion
├── /sobre-matchgame
└── /contacto
```

## Estructura principal

```text
matchgame-frontend/
├── public/
│   └── images/
│       └── juegos/
├── src/
│   ├── components/
│   │   ├── CatalogoJuegos.jsx
│   │   ├── ContactForm.jsx
│   │   ├── Footer.astro
│   │   ├── GameCard.astro
│   │   ├── Navbar.astro
│   │   └── SeleccionMatchGame.jsx
│   ├── layouts/
│   │   └── Layout.astro
│   ├── pages/
│   │   ├── juegos/
│   │   │   └── [id].astro
│   │   ├── catalogo.astro
│   │   ├── contacto.astro
│   │   ├── index.astro
│   │   ├── seleccion.astro
│   │   └── sobre-matchgame.astro
│   └── styles/
│       └── global.css
├── .env.example
├── .gitignore
├── astro.config.mjs
├── package.json
└── pnpm-lock.yaml
```

## Requisitos

Para ejecutar el proyecto localmente es necesario tener instalado:

- Node.js
- pnpm

También es necesario tener disponible la API de MatchGame.

Repositorio del backend:

https://github.com/alexgonzalez91/matchgame-backend

## Instalación

Clonar el repositorio:

```bash
git clone https://github.com/alexgonzalez91/matchgame-frontend.git
```

Entrar en la carpeta:

```bash
cd matchgame-frontend
```

Instalar las dependencias:

```bash
pnpm install
```

## Variables de entorno

Crear un archivo `.env` en la raíz del proyecto.

Ejemplo:

```env
PUBLIC_API_URL=http://localhost:3000
```

También existe un archivo:

```text
.env.example
```

como referencia para conocer las variables necesarias.

> El archivo `.env` no debe subirse al repositorio.

## Ejecutar en desarrollo

```bash
pnpm dev
```

El frontend estará disponible normalmente en:

```text
http://localhost:4321
```

La API debe estar ejecutándose simultáneamente.

En desarrollo, la arquitectura es:

```text
Frontend Astro + React
http://localhost:4321
        ↓
      fetch
        ↓
Backend Node + Express
http://localhost:3000
        ↓
      MySQL
```

## Build de producción

Para generar la versión de producción:

```bash
pnpm build
```

Astro generará los archivos estáticos en:

```text
dist/
```

La carpeta `dist` está incluida en `.gitignore` porque se genera automáticamente.

## API

El frontend obtiene sus datos exclusivamente de la API propia de MatchGame.

Ejemplos de recursos consumidos:

```text
GET /api/juegos
GET /api/juegos/:id
GET /api/generos
GET /api/plataformas
GET /api/resenas
GET /api/etiquetas
```

La URL base se configura mediante:

```env
PUBLIC_API_URL
```

El frontend nunca se conecta directamente a la base de datos.

## Responsive

La interfaz está adaptada para:

- Escritorio
- Tablet
- Móvil

En pantallas reducidas, la navegación principal se transforma en un menú hamburguesa.

Los grids, formularios, filtros, tarjetas y secciones se reorganizan en función del espacio disponible.

## Diseño

Paleta principal:

```text
Fondo principal:      #0F172A
Fondo secundario:    #111827
Tarjetas:             #1E293B
Color principal:     #7C3AED
Color secundario:    #8B5CF6
Texto principal:     #F8FAFC
Texto secundario:    #94A3B8
Bordes:              #334155
Éxito:               #22C55E
Error:               #EF4444
Aviso:               #F59E0B
```

Tipografías:

```text
Títulos: Space Grotesk
Texto:   Inter
```

## Repositorios

Frontend:

https://github.com/alexgonzalez91/matchgame-frontend

Backend:

https://github.com/alexgonzalez91/matchgame-backend

## Despliegue

El despliegue previsto utiliza:

```text
Frontend → Netlify
Backend  → Render
Database → MySQL externo
```

La URL pública del frontend se añadirá aquí cuando finalice el despliegue.

## Proyecto educativo

MatchGame ha sido desarrollado como proyecto final de formación Full Stack.

El objetivo del proyecto es integrar en una misma aplicación conceptos de frontend, backend, API REST, bases de datos relacionales, diseño responsive y despliegue web.

© 2026 MatchGame.