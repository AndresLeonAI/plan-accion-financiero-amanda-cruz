# 08 — Desmonte de deudas (Fase 10)

**Se ejecuta ANTES de escribir las estrategias del `Plan de Acción`.**

**[E]** Amanda lo declara aunque lo explique al final del video: *"**previo a esto, hice un análisis también del tema de las deudas**"* y *"Hice un análisis por aparte de sus deudas, donde le doy una estrategia de cómo salir de deudas lo más pronto posible, generando un impacto importante de reducción en el tiempo y de los intereses."*

**Por qué es previo:** el monto de la primera estrategia mensual (`Plan de Acción`!G19) sale de aquí.
**[E]** *"De esta manera, esta es la razón por la cual se tuvo en cuenta en el plan de acción que **sí o sí se debe dejar presupuestado un pago de inyección a capital de 4.900.000**."*

---

## Objetivo de la fase

**[E]** *"nos muestra que **la mejor forma para ahorrar y minimizar el impacto en tiempo y en intereses** es inyectando esos 4.900.000 primero al carro, al crédito del carro, y luego al crédito hipotecario. **Pero para esto hay que hacer el análisis puntual, teniendo presente cuándo se van a inyectar.**"*

Dos métricas de decisión, siempre las dos:
1. **Ahorro en intereses** (COP)
2. **Reducción de plazo** (meses)

---

## Paso 1 — Verificar que `Info Patrimonio` está completo

El bloque RESUMEN DEUDAS **se alimenta por fórmula**, no se teclea:

**[V]** `B21 = =SI('Info Patrimonio'!D68="";"";'Info Patrimonio'!D68)`

**[E]** *"Estos ítems son sacados de la información del patrimonio."*

Para cada deuda necesitas, en `Info Patrimonio` (filas 47+ corto plazo, 68+ largo plazo):

| Col | Dato | ¿Bloqueante? |
|---|---|---|
| B | PASIVO (nombre) | sí |
| C | SALDO DE CAPITAL | **sí** |
| D | ENTIDAD | sí |
| E | **TASA** | **sí — sin ella no hay amortización** |
| F | **#CUOTAS PENDIENTES** | **sí** |
| G | CUENTA MENSUAL | **sí** |

> ⚠️ Si falta la tasa o las cuotas pendientes de alguna deuda, **detente y pídelas.** No estimes una tasa "de mercado": violarías la regla anti-invención y todo el análisis quedaría inventado.

---

## Paso 2 — Leer el bloque RESUMEN DEUDAS

Encabezados en fila 6; datos en filas 21–22; TOTAL en fila 25.

| Col | Campo |
|---|---|
| B | Entidad |
| C | Pasivo |
| D | **Deuda Total** |
| E | Tasa |
| F | Cuotas Pendientes |
| G | **Interés pendiente por pagar** |
| H | Cuota mensual de pago |
| I | Cuota mensual de pago TOTAL |

**[V] Ejemplo:**

| Fila | Entidad | Pasivo | Deuda Total | Tasa | Cuotas | Interés pend. | Cuota mensual |
|---|---|---|---|---|---|---|---|
| 21 | Bancolombia | Crédito Hipotecario | 266.556.066 | 12 % | 263 | 52.357.210 | 2.894.901 |
| 22 | Otros | Crédito Vehículo Sufi | 72.994.380 | 11 % | 30 | 4.039.579 | 2.803.641 |
| **25** | | **TOTAL** | **339.550.446** | | | **56.396.789** | **5.698.542** |

*(La tasa se muestra redondeada; el dato fino —11,90 % y 11,15 %— vive en `Info Patrimonio`.)*

**[E]** *"La relación queda consignada acá en la fila 21 y 22, clasificada por entidad, pasivo, deuda, tasa, cuota, interés por pagar y cuota mensual."*

---

## Paso 3 — Construir una tabla de amortización por deuda

Cada crédito tiene su bloque. En el ejemplo:
- **Crédito Hipotecario** — cabecera filas 1324–1327, tabla desde 1330
- **Crédito Vehículo** — cabecera filas 1623–1626, tabla desde 1629

### Cabecera

| Celda (ej. hipotecario) | Contenido | Fórmula |
|---|---|---|
| C1324 | **Saldo Préstamo** | del RESUMEN DEUDAS — en el vehículo: `C1623 = =D22` **[V]** |
| **E1324** | **TOTAL INTERESES** | `=SUMA(G1330:G1592)` **[V]** |
| C1325 | **Tasa EA** | de `Info Patrimonio` |
| **C1326** | **Tasa Periódica** | `=SI.ERROR(TASA.NOMINAL(C1325;12)/12;"CAMBIAR TASA")` **[V]** |
| C1327 | **Plazo** | cuotas pendientes |
| **H1324** | **Intereses sin intervención** (escenario base) | |
| **H1325** | **Ahorro en intereses** *(verde)* | base − con intervención |

