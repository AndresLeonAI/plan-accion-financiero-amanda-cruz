# 13 — Construccion del Plan de Accion (Fases 12, 13 y 14)

Esta es la hoja que se le presenta al cliente. Todo lo anterior existe para llenarla.

**Requisitos previos:**
- La **fase 10** ([08 — Desmonte de deudas](08-deudas.md)) debe estar hecha: el monto de la primera estrategia mensual sale de ahí, no de la intuición.
- La **fase 11** ([10 — Riesgos y coberturas](10-riesgos-y-coberturas.md)) debe estar hecha: si falta una cobertura, se añade una prima al presupuesto y `D69` cambia.

---

## ⭐ El orden de prioridad de las estrategias

**[E]** *"dentro de la escala, **lo primero que recomiendo son las coberturas, el tema de las anualidades, la provisión para el pago de las anualidades, y luego viene toda la parte de inversiones** y que concuerde cómo logramos esos objetivos en el corto, mediano y largo plazo."*

### Caso normal — capacidad de ahorro positiva
```
1. COBERTURAS            los 7 riesgos, empezando por los descubiertos
2. ANUALIDADES           + su provisión mensual si hace falta
3. FONDO DE EMERGENCIA   dimensionado en meses según perfil profesional
4. INVERSIONES           objetivos de corto, mediano y largo plazo
```

### Caso excepcional — capacidad de ahorro negativa o nula

**[E]** *"cuando tiene capacidad de ahorro negativa y no tiene nada para ahorrar, pues entonces **solamente le cubro lo básico: anualidades, fondo de emergencia, nada más**. Y si tiene que pagar deudas, pues trato de ajustar que haya para pagar las deudas, que haya para pagar las anualidades y que se pueda crear el fondo de emergencias. **Si no se puede crear el fondo de emergencias, trato de buscar la forma de ayudarle a crear, así sea un mínimo** para el fondo; pero si no, **como por prioridades: pago de deudas, anualidades**."*

```
1. PAGO DE DEUDAS
2. ANUALIDADES
3. FONDO DE EMERGENCIA   aunque sea un mínimo simbólico
—— y nada más ——
```

**Las inversiones y los objetivos de largo plazo desaparecen del plan.**

**[E]** Antes de asumirlo: *"la gran mayoría de mis clientes, el 99,9 %, sí toman las asesorías porque tienen algo de liquidez… **es una probabilidad muy, muy bajita**."*
> **Si detectas capacidad negativa, verifica primero que no sea un error de captura.**

**[E]** Y avisa temprano: *"cuando yo estoy en el levantamiento de información y **si veo que el ingreso es negativo, obviamente doy de una vez la recomendación**."*

---

## El modelo mental

El plan asigna **dos bolsas independientes**:

| Bolsa | Qué es | Origen | Bloque destino |
|---|---|---|---|
| **Capacidad de Ahorro Mensual** | flujo que sobra cada mes | `Presupuesto`!D69 | filas 18–31 |
| **Capital Disponible** | stock que ya existe y se puede mover | `Info Patrimonio` filtrado + bonificaciones anuales | filas 55–76 |

Cada bolsa se agota al **100 %**. Cada línea responde cinco preguntas:

```
¿Cubre riesgo u objetivo?  →  ¿De dónde sale?  →  ¿Para qué?  →  ¿A dónde va?  →  ¿Cuánto?
        C                          D                  E              F              G
```

Y la columna **H** lleva el saldo en cascada hasta cero.

---

## FASE 12 — Capacidad de ahorro mensual y sus estrategias

### 12.1 Cargar la bolsa

| Celda | Qué poner |
|---|---|
| **F6** | etiqueta de la fuente — `Capacidad de Ahorro Mensual` |
| **G6** | valor ← **`Presupuesto`!D69** |
| F7:H10 | otras fuentes mensuales, si las hay |
| **F11 / G11** | **total de la bolsa** *(amarillo)* |

**[E]** *"se relaciona la capacidad de ahorro mensual en la celda F6. En la G6 se coloca el valor mensual, que es ese ítem que revisamos en el presupuesto, **donde se trae el resultado de la columna D69, que es el monto disponible mensual**."*

