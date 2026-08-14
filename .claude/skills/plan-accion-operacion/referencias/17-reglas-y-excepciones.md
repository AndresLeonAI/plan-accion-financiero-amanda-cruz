# 17 — Catalogo de reglas y excepciones

Todas las micro-reglas del método, agrupadas. Cada una con su cita literal.

---

## 1. MENSUALIZACIÓN

Todo lo que entra al bloque de egresos mensuales debe estar expresado **por mes**.

### 1.1 Regla general del prorrateo

**[E]** *"Si el cliente llegara a mencionar que gasta cada tres meses 300 mil, por dar un ejemplo, pues **se debe especificar que son 300 dividido en tres meses, para poder sacar el valor prorrateado a lo del mes**."*

```
valor mensual = valor del periodo / número de meses del periodo
```

### 1.2 Excepción del colegio — 11 meses, no 12

**[E]** *"si el colegio, la persona dice que se pagan 3 millones mensuales por el servicio de colegio, lo importante acá es **desglosarlo, porque el colegio de un niño son 11 meses**. Se podría llegar a dejar 12 meses, pero incluida ya la matrícula. **De lo contrario, se coge el monto multiplicado por 11 y dividido por 12.**"*

| Caso | Fórmula | Rótulo |
|---|---|---|
| Solo pensión (11 pagos al año) | **`monto × 11 / 12`** | `Pensión Colegio` |
| Pensión + matrícula (equivale a 12) | **monto mensual tal cual** | `Pensión + Matrícula` |

**[E]** *"Si no, entonces dejar pensión más matrícula y se coloca el valor mensual que se paga, **para que de esta forma dé un valor mensual acertado**."*

### 1.3 Mascotas — un solo ítem agregado

**[E]** *"debe ir relacionado el monto que el cliente pague de forma mensual por alimentación de su mascota, por veterinario mensual si se paga, por medicamentos, y en general **reunir esos diferentes ítems y sumarlo como una suma única para el ítem de mascotas de forma mensual**."*

### 1.4 Almuerzos — de lunes a viernes

**[E]** *"Acá son los almuerzos que vamos a tener en cuenta **de lunes a viernes** que gasta."*

### 1.5 Salidas — fines de semana y festivos

**[E]** *"colocarle **salidas en general**, que esto es lo que reúne los gastos de la persona o de la pareja **el sábado, el domingo y días festivos**… y se coloca el valor mensualizado."*

---

## 2. ANTI-DUPLICACIÓN

Los tres errores que inflan artificialmente el gasto.

### 2.1 Tarjeta de crédito

**[E]** *"Si el cliente dice que debe pagar una tarjeta de crédito de forma mensual y que quiere relacionarla, **es importante entender si ese pago por tarjeta de crédito ya tiene contemplados los gastos mensuales**. Si es así —es decir, si con esa tarjeta se pagan los gastos mensuales como el servicio del agua, de la luz—, **no se debe relacionar acá el servicio a la deuda, porque de lo contrario se duplica el monto: ya están relacionados anteriormente, solo que lo pagan a través de tarjeta de crédito**."*

| Situación | ¿Va en Servicio a la deuda? |
|---|---|
| La tarjeta es el **medio de pago** de gastos ya registrados | **NO** |
| La tarjeta financió un **consumo puntual no desglosado** en la hoja | **SÍ** |
| La tarjeta arrastra **saldo de años anteriores** | **SÍ** |

**[E]** *"Pero si la tarjeta de crédito fue utilizada con un fin puntual que no está discriminado en esta hoja de cálculo, entonces se debe colocar acá en dado caso."*

**[E] Frecuencia real:** *"**Usualmente, en la gran mayoría de mis clientes, este ítem no se coloca como gasto de tarjeta de crédito mensual.** En la gran mayoría. Pero va a depender mucho si el cliente trae una deuda de tarjeta de crédito de años anteriores; entonces seguramente acá sí se debe colocar el pago mensual."*

### 2.2 Cuenta AFC — ahorro vs. deuda

**[E]** *"**Acá hay que tener mucho cuidado con el ahorro de cuenta de FC versus el servicio a la deuda de crédito hipotecario a FC.** La diferencia está en que **el crédito hipotecario es la cuota que debe pagar el cliente mensual, y todo excedente que se pague es el ahorro que va a la cuenta de FC**."*