**[E]** *"me permite ver cómo el crédito hipotecario, partiendo de cuánto es el saldo del préstamo a la fecha, la tasa, **me convierte la tasa efectiva anual a la tasa periódica** en la celda C1326… y luego, teniendo presente las cuotas que faltan —para este caso 263—, lo distribuye por periodo, saldo, cuota, abono a capital, interés y saldo final."*

> La fórmula `TASA.NOMINAL(EA;12)/12` convierte **efectiva anual → periódica mensual**. Si devuelve `"CAMBIAR TASA"`, la tasa de entrada está mal.

### Tabla (encabezados fila 1329)

| Col | Campo |
|---|---|
| **B** | fecha (`jul-26`, `ago-26`, …) |
| **C** | Periodo (1, 2, 3 …) |
| **D** | Saldo Inicial |
| **E** | Cuota |
| **F** | **Abono a Capital** ← aquí se inyecta |
| **G** | Intereses |
| **H** | Saldo Final |

**[E]** *"acá yo coloco la fecha en la que se encuentra el estado del saldo inicial **y la proyecto en el tiempo**."*

> **Ancla la fecha del periodo 1 al mes real del saldo.** Todo el análisis de secuenciación depende de que las fechas sean correctas.

---

## Paso 4 — Simular la inyección

### La fórmula [V]

```
=SI.ERROR(SI(C1341="";"";E1341-G1341)+I1341;"")+4900000+2800000+1000000
```

Descompuesta:

| Componente | Qué es |
|---|---|
| `E1341-G1341` | abono base = **Cuota − Intereses** |
| `+I1341` | abono extraordinario puntual, si lo hay |
| `+4900000` | **inyección mensual del plan** |
| `+2800000` | **cuota liberada** de la deuda ya extinguida |
| `+1000000` | adicional disponible |

**[E]** *"se muestra que relaciono 4.900.000, que es lo que quedaría libre, más 2.800.000 del pago del crédito del vehículo que quedaría libre, más acá estaré llevando un millón de pesos adicionales para inyectar."*

### Marcar el punto de inicio en verde

**[E]** *"se lo dejé, lo colocó **como en casillita en verde para saber en dónde empecé a colocar el ajuste**"* · *"lo mismo acá lo dejé en verde para entender que la de abono capital se colocó desde ahí."*

**Toda intervención se resalta en verde en la fila donde empieza.** Es la trazabilidad de la simulación.

### Replicar hacia abajo

**[E]** *"yo acá lo coloco así y **lo repliqué de ahí hacia abajo**."*

### Dos tipos de inyección

| Tipo | Origen | Ejemplo del video |
|---|---|---|
| **Puntual** | capital disponible | 27.335.256 del AFC, en ago-26 (fila 1331), abono a capital 27.235.526 |
| **Recurrente** | capacidad de ahorro mensual | 4.900.000/mes, replicado |

---

## Paso 5 — La regla de secuenciación (bola de nieve con simulación)

Este es el hallazgo metodológico central de la fase.

### 5.1 Primero se prueba lo obvio y se descarta si no funciona

**[E]** *"si se inyecta los 4.900.000 **no va a impactar tan fuerte en el crédito hipotecario**, porque esto ya lo había revisado."*

→ La deuda más grande **no** es necesariamente la que primero se ataca.

### 5.2 Se prueba la deuda que se extingue antes

**[E]** *"Sin embargo, si yo lo proyecto, **primero llevo esos 4.900.000 al crédito del vehículo**… y lo que nos muestra es que, al inyectar esos 4.900.000 en el crédito del vehículo, **este cliente ya no saldría en 30 meses, sino en el mes 11**."*

**[V]** Resultado: plazo 30 → **periodo 11 (may-27)**. Saldo final negativo (−2.557.408) marcado en verde. Las filas siguientes muestran `#¡VALOR!` — **es esperado**, la deuda ya no existe.

**[V]** Intereses: sin intervención **10.436.622,20** → con intervención **4.039.579**. **Ahorro: 6.397.043** (H1624).

**[E]** *"si no hiciera ningún movimiento especial, el cliente pagaría intereses 10.436.622… y si el cliente inyecta 4.900.000 mes a mes a partir de agosto, pagará… la diferencia me la muestra en la casilla H1624… **el cliente va a ahorrarse 6.3 millones de pesos en intereses**."*

### 5.3 Se encadena: la cuota liberada se suma a la siguiente deuda

**[E]** *"este cliente muestra con esta tabla de amortización que saldría en mayo 27 en la cuota 11, es decir, en mayo del 2027. **Si yo me voy ahora al crédito hipotecario y cojo mayo del 2027, es decir que para junio puedo inyectarle esos 4.900.000 más los 2.800.000 que estaba pagando de cuota** por el crédito del vehículo… **y ya al quedar libre se puede inyectar al crédito hipotecario**."*