### 12.2 Fijar la TRM (H15)

**[E]** *(audio — regla definitiva)* *"para el plan de acción y el desarrollo del presupuesto, se debe colocar **una TRM del día más 200 pesos más adicional**. Esto solamente por tener presente que **la TRM puede llegar a crecer** y el presupuesto está ajustado a si hay un crecimiento de la TRM."*

```
H15 = TRM del día + 200 COP
```

Es un supuesto conservador: si el peso se devalúa, harán falta más pesos para mantener el mismo aporte en USD. Presupuestar con la TRM alta evita quedarse corto.

> ⚠️ **[CORR]** El video decía *"200 o 300 pesos"*. Amanda fija **+200**.
> ⚠️ **Una sola TRM en todo el archivo.** Solo `PROYECTADO TRM` lleva la TRM del día exacta; todo lo demás lleva día + 200. Ver [18 D-02 y D-03](18-discrepancias-resueltas.md).

### 12.3 Escribir las estrategias

Una fila por estrategia, desde la **19**:

| Col | Qué escribir | Valores observados |
|---|---|---|
| **C** | clasificación | `COBERTURA / OBJETIVO` · `OBJETIVO` · `COBERTURA` |
| **D** | **Fuente** — de dónde sale | `Capacidad Ahorro Mensual` |
| **E** | **Objetivo** — qué se cubre | `Pago Deudas` · `Libertad Financiera/ Estudios Niños/ Jubilación` · `Fondo de Emergencia` |
| **F** | **Vehículo** — a dónde va | `Inyección a Capital` · `Inversión` · `Ctas Alta Rentabilidad, Fiduciaria, FICS, Global 66` |
| **G** | **Monto** | |
| **H** | **Saldo Disponible** | fórmula de cascada |

**[E]** *"en la del 19 es la primera estrategia, donde vamos a saber **si lo que vamos a cubrir va a ser una cobertura o un objetivo, o las dos cosas**."*

### 12.4 La cascada de saldos [V]

```
H19 = G11 − G19          ← fórmula leída en pantalla
H20 = H19 − G20
H21 = H20 − G21
...
```

**La última estrategia absorbe el remanente:** `G21 = =H20` **[V]**, de modo que **H final = 0**.

**[V] Ejemplo completo:**

| Fila | C | D | E | F | G | H |
|---|---|---|---|---|---|---|
| 19 | COBERTURA / OBJETIVO | Capacidad Ahorro Mensual | Pago Deudas | Inyección a Capital | 4.900.000 | `=G11-G19` → 6.996.812 |
| 20 | COBERTURA / OBJETIVO | Capacidad Ahorro Mensual | Libertad Financiera/ Estudios Niños/ Jubilación | Inversión | `=1500*H15` → 5.250.000 | 1.746.812 |
| 21 | COBERTURA / OBJETIVO | Capacidad Ahorro Mensual | Fondo de Emergencia | Ctas Alta Rentabilidad, Fiduciaria, FICS, Global 66 | `=H20` → 1.746.812 | **0** |
| 31 | | | | **Total** | 11.896.812 | **0** |

### 12.5 De dónde sale cada monto

| Estrategia | Origen del monto |
|---|---|
| **Pago de deudas (G19)** | **[E]** del análisis de la fase 10: *"esta es la razón por la cual se tuvo en cuenta en el plan de acción que **sí o sí se debe dejar presupuestado un pago de inyección a capital de 4.900.000**."* En el ejemplo coincide con el ahorro AFC liberado en el patrón 2. |
| **Inversión (G20)** | **[E]** *"hice un aproximado de 1.500 dólares"*, con `=1500*H15`. **[ND]** El 1.500 está **hardcodeado** — es la capacidad de inversión mensual en USD que decide el asesor tras contrastar necesidad (fase 15) con capacidad. **[E]** *"En principio hice un balance de cuánto podría llegar a ser y luego voy ajustando los montos para saber cuál podría ser el monto ideal."* |
| **Fondo de emergencia (G21)** | El remanente: `=H20` |

### 12.6 Sobre el vehículo

