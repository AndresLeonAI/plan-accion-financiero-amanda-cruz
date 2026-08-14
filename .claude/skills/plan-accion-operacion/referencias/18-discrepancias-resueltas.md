# 18 — Discrepancias resueltas

Registro de todas las contradicciones detectadas entre fuentes, con su análisis y la **regla final que debes aplicar**.

**Jerarquía de evidencia usada para resolverlas:**

| # | Tipo de evidencia | Peso |
|---|---|---|
| 1 | **Metodología explícita de Amanda** (audio de respuestas) | máximo — es la regla declarada |
| 2 | **Implementación real** en la plantilla (fórmula leída) | alto — es lo que efectivamente ocurre |
| 3 | **Evidencia visual** (valores en pantalla) | alto — verificable aritméticamente |
| 4 | **Explicación verbal** durante la operación (video) | medio — sujeta a lapsus |
| 5 | **Inferencia** | bajo — se marca como tal |
| 6 | **Desconocido** | se marca `[ND]` |

> **Cuando 1 y 2 chocan, gana 1** (Amanda corrige su propia plantilla).
> **Cuando 2 y 4 chocan, gana 2** (la fórmula manda sobre la narración).

---

## D-01 · El signo de la PROVISIÓN MENSUAL

**Fuente A — Explicación verbal (video, 29:03):**
> *"coge el valor de los ingresos, es decir en la celda C77, le resta el total de las anualidades de la celda C104, y a ese resultado lo divide en 12."*

**Fuente B — Implementación real (fórmula leída en `Presupuesto`!C105):**
```
=SI(C104>0;(C104-C77)/12;"")
```
→ **anualidades menos ingresos anuales**, exactamente al revés.

### Análisis
La fórmula es la inversa de lo narrado. Amanda **se corrige a sí misma** unos minutos después, al leer el resultado en pantalla:
> *"Aparece negativo, **pero en realidad es algo que estaría quedando de forma mensualizada**. Porque los ingresos anuales superan los gastos anuales, y lo que queda se divide en 12."*

Verificación aritmética en las cuatro columnas del ejemplo:

| Col | (104 − 77)/12 | Valor en pantalla |
|---|---|---|
| C | (36.617.989 − 47.846.500)/12 | **−935.709** ✓ |
| D | (46.617.989 − 47.846.500)/12 | **−102.376** ✓ |
| F | (49.517.989 − 47.846.500)/12 | **+139.291** ✓ |

### Resolución
**Gana la fórmula.** Fue un lapsus verbal, no un cambio de método.

### ⚖️ REGLA FINAL
```
PROVISIÓN MENSUAL = (TOTAL ANUALIDADES − TOTAL INGRESOS ANUALES) / 12
```
| Resultado | Significado | Acción |
|---|---|---|
| **NEGATIVO** | los ingresos anuales cubren y sobra | **no provisionar** |
| **POSITIVO** | falta dinero | **provisionar ese importe mensual** |

**Impacto si se equivoca:** invierte la arquitectura del plan — se provisionaría cuando sobra y no cuando falta. **Es la discrepancia más grave del proyecto.**

---

## D-02 · Las tres TRM del archivo

**Fuente A — Evidencia visual (plantilla del video):**
| Hoja | Valor |
|---|---|
| `ANALISIS`!D7 y `PROYECTADO TRM` | **3.250** |
| `UNIVERSIDAD` | **3.300** |
| `Plan de Acción`!H15 | **3.500** |

**Fuente B — Metodología explícita (audio, 05:53):**
> *"**Es cierto, solamente se debería utilizar una sola TRM**, solo que para el caso que te compartí, **se me olvidó cambiarlas**."*

### Análisis
No era una regla con matices: **era un descuido del archivo de ejemplo**. Amanda lo reconoce y fija la regla correcta.

### Resolución
**Gana la metodología explícita.** El archivo de ejemplo está mal en este punto.

### ⚖️ REGLA FINAL
| Hoja | TRM |
|---|---|
| `PROYECTADO TRM`, fila del año en curso | **TRM del día, exacta** |
| **Todo lo demás** (plan de acción, presupuesto, universidad, análisis) | **TRM del día + 200 COP** |

