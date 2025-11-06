# Análisis de Rendimiento Financiero con Power BI

Este proyecto es parte de mi portafolio de análisis de datos en Power BI, centrado en un informe interactivo de **Rendimiento Financiero Empresarial**. A través de diversas visualizaciones y cálculos, se analizan las principales métricas relacionadas con la salud financiera de un negocio, comparando los resultados reales contra los objetivos (presupuestos y metas).


---

## Objetivos del Proyecto

El objetivo principal de este reporte es ofrecer una visión integral de la **salud financiera de la empresa**, proporcionando insights clave que faciliten la toma de decisiones. El reporte se centra en:

* Medir la **Utilidad** real vs. la utilidad esperada.
* Controlar la **Cuota de Gastos** (Gastos Reales vs. Presupuesto).
* Monitorear la **Cuota de Ingresos** (Ingresos Reales vs. Metas).
* Analizar el **Saldo** final vs. el saldo esperado.

## Fuentes de Datos

El modelo de datos se construyó a partir de **tres fuentes de datos** distintas:

1.  **`Finanzas-Final.xlsx`**: El archivo principal que contiene 4 hojas (tablas) separadas que fueron importadas y transformadas:
    * `Ingresos`: Registros de ingresos por categoría (ej. Online, Remuneración).
    * `Gastos`: Registros de gastos operativos por categoría.
    * `Meta Ingresos`: Metas de ingresos mensuales por categoría.
    * `Presupuesto Gastos`: Presupuesto de gastos mensual por categoría.

2.  **`Categorias.xlsx`**:
    * Una tabla de dimensiones para agrupar y clasificar las categorías.

3.  **Carpeta `Calendario`**:
    * Contiene dos archivos Excel (`2018.xlsx` y `2019.xlsx`) que se unieron en Power Query para crear la **Tabla de Dimensiones de Calendario**. Esta tabla es la base para todos los análisis de inteligencia de tiempo.

* **Transformación:** Se utilizó **Power Query** para limpiar, unificar (el calendario) y pivotar los datos de presupuesto para el modelado.

## Cálculos DAX

Para enriquecer el análisis, se crearon diferentes medidas y columnas calculadas utilizando DAX. El uso de la tabla de **Calendario** fue esencial para esto:

* **Medidas Principales:** `Ingresos`, `Gastos`, `Utilidad` (Ingresos - Gastos) y `Saldo`.
* **Medidas de Objetivos:** `Meta` (de Ingresos), `Presupuesto` (de Gastos), `Ut. Esperada` y `Sa. Esperado`.
* **Medidas de Cuota (Rendimiento):**
    * `Cuota Ingresos = [Ingresos] / [Meta]`
    * `Cuota Gastos = [Gastos] / [Presupuesto]`
    * `Cuota Utilidad = [Utilidad] / [Ut. Esperada]`
    * `Cuota Saldo = [Saldo] / [Sa. Esperado]`

##  Visualizaciones Incluidas

El informe de Power BI está dividido en [NÚMERO] páginas principales (basado en el PDF, parece tener varias secciones):

* **Página Principal (Resumen):** 4 medidores (gauges) principales que muestran las 4 "Cuotas" (Ingresos, Gastos, Saldo, Utilidad) y sus KPIs.
* **Comparativa Mensual:** Una página con una tabla detallada que compara todas las métricas financieras mes a mes.
* **Análisis de Saldo y Utilidad:** Gráficos de líneas y barras para analizar la evolución de la `Cuota Saldo` y la `Utilidad vs. Utilidad Esperada` por categoría y tiempo.

## Funcionalidades Interactivas

* **Segmentadores:** Se agregaron filtros interactivos que permiten segmentar los datos por Año y Mes.
* **Botones de navegación:** Se añadieron botones para facilitar el desplazamiento entre las diferentes páginas del informe.
* **Interactividad avanzada:** Todas las visualizaciones están conectadas. Al hacer clic en un mes, todos los gráficos de la página se filtran para mostrar solo la información de ese periodo.


---

## 🚀 Cómo Utilizar este Proyecto

### 1. Descargar el archivo .pbix

Puedes descargar el archivo **`financial-performance.pbix`** (te recomiendo renombrar tu "Proyecto 4.pbix" a este nombre) desde este repositorio y abrirlo en Power BI Desktop para explorar las visualizaciones, el modelo de datos y las fórmulas DAX.

### 2. Filtros y Segmentación

El informe incluye segmentadores de **Fecha**. Úsalos para investigar el rendimiento en meses específicos o comparar la evolución entre 2019 y 2020.
