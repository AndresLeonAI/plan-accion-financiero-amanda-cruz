# 03 — Mapa de la plantilla, hoja por hoja y celda por celda

Todas las direcciones de celda de este documento están **[V] verificadas en pantalla** salvo indicación contraria.

---

## Índice de hojas (orden real de pestañas)

| # | Pestaña | Color | Uso en el método |
|---|---|---|---|
| 1 | `Desprendibles de nom. 2026` | — | **Sí** — promediar conceptos variables |
| 2 | `Calculadora liquidacion Andrés` | — | **Sí** — liquidación por despido |
| 3 | `ANALISIS` | — | **Sí** — comparativa de productos |
| 4 | `PROYECTADO TRM` | — | **Sí** — proyección de devaluación |
| 5 | `UNIVERSIDAD` | — | **Sí** — costeo de educación superior |
| 6 | `INICIO` | rojo | **Diagnóstico previo — fuera de alcance** |
| 7 | `INFORMACION Seg soc` | amarillo | **Sí — hoja base** |
| 8 | `Presupuesto` | — | **Sí — hoja base (núcleo)** |
| 9 | `Plan de Acción` | — | **Sí — entregable central** |
| 10 | `Patrimonio` | — | **Diagnóstico previo — fuera de alcance** |
| 11 | `Incapacidad` | — | **Diagnóstico previo — fuera de alcance** |
| 12 | `Proyeccion Retiro` | — | **Diagnóstico previo — fuera de alcance** |
| 13 | `Info Objetivos` | cian | **Sí — hoja base** |
| 14 | `Info Patrimonio` | morado | **Sí — hoja base** |
| 15 | `DISTRIBUCION ACTIVOS` | — | **Diagnóstico previo — fuera de alcance** |
| 16 | `Resumen Deudas` | — | **Diagnóstico previo — fuera de alcance** |
| 17 | `Desmonte Deudas` | — | **Sí** — amortización y estrategia |
| 18 | `Flujo de Efectivo` | — | **Diagnóstico previo — fuera de alcance** |
| 19 | `Grafico Presupuesto` | — | **Diagnóstico previo — fuera de alcance** |

### Las 8 hojas fuera de alcance — resuelto

**[E]** *"esas hojas de cálculo son **una herramienta que yo utilizo previo al plan de acción**, para mostrarle a mi cliente **cómo se encuentra en las cinco áreas de las finanzas**. Y esto sirve para hacer una planeación financiera, o sea, **un diagnóstico financiero**."*

**[E]** *"con estas cuatro hojas de insumo para hacer el plan de acción **está más que suficiente**."*

**[V]** *"las cinco áreas de las finanzas"* = los cinco niveles de la pirámide (Objetivos · Protecciones · Presupuesto · Impuestos · Inversiones).

> **No las diligencies.** Son una fase anterior del servicio. Si se requieren, escala.

**[AMB]** La hoja 2 lleva el nombre del cliente del ejemplo. **[ND]** Amanda no aclaró si se renombra o duplica por cliente. Impacto bajo: la fórmula `Plan de Acción`!E86 debe apuntar a la hoja **como se llame en el archivo real**.

---

## 1. `INFORMACION Seg soc`

### Bloque INFORMACIÓN GENERAL (titular) — fila 2 título

Etiquetas en **B**, valores en **C**:

| Celda | Campo |
|---|---|
| B4 / C4 | Fecha (dd/mm/aaaa) |
| B5 / C5 | Planeación Financiera |
| B6 / C6 | **Nombre** |
| B7 / C7 | **Apellidos** |
| B8 / C8 | Cédula de Ciudadanía |
| B9 / C9 | Fecha de Nacimiento |
| B10 / C10 | Lugar de Nacimiento |
| B11 / C11 | Edad |
| B12 / C12 | Dirección Casa |
| B13 / C13 | Dirección Oficina |
| B14 / C14 | Celular |
| B15 / C15 | Teléfono Casa |
| B16 / C16 | Teléfono Oficina |
| B17 / C17 | Empresa |
| B18 / C18 | **Cargo** |
| B19 / **C19** | **Fecha de Ingreso Compañía** *(amarilla — alimenta la calculadora de liquidación)* |
| B20 / C20 | Tipo de contratación |
| B21 / C21 | Profesión |
| B22 / C22 | Universidad |
| B23 / C23 | Correo Electronico |
| B24 / C24 | **Declarante de Renta** (Sí/No) |
| B25 / C25 | Estado Civil |
| B26 / C26 | # Cuenta Principal |