**[E]** *"para el plan de acción y el desarrollo del presupuesto, se debe colocar una TRM del día **más 200 pesos más adicional**. Esto solamente por tener presente que la TRM puede llegar a crecer."*

> **Control de calidad:** en un archivo correcto solo deben existir **dos** valores de TRM. Tres = error.

---

## D-03 · El incremento de la TRM: ¿+200 o +200 a 300?

**Fuente A — Explicación verbal (video, 61:32):**
> *"coloqué una TRM un poquito más elevada de la que está, **unos 200 pesos más, elevado 300 pesos más** de la TRM actual."*

**Fuente B — Metodología explícita (audio, 06:46):**
> *"se debe colocar una TRM del día **más 200 pesos más adicional**."*

### Análisis
En el video Amanda titubea entre 200 y 300 mientras trabaja. En el audio, respondiendo una pregunta directa, fija **200**.
Evidencia visual: TRM real 3.250 → usada 3.500 = **+250** (punto medio del titubeo).

### Resolución
**Gana la metodología explícita.** La respuesta deliberada pesa más que el titubeo durante la operación.

### ⚖️ REGLA FINAL
```
Plan de Acción!H15 = TRM del día + 200 COP
```
**[CORR]** Corrige la documentación previa, que decía "+200 a 300".

---

## D-04 · El reparto de la prima en la comparativa

**Fuente A — Explicación verbal (video, 112:15):**
> *"acá de **1.500 para inversión pura**, 250 para cobertura de inversión más acumulación para él y 250 de inversión con acumulación para ella."*

**Fuente B — Evidencia visual (`ANALISIS` fila 30):**
| | E (Esc. 1) | F | G | H | Total (fila 31) |
|---|---|---|---|---|---|
| Prima Mensual USD | 1.500 | **1.000** | 250 | 250 | **1.500** |

### Análisis
Si el reparto fuera 1.500 + 250 + 250, el escenario 2 costaría **2.000 USD/mes** frente a los 1.500 del escenario 1, y **la comparación no significaría nada**. La fila 31 confirma que los tres escenarios suman exactamente **1.500**.

### Resolución
**Gana la evidencia visual.** Lapsus verbal.

### ⚖️ REGLA FINAL
```
Los tres escenarios se comparan a PRIMA TOTAL IDÉNTICA.
Escenario 1:  1.500  (todo a inversión pura)
Escenario 2:  1.000 + 250 + 250 = 1.500
Escenario 3:  1.000 + 250 + 250 = 1.500
```
**Control de calidad:** si la fila 31 no es igual en las tres columnas, la comparativa está mal construida.

---

## D-05 · La celda de la liquidación

**Fuente A — Explicación verbal (video, 83:31):**
> *"la liquidación, que la suma entre la indemnización más el salario, es decir, la suma de la celda **P27** más la suma de la celda B28."*

**Fuente B — Evidencia visual + fórmula de enlace:**
- En pantalla: `A27/B27` Indemnización · `A28/B28` Salario · `A29/B29` Liquidación
- `Plan de Acción`!E86 = `=+'Calculadora liquidacion Andrés'!**B29**`
- Aritmética: 65.979.738 + 12.231.324 = **78.211.062** = B29 ✓

### Análisis
"P27" no existe en esa hoja. La fórmula de enlace apunta inequívocamente a **B29**.

### Resolución
**Gana la evidencia visual.**

### ⚖️ REGLA FINAL
```
B29 (Liquidación) = B27 (Indemnización) + B28 (Salario)
Plan de Acción!E86 = 'Calculadora liquidacion «Cliente»'!B29
```

---

## D-06 · Las filas de `Desprendibles de nom.`

**Fuente A — Explicación verbal (video, 40:08):**
> *"en total de egresos en esta celda B50 veo el concepto y en la columna **C50** me está sumando… luego vemos en la celda **P52** ingresos menos egresos, y en la celda **C51** vemos lo que realmente…"*

**Fuente B — Evidencia visual:**
- `B50` = TOTAL EGRESOS ✓
- `B52` = INGRESOS − EGRESOS *(amarilla)*
- `B53` = Beneficio IBC por excedido del 40 % *(verde)*
- **No existe fila 51 con ese contenido**

### Resolución
**Gana la evidencia visual.** Confusión de referencias al hablar.

