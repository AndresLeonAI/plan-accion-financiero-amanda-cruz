# 19 — Control de calidad y entrega (Fase 18)

**Ningún plan se entrega sin pasar este control completo.**

---

## A. Cuadres aritméticos obligatorios

Si alguno falla, **hay un error de construcción**. No se entrega.

### A.1 `Presupuesto` — por cada columna de propuesta

| # | Comprobación |
|---|---|
| 1 | `fila 11` = suma de los ítems de ingreso mensual |
| 2 | `fila 67` = suma de los **once subtotales azules** (14, 17, 20, 25, 37, 40, 43, 50, 56, 59, 64) |
| 3 | `fila 68` = `fila 11` |
| 4 | **`fila 69` = `fila 68` − `fila 67`** |
| 5 | `fila 77` = suma de los ítems de ingreso anual |
| 6 | **`fila 104` = `fila 80` + `fila 86` + `fila 91` + `fila 98`** |
| 7 | **`fila 105` = (`fila 104` − `fila 77`) / 12** — y el signo leído correctamente |
| 8 | `fila 106` = `fila 77` − `fila 104` |
| 9 | `fila 107` = `fila 69` − `fila 105` |
| 10 | `fila 66` espeja `fila 69` (no la modifiques) |

### A.2 `Plan de Acción` — los cuadres que cierran el plan

| # | Comprobación |
|---|---|
| 11 | `G6` = `Presupuesto`!D69 (o la columna del escenario elegido) |
| 12 | `G11` = suma de las fuentes mensuales |
| 13 | Cascada mensual: `H19 = G11 − G19`, `H(n) = H(n−1) − G(n)` |
| 14 | **`H` de la última estrategia mensual = 0** |
| 15 | `fila 31` Total `G` = `G11` · Total `H` = 0 |
| 16 | `G49` = suma de `G36:G48` |
| 17 | Cascada de capital: `H56 = G49 − G56`, `H(n) = H(n−1) − G(n)` |
| 18 | `G` de la última estrategia de capital = `H` de la penúltima |
| 19 | **`fila 76` Total `G` = `G49` · Total `H` = 0** |
| 20 | Doble contabilidad: `H(activo) = G(activo) − Σ` asignaciones a ese activo |
| 21 | **`H49` = `G60`** ⭐ *el cuadre maestro* |
| 22 | `E82` = `J21` · `J21` = `G21 × 12` |
| 23 | `E87` = suma de `E82:E86` |
| 24 | `E88` = `Presupuesto`!P9 |
| 25 | **`E89` = `E87` / `E88`** |

### A.3 Hojas auxiliares

| # | Comprobación |
|---|---|
| 26 | `Desprendibles`: cada mes, `B52` coincide con lo que el cliente **realmente recibió** |
| 27 | `Desprendibles`: cada promedio verde aterriza en su celda de `Presupuesto` columna D |
| 28 | `Desmonte Deudas`: `RESUMEN DEUDAS` se alimenta por fórmula desde `Info Patrimonio` |
| 29 | `Desmonte Deudas`: tasa periódica ≠ `"CAMBIAR TASA"` |
| 30 | `Desmonte Deudas`: escenario base y escenario con intervención calculados; ahorro = diferencia |
| 31 | `Calculadora liquidacion`: `B29` = `B27` + `B28` |
| 32 | `UNIVERSIDAD`: `D30` = suma de los totales por hijo · `F30` = suma de los ahorros mensuales USD |
| 33 | `ANALISIS`: **la prima total (fila 31) es idéntica en los tres escenarios** |

---

### A.4 Chequeos nuevos derivados del audio de Amanda