**El mecanismo:**
```
may-27  → se extingue el crédito de vehículo
jun-27  → la fila 1341 del hipotecario recibe:
          4.900.000 (inyección del plan)
        + 2.800.000 (cuota del vehículo, ahora libre)
        + 1.000.000 (adicional)
```

**La fecha de encadenamiento no se estima: se lee de la tabla de amortización de la primera deuda.**

### 5.4 Se suman las inyecciones puntuales de capital

**[E]** *"Pero previo a eso, ahorita en agosto, vimos que tenía un valor de AFC que se puede inyectar a capital, entonces acá también lo inyecto y lo dejo relacionado en la celda F1331."*

**[V]** Resultado del hipotecario con ambas intervenciones: sale en el **mes 34 = abril 2029**; intereses **52.357.210**; **ahorro 402.389.211,55** (H1325).

**[E]** *"lo proyecté y lo que me muestra es que **el cliente saldrá en el mes 34, que corresponde a abril de 2029**… terminará pagando 52.3 millones de pesos [de intereses]… **se ahorrará 402.3 millones de pesos en intereses**."*

### 5.5 La regla

> **No se decide por tasa. No se decide por saldo. Se decide simulando.**
>
> 1. Simula la inyección sobre cada deuda por separado
> 2. Compara **ahorro de intereses** y **reducción de plazo**
> 3. Elige la secuencia que optimiza ambos
> 4. Encadena: al extinguirse una deuda, **su cuota se suma** a la inyección sobre la siguiente
> 5. Suma las inyecciones puntuales de capital disponible en su fecha real

**[E]** *"esto nos muestra claramente cuánto es el ahorro por cada uno de los créditos, y nos muestra que la mejor forma para ahorrar y minimizar el impacto en tiempo y en intereses es inyectando esos 4.900.000 primero al carro… **pero para esto hay que hacer el análisis puntual teniendo presente cuándo se van a inyectar**."*

---

## Paso 6 — Llevar el resultado al `Plan de Acción`

De este análisis salen **tres cosas**:

| Resultado | Va a |
|---|---|
| **Monto de la inyección mensual** | `Plan de Acción`!G19, con objetivo `Pago Deudas` |
| **Destino de las inyecciones puntuales de capital** | estrategias del bloque Destino Capital Disponible (filas 56+) |
| **Ahorro de intereses y fechas de liberación** | el argumento que se le presenta al cliente |

**[E]** *"esta es la razón por la cual se tuvo en cuenta en el plan de acción que sí o sí se debe dejar presupuestado un pago de inyección a capital de 4.900.000."*

**[E]** El vehículo puede quedar genérico si el reparto fino aún está abierto: *"el vehículo va a ser inyección a capital, **porque no sabemos a qué deuda se le va a inyectar**… pero de igual forma coloqué que sea inyección a capital."*

---

## Restricciones de destino que hay que respetar

| Fuente | Restricción |
|---|---|
| **AFC** | **[E]** *"esa plata definitivamente de la FC **solamente puede ser llevada para crédito hipotecario**"* |
| **Deuda con tasa muy alta** | **[E]** prioridad de pago con capital líquido: *"había excedido en un gasto y estaba pagando una tasa muy alta, muy muy alta, razón por la cual tuve en cuenta que es importantísimo salir de esa deuda… **en vez de dejar el dinero estancado en una cuenta de ahorros, hay que ir a pagar esa deuda**"* |

---

## Checklist de la fase 8

- [ ] `Info Patrimonio` completo: saldo, tasa, cuotas pendientes y cuota mensual de **cada** deuda
- [ ] RESUMEN DEUDAS alimentándose por fórmula (no tecleado)
- [ ] Una tabla de amortización por deuda, con la tasa periódica bien convertida
- [ ] Fecha del periodo 1 anclada al mes real del saldo
- [ ] Escenario base (sin intervención) calculado y anotado — es la referencia del ahorro
- [ ] Simulación de inyección sobre **cada** deuda por separado
- [ ] Comparación de ahorro de intereses **y** reducción de plazo
- [ ] Fecha de extinción de la primera deuda leída de la tabla, no estimada
- [ ] Encadenamiento de la cuota liberada en la fecha correcta
- [ ] Inyecciones puntuales de capital ubicadas en su mes real
- [ ] Celdas de inicio de intervención en **verde**
- [ ] `#¡VALOR!` posteriores a la extinción: verificados como esperados
- [ ] Monto de inyección mensual trasladado a `Plan de Acción`!G19
- [ ] Ahorro total en intereses y nuevas fechas de liberación documentados para la presentación
