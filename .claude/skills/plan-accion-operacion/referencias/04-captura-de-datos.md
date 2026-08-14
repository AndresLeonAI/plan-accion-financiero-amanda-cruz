# 04 — Captura de datos (Fases 2 a 5)

**Objetivo de esta etapa:** dejar las cuatro hojas base completamente diligenciadas con lo que el cliente declaró, **sin analizar, sin optimizar y sin proponer nada todavía**.

**[E]** El video separa explícitamente esta fase: *"ya revisamos entonces la información de seguridad social, el presupuesto, los objetivos y el patrimonio. **Con base en esta información base… vamos a empezar a trabajar en el plan de acción**."*

---

## Antes de empezar

El **intake** (verificar insumos, pedir el archivo Word y los desprendibles, leer el contexto humano) está en:
- [01 — Intake y fuentes](01-intake-y-fuentes.md)
- [02 — Contexto humano](02-contexto-humano.md)

**No empieces a cargar datos sin haber leído el archivo Word.** Sin él, los objetivos y las estrategias quedan despersonalizados.

El tratamiento detallado de los **ingresos** (bruto/neto, periodicidad, promedios de nómina) está en [05 — Ingresos y nómina](05-ingresos-y-nomina.md).

---

## FASE 2 — `INFORMACION Seg soc`

**[E]** *"lo número uno es tener diligenciado cada una de estas casillas que aparecen acá."*

### 2.1 Decide la modalidad

**[E]** *"Hay dos posibilidades de trabajar: una asesoría financiera para una sola persona o una asesoría financiera para una pareja. Dependiendo del caso se debe manejar la situación financiera."*

| Caso | Qué diligencias |
|---|---|
| **Individual** | Solo el bloque titular (B4:C26 + E8:F15) |
| **Pareja** | Titular **y** bloque CONYUGE (B30:C50) + segundo bloque de seguridad social |

**[E]** Aunque uno de los dos no genere ingresos, **igual se registran sus datos**: *"la otra persona se dedica al hogar, por ende no genera un ingreso, **pero de igual forma se anotan algunos datos de la pareja**."*

### 2.2 Diligencia el bloque general (valores en columna C)

Recorre B4 a C26. Campos que **alimentan otras hojas** — no los dejes vacíos:

| Campo | Celda | Alimenta |
|---|---|---|
| **Fecha de Ingreso Compañía** | **C19** | `Calculadora liquidacion`!B8 |
| Cargo, Empresa, Tipo de contratación | C17, C18, C20 | contexto de estabilidad laboral |
| **Declarante de Renta** | C24 | planeación tributaria |
| Estado Civil | C25 | determina si aplica el bloque cónyuge |
| Fecha de Nacimiento / Edad | C9 / C11 | `ANALISIS` (edad para cotizaciones) |

### 2.3 Diligencia seguridad social (valores en columna F)

| Celda | Campo |
|---|---|
| F8 | EPS |
| F9 | PREPAGADA *(si tiene)* |
| F10 | ARL *(si tiene)* |
| F11 | FONDO DE CESANTIAS |
| **F12** | SALDO FONDO DE CESANTIAS |
| F13 | AFP (fondo de pensiones) |
| **F14** | SALDO AFP |
| F15 | Cotizó al ISS? |
| **H14** | **semanas cotizadas** |

**[E]** Sobre F13: *"acá se debe colocar la opción que haya en estas casillas **o se coloca una distinta en caso de que sea algo distinto**"* — las listas desplegables no son limitantes.

**[E]** Sobre las semanas: *"se debe colocarle al lado, en lo posible en la H14, colocar el número de semanas que indique el cliente."*
**[AMB]** En el archivo del ejemplo H14 está vacía y las semanas figuran en el COMENTARIO de `Info Patrimonio` (`731 semanas`, `122 semanas`). **Registra en ambos sitios** hasta validar con Amanda.

### 2.4 Repite para el cónyuge

Bloque B30:C50 y el segundo bloque de seguridad social desde E18.
**[E]** *"Lo mismo pasaría para el tema de seguridad social, EPS, prepagada y demás."*

