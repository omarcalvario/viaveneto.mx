# Wireframe — Pizzería Vía Veneto

## Dirección del proyecto

Sitio **mobile-first** desarrollado con **Astro**: páginas rápidas y accesibles, con interacciones pequeñas en JavaScript (búsqueda, filtros, comparación y pedido). El menú se guardará como datos estructurados editables, separado de la presentación. El PDF adjunto es la única fuente autorizada para productos, ingredientes, categorías y precios; no se agregan platillos de otras fuentes.

**Objetivo principal:** ayudar a explorar un menú amplio, resolver “¿qué pido?” y facilitar el contacto directo. Las acciones de pedido y reserva abren WhatsApp; no hay pago en línea ni confirmación automática en esta propuesta.

## Mapa del sitio

- **Inicio** (`/`): identidad, acceso al menú, especialidades, experiencia y ubicación.
- **Menú** (`/menu`): catálogo interactivo completo, buscador, filtros, comparación y lista para WhatsApp.
- **Información** (bloques en inicio): historia, ubicación, horarios y contacto, sujetos a validación del restaurante.

## Wireframe móvil — Inicio (390 px aprox.)

```text
┌──────────────────────────────┐
│ VIA VENETO            [☰]    │  Header compacto
├──────────────────────────────┤
│ [Foto protagonista: pizza]   │
│ Vía Veneto                   │
│ [Frase de marca por validar] │
│ [ EXPLORAR EL MENÚ ]         │  CTA principal
│ [Pedir]       [Reservar]     │  Atajos secundarios
├──────────────────────────────┤
│ ¿QUÉ SE TE ANTOJA?           │
│ [Encontrar mi plato →]       │  Selector guiado
├──────────────────────────────┤
│ ESPECIALIDADES DEL MENÚ      │
│ [foto] Giuliana        $250  │  Carrusel opcional
│ Higo, nuez, queso, brie...   │  Solo ítems verificados
│ [Ver menú completo]          │
├──────────────────────────────┤
│ La experiencia Vía Veneto    │  Foto/texto breve
│ [Conocer más]                │
├──────────────────────────────┤
│ UBICACIÓN Y CONTACTO         │
│ Dirección y horario*         │
│ [Cómo llegar] [Llamar]       │
│ [WhatsApp]                   │
├──────────────────────────────┤
│ Redes · aviso de privacidad  │
└──────────────────────────────┘
┌──────────────────────────────┐
│ [Ver menú]       [Pedir]     │  Barra fija, no invasiva
└──────────────────────────────┘
*Publicar únicamente después de confirmar los datos.
```

## Wireframe móvil — Menú interactivo

```text
┌──────────────────────────────┐
│ ← Vía Veneto      Mi pedido 0│  Encabezado persistente
├──────────────────────────────┤
│ MENÚ                         │
│ [Buscar plato o ingrediente] │  Busca en nombre y descripción
│ [¿Qué se te antoja?]         │  Abre selector guiado
│ [Filtrar] [Comparar (0)]     │
├──────────────────────────────┤
│ Categorías desplazables      │  Se fijan bajo el header al scroll
│ Meraviglie · Pizze · Speciali│
│ Paste · Insalate · Entradas  │
│ Bibite · Caffè · Dolci       │
├──────────────────────────────┤
│ LE MERAVIGLIE                │
│ ┌──────────────────────────┐ │
│ │ Nombre             $250  │ │  Precio siempre a la vista
│ │ Ingredientes resumidos   │ │
│ │ [Detalles] [＋ Comparar]  │ │
│ └──────────────────────────┘ │
│ ...                          │
│ Sin resultados: limpiar filtros│
├──────────────────────────────┤
│ [Mi pedido · 2 productos]    │  Se muestra al agregar
└──────────────────────────────┘
┌──────────────────────────────┐
│ [Ver pedido / WhatsApp]      │  CTA fija contextual
└──────────────────────────────┘
```

### Interacciones acordadas

