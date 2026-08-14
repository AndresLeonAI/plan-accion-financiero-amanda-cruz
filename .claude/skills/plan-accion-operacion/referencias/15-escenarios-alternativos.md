# 15 — Escenarios alternativos (Fase 17)

Las columnas E, F, G… del `Presupuesto` son **escenarios "¿y si…?"** que responden preguntas del cliente.

---

## Principio: los escenarios nacen de preguntas del cliente

**[E]** *"planteé una propuesta B sin la consultoría **porque el cliente dijo: bueno, ¿y qué pasa si ya no trabajo más la consultoría? ¿cómo se mueve mi presupuesto?**"*

**No inventes escenarios.** Se modelan las incertidumbres que el cliente declaró, no las que a ti te parezcan interesantes.

**[E]** El origen está en la conversación: *"por supuesto hay que considerar muchos ítems que alrededor del presupuesto el cliente va a mencionar como necesarios"* · *"después de haber hecho un plan de acción puede que el cliente cambie y diga: ay, se me olvidó contarte que… **Entonces eso cambia ya el escenario, pero uno puede estar en la capacidad de hacer los ajustes**."*

---

## Cómo se nombra un escenario

**[V]** La convención observada:

| Col | Nombre literal |
|---|---|
| C | **REGULAR** |
| D | **PROPUESTA (A) Organización Actual** |
| E | **PROPUESTA (B) sin consultoria** |
| F | **PROPUESTA (C) sin consultoria y con Apto. Nvo.** |
| G | **PROPUESTA (D) … 18 meses** |

> Letra secuencial + **descripción explícita de la condición**. Nunca "Escenario 2" a secas: el nombre debe decir qué cambia.

**[E]** *"Está la columna D, la columna E, la columna F y la columna G. Esto es en general la propuesta."*
→ **El número de columnas es variable.** Se abren tantas como escenarios pida el cliente.

---

## Los tres tipos de escenario observados

### Tipo 1 — Pérdida de una fuente de ingreso (columna E)

**Pregunta del cliente:** *"¿qué pasa si ya no trabajo más la consultoría?"*

**Qué se toca [V]:**
- Se elimina el ingreso: `E9` Consultoría → vacío
- **Se activan las palancas de ajuste que quedaron marcadas en amarillo:** `E38` Salidas 2.000.000 → **1.500.000**
- El resto se replica de D

**[E]** *"entonces acá muestro qué pasa: tocaría **bajarle a las salidas**, hacer los demás ajustes que ya se tenían, y pues ya no se logra tener este ahorro de 11.8 millones, sino que quedaría como que **cruzan los ingresos con los gastos mensuales**."*

**[V] Resultado:** ingresos 54.337.990 · excedente **360.004** (vs. 11.896.812 en D)

> **Aquí se materializa el uso del amarillo como "palanca reservada"** (ver [03 §7.4](06-gastos-y-optimizacion.md)). Los ítems que marcaste sin cambiar en la propuesta A son exactamente los que se accionan cuando el escenario se tensiona.

### Tipo 2 — Nueva fuente de ingreso con sus costos asociados (columna F)

**Contexto [E]:** *"ese pago del apartamento: necesito pagar la remodelación del apartamento **para poder generar una inyección, tener una renta de capital mensual**."*

**[E]** *"le hice otra propuesta sin la consultoría y con el arriendo del nuevo apartamento, porque **al remodelarlo tendría una renta del nuevo apartamento en sus ingresos**… sería un ingreso adicional."*

**Qué se toca [V]:**

| Celda | Concepto | Efecto |
|---|---|---|
| `F10` | Apto. Fontibón | **+1.400.000** ingreso mensual |
| `F65` | Admon. Apto. Nvo. | **+280.000** gasto mensual |
| `F83` | Seguro de Arrendamiento | **+1.400.000** gasto anual |
| `F102` | Impuesto Apto. Fontibón | **+1.500.000** gasto anual |