### Bloque SEGURIDAD SOCIAL (titular)

Etiquetas en **E**, valores en **F**:

| Celda | Campo | Nota |
|---|---|---|
| E8 / F8 | EPS | lista desplegable |
| E9 / F9 | PREPAGADA | |
| E10 / F10 | ARL | |
| E11 / F11 | FONDO DE CESANTIAS | |
| E12 / **F12** | SALDO FONDO DE CESANTIAS | **amarilla** |
| E13 / F13 | AFP | |
| E14 / **F14** | SALDO AFP | **amarilla** |
| E15 / F15 | Cotizó al ISS? | |
| **H14** | **semanas cotizadas** | **OBLIGATORIA.** **[E]** *"esas semanas cotizadas **van en los dos**: tanto en la primera hoja de seguridad social como en la del patrimonio."* En el archivo del ejemplo estaba vacía por descuido. Alimenta la proyección de mesada pensional |

### Bloque CONYUGE — fila 29 título

Etiquetas **B30:B50**, valores en **C**. Réplica exacta del bloque titular:
Nombre Conyuge · Apellidos · Cédula de Ciudadanía · Fecha de Nacimiento · Lugar de Nacimiento · Edad · Dirección Casa · Dirección Oficina · Celular · Teléfono Casa · Teléfono Oficina · Empresa · Cargo · Fecha de Ingreso Compañía · Tipo de contratación · Profesión · Universidad · Correo Electronico · Declarante de Renta · Estado Civil · # Cuenta Principal

### Segundo bloque SEGURIDAD SOCIAL (cónyuge) — desde E18

Etiquetas observadas: Fecha Nacimiento · Nombre · Fecha de Nacimiento · Nombre · SALDO FONDO DE CESANTIAS · AFP · SALDO AFP · Cotizó al ISS?

**[AMB] Este bloque está mal construido en la plantilla:** duplica "Nombre" y "Fecha de Nacimiento", y le faltan EPS, PREPAGADA, ARL y FONDO DE CESANTIAS respecto al bloque titular. Es un defecto de la plantilla, no del método. **No lo "arregles" por tu cuenta — repórtalo.**

### Celdas de ampliación y listas auxiliares

| Celda | Contenido |
|---|---|
| **E38** | **Celda de ampliación.** **[E]** *"Si la casilla no está en el archivo debe ser creada en la casilla E38, donde se registrará si es la IPS, la medicina prepagada, el EDL, fondo de cesantías, el saldo, dónde está el fondo de pensiones y el saldo de pensiones"* |
| E28 / E29 / E30 | Seguro SOAT · Seguro todo riesgo · Seguro de… *(fuente de desplegables)* |
| E32 / E33 / E34 | Salario integral · Salario ordinario · Prestacion servicios *(fuente de desplegables)* |

---

## 2. `Presupuesto` — hoja núcleo

### Columnas

| Col | Encabezado literal |
|---|---|
| **B** | Concepto |
| **C** | **REGULAR** — la situación actual declarada por el cliente |
| **D** | **PROPUESTA (A) Organización Actual** |
| **E** | **PROPUESTA (B) sin consultoria** *(nombre del ejemplo)* |
| **F** | **PROPUESTA (C) sin consultoria y con Apto. Nvo.** |
| **G** | **PROPUESTA (D) … 18 meses** |
| **H** | libre |

Los encabezados se repiten en **filas 5, 13, 72 y 79**.
**[E]** El número de columnas de propuesta es **variable** — depende de los escenarios que pida el cliente.

### Bloque INGRESOS MENSUALES

| Fila | Contenido |
|---|---|
| 5 | encabezados |
| 6–10 | ítems de ingreso (Salario Integral, Bonos, Acciones, Consultoría, Renta de inmueble…) |
| **11** | **TOTAL INGRESOS** |

