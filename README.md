#  North America Retail — Supply Chain & Sales Analysis

> Proyecto de práctica en análisis de datos, supply chain y ventas retail para Norteamérica, desarrollado en Power BI Desktop.

---

##  Herramienta utilizada: Microsoft Power BI

Power BI es la plataforma de Business Intelligence de Microsoft diseñada para conectar, transformar y visualizar datos de múltiples fuentes en reportes interactivos. Es una de las herramientas más demandadas en el mercado para roles de Data Analyst, Business Analyst y BI Developer.

**¿Por qué Power BI para este proyecto?**
- Permite construir dashboards interactivos con **filtros cruzados** entre todos los visuales simultáneamente
- Soporta medidas DAX para cálculos avanzados como Year-over-Year, acumulados y comparaciones de períodos
- Incluye mapas geográficos nativos para análisis por región o país
- El modelo de datos relacionales permite combinar múltiples tablas sin duplicar información

---

##  Objetivo del Proyecto

Construir un reporte analítico completo sobre el desempeño comercial y de cadena de suministro de un negocio retail en Norteamérica, que permita responder preguntas clave de negocio como:

- ¿Cuáles son las ventas, ganancias, órdenes y devoluciones actuales vs. el año anterior?
- ¿Cuál es la tendencia de ventas y rentabilidad a lo largo del tiempo?
- ¿Qué segmentos de clientes generan más ventas?
- ¿Cómo se distribuye el rendimiento geográficamente por país/región?
- ¿Cuál es la vista consolidada por región del negocio?

---

##  Estructura del Reporte

El archivo `.pbix` contiene **2 páginas** con propósitos diferenciados:

### Página 1 — `Página 2` (Portada / Navegación)
Página de entrada con un botón de acción (`actionButton`) que redirige al dashboard principal. Sirve como portada visual profesional del reporte.

> 📸 **[FOTO: Pantalla de portada/navegación del reporte]**
>
> *Cómo agregarla: Abre el archivo en Power BI Desktop → ve a "Página 2" → usa la opción de exportar imagen o toma un screenshot → guárdala como `portada.png` en una carpeta `/assets/` del repositorio → reemplaza esta línea con:*
> ```markdown
> ![Portada](assets/portada.png)
> ```

### Página 2 — `Analisis` (Dashboard principal)
Página central del reporte con todos los visuales de análisis. Usa el tema **Storm** para una estética oscura y profesional.

> 📸 **[FOTO: Vista completa del dashboard "Analisis"]**
>
> *Cómo agregarla: Ve a la página "Analisis" en Power BI → captura el dashboard completo → guarda como `dashboard_analisis.png` en `/assets/` → usa:*
> ```markdown
> ![Dashboard Análisis](assets/dashboard_analisis.png)
> ```

---

##  Visualizaciones del Dashboard

###  Tarjetas KPI (Cards)
Se implementaron **12 tarjetas** organizadas en 4 grupos temáticos, cada grupo con sus métricas de valor actual, comparación y variación:

| Grupo | KPIs Incluidos |
|-------|---------------|
| **Ventas** | CV Sales · PY Sales · YoY% Growth |
| **Rentabilidad** | CV Profit · PY Profit · YoY% Profit |
| **Órdenes** | CV Orders · PY Orders · YoY% Orders |
| **Devoluciones** | CV Returns · PY Returns · YoY% Returns |

> *CV = Current Value (valor actual) · PY = Previous Year · YoY% = Year-over-Year (variación interanual)*

>  **[FOTO: Fila de tarjetas KPI del dashboard]**
>
> *Cómo agregarla: Haz zoom en la sección de tarjetas → captura → guarda como `kpi_cards.png` → usa:*
> ```markdown
> ![KPI Cards](assets/kpi_cards.png)
> ```

---

###  Gráficos de Área Apilada (Stacked Area Charts) — x4
Cuatro gráficos de área que muestran la **evolución temporal** de cada métrica principal (Ventas, Profit, Órdenes, Devoluciones), permitiendo identificar estacionalidad y tendencias.

---

### Gráfico Combinado: Tendencia de Ventas y Rentabilidad
`lineStackedColumnComboChart` — **"Sales & Profit trend"**

Combina barras de ventas con una línea de ganancia en el mismo eje de tiempo, permitiendo ver de un vistazo si el crecimiento en ventas se está traduciendo en mayor rentabilidad.

>  **[FOTO: Gráfico combinado de tendencia Sales & Profit]**
>
> *Cómo agregarla: Captura el visual del gráfico combinado → guarda como `sales_profit_trend.png` → usa:*
> ```markdown
> ![Sales & Profit Trend](assets/sales_profit_trend.png)
> ```

---

###  Mapa Coroplético (Filled Map)
**"Sum of sales by Country/Region"**

