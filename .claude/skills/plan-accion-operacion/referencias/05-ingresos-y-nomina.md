# 05 — Ingresos, nómina y normalización

Todo lo relativo a lo que entra: clasificación, periodicidad, bruto/neto, y el método del promedio.

---

## 1. El principio rector

**[E]** *"En estas casillas de ingresos lo que vemos y se debe anotar son **todos los ítems que entran al bolsillo del hogar**, tanto ingresos de él como ingresos de ella."*

**[E]** *"Todos los ingresos del mes de la persona **a detalle**. Si es por salario ordinario, si es salario integral y todos los ítems que el cliente me deja conocer, **yo los detallo** en ese Excel."*

> **Detalle, no agregación.** Un renglón por concepto. Nunca "ingresos varios".

---

## 2. Taxonomía de ingresos

### 2.1 Por naturaleza

| Tipo | Ejemplos | Dónde va |
|---|---|---|
| **Salario** | integral · ordinario · prestación de servicios | `Presupuesto` fila 6 |
| **Variable de nómina** | bonos, comisiones, acciones, adelantos | filas 7-9 — **se promedian** |
| **Rentas** | apartamentos, locales, bodegas | fila 10 — **marcar neto/bruto** |
| **Honorarios / consultoría** | actividad independiente | fila 9 |
| **Dividendos** | de sociedades o inversiones | mensuales → fila 10 · anuales → fila 73 |
| **Reembolsos del empleador** | banda ancha, matrícula, servicios | ver §5 |
| **Anuales** | prima de junio, prima de diciembre, extraprima, bono anual, comisión grande, utilidades | fila 73+ |

**[E]** Tipos de contrato que la plantilla ofrece como lista: **Salario integral · Salario ordinario · Prestación servicios**.

### 2.2 Por periodicidad — la regla de asignación

**[E]** *"**Todo lo que sea mensual a nivel de ingresos** lo coloco en el ítem de ingresos."*
**[E]** *"si recibe dividendos también lo coloco allí, **si mensuales**."*

```
¿Se recibe todos los meses?  →  SÍ  →  Bloque INGRESOS MENSUALES (filas 6-10)
                             →  NO  →  Bloque INGRESOS ANUALES  (filas 73-76)
```

**[E]** Qué va en anuales: *"desgloso qué tanto reciben: si son **primas en junio, prima en diciembre, extraprima**, o si es solamente **un bono anual**, o si son bonos y aparte de eso **una comisión grande**."*

> Una comisión grande y esporádica es **anual**, aunque el concepto "comisión" suene mensual. Manda **cuándo se cobra**, no cómo se llama.

### 2.3 Bruto vs. neto — **regla explícita**

**[E]** *"si tiene un ingreso adicional por rentas de apartamento, yo coloco el valor de la renta y **usualmente especifico si es un ingreso neto o si es un ingreso bruto**."*

> **Regla:** todo ingreso por **renta** o por **actividad independiente** se rotula en la columna B:
> - `Apto. Fontibón (neto)`
> - `Consultoría (bruto)`
> - `Local Suba (bruto — sin verificar)` + comentario, si no se sabe

**Por qué importa:** un ingreso bruto arrastra costos (administración, seguro, predial, retención) que deben aparecer como gasto. Si se registra bruto y no se registran sus costos, el excedente sale inflado.

**[E]** Y los costos asociados tienen destino propio: *"en el ítem de **otros**… desgloso la administración de ese apartamento… cuánto paga si paga algún seguro mensual, si de repente no está alquilado y tiene que pagar los servicios públicos."*

### 2.4 Orden en pareja

**[E]** *"si fueran dos personas se relacionan entonces **el ingreso de ella primero**"* y después los de él.

---

## 3. Ingresos anuales y retención

**[E]** *"idealmente colocar acá el dato que da el cliente. Sería importante entender **cuánto es lo que le cobran por retención en la fuente y descontarlo de una vez**; pero si no se tiene, al menos relacionar el monto que aparece en su desprendible de nómina."*