### Bloque EGRESOS MENSUALES

Las filas de **subtotal** tienen **fondo azul claro** y terminan en dos puntos. Los ítems de detalle van debajo.

| Fila subtotal | Rubro | Filas de detalle |
|---|---|---|
| **14** | **Ahorro:** | 15–16 |
| **17** | **Transporte:** | 18–19 |
| **20** | **Gastos personales:** | 21–24 |
| **25** | **Hogar:** | 26–36 |
| **37** | **Entretenimiento:** | 38–39 |
| **40** | **Protecciones personales:** | 41–42 |
| **43** | **Otros Descuentos de Nomina:** | 44–49 |
| **50** | **Educación:** | 51–55 |
| **56** | **Financieros:** | 57–58 |
| **59** | **Servicio a la deuda:** | 60–63 |
| **64** | **Otros:** | 65 |
| **66** | **Egreso no Identificado** | — |
| **67** | **TOTAL EGRESOS** | — |
| **68** | *(sin etiqueta)* — replica TOTAL INGRESOS | — |
| **69** | **INGRESOS - EGRESOS** *(amarilla)* | — |

**[V]** `fila 67` = suma de los **once subtotales azules**. **No incluye la fila 66.**
**[V]** `fila 69` = `fila 68 − fila 67`.
**[V][ND]** `fila 66` **espeja exactamente el valor de la fila 69** en las cuatro columnas. **[I]** Rotula el excedente como "gasto que el cliente no logró identificar" — es un indicador de diagnóstico. **El video nunca la menciona.** No la modifiques.

**Ítems observados en el ejemplo** (útiles como catálogo de referencia):

- **Ahorro:** 15 Ahorro Cuenta AFC
- **Transporte:** 18 Gasolina, peajes, plataformas, parqueaderos
- **Gastos personales:** 21 Celular · 22 Cuidado Personal · 23 Maquillaje
- **Hogar:** 26 Mercado · 27 Servicios Públicos · 28 Plantaformas Netflix, Spotify, HBO, Direc Tv · 29 Mascotas · 30 Ayuda Aseo · 31 Almuerzos · 32 Administración · 33 Icloud
- **Entretenimiento:** 38 Salidas
- **Otros Descuentos de Nomina:** 44 Salud · 45 Pensión · 46 Retención en la Fuente · 47 Fondo de Solidaridad Pensional · 48 Adelanto GSU · 49 Seguridad Social
- **Educación:** 51 Pensión Colegio · 52 Jardín · 53 Maestría
- **Financieros:** 57 Cuotas Manejo TC
- **Servicio a la deuda:** 60 AFC Cred. Hipotecario · 61 Crédito Vehículo
- **Otros:** 65 Admon. Apto. Nvo.

### Bloque INGRESOS ANUALES

| Fila | Contenido |
|---|---|
| 72 | encabezados |
| **73** | primer ítem anual (Bono anual) *(amarilla)* |
| 74–76 | ítems adicionales |
| **77** | **TOTAL INGRESOS** *(anuales)* |

### Bloque EGRESOS ANUALES

| Fila subtotal | Rubro | Filas de detalle |
|---|---|---|
| **80** | **Seguros:** | 81–85 |
| **86** | **Anualidades Fijas:** | 87–90 |
| **91** | **Anualidades Presupuestadas:** | 92–97 |
| **98** | **Impuestos:** | 99–103 |
| **104** | **TOTAL ANUALIDADES** | `=G80+G86+G91+G98` **[V]** |
| **105** | **PROVISIÓN MENSUAL** | `=SI(C104>0;(C104-C77)/12;"")` **[V]** |
| **106** | *(sin etiqueta, texto rojo, fondo amarillo)* | **[I]** `= fila 77 − fila 104` |
| **107** | *(sin etiqueta, texto rojo)* | **[I]** `= fila 69 − fila 105` |
| 109–112 | % de distribución de anualidades por rubro + gráficos de torta | |

