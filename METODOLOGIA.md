# SurTexto — Metodologia de Periodismo de Datos

Proceso editorial para producir una pieza semanal por pais con visualizaciones de datos.

---

## Principios

1. **Narrativa primero, datos despues.** El articulo tiene arco narrativo: presentacion, descripcion, desarrollo, climax, cierre. Los datos dan profundidad, no son el articulo.
2. **Los datos dan la extension.** El cable EFE da la estructura y los hechos clave. Los datos publicos dan el contexto, la comparacion, la historia. Sin datos, el articulo es un cable reescrito. Con datos, es periodismo.
3. **Expresividad visual.** Las visualizaciones no son graficas — son piezas expresivas. Color, forma, posicion, movimiento, escala deben comunicar la emocion del dato. Un bar chart puede ser correcto pero no expresivo. Un treemap con colores que gritan emergencia es expresivo.
4. **Rigor absoluto.** Cada dato debe tener fuente verificable. No hay margenes de interpretacion con cifras. Si el dato es estimacion, se dice. Si hay incertidumbre, se muestra. No se lleva al lector a conclusiones que los datos no soportan.

---

## Proceso por articulo

### Paso 1: Seleccion editorial (del repositorio S3)

- Revisar cables curados de la semana por pais
- Identificar el tema con mayor potencial de datos:
  - Tiene cifras concretas en el cable?
  - Existen fuentes publicas para ampliar?
  - Permite comparacion temporal o entre paises?
  - El tema afecta la vida cotidiana de la audiencia?

### Paso 2: Investigacion de datos

Fuentes por orden de prioridad:

1. **APIs de datos abiertos** — World Bank, CEPAL, FAO, NOAA, etc.
   - Datos estructurados, descargables, citables
   - Usar siempre que existan

2. **Institutos nacionales de estadistica** — INE, INEGI, INDEC, DANE, etc.
   - Datos oficiales del pais, alta credibilidad
   - Muchos tienen portales de datos abiertos

3. **Organismos internacionales** — ONU, IDMC, ACNUR, OMS, etc.
   - Informes anuales con datos comparativos
   - PDFs con tablas extraibles

4. **Papers y reportes** — academia, think tanks, ONGs
   - Datos procesados con metodologia explicita
   - Siempre citar la fuente primaria

### Paso 3: Verificacion de datos (fact-check)

Antes de visualizar:

- [ ] Cada cifra tiene fuente primaria identificada
- [ ] Los datos son del periodo correcto (no mezclar anos)
- [ ] Las unidades son consistentes (millones vs miles, USD vs moneda local)
- [ ] Los porcentajes suman 100% cuando deben
- [ ] Las comparaciones son justas (misma base, mismo periodo)
- [ ] Si hay estimaciones, estan marcadas como tal
- [ ] Si hay margenes de error, estan documentados

### Paso 4: Estructura narrativa

```
PRESENTACION
  Hook: dato que sorprende o contradice expectativas
  Contexto minimo: por que importa ahora

DESCRIPCION
  Los hechos: que paso, segun el cable + datos adicionales
  Primera visualizacion: el dato central, expresivo

DESARROLLO
  Profundidad: comparacion temporal, entre paises, o entre grupos
  Segunda visualizacion: la comparacion, la tendencia, el patron
  Voces: citas del cable, declaraciones oficiales

CLIMAX
  El dato que cambia la perspectiva
  Tercera visualizacion: el dato mas impactante
  Conexion con la vida del lector

CIERRE
  Hacia donde va esto
  Que no sabemos aun
  Fuentes y metodologia
```

### Paso 5: Diseno de visualizaciones

Cada viz debe responder:

| Pregunta | Respuesta |
|----------|-----------|
| Que dato muestra? | Un numero, una tendencia, una comparacion, una distribucion |
| Que emocion transmite? | Urgencia, esperanza, contraste, escala |
| Que forma es la mas expresiva? | Bar, treemap, mapa, strip plot, timeline, waffle, etc. |
| Es responsive? | Debe verse bien en movil (430px) y desktop (1280px) |
| Tiene fuente? | Siempre al pie: "Fuente: [organismo], [ano]" |

Paleta de colores SurTexto:
- `#C67132` (accent) — dato principal, alerta
- `#ECB033` (highlight) — segundo dato, contraste
- `#B69476` (st-600) — dato secundario
- `#DFBFA1` (st-200) — fondo, referencia
- `#3B3231` (st-900) — texto, ejes

### Paso 6: Implementacion tecnica

- D3.js para visualizaciones interactivas
- SVG responsivo con viewBox
- Tooltips con datos contextuales
- Pagina Astro dedicada por edicion (no embeber en article body)
- Datos hardcodeados en el script (no API calls desde el frontend)

### Paso 7: Publicacion

- Crear pagina Astro en `frontend/src/pages/ediciones/YYYY-MM-DD/[slug].astro`
- Subir a VPS: build + restart frontend
- Enviar newsletter con highlights
- Push notification (cuando PWA Fase 4 este lista)

---

## Checklist de calidad por pieza

- [ ] Arco narrativo completo (5 actos)
- [ ] Minimo 2 visualizaciones D3
- [ ] Cada viz tiene fuente al pie
- [ ] Todas las cifras verificadas contra fuente primaria
- [ ] Responsive: probado en movil real
- [ ] Sin conclusiones que los datos no soportan
- [ ] Titulo que engancha sin ser clickbait
- [ ] Subtitulo que resume el hallazgo principal