> ⚠️ **Regla clave: un ingreso nuevo trae gastos nuevos.** No se modela la renta sin su administración, su seguro y su predial. Modelar solo el ingreso es el error clásico.

**[E]** *"el ingreso mensual se elevaría, los gastos seguirían exactamente iguales los mensuales; sin generar la consultoría tendría ya un excedente de 980.000 mensuales. Y sus ingresos anuales siguen iguales, versus **sus gastos anuales aumentarían por concepto de seguro de arrendamiento del nuevo apartamento y el impuesto predial del nuevo apartamento**."*

**[V] Resultado:** excedente mensual **980.004** · **la provisión mensual cambia de signo**

**[E]** *"Entonces acá sí vemos que los ingresos anuales siguen iguales, pero los gastos anuales se aumentan, **lo que quiere decir que acá en la casilla F105 nos muestra que hay que generar ya una provisión mensual de 139.000**."*

**[V] Verificación:** (49.517.989 − 47.846.500) / 12 = **139.291** ✓

> **Este es el caso que activa el segundo brazo de la regla de anualidades:** con `F105` **positivo**, la provisión deja de resolverse con el bono anual y pasa a ser una línea del recurso mensual. Ver [17 §5](17-reglas-y-excepciones.md).

### Tipo 3 — Proyección temporal (columna G)

**[E]** *"Luego también hice otra proyección, un presupuesto, una propuesta **de al cabo de 18 meses**. Si continúa todo igualito con la consultoría más la renta del 1.400.000, y sigue la misma empresa, **y sin tener incluso incrementos en el salario**, tendría un ingreso de 66.2 millones mensuales."*

**Supuesto conservador [E]:** *"**sin tener incluso incrementos en el salario**" — no se proyectan aumentos que no estén confirmados.

**[V] Resultado:** excedente mensual ≈ **12,3 M** (G107 = 12.326.122,25) · provisión **139.291**

**[E]** El cierre: *"nos muestra que en la columna G105 nos está informando que debería ser un presupuesto mensual adicional de 139.291, **el cual debería salir de la parte mensual; pero pues como acá hay un excedente de 12.4 millones de pesos, de ahí puede salir**."*

> **La provisión mensual se financia con el excedente mensual cuando lo hay.** Esa es la conexión entre las filas 105 y 69.

---

## Cómo se construye un escenario

1. **Duplica la columna de referencia** (normalmente D) en la siguiente columna libre
2. **Renombra el encabezado** con letra + descripción de la condición, en las **cuatro** filas de encabezado (5, 13, 72, 79)
3. **Modifica solo las celdas que el escenario afecta**; el resto se replica
4. **Aplica los efectos en cadena:**
   - ingreso nuevo → ¿qué gastos trae? (administración, seguro, impuesto)
   - ingreso perdido → ¿qué palancas de ajuste hay que activar?
   - ¿cambian las anualidades? → recalcular fila 104 y **leer el signo de la 105**
5. **Marca en amarillo** todo lo modificado
6. **Lee las cinco cifras de cierre:** filas 11, 67, **69**, 104, **105** y 107
7. **Comprueba si cambia la arquitectura del plan:** si la fila 105 pasa de negativa a positiva, la estrategia de anualidades se mueve del bloque de capital al bloque mensual

---

## Cómo se leen los escenarios

**[V] Cuadro comparativo del ejemplo:**

| | C REGULAR | D (A) | E (B) | F (C) | G (D) |
|---|---|---|---|---|---|
| TOTAL INGRESOS (11) | 64.943.990 | 64.877.990 | 54.337.990 | 55.737.990 | — |
| TOTAL EGRESOS (67) | 56.047.699 | 52.981.178 | 53.977.986 | 54.757.986 | — |
| **INGRESOS − EGRESOS (69)** | **8.896.291** | **11.896.812** | **360.004** | **980.004** | ≈12,4 M |
| TOTAL ING. ANUALES (77) | 47.846.500 | 47.846.500 | 47.846.500 | 47.846.500 | — |
| TOTAL ANUALIDADES (104) | 36.617.989 | 46.617.989 | 46.617.989 | **49.517.989** | 49.517.989 |
| **PROVISIÓN MENSUAL (105)** | (935.709) | (102.376) | (102.376) | **139.291** | **139.291** |
| Excedente neto (107) | 9.831.999 | 11.999.188 | 462.379 | 840.713 | 12.326.122 |

