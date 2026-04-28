# Nomade Vans — Simulador de precios

Simulador de precios interactivo y autocontenido para el caso Nomade Vans.
Combina **pricing basado en competencia** con **factores psicológicos**, te permite elegir los gráficos que quieres dinámicamente y exporta el cuestionario + el posicionamiento que hayas escogido.

> Aplicación de un único fichero. Sin paso de build. Suelta `index.html` en cualquier sitio y funciona.

---

## Funcionalidades

### 1. Módulo basado en competencia
- Distribución DAP con curva de aceptación acumulada
- Curva de beneficio con marcadores de óptimo Std / Prem y tu propio marcador de precio
- Gráfico combinado Demanda + Ingresos
- Gráfico de barras de posicionamiento competitivo
- Brecha frente a cada competidor
- Precios de competidores editables (Further VAN, People Camper, Ocean Vans) por periodo

### 2. Módulo de factores psicológicos
- **Anclaje — sandwich Good-Better-Best** (gamas básico / medio / premium editables)
- **Charm pricing — efecto del dígito 9** (precio redondo vs charm, uplift de percepción)
- **Teoría de las Perspectivas** — función de valor (las pérdidas pesan más que las ganancias)
- **Precio de referencia** — cuántos encuestados quedan por debajo / en / por encima

### 3. Selector dinámico de gráficos
Cada módulo tiene un selector tipo chip — marca los gráficos que quieras en el panel. Recharts los renderiza uno al lado del otro, sensibles a periodo + versión.

### 4. Recorrido "Cómo usarlo"
Pestaña integrada con una guía de 5 pasos, explicaciones por pestaña, anotaciones "qué muestra esto" en cada gráfico y un glosario expandible (DAP, precio óptimo, anclaje, charm pricing, Teoría de las Perspectivas, precio de referencia, …).

### 5. Curva de beneficio interactiva
- **Arrastra la línea verde "Nuestro precio"** a izquierda/derecha — los KPIs de beneficio, demanda, ingresos y "perdido vs óptimo" se actualizan en vivo.
- Los competidores (Further VAN, People Camper, Ocean Vans) aparecen como **líneas discontinuas de colores en la curva de beneficio**, para que puedas leer en la x de cada competidor cuál sería nuestro beneficio a su precio — y ver al instante si conviene subir o bajar.
- Botones rápidos: *Saltar al óptimo*, *Igualar Further VAN*, *Igualar People Camper*, *Igualar Ocean Vans*.
- El mismo gráfico vive en la pestaña Posición y precios, así que arrastrarlo sincroniza los inputs numéricos.

### 6. Cuaderno del alumno (Word)
`Nomade_Vans_Case_Study_Simulator_Edition.docx` — un documento Word complementario generado desde `build_case_docx.py`. Contiene el contexto del caso, la estructura de costes, los precios de los competidores, las 13 preguntas de la encuesta para que el alumno responda, un recorrido del simulador en 5 pasos y 8 preguntas formales de entregable con cajas de respuesta.

### 7. Exportación a Excel en un clic
Una única descarga `.xlsx` con **7 hojas**:
- **Guía** — explicación breve del fichero
- **Preguntas** — las 13 preguntas de la encuesta (texto, tipo, opciones)
- **Respuestas — Día / Fin de semana / Semana** — tablas DAP agregadas (precio, respuestas, %, aceptación acumulada)
- **Posición** — tus precios de Nomade, precios de competidores, KPIs (beneficio óptimo, brecha vs media, % de aceptación), parámetros psicológicos y nota libre del analista
- **Gráficos** — los 9 gráficos del simulador, embebidos como imágenes PNG

Se abre en Excel, Numbers, Google Sheets o LibreOffice sin plug-ins.

---

## Ejecutar en local

```bash
# vale cualquier servidor estático
python -m http.server 8080
# luego abre http://localhost:8080
```

O haz doble clic en `index.html` — carga React, Recharts y Babel desde una CDN.

---

## Publicar en GitHub Pages

```bash
# dentro de esta carpeta
git init
git add index.html README.md
git commit -m "Simulador de precios Nomade Vans"
git branch -M main
git remote add origin https://github.com/<tu-usuario>/nomade-pricing-simulator-es.git
git push -u origin main
```

Luego en GitHub:

1. Repo → **Settings** → **Pages**
2. Source: **Deploy from a branch** → **main** → **/ (root)**
3. Save. El simulador estará disponible en `https://<tu-usuario>.github.io/nomade-pricing-simulator-es/`.

Sin build, sin Node, sin workflow.

---

## Fuentes de datos

- Cuestionario de 90 encuestados (ver `Copy of Respuestas Cuestionario 90 respuestas.xlsx`)
- Pricing basado en competencia — `TECHNICAL NOTE_ competition based pricing v3.0.pdf`
- Factores psicológicos — `TECHNICAL NOTE_ psicologocal factors_ v 1.0.pdf`

## Créditos

© César Moreno Pascual PhD.
