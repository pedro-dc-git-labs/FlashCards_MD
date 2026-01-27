# Especificación técnica - FlashCards English Path

## Resumen
- Sitio web estático en **HTML/CSS/JavaScript vainilla** (sin frameworks ni librerías externas).
- Página principal `index.html` que actúa como **panel de navegación** para las flashcards por tema.
- Cada tema enlaza a páginas individuales de flashcards dentro de `views/`.

## Estructura de carpetas
```
/ (raíz)
├── index.html
├── public/
│   └── stylesheets/
│       └── style.css
└── views/
    ├── flashcard1.html
    ├── flashcard2.html
    └── ... (más páginas de flashcards)
```

## Descripción de la arquitectura
### 1. `index.html`
- **Documento principal** con la estructura base del layout.
- Incluye estilos globales desde `public/stylesheets/style.css` y estilos locales embebidos en el `<style>`.
- Contiene la **barra lateral (sidebar)** con botones de categorías y la **sección principal (main)** para listar las flashcards.
- Incluye un bloque de **JavaScript embebido** que:
  - Define un objeto `categories` con los temas y enlaces a cada flashcard.
  - Renderiza dinámicamente las tarjetas en la grilla central.
  - Maneja la interacción: cambio de categoría y búsqueda por texto.

### 2. `public/stylesheets/style.css`
- Hoja de estilos base con:
  - Variables CSS (`:root`) para colores y tipografía.
  - Estilos generales de layout (body, grids, cards).
  - Componentes reutilizables como `.card`, `.badge`, `.pill`, tablas y bloques de notas.
- Define el **tema visual** de la web (dark UI con acentos en azul).

### 3. `views/`
- Carpeta que contiene las **páginas individuales de flashcards**.
- Cada archivo `flashcardX.html` es una página estática autónoma con su propio contenido.

## Flujo de navegación
1. El usuario abre `index.html`.
2. Selecciona una categoría en la sidebar.
3. Se renderizan las tarjetas correspondientes en el panel principal.
4. Al hacer clic en **“Practicar”**, se navega a un archivo `flashcardX.html`.

## Tecnologías utilizadas
- **HTML5** para la estructura semántica.
- **CSS3** para estilos y diseño responsive (sin preprocesadores).
- **JavaScript Vainilla** (sin frameworks, sin dependencias externas) para:
  - Renderizado dinámico de tarjetas.
  - Interacción con categorías y búsqueda.

## Consideraciones técnicas
- No existe back-end ni API: todo el contenido es **estático**.
- La web puede desplegarse en cualquier hosting estático (GitHub Pages, Netlify, etc.).
- La organización por carpetas facilita el mantenimiento y la ampliación con nuevas flashcards.