### ⚖️ REGLA FINAL
`B50` total egresos · **`B52` ingresos − egresos** · `B53` beneficio IBC.
El control de realidad (*"que sea acorde con lo que recibió"*) se hace contra **B52**.

---

## D-07 · La tasa periódica: ¿celda o valor?

**Fuente A — Explicación verbal (video, 94:24):**
> *"me convierte la tasa efectiva anual a la tasa periódica en la celda C, **1.326** para este ejemplo."*

**Fuente B — Evidencia visual:**
- `C1326` es **la dirección de la celda**
- Su valor es **0,94 %**
- Fórmula: `=SI.ERROR(TASA.NOMINAL(C1325;12)/12;"CAMBIAR TASA")`

### Resolución
Ambigüedad de lectura, no contradicción. **"1.326" era la celda, no un valor.**

### ⚖️ REGLA FINAL
`C1326` contiene la **tasa periódica mensual**, derivada de la EA de `C1325`. Si muestra `"CAMBIAR TASA"`, la tasa de entrada es inválida.

---

## D-08 · Las cuatro deducciones que se enumeran como cinco

**Fuente A — Metodología explícita (audio, 08:49):**
> *"las deducciones… **son cuatro ítems**: dependientes, intereses de vivienda en un año, si hace aportes a pensiones voluntarias, AFC si tiene, el tema de la medicina prepagada."*
→ dice **cuatro**, enumera **cinco**.

**Fuente B — Evidencia visual (`Desprendibles de nom.`, columna Z):**
```
Interes de Vivienda
AFC, PV              ← AFC y Pensión Voluntaria en UNA sola celda
Dependientes
Medi. Prepagada
```
→ exactamente **cuatro** anotaciones.

### Análisis
La plantilla resuelve la aparente contradicción: **AFC y Pensión Voluntaria son una sola categoría**, agrupadas en la misma celda.

> Además, esto **cierra un `[ND]` de la auditoría anterior**: esas anotaciones sueltas nunca se habían explicado.

### Resolución
**Las dos fuentes concuerdan.** El "cuatro" de Amanda es correcto.

### ⚖️ REGLA FINAL
```
1. Dependientes
2. Intereses de vivienda (anuales)
3. AFC + Pensión Voluntaria
4. Medicina prepagada
```

---

## D-09 · La naturaleza de la reunión de sensibilización

**Fuente A — Supuesto del proyecto:**
La sensibilización aporta el contexto humano y financiero inicial; puede contradecir la reunión de datos.

**Fuente B — Metodología explícita (audio, 00:10):**
> *"para esa reunión de sensibilización, es la primera reunión con el cliente **donde le muestro cómo desarrollo la asesoría**."*
> *"**no tienen por qué contradecirse**; todos los datos que yo voy a preguntar en el levantamiento de información son todos los datos que me van a servir para el desarrollo del plan de acción."*

### Análisis
La sensibilización es **comercial y de encuadre**, no de captura. **Todo el dato —incluido el contexto humano— sale del levantamiento** y del archivo Word.

### Resolución
**Gana la metodología explícita.** El supuesto del proyecto era incorrecto.

### ⚖️ REGLA FINAL
- **Sensibilización:** tono y expectativas. **Nunca fuente de cifras.**
- **Levantamiento de información:** única fuente de datos.
- **Archivo Word:** contexto cualitativo y detalles.
- La jerarquía de fuentes se mantiene como red de seguridad, pero el conflicto esperable es **documento oficial vs. declaración verbal**, no sensibilización vs. datos.

---

## D-10 · Las ocho hojas sin instrucción

**Fuente A — Auditoría anterior:**
8 de 19 hojas nunca se abren → "42 % de la plantilla sin instrucción", marcado `[ND]`.

**Fuente B — Metodología explícita (audio, 11:02):**
> *"esas hojas de cálculo son **una herramienta que yo utilizo previo al plan de acción**, para mostrarle a mi cliente **cómo se encuentra en las cinco áreas de las finanzas**… un **diagnóstico financiero**."*
> *"con estas cuatro hojas de insumo para hacer el plan de acción **está más que suficiente**."*

### Análisis
No eran un hueco: son **una fase anterior del servicio**, fuera del alcance del plan de acción.
**[V]** *"las cinco áreas de las finanzas"* = los cinco niveles de la pirámide verificados en el video.