**[E]** Para el pago de deudas, cuando aún no está decidido a cuál: *"Acá vamos a colocar pago de deudas; **el vehículo va a ser inyección a capital, porque no sabemos a qué deuda se le va a inyectar** —si es al crédito hipotecario, si tiene sentido que siga inyectando al crédito hipotecario o mejor al crédito del carro. Pero de igual forma coloqué que sea inyección a capital."*
→ **Es legítimo dejar el vehículo genérico** cuando el destino fino depende del análisis de deuda.

**[E]** Para el fondo de emergencia: *"el vehículo hacia donde se puede llevar es una cuenta de alta rentabilidad, una fiducia, un FIC o un Global 66, **o bueno, la mejor recomendación que se dé**."*
→ Se listan alternativas, no se impone una.

### 12.7 Proyección a 12 meses (J21)

**[V]** `J21 = =G21*12` → 20.961.747

**[E]** *"si cogemos la celda G21, que es el fondo de emergencias mensual, multiplicado por 12, va a aparecer en la celda J21 **para que el cliente sepa cuánto logra reunir en total del fondo de emergencias al cabo de un año**."*

Este valor alimenta después `E82` del bloque Fondo de Emergencia.

### 12.8 Iteración

**[E]** *"En principio hice un balance de cuánto podría llegar a ser y **luego voy ajustando los montos para saber cuál podría ser el monto ideal**"* · *"en la medida en la que yo le presento el plan de acción **voy haciendo ajustes en caso dado**."*

**Las estrategias son un borrador que se ajusta**, incluso en vivo durante la reunión. Lo que no cambia es la restricción: la suma siempre debe agotar la bolsa.

---

## FASE 13 — Capital disponible y sus estrategias

**[E]** Amanda la llama explícitamente **"la segunda fase"**: *"luego ahora vamos a pasar… **a una segunda fase, y es el capital disponible de una persona. El capital disponible lo que me hace referencia es a qué tanto dinero tengo hoy disponible para gastar.**"*

**[E]** Y su origen: *"estos ítems **son sacados del registro de la información del patrimonio**"* — el bloque no se construye de cero, se filtra desde `Info Patrimonio`.

**[E]** Su propósito: *"se trajo los que puede utilizar el cliente **para poder crear una estrategia para el plan de acción que le permita cumplir sus objetivos**."*

### 13.1 Filtrar qué activos entran

**[E]** *"lo que tenemos que tener en cuenta es **cuál de estos puede utilizar y cuáles no**."*

Recorre `Info Patrimonio` activo por activo y pregunta explícitamente:

| Activo | ¿Entra? | Fundamento [E] |
|---|---|---|
| Cuentas de ahorro | **Sí** | *"¿Cuenta de ahorros puede utilizar? Sí."* |
| Cuentas de inversión (Global 66, brokers) | **Sí** | *"¿Lo de Global? Sí."* |
| AFC | **Sí** | *"¿Lo de la FC también?"* — **con restricción de destino, ver 11.4** |
| Acciones | **Sí** | *"¿Lo de las acciones se pueden utilizar? Sí."* |
| **Pensión obligatoria** | **NO** | *"¿Lo de la pensión obligatoria de él y de ella se puede utilizar? **No.** Entonces no lo relacionamos."* |
| **Activos improductivos** | **NO**, salvo excepción | *"¿Los activos improductivos se pueden utilizar? **No, a menos de que el cliente diga: voy a vender el carro** en caso de que tenga que hacerlo, o voy a vender el apartamento. Entonces hay que relacionarlo en el capital disponible **en dado caso que venda**."* |
| **Bono / prima anual** | **Sí — aunque no esté en el patrimonio** | *"este no está en la información del patrimonio, pero sabemos que hay un bono anual de él, entonces vamos a colocar el bono anual. Acá puede ser una prima también, una prima anualizada que esté relacionada en el presupuesto, una prima que se entrega semestral en junio o en diciembre, **o todas las bonificaciones anualizadas se deben colocar acá**."* |

> ⚠️ Revisa la columna COMENTARIO de `Info Patrimonio` antes de decidir. Un activo marcado `GSU no vesting` puede no ser realmente disponible. **Ante la duda, pregunta.**