| # | Comprobación |
|---|---|
| 34 | **Una sola TRM coherente:** `PROYECTADO TRM` = TRM del día · todo lo demás = TRM del día **+ 200**. **Tres valores distintos = error** |
| 35 | `ANALISIS` fila 31: **la prima total es idéntica en los tres escenarios** |
| 36 | **Semanas cotizadas registradas en `INFORMACION Seg soc`!H14 Y en el COMENTARIO de `Info Patrimonio`** |
| 37 | Liquidación calculada **sin primas y sin vacaciones** |
| 38 | **`E89` (meses de cobertura) contrastado con la meta del perfil profesional**: salud 1-3 · resto ≥6 · default 6 |
| 39 | Si `E89` < meta: calculado **en cuántos meses se alcanza** al ritmo de `G21` |
| 40 | Ingresos por renta y honorarios **rotulados (neto) o (bruto)** |
| 41 | Si algún ingreso es bruto: **sus costos asociados registrados en *Otros*** |
| 42 | Objetivos **clasificados por horizonte** (corto / mediano / largo) |
| 43 | `Analizar Estrategia` presente donde el cliente no dio cifra; estimaciones **solo en COMENTARIOS y en amarillo** |
| 44 | **Las 4 deducciones tributarias** recopiladas: dependientes · intereses de vivienda · AFC+PV · medicina prepagada |
| 45 | Fichas **tributaria y pensional** redactadas y marcadas para revisión de Amanda |
| 46 | **Ningún impuesto ni mesada pensional calculados por el agente** |
| 47 | **Ningún 15 % de retención aplicado por defecto** |
| 48 | **Las 8 hojas de diagnóstico sin tocar** |
| 49 | **AXIA y UNITED FINANCIAL CONSULTANTS. no aparecen** en ninguna parte del entregable |
| 50 | **Orden de prioridad respetado**: coberturas → anualidades → fondo → inversiones |
| 51 | Si la capacidad es negativa: plan reducido a **deudas → anualidades → fondo mínimo**, sin inversiones |
| 52 | Si la capacidad es negativa: **verificado que no sea un error de captura** |

---

## B. Integridad estructural

- [ ] Todas las fórmulas originales de la plantilla **siguen siendo fórmulas** — ninguna sustituida por un valor fijo
- [ ] No se eliminaron filas, columnas ni hojas
- [ ] No se renombraron hojas
- [ ] Los enlaces entre hojas resuelven correctamente
- [ ] **Ningún `#¡REF!`, `#N/A`, `#¡DIV/0!` ni `#¡NOMBRE?`**
- [ ] Los `#¡VALOR!` de `Desmonte Deudas` posteriores a la extinción de una deuda: **verificados como esperados**
- [ ] Las filas agrupadas/ocultas siguen intactas (saltos 42→49, 60→76, 29→1321)
- [ ] Las listas desplegables siguen funcionando
- [ ] El archivo recalcula correctamente al cambiar un insumo

---

## C. Integridad de datos

### C.1 Completitud
- [ ] `INFORMACION Seg soc`: titular completo; cónyuge completo si aplica
- [ ] Fecha de ingreso a la compañía registrada (`C19`)
- [ ] Seguridad social: EPS, prepagada, ARL, cesantías, AFP, saldos, **semanas cotizadas**
- [ ] `Presupuesto` columna C: todos los rubros mensuales y anuales
- [ ] `Info Objetivos`: prioridad, objetivo, descripción, plazo, valor
- [ ] `Info Patrimonio`: los cinco bloques
- [ ] **Cada deuda con saldo, tasa, cuotas pendientes y cuota mensual**

### C.2 Reglas de tratamiento aplicadas
- [ ] Todos los gastos **mensualizados** (trimestrales prorrateados)
- [ ] **Colegio:** `×11/12`, o rotulado "pensión + matrícula"
- [ ] **Mascotas:** un solo ítem agregado
- [ ] **Ayuda de aseo:** verificado si incluye prestaciones
- [ ] **Tarjeta de crédito:** no duplicada
- [ ] **AFC:** cuota en deuda, excedente en ahorro
- [ ] **Administración de rentas:** en *Otros*, no en *Hogar*
- [ ] **Pareja:** descuentos de nómina identificados con nombre entre paréntesis
- [ ] **Varios inmuebles:** identificados por ubicación
- [ ] **Impuestos:** discriminados por activo
- [ ] **Seguros:** vencimiento y compañía en comentarios
- [ ] Conceptos anuales en Anualidades, no en mensuales

### C.3 Anti-invención
- [ ] **Ningún dato inventado**
- [ ] Los faltantes marcados con **`Analizar Estrategia`** o celda vacía + comentario
- [ ] Todos los valores calculados por ti, **en amarillo**
- [ ] Todos los supuestos, **en comentario y en el informe**
- [ ] Ninguna metodología externa introducida
- [ ] Las discrepancias entre fuentes, **señaladas y no resueltas a la fuerza**

---

## D. Cobertura metodológica

- [ ] **Los siete riesgos revisados uno por uno** — vida, salud, incapacidad, iliquidez, patrimonial, inflacionario, país
- [ ] Coberturas del empleador identificadas y su dependencia advertida
- [ ] Riesgos descubiertos → convertidos en gasto o en estrategia
- [ ] Brechas cualitativas ("cubierto pero no bien") documentadas
- [ ] **Regla de las anualidades aplicada según el signo de la fila 105**
- [ ] **Análisis de deuda ejecutado ANTES** de fijar el monto de la estrategia mensual
- [ ] Restricción del AFC (solo crédito hipotecario) respetada
- [ ] Secuenciación de deuda decidida **simulando**, no por tasa ni por saldo
- [ ] Encadenamiento de cuota liberada ubicado en la fecha real
- [ ] **Cada objetivo de `Info Objetivos` atendido por al menos una estrategia**, o con brecha cuantificada
- [ ] Fondo de emergencia expresado en **meses de cobertura**
- [ ] Liquidación por despido sin justa causa integrada al fondo
- [ ] Escenarios alternativos construidos si el cliente planteó incertidumbres