```
Cuota obligatoria del hipotecario  →  rubro SERVICIO A LA DEUDA (fila 59+)
Excedente sobre esa cuota          →  rubro AHORRO (fila 14+), "Ahorro Cuenta AFC"
```

**[E]** *"esta familia estaba entregando 4.9 millones de pesos adicionales mensuales **como ahorro** para inyectar a su crédito hipotecario. Entonces, **el excedente a la cuota mensual del crédito hipotecario va en ahorro**."*

> ⚠️ Esta distinción es la que después permite **liberar** esos 4,9 millones y reasignarlos en el plan. Si se registran como deuda, quedan atrapados.

### 2.3 Administración de inmuebles en renta

**[E]** *"Si hay rentas de apartamentos, entonces **exclusivamente acá [en *Otros*] se coloca administración de esa renta del local o del apartamento que se relacionó inicialmente**."*

El ingreso va en Ingresos; el gasto de administración va en **Otros**, no en Hogar.

---

## 3. DESGLOSE E IDENTIFICACIÓN

### 3.1 Ayuda de aseo — preguntar por las prestaciones

**[E]** *"también especial cuidado en ayuda de aseo, porque acá podemos colocar el valor de lo que se le paga a la persona que nos colabora con el aseo, **pero debemos especificar si acá está incluido ya el tema de pago de primas, intereses sobre cesantías y cesantías**. Si ya está incluido, pues se deja el valor mensualizado. **Si no está incluido, se deja solamente el del mes como ayuda de aseo, y en las anualidades se coloca prestaciones servicio de aseo.**"*

| Caso | Mensual | Anual |
|---|---|---|
| Ya incluye prestaciones | valor mensualizado | — |
| No las incluye | solo el mes | `Prestaciones servicio aseo` en Anualidades Fijas |

### 3.2 Pareja — nombre entre paréntesis

**[E]** *"recordemos, si es una pareja se coloca en la parte superior… la parte de la mujer y luego la del hombre, **dejando claro entre paréntesis el nombre del cliente**. Por ejemplo, si ella se llama Sofía, le colocamos `salud (Sofía)`. Si ya pasamos a los ítems de él y él se llama, por dar un ejemplo, Andrés, entonces colocamos `salud (Andrés)`. **Se maneja de forma conjunta, como para diferenciar lo de ella y lo de él.**"*

**Orden:** primero los de ella, después los de él.

### 3.3 Varios inmuebles — identificar por ubicación

**[E]** *"y especificar si es servicio público de qué lugar, si es diferente a donde vive. Entonces, si es finca, pues colocar finca. Si es apartamento en renta, colocar apartamento en renta. **Si tiene varios apartamentos, entonces colocar del apartamento 1 o del apartamento 2 o del apartamento 3, haciendo referencia a dónde se encuentra ubicado** —porque sea, por ejemplo, `/Mazurén` o `/Suba`, donde esté el apartamento—, **para tener claridad de cuánto es que se paga por servicios, cuánto se paga por administración de esos diferentes ítems**."*

### 3.4 Impuestos — discriminar por activo

**[E]** *"hay que tratar de clasificar si este cliente tiene diferentes activos —bien sea fincas, apartamentos o locales— **discriminar el impuesto predial correspondiente** a si es apartamento, si es finca o si son locales, y describir el local, para revisar puntualmente cuánto paga anualmente por cada ítem."*

### 3.5 Seguros — vencimiento y compañía en comentarios

**[E]** *"En comentarios siempre suelo colocar el seguro de riesgo: **cuándo vence, con qué compañía**, como para estar atento y poderle ayudar al cliente un mes antes y poderle avisar que está a punto de renovarse."*

### 3.6 Pasivos — lo más desglosado posible

**[E]** *"Luego de acá, y así fila por fila, rubro por rubro, **lo más desglosado posible**."*

---

## 4. CLASIFICACIÓN MENSUAL vs. ANUAL

### 4.1 La regla

**[E]** *"acá por ejemplo hay una donación proyecto unión, **pero esta donación no es mensual, es una donación anual; por esa razón va en anualidades fijas, no en mensuales**."*