Mapa geográfico que colorea cada país/región según su volumen de ventas, permitiendo identificar mercados más y menos desarrollados de forma visual e intuitiva.

> 📸 **[FOTO: Mapa de ventas por país/región de Norteamérica]**
>
> *Cómo agregarla: Captura el visual del mapa → guarda como `mapa_ventas.png` → usa:*
> ```markdown
> ![Mapa de Ventas](assets/mapa_ventas.png)
> ```

---

###  Gráfico de Torta (Pie Chart)
**"Which Segment Contributes mostly in Sales?"**

Muestra la participación de cada segmento de clientes (Consumer, Corporate, Home Office) en las ventas totales, respondiendo directamente una de las preguntas estratégicas del negocio.

> 📸 **[FOTO: Gráfico de torta de segmentos]**
>
> *Cómo agregarla: Captura el visual → guarda como `segmentos_ventas.png` → usa:*
> ```markdown
> ![Segmentos de Ventas](assets/segmentos_ventas.png)
> ```

---

###  Tabla: Region-Wise Business Overview
Vista tabular consolidada del desempeño por región, que complementa el mapa con valores numéricos exactos para comparar regiones entre sí.

---

###  Gráfico de Barras (Bar Chart)
Visual adicional de comparación categórica para analizar una dimensión del negocio en formato horizontal, facilitando la comparación entre categorías con nombres largos.

---

### Segmentadores (Slicers) — x2
Dos filtros interactivos que permiten al usuario del reporte filtrar todos los visuales simultáneamente por dimensiones como período, categoría de producto u otra variable clave, haciendo el reporte completamente dinámico.

---

##  ¿Cómo se construyó?

### Paso 1 — Conexión y carga de datos
Se conectaron las fuentes de datos del negocio retail (ventas, órdenes, devoluciones, geografía) y se cargaron al modelo de Power BI.

### Paso 2 — Modelado de datos
Se construyó el modelo relacional entre tablas (hechos y dimensiones), base fundamental para que todos los cálculos y filtros funcionen correctamente entre sí.

### Paso 3 — Creación de medidas DAX
Se desarrollaron las medidas clave del reporte:
- Medidas de valor actual (`CV Sales`, `CV Profit`, `CV Orders`, `CV Returns`)
- Medidas de año anterior (`PY Sales`, `PY Profit`, etc.) usando funciones de inteligencia de tiempo
- Medidas de variación interanual (`YoY% Growth`, `YoY% Profit`, etc.)

### Paso 4 — Diseño del dashboard
Se aplicó el tema visual **Storm** (oscuro) y se organizaron los visuales en un layout claro: KPIs arriba, tendencias al centro, distribución geográfica y por segmento abajo, con filtros accesibles en los laterales.

> 📸 **[FOTO: Panel de modelo de datos mostrando las tablas y relaciones]**
>
> *Cómo agregarla: En Power BI Desktop, ve a la vista "Modelo" → captura el diagrama de relaciones → guarda como `modelo_datos.png` → usa:*
> ```markdown
> ![Modelo de Datos](assets/modelo_datos.png)
> ```

### Paso 5 — Portada y navegación
Se diseñó una página de portada con botón de navegación para dar una experiencia de usuario más profesional al abrir el reporte.

---

##  Habilidades demostradas

| Área | Detalle |
|------|---------|
| **DAX** | Medidas de tiempo inteligente (YoY), cálculos de CV/PY |
| **Modelado de datos** | Relaciones entre tablas, esquema estrella |
| **Visualización** | Mapas, combos, áreas, pie charts, tablas, KPI cards |
| **UX del reporte** | Navegación entre páginas, slicers, tema visual consistente |
| **Supply Chain Analytics** | Análisis de devoluciones, órdenes y rentabilidad integrados |
| **Análisis geográfico** | Mapas coropléticos por región/país |

---

##  Contexto del Dataset

El análisis cubre el mercado **retail de Norteamérica**, incluyendo métricas de:
- **Ventas** y su evolución temporal
- **Rentabilidad** por segmento y región
- **Gestión de órdenes** y volumen de operaciones
- **Devoluciones** como indicador de calidad de la cadena de suministro

---

##  Conclusiones

Este proyecto demuestra el ciclo completo de trabajo en Power BI: desde la carga y modelado de datos hasta la creación de un reporte ejecutivo con métricas de negocio relevantes. La combinación de análisis temporal (YoY), geográfico (mapa) y por segmento convierte el reporte en una herramienta de toma de decisiones completa.

---

*Proyecto de práctica — Business Intelligence y análisis de supply chain con Power BI*
<img width="1253" height="577" alt="image" src="https://github.com/user-attachments/assets/b082f949-c2be-4e12-81b6-d6e75a6f997c" />