1. **Selector “¿Qué se te antoja?”**: flujo corto con opciones derivadas de los ingredientes/categorías reales del PDF (por ejemplo, verduras, quesos, carnes, mariscos o dulce, solo cuando aplique). Devuelve platos coincidentes; permite omitirlo y explorar todo.
2. **Buscador por ingrediente o nombre**: resultados instantáneos, estado vacío útil y botón para borrar búsqueda/filtros.
3. **Comparador**: seleccionar hasta tres productos; vista compacta con nombre, ingredientes y precio. En móvil se abre como panel, no como tabla comprimida.
4. **Lista de pedido**: añadir productos y ajustar cantidades; muestra subtotal calculado a partir del PDF. Acción final genera un mensaje de WhatsApp legible con selección y cantidades. El usuario lo revisa y envía; disponibilidad, costo de envío y total final se confirman con el restaurante.
5. **“Para compartir”**: atajo/filtro para explorar entradas, ensaladas, pizzas y bebidas disponibles en el PDF. No crear combos ni precios de paquete no publicados.
6. **Detalles de plato**: ingredientes completos, precio y notas existentes en el PDF. Imágenes solo cuando haya fotografía real; el catálogo sigue siendo usable sin imágenes.
7. **Reserva**: CTA abre WhatsApp con campos/prompt de fecha, hora y personas. Presentar como solicitud, sujeta a confirmación.

## Categorías visibles del menú

Orden inicial sugerido, basado exclusivamente en la organización del PDF:

1. **Le Meraviglie**
2. **Le Pizze**
3. **Le Pizze Speciali**
4. **Entradas y acompañamientos** (incluye lo que el PDF presenta como acompañamiento/antipasti)
5. **Le Paste**
6. **Insalate**
7. **Bibite**
8. **I Nostri Caffè / Gli Speciali**
9. **Il Dolci**

En la interfaz se puede usar el nombre italiano del impreso con una aclaración en español cuando ayude. Revisar manualmente la transcripción: el PDF/OCR presenta algunos caracteres deformados. Precios visibles en MXN y sin depender de abrir la ficha.

## Wireframe escritorio

```text
┌──────────────────────────────────────────────────────────────┐
│ Logo       Inicio  Menú  Nuestra experiencia  Ubicación [Pedir]│
├──────────────────────────────────────────────────────────────┤
│ Hero: imagen real + propuesta de marca + [Explorar menú]       │
├──────────────────────────────────────────────────────────────┤
│ ¿Qué se te antoja? [iniciar selector]                          │
├──────────────────────────────────────────────────────────────┤
│ Especialidades del menú (3–4 ítems verificados)                 │
├──────────────────────────────────────────────────────────────┤
│ MENÚ INTERACTIVO                                                │
│ Índice de categorías │ Buscar / filtros │ Lista de platos      │
│                      │ Comparar         │ nombre, ingredientes│
│                      │                  │ precio, acciones     │
├──────────────────────────────────────────────────────────────┤
│ Experiencia / historia       │ Imagen                           │
├──────────────────────────────────────────────────────────────┤
│ Ubicación · horario · teléfono · WhatsApp · enlaces de mapa    │
└──────────────────────────────────────────────────────────────┘
```

## Reglas de experiencia y contenido

- Mobile-first: controles cómodos al tacto, texto legible, navegación por teclado y foco visible. La barra fija respeta el área segura y no oculta platos.
- No depender del color ni de fotos para comunicar ingredientes, precio, filtros o selección.
- Mantener nombre, ingredientes y precio coherentes con el PDF; corregir OCR contra la imagen del menú antes de cargar datos.
- La información de contacto, ubicación, horarios, terraza, entrega a domicilio y disponibilidad de reservas requiere confirmación del negocio; el PDF no basta para validarla.
- No prometer entrega a domicilio hasta confirmar que se ofrece. El CTA de pedido puede denominarse “Pedir por WhatsApp” y especificar modalidad una vez validada.

## Alcance técnico sugerido en Astro

- Rutas estáticas `/` y `/menu`; componentes Astro para contenido y layout.
- Datos del menú en un archivo tipado (por ejemplo, `src/data/menu.ts`); fuente de verdad editable, no extracción automática del PDF.
- JavaScript ligero e hidratación solo para los controles interactivos del menú.
- Enlaces `wa.me` con número oficial confirmado y texto codificado; sin guardar datos personales innecesarios.
- Revisar accesibilidad, rendimiento móvil y metadatos/SEO local antes del lanzamiento.
