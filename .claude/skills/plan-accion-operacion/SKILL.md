---
name: plan-accion-operacion
description: SOP operacional completo para construir un Plan de Acción Financiero Personalizado de Amanda Cruz González sobre la plantilla de Excel, a partir del levantamiento de información, el archivo Word de observaciones y los soportes del cliente. Contiene el mapa celda por celda de la plantilla, las 20 fórmulas verificadas, el análisis de ingresos, gastos, flujo, deudas, patrimonio, inversiones, tributario y pensional, el contexto humano, el modelo de decisión de Amanda, las reglas y excepciones, las discrepancias resueltas y el control de calidad. Actívala para diligenciar, calcular, optimizar, validar o auditar cualquier Plan de Acción. Requiere plan-accion-contexto cargada.
user-invocable: true
---

# Plan de Acción Financiero — SOP operacional

**Versión 2.0** · Consolidada con el audio de respuestas de Amanda (24 min, 12-ago-2026).

> **Requisito previo:** carga primero **`plan-accion-contexto`**. Sin ella no tienes la filosofía, el modelo de reuniones, la jerarquía de fuentes ni las reglas anti-invención, y esto se convierte en llenado mecánico de celdas.

**Marcas:** **[E]** explícito · **[V]** verificado · **[I]** inferencia · **[ND]** no determinado · **[AMB]** ambiguo · **[CORR]** corrige una fuente anterior; manda la evidencia indicada.

---

## Las dos reglas de oro

### 1. Primero se captura TODO. Después se analiza.

**[E]** *"ya revisamos la información de seguridad social, el presupuesto, los objetivos y el patrimonio. **Con base en esta información base… vamos a empezar a trabajar en el plan de acción**. Y para ese plan de acción vamos **primero que todo a revisar los objetivos**."*

No empieces a optimizar mientras todavía cargas datos.

### 2. El orden de prioridad del plan es fijo

**[E]** *"dentro de la escala, **lo primero que recomiendo son las coberturas, el tema de las anualidades, la provisión para el pago de las anualidades, y luego viene toda la parte de inversiones**."*

```
CAPACIDAD POSITIVA              CAPACIDAD NEGATIVA O NULA
1. Coberturas (7 riesgos)       1. Pago de deudas
2. Anualidades + provisión      2. Anualidades
3. Fondo de emergencia          3. Fondo de emergencia (mínimo)
4. Inversiones y objetivos      —— nada más ——
```

---

## Secuencia maestra — 18 fases

| # | Fase | Hoja | Referencia |
|---|---|---|---|
| **0** | Intake: verificar los 4 insumos, pedir Word y desprendibles | — | [01](referencias/01-intake-y-fuentes.md) |
| **1** | Leer el contexto humano y fichar al cliente | Word + levantamiento | [02](referencias/02-contexto-humano.md) |
| **2** | Datos personales y seguridad social | `INFORMACION Seg soc` | [04](referencias/04-captura-de-datos.md) |
| **3** | Presupuesto **columna C (REGULAR)** | `Presupuesto` | [04](referencias/04-captura-de-datos.md) · [05](referencias/05-ingresos-y-nomina.md) · [06](referencias/06-gastos-y-optimizacion.md) |
| **4** | Objetivos con horizonte | `Info Objetivos` | [04](referencias/04-captura-de-datos.md) |
| **5** | Activos y pasivos | `Info Patrimonio` | [09](referencias/09-patrimonio-y-capital-disponible.md) |
| — | **⛔ FIN DE LA CAPTURA — INICIO DEL ANÁLISIS ⛔** | | |
| **6** | Releer los objetivos — fijan la prioridad | `Info Objetivos` | [06](referencias/06-gastos-y-optimizacion.md) |
| **7** | Promediar conceptos variables de nómina | `Desprendibles de nom.` | [05](referencias/05-ingresos-y-nomina.md) |
| **8** | Construir **columna D (PROPUESTA A)** | `Presupuesto` | [06](referencias/06-gastos-y-optimizacion.md) |
| **9** | Flujo, anualidades y provisión | `Presupuesto` | [07](referencias/07-flujo-anualidades-y-provision.md) |
| **10** | **Analizar deuda y fijar el monto de inyección** | `Desmonte Deudas` | [08](referencias/08-deudas.md) |
| **11** | **Verificar los 7 riesgos** — prioridad 1 | `Plan de Acción` | [10](referencias/10-riesgos-y-coberturas.md) |
| **12** | Capacidad de ahorro mensual + estrategias | `Plan de Acción` | [13](referencias/13-plan-de-accion.md) |
| **13** | Capital disponible + estrategias | `Plan de Acción` | [09](referencias/09-patrimonio-y-capital-disponible.md) · [13](referencias/13-plan-de-accion.md) |
| **14** | Fondo de emergencia y meses de cobertura | `Plan de Acción` | [13](referencias/13-plan-de-accion.md) |
| **15** | Calculadoras de objetivos e inversiones | `UNIVERSIDAD` · `ANALISIS` · `PROYECTADO TRM` | [11](referencias/11-inversiones.md) · [14](referencias/14-calculadoras-auxiliares.md) |
| **16** | Recopilar datos tributarios y pensionales → **escalar** | — | [12](referencias/12-tributario-y-pensional.md) |
| **17** | Escenarios alternativos | `Presupuesto` | [15](referencias/15-escenarios-alternativos.md) |
| **18** | **Control de calidad** y entrega | todas | [19](referencias/19-control-de-calidad.md) |

