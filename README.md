# Portafolio de Oscar Santa

Portafolio personal en Astro, con contenido en español e inglés, tema claro y oscuro y un diseño adaptable a móvil. Presenta experiencia profesional, trabajos destacados, tecnologías, formación y contacto.

## Contenido

- `cv.json`: información profesional en español.
- `cv_english.json`: traducción al inglés con la misma estructura.
- `src/components/Portfolio.astro`: secciones y textos de la interfaz en ambos idiomas.
- `src/styles/portfolio.css`: diseño, temas, adaptación a móvil y estilos de impresión.
- `public/Oscar-Santa-ES.docx`: CV original descargable, en español.

La fuente de los datos es el CV facilitado por Oscar. Los trabajos destacados son contribuciones profesionales en LabsMobile, no proyectos personales con repositorios públicos. No se atribuyen métricas ni enlaces de demostración ausentes en el CV. Las fechas se guardan con precisión de mes (`YYYY-MM`); los campos desconocidos permanecen vacíos y `endDate: null` indica un empleo vigente. El diplomado Linux Essential no incluye fecha ni institución porque el CV no los especifica.

Las rutas son `/` (español) y `/en/` (inglés). Al cambiar información profesional, actualiza ambos JSON. Los textos generales del nuevo diseño están en `Portfolio.astro`; los del selector de idioma y tema permanecen en `src/i18n/ui.ts`.

## Desarrollo

Requiere Node.js 24 y pnpm.

```bash
pnpm install
pnpm exec astro dev --background
```

Gestiona el servidor con:

```bash
pnpm exec astro dev status
pnpm exec astro dev logs
pnpm exec astro dev stop
```

## Validación y producción

```bash
pnpm build
```

El comando ejecuta `astro check` y genera las páginas estáticas en `dist/`. Antes de publicar, configura `site` en `astro.config.mjs` con el dominio definitivo para generar los enlaces canónicos y alternativos de idiomas.

## Créditos

Proyecto basado en [minimalist-portfolio-json de midudev](https://github.com/midudev/minimalist-portfolio-json), con rediseño y contenido personalizados. Tipografía local Portfolio Sans. Licencia [MIT](LICENSE.txt).

## Foto y GitHub

Guarda tu foto en `public/foto.webp` (también puedes usar JPG o PNG). En `basics.image`, dentro de `cv.json` y `cv_english.json`, escribe `/foto.webp`. Usa la barra inicial y omite `public` en la ruta. Si el campo está vacío o la imagen no carga, se muestran las iniciales.

En ambos JSON, busca la entrada con `"network": "GitHub"` dentro de `basics.profiles`. Completa `username` con tu usuario y `url` con `https://github.com/TU_USUARIO`. El botón aparece en la presentación y en contacto cuando completas la URL; también se incluye al imprimir. Las entradas sin URL permanecen ocultas.
