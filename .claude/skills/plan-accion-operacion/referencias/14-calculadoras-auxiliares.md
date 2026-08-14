# 14 — Calculadoras auxiliares

Cuatro hojas de apoyo: liquidación, TRM, universidad y comparativa de productos.

---

## A. `Calculadora liquidacion Andrés` — liquidación por despido sin justa causa

### Para qué sirve

**[E]** *"la calculadora de liquidación nos sirve para entender cuánto sería el fondo de emergencias, **integrándolo con una liquidación por despido sin justa causa en el peor de los escenarios**."*

Es la aplicación directa del principio de **no depender del empleador**: si el cliente pierde el trabajo, ¿con cuánto cuenta?

### Cómo se diligencia

| Celda | Qué poner | Origen |
|---|---|---|
| **B8** | **fecha de ingreso** | `INFORMACION Seg soc`!C19 |
| **C8** | **fecha de retiro** | **la fecha de la reunión con el cliente** |
| **F8** | vacaciones tomadas | ver regla abajo |
| C10 | salario | `Presupuesto`!C6 o el desprendible |
| C11 | subsidio de transporte | si aplica |
| C13 / D13 | fecha de prima (desde / hasta) | |

**[E]** *"En la celda B8 coloco la fecha de ingreso del cliente que mencionó en la información de seguridad social; la fecha del retiro en la casilla C8, **teniendo presente la fecha en la cual voy a tener la reunión con el cliente**, y ya él me calcula el resto de la liquidación."*

### ⭐ La regla del cálculo básico [E]

**[E]** *(video)* *"Si me sale vacaciones acumuladas, le coloco en la celda F8, **que se las tomo completas**."*

**[E]** *(audio — amplía la regla)* *"básicamente tengo presente **el monto que gana de ingreso mensual promedio** que gana mi cliente, **la fecha de ingreso**, y **lo liquido año por año**. Y luego le muestro a mi cliente **sin primas, sin vacaciones, sino con lo básico**, cuánto podría ser esa liquidación en general."*

> **Regla consolidada: la liquidación se calcula sobre LO BÁSICO — sin primas y sin vacaciones.**
>
> Supuesto deliberadamente conservador: **subestima** el resultado para no inflar el fondo de emergencia.

**Los dos insumos obligatorios:**
1. **Ingreso mensual promedio** del cliente
2. **Fecha de ingreso** a la compañía

Y se liquida **año por año** (filas 17-21).

### Lo que devuelve

| Celda | Contenido |
|---|---|
| D4 / E4 / F4 | tiempo en la empresa: años / meses / días |
| Fila 16 | encabezados: **B Año Inicio · C Año Final · D Indemnización** |
| B17:D21+ | un renglón por año trabajado |
| B24 / D24 | **Total** de indemnización |
| A27 / **B27** | Indemnización |
| A28 / **B28** | Salario |
| A29 / **B29** | **Liquidación = B27 + B28** **[V]** |

**[E]** *"me hace el cálculo… el año de inicio, el final del año y la indemnización correspondiente usando la fórmula que aparece registrada allí. Al final me entrega el total de la indemnización, el valor del salario, y la liquidación, que la suma entre la indemnización más el salario. **Y ese valor es el que llevo al plan de acción y lo coloco en liquidación sin justa causa.**"*

**[CORR]** El audio dice *"la suma de la celda P27 más la celda B28"*. La pantalla confirma **B27 + B28 = B29**, y `Plan de Acción`!E86 referencia exactamente **B29**.

**[V] Ejemplo:** 65.979.738 (indemnización) + 12.231.324 (salario) = **78.211.062**

**[ND]** El motor interno de la indemnización (la fórmula por año) no fue legible. **No lo reconstruyas** — usa la calculadora tal cual.

**[AMB]** La hoja lleva el nombre del cliente del ejemplo. Consulta antes de renombrarla o duplicarla.

### Destino

`Plan de Acción`!E86 = `=+'Calculadora liquidacion «Cliente»'!B29` **[V]**

---

## B. `PROYECTADO TRM` — proyección de devaluación

### Para qué sirve

Convertir montos en USD a COP **en el horizonte del objetivo**, no a la TRM de hoy. Sin esto, cualquier proyección en dólares a 20 o 25 años queda mal valorada.

### Estructura

| Col | Campo |
|---|---|
| **B** | No AÑOS (0, 1, 2 … 35) |
| **C** | AÑO |
| **D** | VALOR TRM proyectada |
| **E** | **CRECIMIENTO PROYECTADO — 4,5 %** constante |