### 13.2 Cargar el bloque (filas 36–49)

| Col | Contenido |
|---|---|
| **F** | nombre del activo — puede enlazarse: `=+'Info Patrimonio'!B20` **[V]** |
| **G** | valor actual — puede enlazarse: `=+Presupuesto!D73` **[V]** |
| **H** | saldo que queda tras aplicar las estrategias |
| **F49/G49/H49** | **Totales** *(amarillo)* |

**Usa enlaces, no valores tecleados**, siempre que el dato exista en otra hoja.

### 13.3 Escribir las estrategias (filas 56–76)

Mismas seis columnas que el bloque mensual.

**[V] Ejemplo completo, con la cascada comprobada:**

| Fila | C | D Fuente | E Objetivo | F Vehículo | G Monto | H Saldo |
|---|---|---|---|---|---|---|
| **56** | COBERTURA / OBJETIVO | Bono Anual Andrés | **Anualidades** | Ctas Alta Rentabilidad, Fiduciaria, FICS, Bolsillo | 46.617.989 ← `Presupuesto`!D104 | 431.990.162 |
| **57** | OBJETIVO | AFC Andrés `=+F39` | Pago C. Hipotecario | Inyección a Capital C. Hipotecario | 27.335.256 | 404.654.906 |
| **58** | OBJETIVO | Morgan Standly Acciones | Remodelación | Remodelación Apto. Nvo. | 40.000.000 | 364.654.906 |
| **59** | OBJETIVO | Cta. Ahorros + Global | Pago Deudas | Inyección a Capital TC | 16.000.000 | 348.654.906 |
| **60** | COBERTURA / OBJETIVO | Saldos | Fondo de Emergencia | Mismos lugares | **348.654.906** | — |
| **76** | | | | **Total** | 478.608.151 | **0** |

Cascada: `H56 = G49 − G56` · `H(n) = H(n−1) − G(n)` · `G60 = H59`

### 13.4 El orden de las estrategias de capital

#### Estrategia 1 — SIEMPRE: separar las anualidades

**[E]** *"lo que debemos revisar es **primero, sí o sí, separar el valor de las anualidades. Eso es algo que es súper importante tener presente.**"*

| Condición | Acción |
|---|---|
| **Ingresos anuales > Gastos anuales** (`D105` negativo) | **[E]** *"podremos coger en el capital disponible, separar las anualidades para ser cubiertas con los ingresos anuales"* → estrategia 1 = fuente **Bono anual**, objetivo **Anualidades**, monto = **`Presupuesto`!D104** |
| **Ingresos anuales < Gastos anuales** (`D105` positivo) | **[E]** *"se deberá tener en cuenta esta provisión mensual dentro de la estrategia del plan de acción **en la parte del recurso mensual**"* → la provisión se convierte en línea del bloque **mensual** |

**[E]** *"colocamos como primera estrategia, para cobertura del objetivo del bono, la fuente donde vamos a sacar el dinero —del bono anual del cliente— para el objetivo de las anualidades, llevarlo a un vehículo de cuentas de alta rentabilidad, fiducia, FIC o bolsillo… **vamos a colocar el valor total de las anualidades que vemos en el presupuesto en la casilla D104**."*

#### Estrategias siguientes — según objetivos y restricciones

**Restricción de destino del AFC [E]:** *"la fuente va a ser la FC de Andrés, el objetivo va a ser pago del crédito hipotecario, inyección a capital como vehículo al crédito hipotecario, **porque esa plata definitivamente de la FC solamente puede ser llevada para crédito hipotecario**."*
→ **El AFC no es de libre destinación.** Va obligatoriamente al crédito hipotecario.

**Objetivos que vienen de la conversación [E]:** *"para cumplir el objetivo de remodelación —en algún momento había mencionado el cliente que necesitaba remodelar un apartamento— dijo que iba a necesitar 40 millones de pesos. **Estos datos son escritos en un archivo de Word** que se van a dejar consignados acá, o que se pueden colocar como observaciones en la información de objetivos."*