**Si el pago ocurre una vez al año, va a Anualidades — aunque exista un rubro mensual con el mismo nombre.**

### 4.2 Seguros

**[E]** *"puede ser el SOAT, el seguro de riesgo, el seguro de arrendamiento si se paga anualizado. **Hay muchas personas que pagan también el seguro de salud anualizado o el seguro del carro anualizado. Si son pagos con temas de coberturas, los seguros se deben relacionar en este ítem** [anual]."*

| Rubro | Qué va |
|---|---|
| *Protecciones personales* (mensual, fila 40) | coberturas de pago mensual |
| *Seguros* (anual, fila 80) | coberturas de pago anualizado |

### 4.3 Los tres tipos de anualidad

| Rubro | Fila | Naturaleza |
|---|---|---|
| **Seguros** | 80 | coberturas |
| **Anualidades Fijas** | 86 | obligaciones anuales de monto conocido — mantenimiento, técnico-mecánica, matrículas, donaciones |
| **Anualidades Presupuestadas** | 91 | gasto anual **estimado** — ropa, viajes, regalos |
| **Impuestos** | 98 | predial, vehículo, renta |

**[E]** Sobre las presupuestadas: *"vamos a colocar ropa de forma anualizada, en promedio cuánto se gasta la familia o la persona. En viajes, cuánto se han venido gastando, **se gastaron el año pasado en viajes**. Regalos de cumpleaños y navidad."*

---

## 5. LA REGLA DE LAS ANUALIDADES

**[E]** *"lo que debemos revisar es **primero, sí o sí, separar el valor de las anualidades. Eso es algo que es súper importante tener presente.**"*

### 5.1 La fórmula y su signo

```
PROVISIÓN MENSUAL (fila 105)  =  SI(fila104>0; (fila104 − fila77)/12; "")
                                          anualidades − ingresos anuales
```

**⚠️ [CORR]** El audio la describe al revés (*"coge los ingresos C77, le resta las anualidades C104"*). **La fórmula real resta ingresos a las anualidades.** Manda la pantalla.

Amanda misma reconcilia el signo al leerlo: *"**Aparece negativo, pero en realidad es algo que estaría quedando de forma mensualizada.** Porque los ingresos anuales superan los gastos anuales, y lo que queda se divide en 12."*

| Resultado | Significado | Acción |
|---|---|---|
| **Negativo** | los ingresos anuales cubren los gastos anuales y **sobra** | **no hay que provisionar** |
| **Positivo** | **falta dinero** | ese es el importe **mensual a provisionar** |

**[V] Comprobaciones:**
- (36.617.989 − 47.846.500)/12 = **−935.709** ✓ (col. C)
- (46.617.989 − 47.846.500)/12 = **−102.376** ✓ (col. D)
- (49.517.989 − 47.846.500)/12 = **+139.291** ✓ (col. F)

### 5.2 Dónde se resuelve, según el signo

| Signo de la 105 | Bolsa | Cómo |
|---|---|---|
| **Negativo** (sobra) | **Capital Disponible** | **[E]** *"podremos coger en el capital disponible, separar las anualidades para ser cubiertas con los ingresos anuales"* → estrategia 1 (fila 56): fuente = bono anual, objetivo = Anualidades, monto = `D104` |
| **Positivo** (falta) | **Capacidad de Ahorro Mensual** | **[E]** *"se deberá tener en cuenta esta provisión mensual dentro de la estrategia del plan de acción **en la parte del recurso mensual**"* |

**[E]** *"si el valor de sus ingresos anuales supera sus gastos anuales, **debe salir de esas anualidades los gastos**. En dado caso que… no alcance para cubrir los gastos anuales, o no haya ingresos anuales para cubrir los gastos anuales, entonces se deberá tener en cuenta esta provisión mensual…"*

### 5.3 De dónde sale la provisión cuando hace falta

**[E]** *"debería salir de la parte mensual; **pero pues como acá hay un excedente de 12.4 millones de pesos, de ahí puede salir**."*

---

## 6. GASTOS BÁSICOS MENSUALES (para el fondo de emergencia)

### 6.1 El escenario mental

**[E]** *"voy a mirar cuáles son los gastos más importantes que tiene la familia de forma mensual **en caso de una incapacidad**."*