- **Fila base (No AÑOS = 0):** la TRM del día
- **Resaltadas en amarillo:** años **10, 15, 20 y 25** — son los horizontes que se usan aguas abajo

### El supuesto y su fundamento [E]

> *"le coloco acá el valor de la TRM de ese momento y proyectado subiendo al 4.5, teniendo presente que **la TRM en los últimos 10 años, entre el 2010 y el 2020, antes de pandemia**, si lo miráramos de forma lineal, está creciendo del 6.15, teniendo presente la gráfica que **ha subido en un 81 %**; pero si lo hacemos de forma lineal, lo que crece es el 6.15 %, y **de una forma de proyección muy conservadora, del 4.5 %**."*

| Referencia | Valor |
|---|---|
| Crecimiento histórico 2010–2020 (acumulado) | **81 %** |
| Crecimiento histórico linealizado | **6,15 %** anual |
| **Proyección que se usa** | **4,5 %** anual |

**Se proyecta por debajo del histórico, deliberadamente.**

**[V]** Gráfico incrustado: *"LA DEVALUACIÓN DEL PESO COLOMBIANO FRENTE AL DÓLAR — PROMEDIO DE LA TRM ENTRE ENERO Y MARZO EN LA ÚLTIMA DÉCADA"*, serie 2010 (1.947) → 2020 (3.535).

**[E]** *"De esta manera puedo mostrar al cliente cuánto sería la proyección de la TRM para el caso de las inversiones."*

### ⭐ Las tres TRM del archivo — RESUELTO

**[E]** *(audio)* *"**Es cierto, solamente se debería utilizar una sola TRM**, solo que para el caso que te compartí, **se me olvidó cambiarlas**."*

**Los tres valores del ejemplo (3.250 / 3.300 / 3.500) eran un descuido, no una regla.**

### ⚖️ REGLA DEFINITIVA

| Hoja | TRM a usar |
|---|---|
| `PROYECTADO TRM`, **fila del año en curso** | **TRM del día, exacta** |
| **Todo lo demás** — `Plan de Acción`!H15, presupuesto, `UNIVERSIDAD`, `ANALISIS` | **TRM del día + 200 COP** |

**[E]** *"Cuando tú lo ves en la hoja donde aparece la TRM, donde está relacionado el logo de Axia y el logo de United Financial, **ahí se coloca la TRM del momento, del día, en la columna donde está en el año 2026**."*

**[E]** *"para el plan de acción y el desarrollo del presupuesto, se debe colocar una TRM del día **más 200 pesos más adicional**."*

> **Control de calidad: en un archivo correcto solo deben existir DOS valores de TRM.** Tres = error.
> Ver [18 D-02 y D-03](18-discrepancias-resueltas.md).

---

## C. `UNIVERSIDAD` — costeo de educación superior

### Estructura

| Celda | Qué poner |
|---|---|
| **C4** | **valor de UN semestre** (promedio de la ciudad) — ejemplo: 20.000.000 Bogotá |
| **D4, E4, …** | **nombre de cada hijo**, una columna por hijo |
| **C5** | valor anual del año base = **C4 × 2** |
| **D5, E5** | **edad de cada hijo en el año base** |
| C6:C26+ | valor anual creciente **+9 % anual** **[V]** |
| D6:E26 | edad proyectada año a año |

**[E]** *"en la celda anterior a la C4 voy a colocar el valor del semestre promedio; para este caso utilicé 20 millones de pesos. Y luego utilicé para el año 2026 lo que gastaría al año: entonces en los dos semestres serían 40 millones. **Al año 2027 lo puse a crecer más un 9 %, y así sucesivamente.**"*

**[V]** Verificación: 40.000.000 × 1,09 = **43.600.000** ✓

### Los supuestos de edad [E]

| Supuesto | Valor |
|---|---|
| Edad de ingreso a la universidad en Colombia | **17 años** |
| Duración de la carrera | **5 años** |

**[E]** *"coloqué la edad actual del niño… **Usualmente acá empiezan en Colombia a estudiar a edad 17. Coloqué por 5 años en verdecito, que es lo que dura la carrera**, cuánto necesitaría en dinero."*

**Marca en verde los 5 años de carrera de cada hijo.** Ese bloque es el que se suma.

### Totales

| Celda | Contenido |
|---|---|
| **D27, E27** | suma de los 5 años de cada hijo |
| **D30** | **Total COP** — `=D27+E27` **[V]** |
| D31 | Total USD |
| **F30** | **Total USD mensual a ahorrar** — `=+I11+I23` **[V]** |
| H30 | Total COP mensual |