**Ítems observados:**
- **Seguros:** 81 Soat · 82 Seguro Todo Riesgo · 83 Seguro de Arrendamiento
- **Anualidades Fijas:** 87 Donación · 88 Mantenimiento · 89 Revisión Técnico-Mecánica · 90 Matrícula + uniformes
- **Anualidades Presupuestadas:** 92 Ropa · **93 Viajes** · 94 Regalos de Cumpleaños y Navidad
- **Impuestos:** 99 Impuesto Predial · 100 Impuesto del carro · 101 Declaración de Renta · 102 Impuesto de otro inmueble

> **La fila 93 (Viajes) se excluye del cálculo de gastos básicos.** Ver [17](17-reglas-y-excepciones.md).

### Celdas auxiliares (a la derecha, fuera de la zona impresa)

| Celda | Contenido | Ejemplo |
|---|---|---|
| **P7** | Gastos básicos **mensuales** — suma manual selectiva | 18.781.821 |
| **Q7** | etiqueta `Gastos B. Mensuales` | |
| **P8** | Gastos **anuales** llevados a mensual — `=+(D80+D86+D92+D94+D98)/12` **[V]** | ≈ 2.718.166 |
| **P9** | `= P7 + P8` → alimenta `Plan de Acción`!E88 | **21.499.987** |

**[AMB]** Las direcciones P7/P8/P9/Q7 provienen de la narración; en pantalla las columnas auxiliares son visibles pero las letras exactas no siempre se leen. **Verifica en la plantilla real antes de escribir.**

---

## 3. `Info Objetivos`

| Col | Encabezado (fila 5) |
|---|---|
| **B** | **PRIORIDAD** *(número, fuente roja)* |
| **C** | **OBJETIVO** *(fondo verde, desplegable)* |
| **D** | **DESCRIPCIÓN** |
| **E** | **PLAZO (Años)** |
| **F** | **VR. OBJETIVO** |
| **G** | **VALOR MENSUAL A AHORRAR** |
| **H** | **COMENTARIOS** |

- Fila 4: título fusionado **VALOR OBJETIVOS**
- Filas 6–9+: un objetivo por fila
- Fila 10: etiqueta *"Valor mensual a ahorrar"*, total en **G10**

**Regla del marcador [E]:** si el cliente no dio `VR. OBJETIVO` o `VALOR MENSUAL A AHORRAR`, se escribe literalmente **`Analizar Estrategia`**. Nunca una cifra estimada.

---

## 4. `Info Patrimonio`

**[E]** Definición que se le explica al cliente: *"el patrimonio es la radiografía de lo que tiene el cliente: **activos menos pasivos (que son las deudas) igual al patrimonio**."*

| Bloque | Título | Encabezados | Datos desde |
|---|---|---|---|
| **ACTIVOS LÍQUIDOS** | B5 | fila 6 | fila 7 |
| **ACTIVOS PRODUCTIVOS** | B18 | fila 19 | **fila 20** |
| **ACTIVOS IMPRODUCTIVOS** | B31 | fila 32 | fila 33 |
| **PASIVOS CORTO PLAZO** *(banda roja)* | B45 | fila 46 | fila 47 |
| **PASIVOS LARGO PLAZO** *(banda roja)* | B66 | fila 67 | **fila 68** |

### Columnas de activos
| Col | Campo |
|---|---|
| **B** | ACTIVO |
| **C** | ENTIDAD |
| **D** | VALOR |
| **F** | COMENTARIO |

### Columnas de pasivos
| Col | Campo |
|---|---|
| **B** | PASIVO |
| **C** | SALDO DE CAPITAL |
| **D** | **ENTIDAD** ← alimenta `Desmonte Deudas`!B21 |
| **E** | TASA |
| **F** | #CUOTAS PENDIENTES |
| **G** | CUENTA MENSUAL |

### Definiciones operativas [E]

