# Versionado y trazabilidad

```
Version:              1.0.0
Fecha de consolidación: 12 de agosto de 2026
Estado:               Apto para uso operacional
```

---

## Fuentes procesadas

| # | Fuente | Detalle | Procesamiento |
|---|---|---|---|
| **1** | **Video de entrenamiento** | `2026-08-04 19-45-51.mov` — 1:59:01, 1440×900, grabación de pantalla de Excel | Whisper large-v3 → **994 segmentos** |
| **2** | **Capa visual del video** | 111 fotogramas a resolución nativa en momentos operativos | Lectura directa de la barra de fórmulas |
| **3** | **Audio de respuestas** | `WhatsApp Ptt 2026-08-12 at 7.49.05 PM.ogg` — 24:01, opus mono | Whisper large-v3 → **322 segmentos** + recuperación de un tramo de 30 s |
| **4** | Transcripción del video | 1.001 líneas | Fuente para el mapa de conocimiento |
| **5** | Transcripción del audio | 332 líneas | Fuente para las fichas de las 14 preguntas |
| **6** | Mapa de conocimiento | 692 líneas | Estructuración intermedia |
| **7** | Auditoría de extracción v1 | 12 secciones | Origen de las 14 preguntas |
| **8** | Skills v1.0 | contexto + operación + 10 referencias | Base reestructurada |

---

## Cambios en esta versión

### Skill de Contexto — reescrita completa

| Sección | Cambio |
|---|---|
| §0 Procedencia | Añadida la segunda fuente (audio de respuestas) |
| §1 Quién es Amanda | Añadidos: proyección de mesada pensional, planeación tributaria, resolución de AXIA/United Financial |
| §2 Tu rol | Añadida la diferencia clave: Amanda captura con el cliente delante; el agente no |
| §3 Qué es un Plan | Añadido: **el entregable final es un PDF, no el Excel** |
| §4.6 | Ampliada con el producto de refuerzo (cobertura + acumulación en dólares) |
| §4.12 | Supuestos corregidos: TRM **+200** (antes "+200 a 300"), liquidación **sin primas y sin vacaciones** |
| **§5 Insumos** | **Reescrita.** Nuevo modelo de las dos reuniones · **cuatro** insumos en vez de tres · el archivo Word documentado · las 4 hojas base declaradas suficientes |
| **§6 Jerarquía** | **Reescrita.** Ya no es una construcción del proyecto: parte de la declaración de Amanda de que las fuentes no deberían contradecirse |
| **§7 Prioridad** | **NUEVA.** Orden explícito del plan, con la rama de capacidad negativa |
| §8 Anti-invención | Añadido el matiz de `Analizar Estrategia` en dos tiempos |
| §9 Límites | **Reescrita.** Tabla de tareas fuera de alcance por diseño |
| §10 Estándares | Añadidos: TRM coherente, neto/bruto, orden de prioridad, meses del fondo, fichas tributaria y pensional |

### Skill de Operación — reestructurada de 10 a 19 referencias

**Referencias nuevas (9):**

| Archivo | Contenido |
|---|---|
| `01-intake-y-fuentes.md` | modelo de reuniones, 4 insumos, jerarquía, detección temprana de flujo negativo |
| `02-contexto-humano.md` | archivo Word, 12 categorías de contexto, 4 señales que cambian el plan, ficha del cliente |
| `05-ingresos-y-nomina.md` | taxonomía de ingresos, bruto/neto, método del promedio con trazabilidad |
| `07-flujo-anualidades-y-provision.md` | los dos circuitos, la trampa del signo, la regla de las anualidades, diagnóstico del flujo |
| `09-patrimonio-y-capital-disponible.md` | los 5 bloques, el filtro de utilizabilidad, doble contabilidad, cuadre maestro |
| `11-inversiones.md` | comparativa de productos, los 5 criterios de recomendación, vehículos |
| `12-tributario-y-pensional.md` | las 4 deducciones, el proceso, los límites operacionales, las 2 fichas |
| `16-modelo-de-decision.md` | 12 decisiones descompuestas en inputs → … → validación |
| `18-discrepancias-resueltas.md` | 16 contradicciones con análisis y regla final |

**Referencias actualizadas (10):** mapa de hojas · captura · gastos y optimización · deudas · riesgos · plan de acción · calculadoras · escenarios · reglas · control de calidad.

---

## Preguntas de auditoría resueltas

