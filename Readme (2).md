# Dashboard de Indicadores: Barcelona 2015-2023

Panel web interactivo de una sola página que presenta **10 indicadores cuantitativos** sobre la evolución de Barcelona durante las dos legislaturas de Ada Colau (2015-2023): seguridad, vivienda, espacio público, finanzas municipales y economía.

* **Autoría:** @bcnopnemind
* **Archivo:** `dashboard\_barcelona\_colau.html`
* **Idioma:** español
* **Fuente principal citada:** [Open Data Ajuntament de Barcelona](https://opendata-ajuntament.barcelona.cat/data/ca/dataset)

\---

## Contenido

### KPIs destacados (cabecera)

|Indicador|Variación mostrada|Rango|
|-|-|-|
|Precio del alquiler medio (INCASÒL)|+49,2 %|688 € → 1.027 €/mes|
|Percepción de inseguridad (Barómetro)|+714 %|3,4 % → 27,7 %|
|Quejas de limpieza y espacio público (IRIS)|+41,7 %|72.000 → 102.000 incidencias/año|
|Deuda viva municipal (SEC)|+49,8 %|835 M€ → 1.251 M€|

### Los 10 gráficos

|#|Indicador|Tipo|Comparativa|Fuente citada|
|-|-|-|-|-|
|1|Inseguridad como principal problema vecinal|Línea|—|Baròmetre Semestral de Barcelona|
|2|Infracciones penales por 1.000 habitantes|Barras|Barcelona vs. Madrid|Balanç de Criminalitat (Min. Interior)|
|3|Sobrecarga financiera del alquiler (>40 % de ingresos)|Línea|Barcelona vs. media UE-27|O-HB / Eurostat|
|4|Precio del alquiler oficial (€/mes)|Barras|—|Lloguer mitjà mensual (INCASÒL)|
|5|Quejas e incidencias en limpieza y vía pública|Línea|—|IRIS|
|6|Valoración de la gestión municipal (buena vs. mala)|Línea|Positiva vs. negativa|Baròmetre Semestral|
|7|Personas sin hogar durmiendo al ras|Barras|—|XAPSLL: Diagnosi del Sensellarisme|
|8|Cuota de inversión extranjera directa productiva|Barras|Cataluña vs. Madrid|DataInvex|
|9|Deuda viva del Ayuntamiento (M€)|Barras|—|Evolució del deute de l'Ajuntament|
|10|Aportación al PIB nacional|Línea|Cataluña vs. Madrid|INE: Contabilitat Regional d'Espanya|

Todas las series usan los años **2015, 2017, 2019, 2021 y 2023** (el gráfico 10 termina en 2022 por disponibilidad de la Contabilidad Regional).

\---

## Cómo usarlo

No requiere instalación ni servidor. Basta con:

1. Descargar `dashboard\_barcelona\_colau.html`.
2. Abrirlo en cualquier navegador moderno (Chrome, Firefox, Edge, Safari).

> \*\*Nota:\*\* se necesita conexión a internet, ya que carga Chart.js y la tipografía Inter desde CDN.

\---

## Detalles técnicos

* **Tecnologías:** HTML5, CSS3 (variables CSS, Grid, Flexbox) y JavaScript vanilla.
* **Librerías externas:**

  * [Chart.js](https://www.chartjs.org/) (vía jsDelivr) para los gráficos.
  * [Google Fonts](https://fonts.google.com/): Inter.
* **Diseño:** tema oscuro, *responsive* (los gráficos pasan de 2 columnas a 1 por debajo de 1024 px), tarjetas con efecto *hover*.
* **Estructura del archivo:**

  1. `<style>`: paleta de colores y estilos.
  2. Cabecera con título, autoría y metadatos.
  3. Rejilla de 4 KPIs.
  4. Rejilla de 10 tarjetas de gráficos (cada una con título, descripción, lienzo y pie con autor y enlace al dataset).
  5. `<script>`: configuración y creación de los 10 gráficos.

### Modificar los datos

Los datos están **escritos directamente en el código** (no se cargan desde una API ni un archivo externo). Para actualizarlos, busca el gráfico correspondiente en el bloque `<script>` (`// 1. Inseguridad Barómetro`, `// 2. Tasa Criminalidad`, etc.) y edita los arrays:

```js
labels: \['2015', '2017', '2019', '2021', '2023'],
data: \[3.4, 7.8, 29.1, 14.5, 27.7],
```

Si cambias los valores de un gráfico, recuerda actualizar también el KPI de cabecera y la descripción asociados.

\---

## Notas metodológicas y limitaciones

Conviene tener en cuenta lo siguiente al citar o reutilizar el panel:

* **Datos introducidos a mano.** Los valores no se extraen automáticamente de los portales oficiales, por lo que deben contrastarse con las fuentes originales antes de usarlos en un contexto formal.
* **Enlaces genéricos.** Varios pies de gráfico enlazan al catálogo general de Open Data BCN y no a un dataset concreto (gráficos 2, 7, 8 y 10), lo que dificulta la verificación.
* **Variación del KPI de inseguridad.** El +714 % es un cambio *relativo* sobre un porcentaje de partida muy bajo (3,4 % → 27,7 %); equivale a +24,3 puntos porcentuales. Además, la serie no es monótona (29,1 % en 2019, 14,5 % en 2021).
* **Redondeos.** Con los datos del gráfico 4, el alquiler pasa de 688 € a 1.027 €, lo que supone aproximadamente +49,3 %, y no +49,2 %.
* **Ámbito territorial mixto.** Algunos indicadores son de la ciudad (barómetro, IRIS, deuda), otros de Cataluña frente a Madrid (IED, PIB) y otros comparan con la UE-27; no todos son comparables entre sí.
* **Causalidad.** El panel muestra evolución temporal entre 2015 y 2023, pero no establece por sí mismo que los cambios se deban a la gestión municipal: en varios indicadores influyen factores autonómicos, estatales y globales (pandemia, mercado inmobiliario, política monetaria, etc.).
* **Selección de indicadores.** El conjunto elegido es mayoritariamente de tendencia negativa; no incluye indicadores potencialmente favorables (empleo, turismo, movilidad, medio ambiente, etc.), por lo que ofrece una visión parcial del periodo.

\---

## Licencia y atribución

Según el pie de página del propio dashboard: *libre distribución bajo mención de autoría* (**@bcnopenmind**). Los datos originales pertenecen a sus respectivos organismos (Ajuntament de Barcelona, INCASÒL, INE, Ministerio del Interior, Eurostat, DataInvex, XAPSLL, entre otros).

