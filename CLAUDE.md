# 🌊 ONDA BASE — E-commerce Estático & Mostrador Streetwear

Documentación y especificaciones técnicas para la landing/mostrador de ropa urbana **ONDA BASE**. Diseñado como un catálogo estático ligero, de alto rendimiento y fácil administración local para despliegue automático.

---

## 📐 1. Resumen del Proyecto

- **Marca:** ONDA BASE (`@ondabase_`)
- **Tipo de sitio:** Mostrador / Catálogo Estático (Jamstack).
- **Propósito:** Mostrar colecciones, productos destacados, categorías e información de marca con estética Streetwear.
- **Flujo de Compra/Atención:** Los usuarios seleccionan productos y talles en un carrito interactivo y, al hacer clic en **"Finalizar Pedido"**, se genera un mensaje estructurado con el detalle de la compra directo al **WhatsApp** de la tienda.
- **Backend:** Sin backend centralizado. Todos los datos se compilan de forma estática en tiempo de *build*.

---

## ⚙️ 2. Stack Tecnológico Recomendado

1. **Framework Principal:** [Astro.build](https://astro.build/) + **Vite** (Garantiza carga ultrarrápida, generación de HTML estático y soporte nativo para JSON/Markdown).
2. **Estilos:** CSS3 nativo (Variables CSS) o Tailwind CSS respetando la paleta de colores urbana/oscura actual (`#0a0d0d`, `#c89431`, `#183b31`).
3. **Persistencia de Datos (Productos):** Archivo local `src/data/productos.json`.
4. **Administración Visual (CMS Local):** 
   - **Decap CMS (anteriormente Netlify CMS)** o **TinaCMS** en modo local, corriendo desde `/admin`. Permite crear/modificar productos, cambiar precios, subir imágenes y actualizar categorías desde un panel de control gráfico sin tocar código.
5. **Hosting & Deployment:** [Vercel](https://vercel.com/) o [Cloudflare Pages](https://pages.cloudflare.com/) (ambos integran despliegue continuo al hacer `git push`).

---

## 📦 3. Estructura del Proyecto

```text
onda-base/
├── public/
│   ├── assets/           # Logos, hero background, íconos
│   ├── uploads/          # Imágenes cargadas desde el panel local
│   └── admin/            # Panel visual de administración (Decap CMS)
├── src/
│   ├── components/       # Componentes Astro reutilizables
│   │   ├── Header.astro
│   │   ├── Hero.astro
│   │   ├── ProductCard.astro
│   │   ├── CartDrawer.astro
│   │   └── Footer.astro
│   ├── data/
│   │   └── productos.json # Fuente de verdad para los productos
│   ├── pages/
│   │   └── index.astro    # Página principal
│   └── styles/
│       └── global.css     # Paleta de colores, fuentes y estilos
├── astro.config.mjs
├── package.json
└── README.md