### Resolución
**Deja de ser un `[ND]` y pasa a ser una frontera definida.**

### ⚖️ REGLA FINAL
Las 8 hojas son **diagnóstico previo**. **No las diligencies.** Si se requieren, escala.
`INICIO` · `Patrimonio` · `Incapacidad` · `Proyeccion Retiro` · `DISTRIBUCION ACTIVOS` · `Resumen Deudas` · `Flujo de Efectivo` · `Grafico Presupuesto`

---

## D-11 · Dónde van las semanas cotizadas

**Fuente A — Explicación verbal (video, 02:12):**
> *"se debe colocarle al lado, **en lo posible en la H14**, colocar el número de semanas."*

**Fuente B — Evidencia visual:**
`H14` está **vacía**; las semanas del ejemplo (`731 semanas`, `122 semanas`) figuran en el COMENTARIO de `Info Patrimonio`.

**Fuente C — Metodología explícita (audio, 11:44):**
> *"esas semanas cotizadas **van en los dos**: tanto en la primera hoja de seguridad social como en la del patrimonio."*

### Resolución
**Gana la metodología explícita.** La H14 vacía era un descuido del ejemplo.

### ⚖️ REGLA FINAL
Registrar en **ambos** sitios: `INFORMACION Seg soc`!**H14** y COMENTARIO de la fila de pensión obligatoria en `Info Patrimonio`.
Alimentan la proyección de mesada pensional.

---

## D-12 · La liquidación: ¿solo sin vacaciones o también sin primas?

**Fuente A — Explicación verbal (video, 82:45):**
> *"Si me sale vacaciones acumuladas, le coloco en la celda F8, **que se las tomo completas**."*
→ solo menciona vacaciones.

**Fuente B — Metodología explícita (audio, 13:24):**
> *"le muestro a mi cliente **sin primas, sin vacaciones, sino con lo básico**, cuánto podría ser esa liquidación."*

### Análisis
No hay contradicción: el audio **amplía** lo que el video mostraba parcialmente.

### Resolución
**Se consolidan ambas.**

### ⚖️ REGLA FINAL
```
La liquidación se calcula sobre LO BÁSICO: sin primas y sin vacaciones.
```
Supuesto deliberadamente conservador: subestima el resultado para no inflar el fondo de emergencia.

---

## D-13 · Activos productivos: ¿por encima de la inflación?

**Fuente A — Explicación verbal (video, 32:28):**
> *"nos generan rentabilidad **en lo posible superior a la inflación, pero a veces no es suficiente**. Entonces, de igual forma, **antes de que nos genere algo de rentabilidad, lo vamos a colocar acá**."*

**Fuente B — Metodología explícita (audio, 04:44):**
> *"todo lo que genera rentabilidad… llámese cuentas de ahorros, **pero con rentabilidad superior a la inflación o al menos cercana a la inflación**."*

### Análisis
Ambas apuntan a lo mismo: el criterio es la **naturaleza** del activo, no su desempeño actual. El audio añade el matiz *"o al menos cercana"*.

### Resolución
**Se consolidan.**

### ⚖️ REGLA FINAL
Es **productivo** todo activo cuya naturaleza sea generar rendimiento, aunque hoy no supere la inflación. Una cuenta de ahorros **con rendimiento cercano a la inflación** es productiva; una cuenta corriente sin rendimiento es **líquida**.

---

## D-14 · Datos inconsistentes en el archivo de ejemplo

**Hallazgo:** en el archivo usado durante el entrenamiento, **el nombre del titular difiere entre hojas**. `INFORMACION Seg soc` registra un nombre; el título del `Plan de Acción` usa otro; `Info Patrimonio` y `ANALISIS` usan un tercero; y la narración menciona un cuarto como ejemplo genérico.

### Análisis
**Ruido del archivo de demostración**, no del método. La plantilla se reutilizó sin homogeneizar los nombres entre hojas.

### Resolución
Irrelevante para el método. **Muy relevante como control de calidad**: demuestra lo fácil que es que sobrevivan datos de un archivo anterior.

### ⚖️ REGLA FINAL
**Control de calidad obligatorio antes de entregar:**