No es el gasto total: es **lo que hay que seguir pagando aunque el ingreso se detenga**.

### 6.2 Criterio rubro por rubro [E]

| Rubro | Decisión | Cita |
|---|---|---|
| **Ahorro** | **excluir** **[I]** | no es gasto de subsistencia |
| **Transporte** | **completo** | *"¿tiene que gastar en transporte el mismo valor? Sí, voy a coger y sumo ese valor mensual"* |
| **Gastos personales** | **parcial** — celular y cuidado personal | *"pues digamos que lo más importante será celular, para este caso, cuidado personal, y ya"* |
| **Hogar** | **completo** | *"si uno está incapacitado, seguramente las plataformas las va a necesitar, todo lo demás va a seguir… mercados, servicios públicos tendrá que pagarse, mascotas, ayuda de aseo, almuerzos, administración… **voy a coger el ítem de hogar completo**"* |
| **Entretenimiento / Salidas** | **la mitad** | *"si uno está incapacitado seguramente no va a salir a gastar lo mismo; **uno podría llegar a dejar la mitad**"* → 1.000.000 de 2.000.000 |
| **Protecciones personales** | **[ND]** | no se menciona |
| **Otros descuentos de nómina** | **excluir**, salvo la seguridad social del cónyuge | *"pues es algo que se pagará dependiendo si se recibe el ingreso, entonces pues por acá no; **pero sí o sí se tendrá que pagar la seguridad social de ella, porque ese sí no está relacionado como tal**"* |
| **Educación** | **completo** | *"se pagará los gastos de educación de los hijos, **sí o sí, así la persona esté incapacitada**"* |
| **Financieros** | **[ND]** | no se menciona |
| **Servicio a la deuda** | **completo** | *"las deudas que tiene el cliente **se deberán pagar así esté incapacitada**"* |
| **Otros** | **[ND]** | no se menciona |

**[V]** Resultado del ejemplo: **P7 = 18.781.821**

### 6.3 Componente anual [V — fórmula leída]

```
P8 = =+(D80+D86+D92+D94+D98)/12
```

| Incluye | Excluye |
|---|---|
| **D80** Seguros (total) | |
| **D86** Anualidades Fijas (total) | |
| **D92** Ropa | **D93 Viajes** ⛔ |
| **D94** Regalos de Cumpleaños y Navidad | |
| **D98** Impuestos (total) | |

**[E]** *"vamos a coger el valor total de los seguros. Luego vamos a colocar el valor total de las anualidades fijas. ¿Hay algo que se deba quitar? No, todo tiene que contarse… **También vamos a contar el valor de las anualidades presupuestadas sin tener en cuenta los viajes.** Entonces vamos a colocar ropa más regalos de cumpleaños más todos los impuestos, **porque eso sí o sí hay que pagarlos**."*

> **Nota:** no se usa el subtotal D91 (Anualidades Presupuestadas), sino sus ítems individuales — precisamente para poder excluir Viajes.

### 6.4 Total

```
P9 = P7 + P8   →   Plan de Acción!E88
```

**[V]** 18.781.821 + 2.718.166 = **21.499.987**

### 6.5 Meses de cobertura

```
Plan de Acción!E89 = E87 / E88
```

**[E]** *"A ese total del fondo de emergencias lo vamos a dividir por el gasto básico mensual del hogar para entender cuántos meses le va a cubrir."*
**[V]** 445.902.729,49 / 21.499.987,19 = **20,74 meses**

**[ND]** No se declara un mínimo aceptable de meses.

---

## 7. USO DEL COLOR

| Color | Significado | Cita |
|---|---|---|
| **Amarillo** | valor modificado, recomendación, o **palanca reservada** | *"todo lo que quiero mejorar lo coloco de amarillito y doy una recomendación de bajar o subir o a tener en cuenta"* · *"lo iluminé en amarillo en dado caso que tocara hacer algún ajuste"* |
| **Verde** | dato variable que se promedia · punto de inicio de una intervención · años de carrera | *"acá los verdecitos son como los datos más importantes a tener en cuenta que se están moviendo"* · *"lo colocó como en casillita en verde para saber en dónde empecé a colocar el ajuste"* |
| **Azul claro** | subtotal por rubro (calculado) | *"las casillas azules de cada uno de estos gastos puntuales va a ir sumando los valores totales por cada ítem"* |
| **Azul oscuro** | encabezado o total general | |
| **Rojo** | banda de pasivos · valores de interés · prioridad de objetivos | |
| **Triángulo en esquina** | comentario de celda | |