| Categoría | Definición literal | Ejemplos citados |
|---|---|---|
| **Líquidos** | *"todos aquellos que podemos hacer fácil uso… para gastar"* | cuenta de ahorros de él y de ella, efectivo en casa, caja fuerte, dólares |
| **Productivos** | *"todos aquellos que nos generan rentabilidad, **en lo posible superior a la inflación, pero a veces no es suficiente. Entonces, de igual forma, antes de que nos genere algo de rentabilidad, lo vamos a colocar acá**"* | acciones, inmuebles de inversión, bodega, bonos, carteras colectivas, casas en renta, CDT, cuenta de inversión, cuentas por cobrar, empresa, fiduciaria, AFC, **pensión obligatoria** |
| **Improductivos** | *"todos aquellos que nos generan gastos"* | apartamento donde viven, carros, inmuebles sin renta, fincas, caballos, joyas, lanchas, local, maquinaria, motos, muebles, terrenos |
| **Pasivo corto plazo** | *"de 1 a 5 años"* | consumo, prelibranza, inversión, hipotecario, rotativo, vehículo, terceros, cooperativo, **tarjeta de crédito si es < 5 años** |
| **Pasivo largo plazo** | > 5 años | hipotecario, vehículo > 5 años, libranza, deuda de terceros, préstamo de fondo de empleados |

**[E]** La columna COMENTARIO es de uso obligatorio para matices: *"si se tiene que hacer algún comentario u observaciones… se debe colocar las observaciones por cada ítem"*. Ejemplos reales: `GSU no vesting;` · `731 semanas` · `40 mill para dejarlo ok con acabados`.

---

## 5. `Plan de Acción` — entregable central

**Fila 2:** título **"Plan de acción____«Nombre del cliente»____"**

### Gráficos incrustados (parte del método, no decoración)
- **Pirámide de 5 niveles** — ver [05](10-riesgos-y-coberturas.md)
- **Círculos concéntricos** INSTRUMENTOS → PLANEACIÓN → OBJETIVOS

### Bloque 1 — Capacidad de Ahorro Mensual

| Celda | Contenido |
|---|---|
| G5:H5 | encabezado fusionado **"Capacidad de Ahorro Mes"** |
| **F6 / G6** | etiqueta y valor de la 1.ª fuente ← `Presupuesto`!D69 |
| F7:H10 | fuentes adicionales |
| **F11 / G11** | **"Capacidad Ahorro Mensual"** *(amarilla)* — **total de la bolsa** |

### Parámetro TRM

| Celda | Contenido |
|---|---|
| F15 | etiqueta **"TRM"** |
| **H15** | **valor de TRM a usar** |

**[E] Regla (fijada por Amanda en el audio):**
```
H15 = TRM del día + 200 COP
```
*"para el plan de acción y el desarrollo del presupuesto, se debe colocar una TRM del día **más 200 pesos más adicional**. Esto solamente por tener presente que **la TRM puede llegar a crecer** y el presupuesto está ajustado a si hay un crecimiento de la TRM."*

> ⚠️ **[CORR]** El video decía *"unos 200 pesos más, elevado 300 pesos más"*. Amanda fija **+200**. Ver [18 D-03](18-discrepancias-resueltas.md).
>
> ⚠️ **Una sola TRM en todo el archivo.** El ejemplo tenía tres (3.250 / 3.300 / 3.500) **por descuido**: *"se me olvidó cambiarlas"*. Ver [18 D-02](18-discrepancias-resueltas.md).

### Bloque 2 — Destino Capacidad de Ahorro

| Col | Encabezado (fila 18) |
|---|---|
| **C** | clasificación: `COBERTURA / OBJETIVO`, `OBJETIVO`, `COBERTURA` |
| **D** | **Fuente** |
| **E** | **Objetivo** |
| **F** | **Vehículo** |
| **G** | **Monto** |
| **H** | **Saldo Disponible** |

- Estrategias desde **fila 19**
- **Fila 31:** Total
- **J21** = `=G21*12` **[V]** — fondo de emergencia acumulado a 12 meses
- **D33** — celda de texto con los 7 riesgos: `R. vida, salud, incapacidad, iliquidez, patrimonial, inflaccionario y pais`
- **≈K15:K21** — columna de notas/pendientes del asesor

**Cascada [V]:** `H(primera) = G11 − G(primera)` · `H(n) = H(n−1) − G(n)` · la última absorbe el remanente → **H final = 0**

### Bloque 3 — Capital Disponible

| Celda | Contenido |
|---|---|
| G35:H35 | encabezado fusionado **"Capital Disponible"** |
| **F36:F48** | nombre del activo utilizable |
| **G36:G48** | valor actual |
| **H36:H48** | saldo tras aplicar las estrategias |
| **F49 / G49 / H49** | **Total** *(amarilla)* |