**Deuda cara primero [E]:** *"El cliente mencionó que debía tarjeta de crédito, por ahí pagaba los gastos del mes, pero que **había excedido en un gasto y que estaba pagando una tasa muy alta, muy muy alta**, razón por la cual tuve en cuenta que es importantísimo salir de esa deuda… **en vez de dejar el dinero estancado en una cuenta de ahorros, hay que ir a pagar esa deuda**."*

**Última estrategia [E]:** *"como una quinta estrategia, para cobertura y objetivo, **la fuente serán los saldos que queden en los diferentes ítems**; van a formar el objetivo del fondo de emergencia y el vehículo van a ser los mismos lugares."*

### 13.5 La doble contabilidad por activo (columna H del bloque 3)

**[E]** *"para poder llegar a ajustar las cifras, lo que yo hago es que, en la medida en la que voy dando la recomendación —por ejemplo, en el capital disponible, en el bono de anualidades, acá 47 millones de pesos que tiene el cliente que vemos registrado en la celda G41—, **en la celda H41 voy colocando la celda a la que hace referencia: las anualidades. Le resto el valor de las anualidades que describí en la celda G56 y el total me queda registrado en la casilla H41, para ir sabiendo cuánto va quedando de saldo en cada uno de esos ítems**."*

**[V]** `H41 = G41 − G56` = 47.846.500 − 46.617.989 = **1.228.511** ✓

Haz esto para **cada activo**: réstale lo que se le asignó en las estrategias.

**[V] Ejemplo — cómo se reparte una estrategia entre dos activos:**
La estrategia 59 toma 16.000.000 de `Cta. Ahorros Andrés + Global Andrés`. Se reparte 8.000.000 + 8.000.000:
- H36 = 8.696.474 − 8.000.000 = **696.474** ✓
- H38 = 10.974.082 − 8.000.000 = **2.974.082** ✓

### 13.6 ⚠️ EL CUADRE OBLIGATORIO

```
H49  (suma de saldos individuales por activo)  ==  G60  (monto del fondo de emergencia)
```

**[E]** *"Si me doy cuenta, el total de lo que queda en cada rubro son 348.6, **que equivale al mismo ítem que aparece en la celda G60**."*

**[V]** 696.474 + 3.777.120 + 2.974.082 + 0 + 339.978.719 + 1.228.511 = **348.654.906** = G60 ✓

**Si estos dos números no coinciden, hay un error de asignación.** No sigas hasta cuadrarlo.

### 13.7 Cuenta y valida las estrategias

**[E]** *"ya hemos entregado en el capital disponible 1, 2, 3, 4, 5 estrategias… y en el anterior panorama creamos 3 estrategias adicionales, **o sea, 8 estrategias**."*

Y comprueba contra los objetivos: **[E]** *"Cuando vamos a ver los objetivos, claramente cumplimos con el tema del colegio del hijo, optimización del presupuesto, inversiones y habremos organizado temas de viajes, **porque los viajes ya están incluidos dentro de las anualidades**."*

> **Vuelve a `Info Objetivos` y verifica objetivo por objetivo que cada uno está atendido por al menos una estrategia** — directamente o vía las anualidades. Si alguno queda fuera, el plan está incompleto.

---

## FASE 14 — Fondo de emergencia

### 14.1 Componer el fondo (filas 81–87)

| Celda | Contenido |
|---|---|
| D82 / **E82** | `MENSUAL /ANUAL` ← **`J21`** (el aporte mensual × 12) |
| D83:D85 / E83:E85 | cada cuenta o activo que queda como fondo, con su saldo remanente |
| D86 / **E86** | `LIQUIDACIÓN SIN JUSTA CAUSA` ← `=+'Calculadora liquidacion Andrés'!B29` **[V]** |
| D87 / **E87** | **TOTAL** |

**[E]** *"lo que va a quedar en Global, en las diferentes cuentas, los saldos —después de haber sacado dineros, lo que queda de las acciones—, lo que queda y en total se suma."*

**[E]** Por qué se incluye la liquidación: *"la calculadora de liquidación nos sirve para entender cuánto sería el fondo de emergencias, **integrándolo con una liquidación por despido sin justa causa en el peor de los escenarios**."*
→ Es coherente con el principio de **no depender del empleador**.