**[E] El propósito del amarillo:** *"lo coloqué en amarillito **para que el cliente pueda identificar los cambios que se presentaron entre el presupuesto que se trabajó con el cliente inicialmente y el que voy a empezar a trabajar para el plan de acción**."*

---

## 8. CRITERIO PARA RECORTAR

**[E]** *"si veo un ítem que está **supremamente elevado** y está en 1.500.000, pues seguramente voy a, dependiendo de la situación del cliente, voy a bajarle un poquito. Y lo dejo con color amarillo para hacer una recomendación."*

**[E]** *"si veo que el concepto de almuerzos es muy elevado, acá puedo sugerir bajarle, y **esto va a depender mucho también de la calidad de vida del cliente**."*

**[E] La única heurística declarada:**
> *"Usualmente miro el concepto de mercado, el concepto de almuerzos, y al sumar los digo esto mensualmente. Si es una persona, está elevado… dependiendo de lo que gane. Pues si es una persona, más o menos en mercado se está yendo 2 millones, 3 millones — depende, **depende de la calidad de vida**, pero **si no es mayor cosa lo dejo quietico**."*

**[AMB] No hay umbrales numéricos.** Juicio contextual sobre tres variables: ingreso, tamaño del hogar, calidad de vida declarada.

**Test antes de recortar:**
- [ ] ¿Es desproporcionado respecto al ingreso y al tamaño del hogar?
- [ ] ¿La reunión de sensibilización lo justifica o lo protege?
- [ ] ¿A qué objetivo concreto va el dinero liberado?
- [ ] ¿Es compatible con la calidad de vida declarada?

Si alguna respuesta es dudosa: **no recortes; marca en amarillo como palanca y escala.**

---

## 9. INGRESOS ANUALES Y RETENCIÓN

**[E]** *"idealmente colocar acá el dato que da el cliente. Sería importante entender **cuánto es lo que le cobran por retención en la fuente y descontarlo de una vez**; pero si no se tiene, al menos relacionar el monto que aparece en su desprendible de nómina."*

**[E]** *"ajustamos ese valor si es del caso; si no, **si ya tiene por descontado la retención en la fuente, dejamos el mismo valor. De lo contrario, se reajusta.**"*

| Caso | Acción |
|---|---|
| El valor **ya viene neto** de retención | dejarlo tal cual |
| El valor viene **bruto** y se conoce la retención | descontarla |
| El valor viene bruto y **no se conoce** la retención | registrar el bruto + **comentario advirtiendo que está sin descontar** |

**[AMB]** En el ejemplo la retención era del **15 %** y *"ahí vemos la fórmula"*, pero **la fórmula no fue legible**. Valida el criterio con Amanda antes de aplicar un porcentaje.

---

## 10. RESUMEN DE SUPUESTOS DEL MÉTODO

Todos conservadores. Úsalos tal cual; si te desvías, decláralo.

| Supuesto | Valor | Fuente |
|---|---|---|
| Crecimiento proyectado de la TRM | **4,5 %** anual | [E] *"de una forma de proyección muy conservadora del 4.5 %"* |
| Crecimiento histórico de la TRM (referencia) | 6,15 % anual · 81 % acumulado 2010-2020 | [V] |
| **TRM para el plan y el presupuesto** | **TRM del día + 200 COP** | **[E] audio** — corrige el "+200 a 300" del video |
| **TRM en `PROYECTADO TRM`** | **TRM del día, exacta** | **[E] audio** |
| Crecimiento del costo de universidad | **+9 %** anual | [V] |
| Edad de ingreso a la universidad | **17 años** | [E] |
| Duración de la carrera | **5 años** | [E] |
| Tasa de rendimiento del ahorro educativo | **4,5 %** | [V] |
| **Liquidación por despido** | **sin primas y sin vacaciones — solo lo básico** | **[E] audio** |
| Meses del año escolar | **11** | [E] |
| Corto plazo (pasivos) | **1 a 5 años** | [E] |
| Salidas en escenario de incapacidad | **50 %** | [E] |
| Escenario del fondo de emergencia | **despido sin justa causa** | [E] |
| **Meses del fondo de emergencia — sector salud** | **1 a 3 meses** | **[E] audio** |
| **Meses del fondo de emergencia — otros sectores** | **mínimo 6 meses** | **[E] audio** |
| **Edad de cotización pensional** | **62 años** | **[E] audio** — [AMB] si el cliente es mujer, señalar |
| Proyección salarial | **sin incrementos** | [E] |

