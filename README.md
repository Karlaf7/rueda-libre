Rueda Libre

Sitio web de Rueda Libre, un negocio ficticio de alquiler de bicicletas y recorridos guiados en Medellín, Antioquia. Proyecto académico de HTML, CSS y Bootstrap: tres páginas con diseño responsive, formulario con validaciones nativas y una paleta de colores revisada por accesibilidad.

Demo: https://karlaf7.github.io/rueda-libre/

---

Características

- 3 páginas enlazadas entre sí: Inicio, Tarifas y Rutas, y Reservas.
- HTML semántico: `header`, `nav`, `main`, `section`, `article`, `aside`, `footer`.
- Diseño responsive (móvil primero) con Bootstrap 5 y CSS propio.
- Catálogo de flota de 7 bicicletas, 3 rutas guiadas y sección de beneficios.
- Tablas de tarifas (alquiler por hora, medio día y día completo; recorridos guiados).
- Formulario de reservas con validación HTML5 (sin JavaScript).
- Menú con estados `hover`, `focus` y página activa (`aria-current="page"`).
- Etiqueta "Nuevo" y botón fijo de WhatsApp posicionados con `position`.
- Contraste de colores medido y documentado (WCAG).

---

Estructura del proyecto

```
rueda-libre/
├── index.html                  # Página de inicio
├── paginas/
│   ├── tarifas.html            # Tarifas de alquiler y recorridos guiados
│   └── reservas.html           # Formulario de reservas y horarios
├── css/
│   └── styles.css              # Estilos propios (cargado después de Bootstrap)
├── img/                        # Logo e ilustraciones (bicicletas, rutas, portada)
│   └── bitacora.txt            # Bitácora de aprendizaje y decisiones de diseño
└── pruebas/
    └── catalogo-bootstrap.html # Prueba del catálogo solo con Bootstrap (sin CSS propio)
```

---

Páginas

| Página | Archivo | Contenido |
|---|---|---|
| Inicio | `index.html` | Portada, servicios, flota, rutas, taller básico, cómo alquilar, beneficios, ubicación |
| Tarifas y Rutas | `paginas/tarifas.html` | Tablas de precios, recorridos guiados, qué llevar, información adicional |
| Reservas | `paginas/reservas.html` | Horarios de atención, formulario de reserva, datos de contacto |

Flota y precios (por hora)

| Bicicleta | Precio |
|---|---|
| Infantil | $8.000 |
| Urbana clásica | $10.000 |
| Urbana plegable | $12.000 |
| Montaña trail | $15.000 |
| Gravel aventura | $18.000 |
| Tándem | $20.000 |
| Eléctrica urbana | $25.000 |

Recorridos guiados

| Ruta | Distancia | Duración | Nivel | Precio por persona |
|---|---|---|---|---|
| Río y parques | 12 km | 2 h | Fácil | $45.000 |
| Sabores de barrio | 18 km | 3 h | Medio | $60.000 |
| Reto Las Palmas | 25 km | 4 h | Difícil | $85.000 |

Salidas: sábados y domingos a las 7:00 a.m. Grupos de máximo 8 personas.

---

Formulario de reservas

Validado únicamente con atributos HTML5:

| Campo | Control | Validación |
|---|---|---|
| Nombre completo | `text` | Obligatorio, mínimo 3 caracteres |
| Número de documento | `text` | Obligatorio, 6 a 10 dígitos (`pattern`). Es un identificador, no una cantidad |
| Celular | `tel` | Obligatorio, 10 dígitos que empiecen por 3 |
| Correo electrónico | `email` | Obligatorio, formato válido |
| Fecha de alquiler | `date` | Obligatorio, entre 2026-11-01 y 2026-12-31 |
| Tipo de bicicleta | `radio` | Obligatorio (Urbana, Montaña, Eléctrica) |
| Plan | `select` | Obligatorio (1 hora, medio día, día completo) |
| Cantidad de bicicletas | `number` | Obligatorio, de 1 a 6 |
| Recorrido guiado | `select` | Opcional |
| Comentarios | `textarea` | Máximo 300 caracteres |
| Políticas de alquiler | `checkbox` | Obligatorio |