**[E]** *"Cuando miro el total en pesos por los dos hijos, es la sumatoria de la celda D más E, 27, y esto estaría en la celda D30 en pesos. Y en la celda D31 estaría en dólares, teniendo presente la TRM que en el momento esté aplicando."*

### Bloque de proyección por hijo

Uno por cada hijo, con columnas **PESOS** y **DÓLARES**:

| Etiqueta | Qué es |
|---|---|
| **Periodos totales** | años desde hoy hasta el ingreso |
| **Tasa** | **4,50 %** |
| **TRM** | la que aplique |
| **Aporte estudios «año-año»** | costo total de la carrera |
| **Valor a ahorrar mensual 4,5%** | **el número que importa** → alimenta F30 |
| **Aportes en plazo establecido** | capital que aporta la familia |
| **Rendimiento del capital** | lo que aporta el rendimiento |
| **Resultante ahorro más inversión** | = Aporte estudios |

**[E]** *"En la celda G10 aparece el aporte de los estudios que se debe dar, de qué año a qué año, y cuánto es lo que necesitaría el cliente, que es lo ahorrado para cubrir esos 5 años de estudio. Esto pasado a dólares, ¿cuánto sería el valor a ahorrar mensual? **Teniendo presente el 4.5** … el valor del plazo establecido, es decir, con estos 5.6 millones de pesos, al cabo de ese número de periodos cuánto genera de acumulación y cuánto sería por rendimiento de capital… y al final la sumatoria de estos dos, en pesos."*

**[V] Ejemplo:**

| | Hijo mayor (5 periodos) | Hijo menor (16 periodos) |
|---|---|---|
| Aporte estudios | 368.328.764 / 111.615 USD | 950.445.269 / 288.014 USD |
| **Ahorro mensual** | 5.610.618 / **1.700 USD** | 3.486.183 / **1.056 USD** |
| Aportes en plazo | 336.637.094 / 102.011 | 669.347.195 / 202.832 |
| Rendimiento | 31.691.671 / 9.604 | 281.098.075 / 85.181 |

**Total requerido: 2.757 USD/mes** (F30)

### ⚠️ La regla de la brecha — cómo se cierra

**[E]** *"Y si te das cuenta, acá son 2.757, pero en el plan de acción, **debido a que en su presupuesto por ahora, lo máximo con lo que podemos llegar a contar para que logre todos sus objetivos por ahora es de 1.500 dólares**. Esa es como la propuesta para el tema educación."*

> **Se calcula la necesidad real (2.757). Se compara con la capacidad real (1.500). Se documenta la brecha. Se propone lo alcanzable.**
>
> **No se ajusta el cálculo para que cuadre. No se promete lo que no se puede.**

Este es el estándar del método para cualquier objetivo cuyo costo supere la capacidad.

**[V]** El vínculo con el plan: `Plan de Acción`!G20 = `=1500*H15` — el 1.500 de la fórmula es **esta** decisión.

---

## D. `ANALISIS` — comparativa de productos de inversión

**Trasladado a [11 — Inversiones](11-inversiones.md).**

Esa referencia contiene: los parámetros de la hoja, los tres escenarios, la corrección del reparto de la prima (**1.000 / 250 / 250**, no 1.500/250/250), la fórmula de conversión `F24 = =F23*D10`, los cinco criterios de recomendación y el origen externo de las cotizaciones.

> Aquí solo se recuerda lo esencial: **la prima total debe ser idéntica en los tres escenarios** (1.500 USD en el ejemplo). Si no lo es, la comparación no significa nada.

## Checklist de las calculadoras

- [ ] **Liquidación:** fecha de ingreso desde `INFORMACION Seg soc`, fecha de retiro = fecha de la reunión, vacaciones asumidas como tomadas
- [ ] Liquidación enlazada a `Plan de Acción`!E86 por fórmula
- [ ] **TRM:** proyección al **4,5 %**, con los años 10/15/20/25 marcados
- [ ] Discrepancias entre las tres TRM del archivo: verificadas o escaladas
- [ ] **Universidad:** valor del semestre, crecimiento **+9 %**, ingreso a los **17**, carrera de **5 años**
- [ ] Bloque de proyección por hijo con tasa **4,5 %**
- [ ] **Brecha necesidad vs. capacidad calculada y documentada** — no disimulada
- [ ] **Comparativa:** prima total **idéntica** en los tres escenarios
- [ ] Conversión a COP con la **TRM del horizonte**
- [ ] Cifras de producto obtenidas de cotizaciones reales, no estimadas
- [ ] Ningún producto declarado "el mejor" — la decisión queda en el cliente