---

## 11. REGLAS NUEVAS DEL AUDIO DE RESPUESTAS

### 11.1 Ingresos por renta: marcar neto o bruto

**[E]** *"si tiene un ingreso adicional por rentas de apartamento, yo coloco el valor de la renta y **usualmente especifico si es un ingreso neto o si es un ingreso bruto**."*

Rotula en la columna B: `(neto)` o `(bruto)`. Si es bruto, sus costos (administración, seguro, servicios si está desocupado) van a ***Otros***.

### 11.2 El rubro *Otros* — contenido cerrado

**[E]** *"en el ítem de otros… desgloso la administración de ese apartamento —el que tiene en renta—; cuánto paga por administración, cuánto paga **si paga algún seguro mensual**, **si de repente no está alquilado y tiene que pagar los servicios públicos**. En ese ítem de otros coloco **donaciones**, coloco **ayudas familiares**."*

### 11.3 Objetivos: clasificación por horizonte

**[E]** *"reviso cuál es el objetivo **a corto, a mediano, a largo plazo**."*

### 11.4 `Analizar Estrategia` en dos tiempos

**[E]** *"Si el cliente no sabe, yo coloco analizar estrategia **y reviso cuánto podrías llegar a necesitar a futuro teniendo en cuenta las observaciones que da el cliente**."*

1. `Analizar Estrategia` en la celda — declara que el cliente no lo dio
2. Estimación en COMENTARIOS, en amarillo, con su criterio — **solo si hay base**

### 11.5 Activos productivos: umbral suavizado

**[E]** *"con rentabilidad superior a la inflación **o al menos cercana a la inflación**."*
Basta con que la **naturaleza** del activo sea generar rendimiento.

### 11.6 Semanas cotizadas: en ambas hojas

**[E]** *"esas semanas cotizadas **van en los dos**."*
`INFORMACION Seg soc`!H14 **y** COMENTARIO de `Info Patrimonio`.

### 11.7 Las cuatro deducciones tributarias

**[E][V]** Dependientes · Intereses de vivienda · **AFC + Pensión Voluntaria** · Medicina prepagada.
*(Amanda dice "cuatro"; la columna Z de `Desprendibles` confirma que AFC y PV son una sola categoría.)*

### 11.8 Orden de prioridad del plan

**[E]** *"lo primero que recomiendo son las coberturas, el tema de las anualidades, la provisión para el pago de las anualidades, y luego viene toda la parte de inversiones."*

| Capacidad positiva | Capacidad negativa |
|---|---|
| 1. Coberturas | 1. **Pago de deudas** |
| 2. Anualidades + provisión | 2. Anualidades |
| 3. Fondo de emergencia | 3. Fondo mínimo |
| 4. Inversiones | — *nada más* — |

### 11.9 Entregable final: PDF, no Excel

**[E]** *"mi Excel me sirve para hacer la parte del insumo… **pero luego lo entrego en un archivo en PDF**; lo paso a un PowerPoint… y luego se lo paso a un PDF."*

El agente entrega **Excel + informe**. La conversión la hace Amanda.

### 11.10 AXIA y UNITED FINANCIAL CONSULTANTS.

**[E]** *"**No vas a tener en cuenta esos dos nombres**… una es el bróker y la otra es una agencia, pero **no tengo que mencionarlas**."*

**No aparecen en el plan ni se mencionan al cliente.**

### 11.11 Las 8 hojas son diagnóstico previo

**[E]** *"son una herramienta que yo utilizo **previo al plan de acción**… un **diagnóstico financiero**."* · *"con estas cuatro hojas… **está más que suficiente**."*

**No las diligencies.**