**[AMB]** La fase 10 se **explica** al final del video pero Amanda declara que se **ejecutó antes** (*"previo a esto, hice un análisis también del tema de las deudas"*). **Ejecútala antes de la 12:** su resultado fija el monto de la primera estrategia mensual.

---

## Ruta rápida

| Necesitas | Ve a |
|---|---|
| Saber qué insumos pedir y cómo se relacionan | [01 — Intake y fuentes](referencias/01-intake-y-fuentes.md) |
| Entender al cliente como persona | [02 — Contexto humano](referencias/02-contexto-humano.md) |
| Qué hay en cada celda | [03 — Mapa de hojas](referencias/03-plantilla-mapa-de-hojas.md) |
| Cargar datos en la plantilla | [04 — Captura de datos](referencias/04-captura-de-datos.md) |
| Tratar ingresos, nómina y promedios | [05 — Ingresos y nómina](referencias/05-ingresos-y-nomina.md) |
| Clasificar gastos y construir la propuesta | [06 — Gastos y optimización](referencias/06-gastos-y-optimizacion.md) |
| Excedente, anualidades, provisión | [07 — Flujo, anualidades y provisión](referencias/07-flujo-anualidades-y-provision.md) |
| Estrategia de deudas y amortización | [08 — Deudas](referencias/08-deudas.md) |
| Activos, pasivos y capital utilizable | [09 — Patrimonio y capital](referencias/09-patrimonio-y-capital-disponible.md) |
| Revisar coberturas | [10 — Riesgos y coberturas](referencias/10-riesgos-y-coberturas.md) |
| Comparar productos de inversión | [11 — Inversiones](referencias/11-inversiones.md) |
| Impuestos y pensión | [12 — Tributario y pensional](referencias/12-tributario-y-pensional.md) |
| Armar las estrategias del plan | [13 — Plan de Acción](referencias/13-plan-de-accion.md) |
| Liquidación, universidad, TRM | [14 — Calculadoras auxiliares](referencias/14-calculadoras-auxiliares.md) |
| Modelar "¿y si…?" | [15 — Escenarios](referencias/15-escenarios-alternativos.md) |
| Entender **por qué** Amanda decide lo que decide | [16 — Modelo de decisión](referencias/16-modelo-de-decision.md) |
| Una regla concreta | [17 — Reglas y excepciones](referencias/17-reglas-y-excepciones.md) |
| Una contradicción entre fuentes | [18 — Discrepancias resueltas](referencias/18-discrepancias-resueltas.md) |
| Validar antes de entregar | [19 — Control de calidad](referencias/19-control-de-calidad.md) |

---

## Las 20 fórmulas verificadas

Leídas en la barra de fórmulas de Excel. **Son la columna vertebral de la plantilla — no las reescribas.**