**[E]** *"si ya tiene por descontado la retención en la fuente, dejamos el mismo valor. De lo contrario, se reajusta."*

| Caso | Acción |
|---|---|
| El valor llega **ya neto** de retención | registrarlo tal cual |
| Llega **bruto** y se conoce el % de retención | aplicarlo y **documentarlo en comentario** |
| Llega bruto y **no se conoce** | registrar el bruto + comentario advirtiéndolo + **escalar** |

> ⚠️ **[CORR]** En el video aparece un caso con **15 %** de retención. **No es una constante del método**: era el porcentaje de ese cliente. **Nunca apliques un 15 % por defecto.**
> **[ND]** El cálculo real lo hace Amanda en una herramienta externa — ver [12](12-tributario-y-pensional.md).

---

## 4. El método del promedio (Fase 7)

### 4.1 Cuándo aplica

**[E]** *"esta parte de las acciones se mueven de forma diferente cada mes, **no es algo regular**."*
**[E]** *"esta persona recibe acciones y cada mes son diferentes. **Por esa razón me llevo el promedio y prefiero trabajarlo sobre un promedio**."*

Aplica a **todo concepto que varíe mes a mes**, de ingreso **y** de descuento:

| Aplica | No aplica |
|---|---|
| Bonos, comisiones, acciones | Salario fijo |
| Retención en la fuente | Gastos estables |
| Salud, pensión, fondo de solidaridad **cuando la base varía** | Cuotas de crédito |
| Adelantos, reembolsos, compensaciones | |

**[E]** *"todos los demás ítems **los dejé igualitos**."* → **solo se promedia lo variable.**

### 4.2 Montar la hoja `Desprendibles de nom.`

1. **Una columna por mes** en C5:H5 (`enero 2026`, `febrero 2026`, …)
2. **Ingresos** desde B6 — un renglón por concepto del desprendible
3. **Egresos** desde B26 — un renglón por descuento
4. **[E]** *"Especifiqué, **dejé súper claro cada ítem**"* — nada agregado
5. Totales: `B14` TOTAL INGRESOS · `B50` TOTAL EGRESOS · `B52` INGRESOS − EGRESOS

**Conceptos observados en el ejemplo:**
- *Ingresos:* Salario Integral · Peer Bonus · Vacaciones Disfrutadas · Acciones GSU · Broadband Reimmbursement · Bono Anual · Gross Up · Tuition Reimbursement Benefit
- *Egresos:* Retención en la Fuente · Salud EGM · Pensión IVM · Aporte fondo solidaridad · Aporte AFC · Subsistencia · Offset for Broadband reimbursement · Adelanto GSU · Tuition Reimbursement Benefit

### 4.3 El control de realidad

**[E]** *"en la celda B52 vemos lo que realmente esos ingresos menos esos gastos —o esas deducciones que le hicieron— lo que se evidencia en el desprendible de nómina, **que sea acorde**, y se coloca acá el valor que recibió."*

> **Cada mes, `B52` debe coincidir con lo que el cliente efectivamente recibió en su cuenta.**
> Si no cuadra, falta un concepto. **No sigas hasta cuadrarlo.**

### 4.4 Calcular suma y promedio

| Columna | Contenido |
|---|---|
| **R** | `=+SUMA(C7:H7)` **[V]** — suma del periodo |
| **S** | promedio de la fila |

**[E]** *"en la columna R saqué la suma de toda la fila de cada ítem… y luego en la columna S saqué el promedio de cada fila."*

### 4.5 Marcar en verde

**[E]** *"acá **los verdecitos** son como los datos más importantes a tener en cuenta **que se están moviendo**."*

Resalta en verde, en R y S, solo los conceptos variables que vas a llevar al presupuesto. Es la trazabilidad de por qué ese número está en la columna D.

