# Visualizaciones — Chile: entre el éxodo y la zanja

Código D3.js de cada visualización del artículo. Para ejecutar, abrir el HTML correspondiente en un navegador o integrar en la página Astro de SurTexto.

## Listado

| # | Archivo | Descripción | Datos |
|---|---------|-------------|-------|
| 1 | `01_desplazados_americas.js` | Mapa proporcional: desplazados por país en América 2025 | `datos/desplazados_americas_2025.csv` |
| 2 | `02_timeline_sismica.js` | Timeline de terremotos y evacuaciones en Chile 1960-2025 | Datos en código (USGS + IDMC) |
| 3 | `03_migracion_neta.js` | Línea temporal de migración neta 2006-2025 | `datos/migracion_neta_chile.csv` |
| 4 | `04_anatomia_crisis.js` | Waffle chart / iconos proporcionales de la crisis migratoria | `datos/crisis_migratoria_chile.csv` |
| 5 | `05_recortes.js` | Barras descendentes: recortes + nueva carga | `datos/recortes_kast_2026.csv` |

## Dependencias

- D3.js v7 (`https://cdn.jsdelivr.net/npm/d3@7`)
- Sin otras dependencias

## Paleta

```javascript
const ST = {
  900: '#3B3231',  // texto, ejes
  600: '#B69476',  // dato secundario
  400: '#C67132',  // accent, alerta
  200: '#DFBFA1',  // fondo, referencia
  50:  '#f7f2ec',  // background
  accent: '#C67132',
  highlight: '#ECB033',
};
```