*(Filas 43–48 agrupadas/ocultas — el salto visible es 42 → 49.)*

**Enlaces [V]:** `F37 = =+'Info Patrimonio'!B20` · `G41 = =+Presupuesto!D73`
**Doble contabilidad [V]:** `H41 = G41 − G56` — cada activo descuenta lo que se le asignó.

### Bloque 4 — Destino Capital Disponible

Mismos encabezados en **fila 55**. Estrategias desde **fila 56**. **Total en fila 76.**
*(Filas 61–75 agrupadas/ocultas.)*

**Enlace [V]:** `D57 = =+F39` — la columna Fuente trae el nombre desde el bloque de capital.
**Cierre [V]:** `G(última) = H(penúltima) = H49` y `H(total, fila 76) = 0`

### Bloque 5 — Fondo de Emergencia

| Celda | Etiqueta | Contenido |
|---|---|---|
| D81 | **FONDO DE EMERGENCIA** *(banda azul)* | |
| D82 / **E82** | MENSUAL /ANUAL | = `J21` |
| D83:D85 / E83:E85 | un renglón por cuenta/activo que queda como fondo | |
| D86 / **E86** | LIQUIDACIÓN SIN JUSTA CAUSA | `=+'Calculadora liquidacion Andrés'!B29` **[V]** |
| D87 / **E87** | **TOTAL** | suma |
| D88 / **E88** | **Cubre Gastos B. Mensuales** | ← `Presupuesto`!P9 |
| D89 / **E89** | **Cubre en meses** | **`= E87 / E88`** **[I, verificado: 445.902.729,49 / 21.499.987,19 = 20,74 ✓]** |

---

## 6. `Desprendibles de nom. 2026`

| Celda / rango | Contenido |
|---|---|
| **B5** | **INGRESOS** |
| **C5:H5** | un mes por columna (`enero 2026` … `junio 2026`) |
| B6:B13 | ítems de ingreso |
| **B14** | TOTAL INGRESOS |
| **B16** | **EGRESOS** |
| **B26** | Otros Descuentos de Nomina: |
| B27:B35 | ítems de descuento |
| **B50** | TOTAL EGRESOS |
| **B52** | **INGRESOS - EGRESOS** *(amarilla)* |
| B53 | Beneficio IBC por excedido del 40% *(verde)* |
| **Col R** | **SUMA de la fila** — `R7 = =+SUMA(C7:H7)` **[V]** |
| **Col S** | **PROMEDIO de la fila** (rótulo "PROMEDIO") |
| **Col Z** | **LAS CUATRO DEDUCCIONES TRIBUTARIAS** — `Interes de Vivienda` · `AFC, PV` · `Dependientes` · `Medi. Prepagada`. **[V] Resuelto por el audio:** son las cuatro deducciones que bajan la base gravable. `AFC, PV` es **una sola categoría**. Ver [12](12-tributario-y-pensional.md) |
| Col Y | valores sueltos — **[ND]** |

**[CORR]** El audio menciona "C50", "P52" y "C51". La pantalla muestra **B50** y **B52**; **no existe fila 51 con ese contenido**.

**Ítems de ingreso del ejemplo:** Salario Integral · Peer Bonus · Vacaciones Disfrutadas · Acciones GSU · Broadband Reimmbursement · Bono Anual · Gross Up · Tuition Reimbursement Benefit
**Ítems de egreso del ejemplo:** Retención en la Fuente Metodo · Salud EGM · Pensión IVM · Aporte fondo solidaridad · Aporte AFC · Subsistencia · Offset for Broadband reimbursement · Adelanto GSU · Tuition Reimbursement Benefit

**[E]** Las celdas **verdes** en R/S marcan *"los datos más importantes a tener en cuenta que se están moviendo"* — es decir, los conceptos variables que sí se promedian.

---

## 7. `Calculadora liquidacion Andrés`