**[AMB]** El segundo bloque de seguridad social está incompleto en la plantilla (duplica etiquetas y le faltan EPS/PREPAGADA/ARL/FONDO DE CESANTIAS). **No lo rediseñes — repórtalo** y usa E38 para lo que no tenga casilla.

### 2.5 Si falta una casilla, créala en E38

**[E]** *"**Si la casilla no está en el archivo debe ser creada** en la casilla E38, donde se anotará o registrará si es la IPS, la medicina prepagada, el EDL, fondo de cesantías, el saldo o fondo de cesantías que hay, en dónde está el fondo de pensiones y el saldo de pensiones que tenga en ese momento."*

---

## FASE 3 — `Presupuesto`, columna C (REGULAR)

> **En esta fase solo se escribe en la columna C.** Las columnas D en adelante son la fase 8.

### 3.1 Principio rector

**[E]** *"En estas casillas de ingresos lo que vemos y se debe anotar son **todos los ítems que entran al bolsillo del hogar**, tanto ingresos de él como ingresos de ella."*

### 3.2 Ingresos mensuales (filas 6–10, total en 11)

Registra cada fuente que llega **mensualmente**:
- Salario (integral / ordinario / prestación de servicios)
- Bonos, acciones, comisiones
- Honorarios, consultorías
- Rentas de apartamentos o locales
- Dividendos **si se reciben mensuales**

**[E]** *"Si hay ingresos adicionales por consultorías o por rentas de apartamentos o locales o por dividendos, **si se reciben mensuales**, se deben relacionar acá."*

**[E] Regla del audio — marcar neto o bruto:** *"si tiene un ingreso adicional por rentas de apartamento, yo coloco el valor de la renta y **usualmente especifico si es un ingreso neto o si es un ingreso bruto**."*
→ Rotula en la columna B: `Apto. Fontibón (neto)` · `Consultoría (bruto)`. Si no se sabe: `(bruto — sin verificar)` + comentario.
→ Si es **bruto**, sus costos asociados (administración, seguro, servicios si está desocupado) van al rubro ***Otros***.

Detalle completo en [05 — Ingresos y nómina](05-ingresos-y-nomina.md).

**En pareja [E]:** *"si fueran dos personas se relacionan entonces el ingreso de ella primero"* → **primero los de ella, después los de él.**

> ⚠️ Los conceptos **variables** (bonos, acciones) se registran aquí con el valor que dé el cliente. **El promedio se calcula en la fase 7 y va a la columna D**, no a la C.

### 3.3 Egresos mensuales

Recorre los rubros **en el orden de la hoja**. En cada uno: el concepto en **B**, el valor mensual en **C**. Los subtotales azules se calculan solos.

**[E]** *"las casillas azules de cada uno de estos gastos puntuales va a ir sumando los valores totales por cada ítem mencionado."*

#### Ahorro (14–16)
Solo el ahorro **efectivo y recurrente**. Tipos que ofrece el desplegable **[E]**: offshore, cartera colectiva, cooperativas, **cuenta FC**, cuenta de ahorros, cuenta corriente, fiducias, fondo de empleados, fondos mutuos, pensión voluntaria, provisiones anualidades, otros.

> ⚠️ **Trampa crítica.** Ver [17 §2.2](17-reglas-y-excepciones.md). Todo excedente pagado **por encima** de la cuota del crédito hipotecario AFC va **aquí**, no en Servicio a la deuda.

#### Transporte (17–19)
**[E]** Gasolina, peajes, plataformas (Didi, Uber, taxis), parqueaderos.

#### Gastos personales (20–24)
**[E]** Almuerzos diarios, celular, cuidado personal, desayunos diarios, gimnasio, mesada para hijos, ropa, maquillaje, snacks.

#### Hogar (25–36)
**[E]** Mercado, servicios públicos, plataformas (Netflix, Spotify, HBO, DirecTV), mascotas, ayuda de aseo, almuerzos, administración.

Dos reglas especiales:
- **Mascotas [E]:** *"debe ir relacionado el monto que el cliente pague de forma mensual por alimentación de su mascota, por veterinario mensual si se paga, por medicamentos, y en general reunir esos diferentes ítems y **sumarlo como una suma única para el ítem de mascotas de forma mensual**."*
- **Ayuda de aseo [E]:** hay que preguntar si el valor **ya incluye** primas, intereses sobre cesantías y cesantías. *"Si ya está incluido, pues se deja el valor mensualizado. Si no está incluido, se deja solamente el del mes como ayuda a aseo y **en las anualidades se coloca prestaciones servicio aseo**."*
- **Almuerzos [E]:** *"son los almuerzos que vamos a tener en cuenta de lunes a viernes."*