Verificar que **ningún dato de un archivo anterior sobreviva** en el del cliente real:
- Nombres del titular y del cónyuge — **coherentes en todas las hojas**
- Nombres y edades de los hijos
- Nombres de hojas que incluyan un nombre propio (p. ej. `Calculadora liquidacion «Cliente»`)
- Entidades bancarias y de inversión
- Fechas y valores

**Recorre las hojas una por una buscando nombres propios.** Si un nombre aparece en una hoja y otro distinto en otra, hay contaminación.

---

## D-15 · El bloque de seguridad social del cónyuge

**Fuente A — Evidencia visual:** el segundo bloque duplica etiquetas ("Nombre", "Fecha de Nacimiento") y le faltan EPS, PREPAGADA, ARL y FONDO DE CESANTIAS.

**Fuente B — Metodología explícita (audio, 21:36):**
> *"solamente en la plantilla dejé cuánto más o menos se estaría pagando la persona. **Pero si tú ves algo por ajustar, te agradezco los comentarios.**"*

### Análisis
Es una **simplificación intencional**, no un defecto: el bloque solo pretende registrar el aporte estimado del cónyuge. Amanda **delega la mejora**.

### Resolución
**Parcialmente resuelta.**

### ⚖️ REGLA FINAL
- Usar el bloque **tal como está**
- **No rediseñarlo** por cuenta propia
- Lo que no tenga casilla → `INFORMACION Seg soc`!**E38** (celda de ampliación)
- **Mejora sugerida a Amanda, no aplicada:** replicar EPS / PREPAGADA / ARL / FONDO DE CESANTIAS y eliminar las etiquetas duplicadas

---

## D-16 · El 15 % de retención

**Fuente A — Explicación verbal (video, 52:38):**
> *"ya traía el valor de la retención por descontado, **que es del 15 %**, y ahí vemos la fórmula."*

**Fuente B — Evidencia visual:** ninguna fórmula legible en esa celda.

**Fuente C — Metodología explícita (audio, 10:33):**
> *"Esto es lo que te estaba explicando… **te cuento cómo yo lo hago entrando a un link puntual** para revisión de esta proyección tributaria."*

### Análisis
El 15 % **no sale de una fórmula de la plantilla**: es el resultado de la herramienta tributaria externa aplicada a **ese** cliente. Eso explica por qué no había fórmula que leer.

### Resolución
**Pendiente de video.** Pero el mecanismo queda claro.

### ⚖️ REGLA FINAL
- Ingreso anual **ya neto** → registrar tal cual
- **Bruto** con retención conocida → aplicarla y documentarla en comentario
- **Bruto** sin retención conocida → registrar bruto + comentario + **escalar**
- ⛔ **NUNCA aplicar 15 % por defecto.** Era el caso de un cliente, no una constante.

---

# Resumen

| ID | Discrepancia | Gana | Gravedad |
|---|---|---|---|
| **D-01** | Signo de la provisión mensual | fórmula | **ALTA** |
| **D-02** | Tres TRM en el archivo | metodología | **ALTA** |
| **D-03** | +200 vs. +200-300 | metodología | Media |
| **D-04** | Reparto de la prima | evidencia visual | **ALTA** |
| **D-05** | Celda de la liquidación | evidencia visual | Media |
| **D-06** | Filas de Desprendibles | evidencia visual | Baja |
| **D-07** | Tasa periódica: celda vs. valor | evidencia visual | Baja |
| **D-08** | Cuatro deducciones vs. cinco | ambas concuerdan | Media |
| **D-09** | Naturaleza de la sensibilización | metodología | **ALTA** |
| **D-10** | Las ocho hojas | metodología | Media |
| **D-11** | Semanas cotizadas | metodología | Media |
| **D-12** | Liquidación sin primas | ambas se consolidan | Media |
| **D-13** | Activos productivos e inflación | ambas se consolidan | Baja |
| **D-14** | Datos del ejemplo | ruido del archivo | Baja *(pero es control de QA)* |
| **D-15** | Bloque del cónyuge | metodología | Baja |
| **D-16** | El 15 % de retención | pendiente | Media |

**16 discrepancias · 15 resueltas · 1 pendiente de material adicional.**

> **Ninguna quedó oculta.** Si encuentras una nueva, documéntala con este mismo formato y **escálala**.