> El formulario aún no envía datos a ningún servidor (`action="#"`).

---

Diseño

Paleta de colores

| Color | Hex | Uso |
|---|---|---|
| Azul Noche | `#14213D` | Texto principal, títulos, hover de botones |
| Verde Ruta | `#1E7A4F` | Botones principales, enlaces, menú activo |
| Naranja Pedal | `#F39A2B` | Etiqueta "Nuevo" (con texto Azul Noche) |
| Crema | `#FAF6EF` | Fondo general |
| Gris Asfalto | `#5B6470` | Texto secundario, bordes |
| Blanco | `#FFFFFF` | Texto sobre fondos oscuros |

Contraste (WCAG)

| Combinación | Relación | Resultado |
|---|---|---|
| Blanco sobre Azul Noche | 15,97:1 | Apta |
| Azul Noche sobre Crema | 14,82:1 | Apta |
| Azul Noche sobre Naranja Pedal | 7,2:1 | Apta |
| Gris Asfalto sobre Crema | 5,56:1 | Apta |
| Blanco sobre Verde Ruta | 5,31:1 | Apta |
| Verde Ruta sobre Crema | 4,93:1 | Apta |
| Blanco sobre Naranja Pedal | 2,21:1 | No apta |
| Naranja Pedal sobre Crema | 2,05:1 | No apta |

El naranja solo se usa como fondo con texto Azul Noche, nunca como color de texto.

Tipografía

- Títulos: Montserrat (700)
- Texto: Open Sans (400, 600)

Ambas se cargan desde Google Fonts, con Arial como respaldo.

Puntos de quiebre

| Ancho | Comportamiento |
|---|---|
| < 576 px | 1 columna |
| ≥ 576 px | Flota en 2 columnas |
| ≥ 768 px | Flota en 3 columnas; encabezado y pie en fila |
| ≥ 992 px | Flota en 4 columnas; tarifas en 8/4 columnas |

---

Tecnologías

- HTML5 semántico
- CSS3: variables (`:root`), Flexbox, Grid, `position`, media queries
- Bootstrap 5.3.8 (vía CDN jsDelivr, con SRI)
- Google Fonts (Montserrat y Open Sans)

No requiere compilación, instalación de dependencias ni JavaScript propio.

---

Cómo ejecutarlo

1. Clona o descarga el repositorio:
   ```bash
   git clone https://github.com/karlaf7/rueda-libre.git
   cd rueda-libre
   ```
2. Abre `index.html` en el navegador, o usa un servidor local como la extensión Live Server de VS Code (por defecto en `http://127.0.0.1:5500/index.html`).

Se necesita conexión a internet para cargar Bootstrap y las fuentes desde CDN.

Publicación

El sitio se publica con GitHub Pages. Todos los enlaces internos son relativos (`../index.html`, `reservas.html`) para evitar errores 404 al servirse desde un subdirectorio.

---

Pruebas

- `pruebas/catalogo-bootstrap.html`: versión del catálogo de flota hecha solo con Bootstrap, usada para comparar con la versión con CSS propio (0 líneas de CSS y 7 clases de grilla).
- Pruebas de formulario: se validaron 8 casos (nombre corto, documento con menos de 6 dígitos o con letras, correo incompleto, celular que no empieza por 3, cantidad mayor a 6, plan sin seleccionar y políticas sin marcar). Todos fueron rechazados con el mensaje esperado.
- DevTools: revisión de herencia, especificidad, `box-sizing` y conflictos entre Bootstrap y `styles.css`.

Los detalles completos están en [`img/bitacora.txt`](img/bitacora.txt).

---

Autoría

Proyecto desarrollado por Karla ([@karlaf7](https://github.com/karlaf7)) · 2026 · Contacto: ruedalibre@gmail.com