#### Entretenimiento (37–39)
**[E]** Cine, club, eventos sociales, golf, restaurantes, reuniones, rumbas, salidas, suscripciones, tenis.

**[E] Recomendación de agregación:** *"si no está acá algo en este ítem, **yo preferiría mejor colocarle salidas en general**, que esto es lo que reúne los gastos de la persona o de la pareja **el sábado, el domingo y días festivos**."*

#### Protecciones personales (40–42)
**[E]** *"todo lo que haga referencia a coberturas puntualmente"*: seguro de contenido, invalidez, responsabilidad civil, salud, vehículo, vida, exequial, vivienda.
Concepto en B, **monto mensual** en C.

> Solo los que se pagan **mensualmente**. Los anualizados van a Seguros anuales (fila 80).

#### Otros Descuentos de Nómina (43–49)
**[E]** *"es como la relación de lo que aparece en el desprendible de nómina de la persona"*: salud, pensión, retención en la fuente, fondo de solidaridad pensional, adelantos de acciones, y cualquier otro que aparezca.

**[E] Regla de identificación en pareja:** *"si es una pareja se coloca en la parte superior… la parte de la mujer y luego la del hombre, **dejando claro entre paréntesis el nombre del cliente**. Por ejemplo, si ella se llama Sofía, le colocamos `salud (Sofía)`. Si ya pasamos a los ítems de él y él se llama Andrés, entonces colocamos `salud (Andrés)`."*

#### Educación (50–55)
**[E]** Pensión de colegio, jardín, maestría, capacitaciones, cursos, idiomas, libros, matrículas.

**[E] Regla del colegio (11 meses):** ver [17 §1.2](17-reglas-y-excepciones.md).

#### Financieros (56–58)
**[E]** Cuotas de manejo de tarjeta de crédito, por banco.

#### Servicio a la deuda (59–63)
**[E]** Créditos: hipotecario, vehículo, cooperativa, libranza.

> ⚠️ **Trampa crítica de la tarjeta de crédito.** Ver [17 §2.1](17-reglas-y-excepciones.md).

#### Otros (64–65)
**[E]** *"Si hay rentas de apartamentos, entonces **exclusivamente acá** se coloca administración de esa renta del local o del apartamento."*
También: ayudas a familiares, donaciones mensuales, servicios de otros inmuebles (finca, apartamento en renta).

**[E] Regla de identificación:** *"especificar si es servicio público de qué lugar, si es diferente a donde vive. Si es finca, pues colocar finca. Si tiene varios apartamentos, colocar `del apartamento 1` o `apartamento 2`… haciendo referencia a dónde se encuentra ubicado, `/Mazurén`, `/Suba`, **para tener claridad de cuánto es que se paga por servicios, cuánto se paga por administración de esos diferentes ítems**."*

### 3.4 Ingresos anuales (72–77)

**[E]** *"Llámese bono anual, llámese bono por una prima, extraprima —usualmente hay diferentes tipos de extraprima—… dividendos, primas, rentas, utilidades. Hay que relacionarla ítem por ítem."*

**[E] Regla de la retención:** *"idealmente colocar acá el dato que da el cliente. Sería importante entender **cuánto es lo que le cobran por retención en la fuente y descontarlo de una vez**, pero si no se tiene, al menos relacionar el monto que aparece en su desprendible de nómina."*
→ **Preferencia: valor neto de retención.** Si solo tienes el bruto, regístralo **y anota en COMENTARIO que está sin descontar.**

### 3.5 Egresos anuales (79–104)

