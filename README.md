# Aluvidrio · Cotizador de aluminio y vidrio

App web instalable (PWA) para generar presupuestos de trabajos de aluminio
y vidrio: cálculo por m² o precio fijo, catálogo de precios editable,
guardado de cotizaciones y vista de impresión/PDF.

## Cómo publicarla (gratis, con GitHub Pages)

1. Crea un repositorio nuevo en GitHub (puede ser público o privado).
2. Sube estos 5 archivos a la raíz del repo:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
3. Ve a **Settings → Pages**, en "Source" elige la rama `main` y carpeta `/root`.
4. Guarda. GitHub te da una URL como:
   `https://tu-usuario.github.io/tu-repo/`
5. Abre esa URL en el celular de tu papá, en **Chrome**.
6. Toca el menú (⋮) → **"Agregar a pantalla de inicio"** (o "Instalar app").
7. Listo — queda como un ícono más en su teléfono, abre a pantalla completa
   y funciona sin internet una vez que se cargó la primera vez.

## Alternativa más rápida: Netlify Drop

Si no quieres usar GitHub: entra a https://app.netlify.com/drop y arrastra
la carpeta completa. Te da una URL al instante, sin cuenta.

## Datos y respaldo

Los presupuestos y el catálogo se guardan en el teléfono (localStorage),
no en un servidor. Esto significa:
- Los datos son privados, nadie más los ve.
- Si borra los datos de navegación de Chrome o cambia de teléfono, se
  pierden. Recomendación: cada mes, usa "Imprimir/Guardar PDF" de las
  cotizaciones importantes como respaldo.

## Qué se corrigió respecto a la versión original

- El guardado usaba `window.storage`, una función que solo existe dentro
  de Claude.ai. Se cambió a `localStorage` para que funcione como app
  independiente en cualquier navegador o teléfono.
- Se corrigió un bug donde el mensaje "Guardado ✓" aparecía aunque el
  guardado hubiera fallado.
- Al elegir un modelo de precio fijo, ahora la categoría de la partida se
  actualiza automáticamente para que coincida.