| # | Pregunta | Estado |
|---|---|---|
| 1 | Jerarquía de fuentes | ✅ Resuelta — **reformula la premisa** |
| 2 | Tres TRM | ✅ Resuelta — era un error del ejemplo |
| 3 | Planeación tributaria | ✅ Resuelta a nivel de proceso |
| 4 | Fórmula del 15 % | ⏳ Pendiente de video |
| 5 | Las 8 hojas | ✅ Resuelta — diagnóstico previo |
| 6 | Semanas cotizadas | ✅ Resuelta — en ambas hojas |
| 7 | Calculadora de liquidación | ✅ Resuelta (método) · ⏳ renombrado |
| 8 | Formato de entrega | ✅ Resuelta — Excel → PPT → PDF |
| 9 | Archivo Word | ✅ Resuelta — cuarto insumo |
| 10 | Meses del fondo de emergencia | ✅ Resuelta — 1-3 salud / ≥6 resto |
| 11 | Escenario ≠ columna D | ❌ No resuelta — pregunta malinterpretada |
| 12 | Bloque del cónyuge | 🟡 Parcial — es intencional |
| 13 | Capacidad de ahorro negativa | ✅ Resuelta — orden reducido |
| 14 | AXIA / United Financial | ✅ Resuelta — no mencionar |

**11 resueltas · 1 parcial · 2 pendientes**

---

## Validaciones ejecutadas

| Validación | Resultado |
|---|---|
| Transcripción completa del audio, sin resumir | ✅ 322 segmentos + tramo de 30 s recuperado |
| Las 14 preguntas mapeadas una por una | ✅ ficha completa por pregunta |
| Conocimiento nuevo fuera de las 14 preguntas | ✅ 11 reglas nuevas extraídas |
| Cruce con video, transcripción, evidencia visual y auditoría v1 | ✅ 16 discrepancias documentadas |
| Fórmulas verificadas | ✅ 20 leídas · 4 inferidas y comprobadas · 6 marcadas no legibles |
| Análisis financiero técnico | ✅ ingresos, gastos, flujo, deudas, patrimonio, inversiones, tributario, pensional |
| Análisis del contexto humano | ✅ referencia dedicada con ficha del cliente |
| Reglas de Excel con celda y fórmula exactas | ✅ mapa completo de las 11 hojas usadas |
| Auditoría de completitud | ✅ ver informe de cierre |
| Auditoría de ejecutabilidad | ✅ ver informe de cierre |
| Paquete autocontenido | ✅ sin rutas locales, sin dependencias externas |
| Seguridad de la información | ✅ sin credenciales, sin datos reales de clientes, sin rutas locales |

---

## Incertidumbres restantes

| # | Incertidumbre | Mitigación en las skills |
|---|---|---|
| 1 | Método del cálculo tributario | Límite operacional explícito + ficha para escalar |
| 2 | Método de la proyección pensional | Ídem |
| 3 | Si un escenario ≠ D sustituye el plan | Regla conservadora + escalar |
| 4 | Si la hoja de liquidación se renombra por cliente | Instrucción de apuntar a la hoja como se llame |
| 5 | Edad de pensión en clientes mujeres | Usar 62 y señalar el caso |
| 6 | Estructura del PowerPoint de entrega | Se entrega Excel + informe |
| 7 | Contenido de las 8 hojas de diagnóstico | Fuera de alcance declarado |
| 8 | Umbrales para decidir si un gasto está alto | Test de 4 preguntas + escalar |
| 9 | Fórmulas no legibles (6) | Marcadas; no reconstruidas |
| 10 | Fuente única sin triangular | Declarado al inicio de la skill de contexto |

---

## Entregables que Amanda se comprometió a enviar

| # | Entregable | Resolvería |
|---|---|---|
| 1 | Video de proyección tributaria | P3, P4 |
| 2 | Video de proyección de mesada pensional | P6 |
| 3 | Video de la calculadora de liquidación | P7 |
| 4 | Video del entregable final (PPT → PDF) | P8 |
| 5 | Video de cómo sacar los gastos básicos | refuerzo |
| 6 | El archivo Word | P9 |
| 7 | Las 8 hojas del diagnóstico financiero | P5 |

**Amanda solicitó retroalimentación** sobre si la información quedó clara y qué entregables faltan.

---

## Convención de marcas

| Marca | Significado |
|---|---|
| **[E]** | Explícito — dicho por Amanda en el video o el audio |
| **[V]** | Verificado — comprobado contra pantalla, aritmética o segunda fuente |
| **[I]** | Inferencia razonable, declarada como tal |
| **[ND]** | No determinado — el agente pregunta, no decide |
| **[AMB]** | Ambiguo — se marca y se escala |
| **[CORR]** | Corrige una fuente anterior; se indica cuál manda |