| Rubro | Fila | Qué va |
|---|---|---|
| **Seguros** | 80 | **[E]** SOAT, seguro de riesgo/todo riesgo, seguro de arrendamiento, salud o carro **si se pagan anualizados**. *"Si son pagos con temas de coberturas, los seguros se deben relacionar en este ítem."* |
| **Anualidades Fijas** | 86 | **[E]** Mantenimiento, revisión técnico-mecánica, matrículas + uniformes, donaciones anuales. Obligaciones anuales de monto conocido. |
| **Anualidades Presupuestadas** | 91 | **[E]** Ropa, viajes, regalos de cumpleaños y navidad. *"en promedio cuánto se gasta la familia… en viajes cuánto se han venido gastando, se gastaron el año pasado."* Gasto anual estimado, no obligación fija. |
| **Impuestos** | 98 | **[E]** Impuesto predial, impuesto del carro, declaración de renta, impuestos de otros inmuebles. |

**[E] Regla de clasificación anual vs. mensual:** *"acá por ejemplo hay una donación proyecto unión, pero esta donación no es mensual, **es una donación anual, por esa razón va en anualidades fijas, no en mensuales**."*

**[E] Regla de discriminación de impuestos:** *"hay que tratar de clasificar si este cliente tiene diferentes activos —fincas, apartamentos o locales— **discriminar el impuesto predial correspondiente** a si es apartamento, si es finca o si son locales, y describir el local, para revisar puntualmente cuánto paga anualmente por cada ítem."*

### 3.6 Comprueba los totales

| Celda | Debe cumplir |
|---|---|
| C67 | = suma de los 11 subtotales azules |
| C69 | = C68 − C67 |
| C104 | = C80 + C86 + C91 + C98 |
| **C105** | `=SI(C104>0;(C104-C77)/12;"")` — **lee el signo según [17 §5](17-reglas-y-excepciones.md)** |

---

## FASE 4 — `Info Objetivos`

**[E]** *"Una vez ya tenemos esto diligenciado, también se le pide la información importante al cliente sobre los objetivos que se quieren cumplir."*

Una fila por objetivo, desde la 6:

| Col | Qué escribir |
|---|---|
| **B** PRIORIDAD | número de orden — **el cliente prioriza, no tú** |
| **C** OBJETIVO | nombre corto del objetivo |
| **D** DESCRIPCIÓN | **[E]** *"la descripción por cada ítem, tratando de ser lo más puntuales posibles"* |
| **E** PLAZO (Años) | **[E]** *"el plazo en el que se quiere cumplir ese objetivo"* |
| **F** VR. OBJETIVO | valor meta — o **`Analizar Estrategia`** |
| **G** VALOR MENSUAL A AHORRAR | aporte mensual — o **`Analizar Estrategia`** |
| **H** COMENTARIOS | **el contexto humano de la reunión de sensibilización** |

### Clasificación por horizonte — regla del audio

**[E]** *"reviso cuál es el objetivo **a corto, a mediano, a largo plazo**, en qué tiempo lo quieren cumplir y cuánto necesita de valor para cumplirlo."*

Todo objetivo se clasifica por horizonte **además** de registrar su plazo en años. El horizonte determina después qué vehículo de inversión es apropiado.

### ⭐ Regla del marcador `Analizar Estrategia` — en dos tiempos

**[E]** *(video)* *"colocar el valor objetivo, **si lo menciona el cliente y si no, colocarlo como analizar estrategia**. Y en la celda G6 colocar el valor mensual a ahorrar dependiendo del valor que haya mencionado el cliente. **Si no lo dio, colocar analizar estrategia**."*

**[E]** *(audio — amplía la regla)* *"Si el cliente no sabe, yo coloco analizar estrategia **y reviso cuánto podrías llegar a necesitar a futuro teniendo en cuenta las observaciones que da el cliente**."*

> **No es un callejón sin salida:**
> 1. Se escribe **`Analizar Estrategia`** en la celda — declara que **el cliente no dio la cifra**
> 2. Si el archivo Word o el levantamiento dan base suficiente, se **propone una estimación** en la columna **H (COMENTARIOS)**, en **amarillo**, con su criterio documentado
>
> Lo que **nunca** se hace es escribir una cifra en F o G como si el cliente la hubiera dado.

> **Aquí es donde cruzas las dos transcripciones.** El objetivo sale de la reunión de datos; el **porqué**, la urgencia y las restricciones salen de la de sensibilización y van a la columna H. Un objetivo sin su porqué está a medio capturar.