### 4.6 Trazabilidad verificada

**[V]** Los siete promedios del ejemplo aterrizan exactamente en su celda:

| Concepto | R (suma) | **S (promedio)** | → destino |
|---|---|---|---|
| Peer Bonus | 2.170.000 | **434.000** | `Presupuesto`!D7 ✓ |
| Acciones GSU | 138.470.048 | **27.694.010** | `Presupuesto`!D8 ✓ |
| Salud EGM | 7.020.100 | **1.170.017** | `Presupuesto`!D44 ✓ |
| Pensión IVM | 7.020.100 | **1.170.017** | `Presupuesto`!D45 ✓ |
| Retención en la Fuente | 78.477.000 | **13.079.500** | `Presupuesto`!D46 ✓ |
| Aporte fondo solidaridad | 1.755.600 | **292.600** | `Presupuesto`!D47 ✓ |
| Adelanto GSU | 87.236.115 | **17.447.223** | `Presupuesto`!D48 ✓ |

**Marca cada celda de destino en amarillo** — es un valor calculado por ti.

> ⚠️ El promedio va a la **columna D (propuesta)**, nunca a la **C (regular)**. La C conserva lo que el cliente declaró.

### 4.7 Usos secundarios

**[E]** *"ya relacioné los desprendibles de nómina para ver qué tanto es el promedio y poderle **explicar al cliente todo el tema de su salario**, entender cómo sería **la parte tributaria**."*

La hoja también sirve como soporte visual en la reunión y como insumo del análisis tributario — ver §5.

---

## 5. Reembolsos y beneficios del empleador

Tres tratamientos distintos según su naturaleza:

| Tipo | Ejemplo del video | Tratamiento |
|---|---|---|
| **Reembolso de un gasto** | *"su compañía le daba un dinero reconociéndole el recibo de la luz"* | **Descontar del gasto** en la propuesta: D27 = 568.000 − 150.000 = **418.000** |
| **Ingreso en especie / compensación** | Broadband Reimbursement con su Offset | Aparecen como ingreso **y** como egreso en la nómina; se neutralizan |
| **Cobertura** | seguro de vida, salud, incapacidad | **No es dinero.** Se documenta en los 7 riesgos y **se advierte la dependencia** — ver [10](10-riesgos-y-coberturas.md) |

---

## 6. Deducciones tributarias que se identifican aquí

**[V]** La columna Z de `Desprendibles de nom.` contiene cuatro anotaciones que Amanda confirmó en el audio como **las cuatro deducciones que bajan la base gravable**:

```
Interes de Vivienda
AFC, PV              ← AFC y Pensión Voluntaria juntas
Dependientes
Medi. Prepagada
```

Al montar la hoja, **identifica y anota estos cuatro conceptos** si aparecen en la nómina. Alimentan la proyección tributaria — ver [12](12-tributario-y-pensional.md).

---

## Checklist de ingresos

- [ ] Cada fuente de ingreso en su propio renglón, sin agregar
- [ ] Clasificación mensual vs. anual según **cuándo se cobra**, no cómo se llama
- [ ] Rentas y honorarios rotulados **(neto)** o **(bruto)**
- [ ] Costos asociados a rentas brutas registrados en *Otros*
- [ ] Dividendos: mensuales arriba, anuales abajo
- [ ] En pareja: ingresos de ella primero
- [ ] Ingresos anuales: retención descontada o advertida en comentario
- [ ] **Sin aplicar 15 % por defecto**
- [ ] Desprendibles montados mes a mes, un concepto por fila
- [ ] `B52` de cada mes cuadra con lo efectivamente recibido
- [ ] Columnas R (suma) y S (promedio) calculadas
- [ ] Conceptos variables marcados en **verde**
- [ ] Promedios llevados a la **columna D** y marcados en **amarillo**
- [ ] Las 4 deducciones tributarias identificadas