**Lectura, escenario por escenario:**

| Escenario | Diagnóstico |
|---|---|
| **C → D** | La optimización libera **3 millones/mes** sin recortar calidad de vida |
| **E** | Sin la consultoría, el hogar **queda al filo**: 360.004 de margen. Sostenible pero sin holgura |
| **F** | La renta del apartamento **recupera margen** (980.004) pero **crea una necesidad de provisión** de 139.291 por los gastos anuales asociados |
| **G** | A 18 meses con todo funcionando, **12,3 M/mes** de excedente — la provisión sale de ahí sin problema |

**[E]** *"Estos son los diferentes escenarios que se plantearon… Esto es en general la propuesta, y **esta es la forma como se organiza un planteamiento de un plan de acción de estas condiciones, donde se revisa a 360 grados la situación del cliente**."*

---

## Qué escenario alimenta el `Plan de Acción`

**[E]** *"acá terminaríamos con esta columna, en la columna D, la propuesta. Yo hice para este caso diferentes propuestas de optimización del presupuesto, **pero en principio vamos a trabajar con esta columna D**."*

> **El plan se construye sobre UNA columna** — normalmente la **D (Organización Actual)**, el escenario más probable.
> Los demás escenarios son **análisis de sensibilidad** que se le presentan al cliente, no planes paralelos.

**[AMB]** El video no dice qué hacer si el cliente decide adoptar el escenario E o F como base. **[I]** Lo conservador es reconstruir el `Plan de Acción` sobre esa columna y **preguntar a Amanda** si se sustituye el plan o se elabora uno adicional.

---

## Cierre: los impuestos

**[E]** El video termina con esto: *"Por supuesto también **se analiza qué tanto pagará de impuestos y cómo se programa el tema de la declaración de renta para el siguiente año**."*

**El procedimiento tributario está ahora documentado en [12 — Tributario y pensional](12-tributario-y-pensional.md)**, a partir del audio de respuestas de Amanda.

Resumen de lo que se sabe:
- Es el **nivel 4** de la pirámide financiera
- **[E]** Amanda usa **una herramienta externa (un link)** para proyectar el impuesto del año siguiente
- **[V]** Las anotaciones de `Desprendibles de nom.` (`Interes de Vivienda`, `AFC, PV`, `Dependientes`, `Medi. Prepagada`) **son las cuatro deducciones** que bajan la base gravable
- La proyección se convierte en **provisión mensual o anual** y se registra en `Presupuesto`!101
- Caso especial: clientes con **comisiones mensuales** — retención × 12 vs. impuesto proyectado; puede haber **saldo a favor**

> ⛔ **Tu límite:** recopilas los datos y las cuatro deducciones, estructuras la ficha y **escalas**. **No calculas el impuesto.**
> **[E]** *"al final se analiza qué tanto pagará de impuestos y **cómo se programa el tema de la declaración de renta para el siguiente año**."*

---

## Checklist de la fase 15

- [ ] Cada escenario responde a una **pregunta real del cliente**, documentada
- [ ] Encabezado con letra + descripción, en las **cuatro** filas de encabezado
- [ ] Solo se modificaron las celdas que el escenario afecta
- [ ] **Los ingresos nuevos traen sus gastos asociados** (administración, seguro, impuesto)
- [ ] Los ingresos perdidos activan las palancas amarillas reservadas
- [ ] Todo lo modificado, en amarillo
- [ ] Filas 104 y **105 recalculadas**, y el **signo de la 105 leído**
- [ ] Si la 105 cambia de signo → arquitectura del plan revisada
- [ ] Cuadro comparativo preparado para la presentación
- [ ] Está claro **sobre qué columna** se construyó el `Plan de Acción`