**[E]** También existe un archivo Word paralelo: *"estos ítems o estos datos son escritos en un archivo de Word que se van a dejar consignados acá, **o que se pueden colocar como observaciones en la información de objetivos**"*. **[ND]** El formato de ese Word no se muestra. Ante la duda, consigna todo en la columna H.

---

## FASE 5 — `Info Patrimonio`

**[E]** Explícale al cliente qué es: *"el patrimonio es **la radiografía como tal de lo que tiene el cliente**… activos menos pasivos, que son las deudas, igual al patrimonio."*

### 5.1 Activos líquidos (desde fila 7)
*"todos aquellos que podemos hacer fácil uso… para gastar"* — cuentas de ahorro de cada uno, efectivo en casa, caja fuerte, dólares.
Columnas: **ACTIVO · ENTIDAD · VALOR · COMENTARIO**

### 5.2 Activos productivos (desde fila 20)
*"todos aquellos que nos generan rentabilidad, en lo posible superior a la inflación, pero a veces no es suficiente. **Entonces, de igual forma, antes de que nos genere algo de rentabilidad, lo vamos a colocar acá**."*

→ **No exijas que sea rentable para clasificarlo como productivo.** Basta con que su naturaleza sea generar rendimiento.

Incluye: acciones, inmuebles de inversión, bodega, bonos, carteras colectivas, casas en renta, CDT, cuentas de inversión, cuentas por cobrar a terceros, empresa, fiduciaria, **AFC**, **pensión obligatoria**.

### 5.3 Activos improductivos (desde fila 33)
*"todos aquellos que nos generan gastos"* — la vivienda propia, los carros, inmuebles sin renta, fincas, caballos, joyas, lanchas, local, maquinaria, motos, muebles, terrenos.

### 5.4 Pasivos a corto plazo (desde fila 47)
**[E]** *"Si es a corto plazo, hablamos de **1 a 5 años**."*
Columnas: **PASIVO · SALDO DE CAPITAL · ENTIDAD · TASA · #CUOTAS PENDIENTES · CUENTA MENSUAL**

Tipos: consumo, prelibranza, inversión, hipotecario, rotativo, vehículo, terceros, cooperativo, **tarjeta de crédito si es < 5 años**.

### 5.5 Pasivos a largo plazo (desde fila 68)
> 5 años: hipotecario, vehículo, libranza, deuda de terceros, préstamo de fondo de empleados.

**[E]** *"colocar los saldos por cada ítem, la entidad, la tasa, la cuota pendiente y la cuota mensual"*, *"así fila por fila, rubro por rubro, **lo más desglosado posible**."*

> ⚠️ **Estas filas alimentan `Desmonte Deudas` por fórmula.** Si quedan incompletas (falta tasa o cuotas pendientes), **no se puede hacer el análisis de deuda** y toda la fase 8 se cae. Es dato bloqueante.

### 5.6 Usa la columna COMENTARIO

**[E]** *"si se tiene que hacer algún comentario u observaciones… se debe colocar las observaciones por cada ítem de acuerdo a la fila donde se encuentre."*

Ejemplos reales del video: `GSU no vesting;` (acciones no consolidadas) · `731 semanas` (pensional) · `40 mill para dejarlo ok con acabados` (inversión pendiente).

Estos matices son los que después determinan **si un activo entra o no al capital disponible**.

---

## Checklist de fin de captura

- [ ] `INFORMACION Seg soc` completa (titular + cónyuge si aplica + seguridad social + semanas)
- [ ] `Presupuesto` columna C completa: ingresos y egresos mensuales, ingresos y egresos anuales
- [ ] Todos los gastos **mensualizados** (ver [17 §1](17-reglas-y-excepciones.md))
- [ ] Sin duplicaciones (tarjeta de crédito, AFC, administración de rentas)
- [ ] Descuentos de nómina identificados por persona si es pareja
- [ ] `Info Objetivos` con prioridad, plazo y `Analizar Estrategia` donde falte cifra
- [ ] Contexto humano volcado en COMENTARIOS
- [ ] `Info Patrimonio` con los cinco bloques y **tasas y cuotas pendientes de cada deuda**
- [ ] Discrepancias detectadas y marcadas, ninguna resuelta a la fuerza
- [ ] **No has escrito nada en la columna D ni en el `Plan de Acción`**