### 14.2 Calcular los gastos básicos mensuales

Ver [17 §6](17-reglas-y-excepciones.md) para el detalle del criterio de selección.

Resultado: `Presupuesto`!P9 → **`E88`** (`Cubre Gastos B. Mensuales`)

### 14.3 Meses de cobertura

```
E89  =  E87 / E88
```

**[E]** *"A ese total del fondo de emergencias lo vamos a dividir por el gasto básico mensual del hogar **para entender cuántos meses le va a cubrir**."*
**[V]** 445.902.729,49 / 21.499.987,19 = **20,74 meses** ✓

**[E]** El cierre narrativo: *"entonces el cliente se va a sentir muy tranquilo… y aparte de eso, robusto."*

### 14.4 ⭐ La meta en meses depende del perfil profesional

**[E]** *(audio)* *"Esa es una muy buena pregunta. **Se establece dependiendo del perfil profesional.**"*

> *"si es de alguien **del sector de la salud**, seguramente va a necesitar un fondo de emergencias de **un mes, dos meses o máximo tres meses**. Pero si es **de otras áreas**, seguramente va a necesitar **como mínimo seis meses** de los gastos básicos."*

| Perfil profesional | Meses de gastos básicos |
|---|---|
| **Sector salud** | **1 – 3** (máximo 3) |
| **Resto de sectores** | **mínimo 6** |
| **Default si no se conoce el sector** | **6** |

**[E]** El objetivo general que usa por defecto: *"usualmente, en términos generales, **trato de crear algo más o menos teniendo presente los gastos básicos de seis meses**."*

**[I]** El fundamento no se declara, pero es coherente: alta empleabilidad y reincorporación rápida → menor colchón necesario.

### 14.5 El fondo se construye progresivamente

**[E]** *"trato de hacerlo ajustado en el plan de acción **con lo que vaya quedando mes a mes hasta que logremos completar**… y **lo multiplico por 12** y de esta forma le digo: bueno, tú puedes sacar si haces un ahorro de 300 mil mensuales, que es lo que restaría de la clasificación de prioridad en el plan de acción; le voy diciendo cuánto puede ahorrar al año y ahí lo vamos construyendo."*

**[E]** *"**no es necesario que en el primer mes ya tenga listo lo de los seis meses; no, se va construyendo en el tiempo.**"*

> **[V] Esto explica la fórmula `J21 = G21*12`:** no es un dato informativo, es **el instrumento para mostrarle al cliente el avance anual hacia la meta de meses.**

### 14.6 Validación obligatoria

```
E89 (meses de cobertura actuales)   vs.   meta según perfil profesional
```

| Resultado | Qué reportar |
|---|---|
| `E89` ≥ meta | ✅ objetivo cumplido |
| `E89` < meta | ⚠️ **decirlo explícitamente** y calcular en cuántos meses se alcanza al ritmo de `G21` |

**Nunca presentes el fondo de emergencia solo como un monto.** Preséntalo como **meses de cobertura contra la meta del perfil.**

---

## Resumen del entregable

Al terminar las fases 12, 13 y 14 debes tener:

- [ ] `G11` cargado desde `Presupuesto`!D69
- [ ] `H15` con TRM real + 200/300
- [ ] Estrategias mensuales escritas, con cascada hasta **H = 0**
- [ ] `J21` calculado
- [ ] Los 7 riesgos revisados ([05](10-riesgos-y-coberturas.md)) **antes** de cerrar el bloque de capital
- [ ] Capital disponible filtrado (sin pensión obligatoria, sin improductivos salvo venta declarada, con bonificaciones anuales)
- [ ] Estrategia 1 de capital = anualidades, si `D105` es negativo
- [ ] Restricción del AFC respetada
- [ ] Estrategias de capital con cascada hasta **H = 0**
- [ ] Doble contabilidad por activo en la columna H del bloque 3
- [ ] **`H49 == G60`** ✓
- [ ] Fondo de emergencia compuesto, con liquidación incluida
- [ ] Meses de cobertura calculados
- [ ] Cada objetivo de `Info Objetivos` verificado contra al menos una estrategia