| Celda | Contenido |
|---|---|
| B3 | "Tiempo en la empresa" |
| D4 / E4 / F4 | Años / Meses / Días |
| **Fila 7** | encabezados: B fecha de ingreso · C fecha de retiro · D dias trabajado · E vacaciones acumuladas · **F vacas tomadas** · G vacas, valor dinero · H cesan · I int cesan opción · J prima |
| **B8** | **fecha de ingreso** ← `INFORMACION Seg soc`!C19 |
| **C8** | **fecha de retiro** = **fecha de la reunión con el cliente** [E] |
| D8 | días trabajados |
| E8 | vacaciones acumuladas |
| **F8** | **vacaciones tomadas** — **[E]** *"se las tomo completas"* |
| E9 | "Vacas pend" |
| B10 / C10 | salario |
| B11 / C11 | sub de trans |
| B13 / C13 / D13 / E13 | fecha de prima · desde · hasta · días |
| **Fila 16** | encabezados: **B Año Inicio · C Año Final · D Indemnización** |
| B17:D21+ | un renglón por año trabajado |
| B24 / D24 | **Total** de indemnización |
| A27 / **B27** | Indemnización |
| A28 / **B28** | Salario |
| A29 / **B29** | **Liquidación = B27 + B28** **[V]** ← referenciada por `Plan de Acción`!E86 |

**[CORR]** El audio dice *"la suma de la celda P27 más la celda B28"*. La pantalla confirma **B27 + B28 = B29**.

---

## 8. `Desmonte Deudas`

### Bloque RESUMEN DEUDAS

Encabezados **fila 6**; datos en **filas 21–22**; **TOTAL en fila 25**.

| Col | Campo |
|---|---|
| **B** | Entidad — `=SI('Info Patrimonio'!D68="";"";'Info Patrimonio'!D68)` **[V]** |
| **C** | Pasivo |
| **D** | Deuda Total |
| **E** | Tasa |
| **F** | Cuotas Pendientes |
| **G** | **Interés pendiente por pagar** |
| **H** | Cuota mensual de pago |
| **I** | Cuota mensual de pago TOTAL |

**[E]** *"Estos ítems son sacados de la información del patrimonio."* — **la tabla se alimenta por fórmula, no se teclea.**

### Tabla de amortización — crédito 1 (hipotecario)

Cabecera **filas 1324–1327**; tabla desde **fila 1330**.

| Celda | Contenido |
|---|---|
| C1324 | Saldo Préstamo |
| **E1324** | TOTAL INTERESES — `=SUMA(G1330:G1592)` **[V]** |
| C1325 | Tasa EA |
| **C1326** | Tasa Periódica — `=SI.ERROR(TASA.NOMINAL(C1325;12)/12;"CAMBIAR TASA")` **[V]** |
| C1327 | Plazo (n.º de cuotas) |
| **H1324** | Intereses **sin** intervención (escenario base) |
| **H1325** | **Ahorro en intereses** *(verde)* |

Encabezados **fila 1329**: **B fecha · C Periodo · D Saldo Inicial · E Cuota · F Abono a Capital · G Intereses · H Saldo Final**

**Fórmula de inyección [V]** (ejemplo en F1341):
```
=SI.ERROR(SI(C1341="";"";E1341-G1341)+I1341;"")+4900000+2800000+1000000
```

### Tabla de amortización — crédito 2 (vehículo)

Cabecera **filas 1623–1626**; tabla desde **fila 1629**.

| Celda | Contenido |
|---|---|
| **C1623** | Saldo Préstamo — `=D22` **[V]** *(enlaza al RESUMEN DEUDAS)* |
| C1624 | Tasa EA |
| C1625 | Tasa Periódica |
| C1626 | Plazo |
| E1623 | TOTAL INTERESES |
| H1623 | Intereses sin intervención |
| **H1624** | **Ahorro en intereses** |

**[I]** Cuando la deuda se extingue antes del plazo original, las filas restantes muestran `#¡VALOR!`. **Es esperado, no un error a corregir.**

---

## 9. `UNIVERSIDAD`