---

## E. Personalización y coherencia humana

- [ ] **Ningún dato del ejemplo de entrenamiento sobrevive** en el archivo
  > ⚠️ El archivo del video contiene nombres inconsistentes ("Juliana", "Camila", "Andrés", "Sofía"). **Verifica que todos los nombres, entidades, hijos y fechas correspondan al cliente real.**
- [ ] El título del `Plan de Acción` lleva el nombre del cliente
- [ ] Los nombres de hijos, entidades y productos son los reales
- [ ] **Los motivos de la reunión de sensibilización están reflejados** en comentarios y objetivos
- [ ] Las restricciones declaradas por el cliente se respetan
- [ ] Los recortes propuestos pasan el test de calidad de vida
- [ ] Los gastos con fecha de liberación están anotados
- [ ] Las acciones que requieren gestión del cliente (ej. negociar cuota de manejo) están listadas

---

## F. Sentido financiero

Más allá de que cuadre, **¿tiene sentido?**

- [ ] ¿Los ingresos son coherentes con el cargo y la profesión declarados?
- [ ] ¿Los gastos son coherentes con el nivel de ingreso y el tamaño del hogar?
- [ ] ¿El patrimonio es coherente con la trayectoria del cliente?
- [ ] ¿Las tasas de las deudas están en rangos plausibles del mercado colombiano?
- [ ] ¿Los meses de cobertura del fondo de emergencia son razonables?
- [ ] ¿El plan resuelve efectivamente lo que el cliente pidió?
- [ ] ¿Alguna estrategia contradice una restricción declarada?
- [ ] ¿Hay algún número que, leído en voz alta ante el cliente, resultaría absurdo?

**[E]** El estándar declarado: *"esta es la forma como se organiza un planteamiento de un plan de acción de estas condiciones, **donde se revisa a 360 grados la situación del cliente**."*

---

## G. Informe de entrega

Todo plan se entrega **acompañado de un informe** con seis secciones:

### 1. Resumen del plan
- Escenario base utilizado (qué columna)
- Capacidad de ahorro mensual y capital disponible
- **Número de estrategias** y qué resuelve cada una
- Meses de cobertura del fondo de emergencia
- Ahorro proyectado en intereses de deuda y nuevas fechas de liberación

### 2. Cambios respecto de lo declarado por el cliente
Una línea por cada celda amarilla: valor original → valor propuesto → **criterio**.

### 3. Supuestos aplicados
Los del método (TRM 4,5 %, universidad +9 %, ingreso a los 17, carrera de 5 años, vacaciones tomadas, colegio 11 meses…) **más cualquiera adicional que hayas tenido que asumir**.

### 4. Datos faltantes
Qué falta, dónde está marcado, y **qué se necesita del cliente** para completarlo.

### 5. Discrepancias detectadas
Fuente A dice X, fuente B dice Y, **qué se hizo** (o por qué quedó sin resolver).

### 6. Puntos que requieren decisión humana
- Decisiones de **Amanda**: recortes sensibles, priorización entre objetivos, recomendación de producto
- Decisiones del **cliente**: elección de producto, venta de activos, cambios de vida
- Situaciones no cubiertas por el método
- **[ND]** y **[AMB]** encontrados

---

## H. Los cuatro errores que invalidan un plan

| # | Error | Por qué es grave |
|---|---|---|
| **1** | **Inventar un dato** | Rompe la confianza y puede producir una recomendación dañina. Un hueco marcado es entregable; un dato falso no |
| **2** | **Leer mal el signo de la provisión mensual** | Invierte la arquitectura del plan: se provisiona cuando sobra, o no se provisiona cuando falta |
| **3** | **Duplicar gastos** (tarjeta de crédito, AFC, administración) | Infla el egreso, reduce artificialmente la capacidad de ahorro y hace el plan más pobre de lo que debería |
| **4** | **Dejar saldo sin asignar** | El plan queda incompleto: hay dinero sin destino y objetivos sin financiar |

---

## Sello final

**Solo se entrega cuando las ocho secciones anteriores están completas.**

> **La fidelidad al método vale más que la completitud aparente.**
> Un plan con huecos marcados es entregable. Un plan completo con datos inventados es un daño.