### `Presupuesto`
| Celda | Fórmula | Qué hace |
|---|---|---|
| G104 | `=G80+G86+G91+G98` | Total anualidades = Seguros + Fijas + Presupuestadas + Impuestos |
| C105 | `=SI(C104>0;(C104-C77)/12;"")` | **Provisión mensual** — ver trampa 1 |
| P8 *(aux.)* | `=+(D80+D86+D92+D94+D98)/12` | Gastos anuales básicos a mensual (**excluye Viajes**) |
| fila 106 **[I]** | `= fila 77 − fila 104` | Diferencia anual sin dividir |
| fila 107 **[I]** | `= fila 69 − fila 105` | Excedente mensual neto de provisión |

### `Plan de Acción`
| Celda | Fórmula | Qué hace |
|---|---|---|
| H19 | `=G11-G19` | Saldo tras la 1.ª estrategia mensual |
| G20 | `=1500*H15` | Aporte de inversión: USD × TRM |
| G21 | `=H20` | La última estrategia **absorbe el remanente** |
| J21 | `=G21*12` | Fondo de emergencia acumulado en un año |
| F37 | `=+'Info Patrimonio'!B20` | Trae el nombre del activo |
| G41 | `=+Presupuesto!D73` | Trae el bono anual |
| D57 | `=+F39` | Trae la fuente desde el bloque de capital |
| E86 | `=+'Calculadora liquidacion «Cliente»'!B29` | Trae la liquidación |
| E89 **[I]** | `= E87 / E88` | **Meses de cobertura del fondo** |

### `Desprendibles de nom.`
| Celda | Fórmula |
|---|---|
| R7 | `=+SUMA(C7:H7)` — suma del periodo por concepto |

### `Desmonte Deudas`
| Celda | Fórmula | Qué hace |
|---|---|---|
| B21 | `=SI('Info Patrimonio'!D68="";"";'Info Patrimonio'!D68)` | **Se alimenta solo desde `Info Patrimonio`** |
| E1324 | `=SUMA(G1330:G1592)` | Total de intereses |
| C1326 | `=SI.ERROR(TASA.NOMINAL(C1325;12)/12;"CAMBIAR TASA")` | EA → tasa periódica mensual |
| C1623 | `=D22` | Saldo del 2.º crédito desde el resumen |
| F1341 | `=SI.ERROR(SI(C1341="";"";E1341-G1341)+I1341;"")+4900000+2800000+1000000` | Abono con inyección |

### `UNIVERSIDAD` / `ANALISIS`
| Celda | Fórmula | Qué hace |
|---|---|---|
| D30 | `=D27+E27` | Costo total de educación de todos los hijos |
| F30 | `=+I11+I23` | Ahorro mensual total requerido en USD |
| F24 | `=F23*D10` | USD → COP con la **TRM del horizonte**, no la de hoy |

---

## ⚠️ Las cinco trampas del método

### 1. El signo de la PROVISIÓN MENSUAL está invertido respecto al audio del video

**[CORR — manda la pantalla]** La fórmula real es **`(C104 − C77)/12`** — **anualidades menos ingresos anuales**.

| Resultado | Significado | Acción |
|---|---|---|
| **Negativo** | los ingresos anuales cubren los gastos anuales **y sobra** | **no hay que provisionar** |
| **Positivo** | **falta dinero** | ese es el importe **mensual a provisionar** |

Amanda misma reconcilia el signo: *"Aparece negativo, pero en realidad es algo que estaría quedando de forma mensualizada."*
**[V]** (49.517.989 − 47.846.500)/12 = **139.291** ✓

### 2. Ahorro AFC ≠ Servicio a la deuda AFC

**[E]** *"Acá hay que tener mucho cuidado."*
- **Cuota mensual** del hipotecario → rubro **Servicio a la deuda**
- **Todo excedente** sobre esa cuota → rubro **Ahorro** (Ahorro Cuenta AFC)

Confundirlos duplica el gasto y **atrapa** un dinero que debería poder reasignarse.

### 3. La tarjeta de crédito casi nunca es un gasto

**[E]** Si con ella se pagan gastos **ya registrados**, **no** se anota en Servicio a la deuda. Solo si financia un consumo puntual no desglosado o arrastra saldo de años anteriores.
*"Usualmente, en la gran mayoría de mis clientes, este ítem no se coloca."*

### 4. La deuda se analiza ANTES de escribir el plan

**[E]** *"esta es la razón por la cual se tuvo en cuenta en el plan de acción que **sí o sí se debe dejar presupuestado un pago de inyección a capital de 4.900.000**."*

### 5. Una sola TRM en todo el archivo