| Celda | Contenido |
|---|---|
| B1 | **CÁLCULO UNIVERSIDAD** |
| **Fila 3** | encabezados: A **Conteo** · B **Año** · C **Valor Universidad** |
| B4 / **C4** | "Valor universidad (promedio) Bogotá semestre" — **valor de un semestre** |
| **D4 / E4 / …** | **nombre de cada hijo** (una columna por hijo) |
| A5 / B5 / **C5** | año base · **valor anual = 2 semestres** |
| **D5 / E5** | **edad de cada hijo en el año base** |
| B6:B26+ | años siguientes |
| C6:C26 | valor anual creciente **+9 % anual** **[V]** |
| D6:E26 | edad proyectada año a año |
| *(verde)* | los **5 años de carrera** de cada hijo |
| B27 | "«año» Año tentativo ingreso Universidad" |
| **D27 / E27** | **suma de los 5 años** por hijo |
| **D30** | **Total COP** — `=D27+E27` **[V]** |
| D31 | Total USD |
| **F30** | **Total USD mensual a ahorrar** — `=+I11+I23` **[V]** |
| H30 | Total COP mensual |

### Bloque de proyección por hijo (uno por cada uno)

| Etiqueta (col G) | Col H (PESOS) | Col I (DÓLARES) |
|---|---|---|
| Periodos totales | | |
| Tasa | **4,50 %** | |
| TRM | | |
| Aporte estudios «año-año» | ✓ | ✓ |
| **Valor a ahorrar mensual 4,5%** | ✓ | ✓ ← **alimenta F30** |
| Aportes en plazo establecido | ✓ | ✓ |
| Rendimiento del capital | ✓ | ✓ |
| Resultante ahorro más inversión | ✓ | |

---

## 10. `PROYECTADO TRM`

| Col | Encabezado |
|---|---|
| **B** | No AÑOS (0, 1, 2 …) |
| **C** | AÑO |
| **D** | VALOR TRM |
| **E** | CRECIMIENTO PROYECTADO — **4,5 %** constante |

- Fila base: No AÑOS = 0, TRM del día
- Proyección a 35 años
- **Resaltadas en amarillo:** años **10, 15, 20 y 25**
- Gráfico incrustado: *"LA DEVALUACIÓN DEL PESO COLOMBIANO FRENTE AL DÓLAR"* — incremento 2010→2020 del **81 %**
- Tabla de apoyo: **AÑO · CRECIMIENTO HISTORICO DÓLAR (6,15 %) · TRM**
- Marca visible: **UNITED FINANCIAL CONSULTANTS.** / **AXIA**

**[E]** El histórico es **6,15 %**; se proyecta con **4,5 %** *"de una forma de proyección muy conservadora"*.

---

## 11. `ANALISIS`

### Parámetros
| Celda | Campo |
|---|---|
| **D7** | **TRM Hoy** (la real) |
| D8 | EDAD titular |
| D9 | EDAD cónyuge |
| **D10** | **TRM 25 AÑOS** ← `PROYECTADO TRM` |
| **D11** | **TRM 20 AÑOS** ← `PROYECTADO TRM` |

### Tabla COMPARATIVA DE PRODUCTOS

| Escenario | Cols | Composición del ejemplo |
|---|---|---|
| **Escenario 1** | E | RL 360 (Inversión Pura) |
| **Escenario 2 — Nasdaq Conservadora** | F · G · H | RL 360 · BMI titular (Tasa Prom) · BMI cónyuge (Tasa Prom) |
| **Escenario 3 — Proyección Nasdaq** | I · J · K | RL 360 · BMI titular · BMI cónyuge |

**Filas comparadas:**

| Fila | Concepto |
|---|---|
| 14 / 15 | Cobertura de Vida inicial — USD / COP |
| 16 / 17 | Cobertura vida año 20 — USD / COP |
| **18 / 19** | **Valor Acumulado año 20** — USD / COP |
| **20** | **Total 20 años** *(fusionado por escenario)* |
| 21 / 22 | Cobertura vida año 25 — USD / COP |
| **23 / 24** | **Valor Acumulado año 25** — USD / COP — `F24 = =F23*D10` **[V]** |
| **25** | **Total 25 años** *(fusionado por escenario)* |
| **30** | **Prima Mensual USD** por producto |
| **31** | **Total prima** *(fusionado)* — **debe ser igual en los tres escenarios** |