**[E]** *"**solamente se debería utilizar una sola TRM**; se me olvidó cambiarlas."*

| Hoja | TRM |
|---|---|
| `PROYECTADO TRM`, fila del año en curso | **TRM del día, exacta** |
| **Todo lo demás** (plan, presupuesto, universidad) | **TRM del día + 200 COP** |

**Tres valores distintos = error.** El archivo del video los tenía por descuido de Amanda.

---

## Los dos cuadres que cierran el plan

### Cuadre 1 — Ambas bolsas llegan a cero
```
Destino Capacidad de Ahorro:  H(última estrategia) = 0
Destino Capital Disponible:   H(total, fila 76)    = 0
```
La última estrategia de cada bolsa **absorbe el remanente**. Si sobra saldo, hay dinero sin asignar.

### Cuadre 2 — El fondo de emergencia iguala la suma de saldos
```
H49  (suma de saldos remanentes por activo)  =  G60  (fondo de emergencia)
```
**[V]** 696.474 + 3.777.120 + 2.974.082 + 0 + 339.978.719 + 1.228.511 = **348.654.906** ✓

---

## La regla de las anualidades — decide la arquitectura

**[E]** *"lo que debemos revisar es **primero, sí o sí, separar el valor de las anualidades**."*

Compara `Presupuesto` fila 77 (ingresos anuales) vs. fila 104 (gastos anuales):

| Condición | Dónde se resuelve | Cómo |
|---|---|---|
| **Ingresos anuales > Gastos anuales** | **Capital Disponible** | estrategia 1 (fila 56): fuente = bono anual, objetivo = Anualidades, monto = `D104` |
| **Ingresos anuales < Gastos anuales** | **Capacidad de Ahorro Mensual** | la `PROVISIÓN MENSUAL` (fila 105, positiva) se convierte en línea de estrategia |

---

## El fondo de emergencia — meta según perfil profesional

**[E]** *"Se establece **dependiendo del perfil profesional**."*

| Perfil | Meses de gastos básicos |
|---|---|
| **Sector salud** | **1 – 3** (máximo 3) |
| **Resto de sectores** | **mínimo 6** |
| **Default si no se sabe** | **6** |

**[E]** *"no es necesario que en el primer mes ya tenga listo lo de los seis meses; **se va construyendo en el tiempo**."*
Por eso existe `J21 = G21*12`: muestra el avance anual hacia la meta.

**Validación:** si `E89` (meses de cobertura) < meta → **decirlo explícitamente** y calcular en cuánto tiempo se alcanza al ritmo del plan.

---

## Marcadores obligatorios

| Situación | Marcador |
|---|---|
| Dato cuantitativo que el cliente no dio | **`Analizar Estrategia`** (literal) — y, si hay base en el Word, una estimación en amarillo con su criterio |
| Valor modificado por ti / recomendación | **amarillo** + comentario |
| Inicio de una intervención en una simulación | **verde** |
| Discrepancia entre fuentes | amarillo + comentario + escalar |
| Supuesto asumido | comentario + línea en el informe |

---

## Qué NO tocar

- No borres ni sobrescribas fórmulas
- No elimines filas (hay agrupadas ocultas: 42→49, 60→76, 29→1321)
- No renombres hojas ni muevas bloques
- Para añadir conceptos, usa **las filas vacías que cada rubro reserva**
- **No menciones AXIA ni UNITED FINANCIAL CONSULTANTS.** — son el bróker y la agencia; no van en el plan

## Las 8 hojas fuera de alcance

`INICIO` · `Patrimonio` · `Incapacidad` · `Proyeccion Retiro` · `DISTRIBUCION ACTIVOS` · `Resumen Deudas` · `Flujo de Efectivo` · `Grafico Presupuesto`

**[E]** Son *"una herramienta que yo utilizo **previo al plan de acción**, para mostrarle a mi cliente cómo se encuentra en las cinco áreas de las finanzas… un **diagnóstico financiero**."*
**[E]** *"con estas cuatro hojas de insumo para hacer el plan de acción **está más que suficiente**."*

> **No las diligencies.** Si se requieren, escala.

*(Ojo: `Patrimonio` ≠ `Info Patrimonio`, y `Resumen Deudas` ≠ el bloque "RESUMEN DEUDAS" que vive dentro de `Desmonte Deudas`.)*
