# 16 — El modelo de decisión de Amanda

No basta con saber **qué** hace. Hay que saber **por qué** lo hace, para poder decidir bien en casos que el entrenamiento no cubrió.

Cada decisión se descompone en siete pasos: **inputs → interpretación → diagnóstico → decisión → justificación → output → validación**.

---

## D1 — ¿Este gasto se recorta?

| Paso | Contenido |
|---|---|
| **Inputs** | valor del ítem · ingreso total · tamaño del hogar · calidad de vida declarada · restricciones del archivo Word |
| **Interpretación** | *"¿es desproporcionado **para esta familia**?"* — no en abstracto |
| **Diagnóstico** | **[E]** *"si veo un ítem que está **supremamente elevado**…"* · heurística del bloque alimentación: *"miro el concepto de mercado, el concepto de almuerzos, y al sumar los digo: esto mensualmente, si es una persona, está elevado… **dependiendo de lo que gane**"* |
| **Decisión** | recortar **un poco** / dejar igual pero marcar / dejar igual |
| **Justificación** | **[E]** *"esto va a depender mucho también de **la calidad de vida del cliente**"* · *"**si no es mayor cosa lo dejo quietico**"* |
| **Output** | valor en columna D + **amarillo** + comentario con el criterio |
| **Validación** | ¿el dinero liberado va a un objetivo concreto? ¿respeta las restricciones declaradas? |

> **Default: no recortar.** El método prefiere liberar dinero por otras vías (§D2).

---

## D2 — ¿Cómo libero capacidad de ahorro sin tocar la calidad de vida?

| Paso | Contenido |
|---|---|
| **Inputs** | presupuesto columna C · beneficios del empleador · condiciones bancarias · valores desactualizados |
| **Interpretación** | *"¿qué está pagando de más sin necesidad, o qué está mal registrado?"* |
| **Diagnóstico** | seis patrones observados: ahorro rígido reasignable · reembolso no descontado · cobro evitable · valor desactualizado · gasto futuro no registrado · cobertura ausente |
| **Decisión** | aplicar el patrón que corresponda |
| **Justificación** | **[E]** *"hay neobancos que ya no cobran cuotas de manejo, pues **este ítem se puede eliminar**"* · *"su compañía le daba un dinero reconociéndole el recibo de la luz"* |
| **Output** | columna D ajustada + amarillo + **acción para el cliente** si la hay |
| **Validación** | **[V]** en el ejemplo se liberaron **3 M/mes sin recortar consumo** |

> **Este es el modo preferido del método.** Recortar es el último recurso.

---

## D3 — ¿Este dato entra al presupuesto aunque no tenga soporte?

| Paso | Contenido |
|---|---|
| **Inputs** | declaración verbal del cliente · ausencia de documento |
| **Interpretación** | *"¿el dinero sale realmente?"* |
| **Diagnóstico** | **[E]** *"él estaba pagando 10 millones… a través de un colega"* |
| **Decisión** | **registrarlo** |
| **Justificación** | **[E]** *"**aunque no vea declarado en la renta en un papel oficial, sí es un dinero que sale** por declaración de renta de otra forma, **y debo dejarlo discriminado**"* |
| **Output** | fila en el presupuesto + comentario indicando que no tiene respaldo documental |
| **Validación** | ¿el excedente resultante es coherente con lo que el cliente dice que le queda? |

> **Regla: si el dinero se mueve, entra al presupuesto.** La ausencia de papel no lo hace inexistente.

---

## D4 — ¿A qué deuda inyecto primero?

| Paso | Contenido |
|---|---|
| **Inputs** | saldo, tasa, cuotas pendientes y cuota de cada deuda · monto disponible para inyectar |
| **Interpretación** | *"¿cuál combinación ahorra más intereses y más tiempo?"* |
| **Diagnóstico** | **se simulan ambas tablas de amortización.** **[E]** *"si se inyecta los 4.900.000 **no va a impactar tan fuerte** en el crédito hipotecario, **porque esto ya lo había revisado**"* |
| **Decisión** | atacar primero la que **se extingue antes**; al liberarse su cuota, **encadenarla** a la siguiente |
| **Justificación** | **[E]** *"la mejor forma para ahorrar y minimizar el impacto **en tiempo y en intereses** es inyectando esos 4.900.000 primero al carro… y luego al crédito hipotecario"* |
| **Output** | monto de `Plan de Acción`!G19 + fechas de encadenamiento + ahorro proyectado |
| **Validación** | **[V]** ahorro de 6.397.043 en el vehículo y 402.389.211 en el hipotecario |

> **No se decide por tasa ni por saldo. Se decide simulando.**
> **[E]** *"para esto hay que hacer el análisis puntual **teniendo presente cuándo se van a inyectar**."*

---

## D5 — ¿Este activo entra al capital disponible?

| Paso | Contenido |
|---|---|
| **Inputs** | `Info Patrimonio` completo, incluidos los COMENTARIOS |
| **Interpretación** | **[E]** *"¿qué tanto dinero tengo **hoy disponible para gastar**?"* |
| **Diagnóstico** | pregunta directa activo por activo: *"¿puede utilizarlo?"* |
| **Decisión** | sí / no / **solo si el cliente declaró venta** |
| **Justificación** | pensión obligatoria = no disponible · improductivos = no, salvo venta declarada · bonificaciones anuales = sí, aunque no sean "activo" |
| **Output** | bloque Capital Disponible cargado |
| **Validación** | ¿algún COMENTARIO desmiente la disponibilidad? (`GSU no vesting`) |

---

## D6 — ¿Dónde resuelvo las anualidades?

| Paso | Contenido |
|---|---|
| **Inputs** | `Presupuesto` fila 77 (ingresos anuales) y fila 104 (gastos anuales) |
| **Interpretación** | *"¿el ingreso anual cubre la carga anual?"* |
| **Diagnóstico** | signo de la fila 105 |
| **Decisión** | negativa → **Capital Disponible**, estrategia 1 · positiva → **Capacidad Mensual**, como provisión |
| **Justificación** | **[E]** *"si el valor de sus ingresos anuales supera sus gastos anuales, **debe salir de esas anualidades los gastos**"* |
| **Output** | estrategia en la bolsa correspondiente |
| **Validación** | si la provisión es positiva, ¿el excedente mensual la cubre? |

> **[E]** *"lo que debemos revisar es **primero, sí o sí, separar el valor de las anualidades**."*

---

## D7 — ¿Este riesgo está cubierto?

| Paso | Contenido |
|---|---|
| **Inputs** | presupuesto · transcripción · archivo Word · pólizas |
| **Interpretación** | *"¿existe cobertura, y es suficiente, y de quién depende?"* |
| **Diagnóstico** | **[E]** *"tengo que chequear **cuál de estos siete riesgos ya tiene** y **cuál es imperante tener en estos momentos cubierto**"* |
| **Decisión** | cubierto / cubierto pero insuficiente / descubierto / no se sabe |
| **Justificación** | **[E]** *"está cubierto, **pero no de la mejor manera**"* · *"debemos **no generar una dependencia de la compañía**"* |
| **Output** | descubierto → línea de gasto o estrategia · insuficiente → brecha documentada |
| **Validación** | si añadiste una prima, **`D69` cambió y las estrategias mensuales hay que rehacerlas** |

> **Las coberturas más importantes suelen no estar en el presupuesto.** Hay que preguntarlas.

---

## D8 — ¿Cuánto propongo invertir?

| Paso | Contenido |
|---|---|
| **Inputs** | necesidad calculada por objetivo (universidad, jubilación) · capacidad del flujo |
| **Interpretación** | *"¿alcanza para todo?"* |
| **Diagnóstico** | **[V]** necesidad 2.757 USD/mes vs. capacidad 1.500 USD/mes |
| **Decisión** | proponer **la capacidad**, no la necesidad |
| **Justificación** | **[E]** *"lo máximo con lo que podemos llegar a contar **para que logre todos sus objetivos por ahora** es de 1.500 dólares"* |
| **Output** | `G20 = 1500*H15` + **la brecha documentada** |
| **Validación** | **[E]** *"En principio hice un balance… y **luego voy ajustando los montos** para saber cuál podría ser el monto ideal"* |

> **Nunca se ajusta el cálculo para que cuadre. Nunca se promete lo que no se puede.**

---

## D9 — ¿Qué producto recomiendo?

| Paso | Contenido |
|---|---|
| **Inputs** | cotizaciones de las compañías · edad · horizonte · TRM proyectada |
| **Interpretación** | *"¿qué resuelve cada escenario, más allá del monto final?"* |
| **Diagnóstico** | comparativa a **prima total idéntica** |
| **Decisión** | **el asesor no decide: presenta** |
| **Justificación** | **[E]** *"**a veces la mejor acumulación no está dada**… cuando se hace una mezcla podemos generar no solamente acumulación, sino diversificación por moneda, por sector, por región, una muy buena cobertura… y optimización tributaria"* |
| **Output** | tres escenarios cuantificados con sus cinco criterios |
| **Validación** | **[E]** *"y pues ya acá **el cliente elige el producto**"* |

---

## D10 — ¿Cuántos meses de fondo de emergencia?

| Paso | Contenido |
|---|---|
| **Inputs** | **sector profesional** del cliente · gastos básicos mensuales |
| **Interpretación** | *"¿qué tan rápido se reincorporaría al mercado laboral?"* **[I]** |
| **Diagnóstico** | **[E]** *"Se establece **dependiendo del perfil profesional**"* |
| **Decisión** | salud → **1-3 meses** · resto → **mínimo 6** · si no se sabe → **6** |
| **Justificación** | **[I]** alta empleabilidad = menor colchón necesario |
| **Output** | meta en meses + `E89` calculado + tiempo para alcanzarla |
| **Validación** | **[E]** *"no es necesario que en el primer mes ya tenga listo lo de los seis meses; **se va construyendo en el tiempo**"* |

---

## D11 — ¿Qué hago si la capacidad de ahorro es negativa?

| Paso | Contenido |
|---|---|
| **Inputs** | `Presupuesto` fila 69 ≤ 0 |
| **Interpretación** | **primero:** *"¿es real o es un error de captura?"* |
| **Diagnóstico** | **[E]** *"la gran mayoría de mis clientes, el 99,9 %, sí toman las asesorías porque tienen algo de liquidez… **es una probabilidad muy, muy bajita**"* |
| **Decisión** | orden reducido: **deudas → anualidades → fondo mínimo → nada más** |
| **Justificación** | **[E]** *"solamente le cubro lo básico: anualidades, fondo de emergencia, **nada más**"* |
| **Output** | plan de tres líneas, **sin inversiones ni objetivos de largo plazo** |
| **Validación** | **[E]** *"si veo que el ingreso es negativo, **obviamente doy de una vez la recomendación**"* — se avisa de inmediato, no al final |

---

## D12 — ¿Este dato falta o lo estimo?

| Paso | Contenido |
|---|---|
| **Inputs** | ausencia de una cifra · observaciones del cliente en el Word |
| **Interpretación** | *"¿tengo base suficiente para estimar, o estaría inventando?"* |
| **Diagnóstico** | **[E]** *"Si el cliente no sabe, yo coloco analizar estrategia **y reviso cuánto podrías llegar a necesitar a futuro teniendo en cuenta las observaciones que da el cliente**"* |
| **Decisión** | escribir `Analizar Estrategia` **siempre**; añadir estimación **solo si hay base** |
| **Justificación** | la celda debe declarar que el cliente no lo dio; la estimación es una propuesta, no un dato |
| **Output** | `Analizar Estrategia` + estimación en COMENTARIOS, en amarillo, con su criterio |
| **Validación** | ¿alguien que abra el archivo distingue el dato del cliente de tu propuesta? |

---

## El patrón común

Nueve de estas doce decisiones comparten la misma forma:

```
1. Reunir el dato duro
2. Contrastarlo con el CONTEXTO del cliente (no con un umbral abstracto)
3. Simular o cuantificar antes de decidir
4. Elegir la opción CONSERVADORA
5. Dejar rastro visible (amarillo, verde, comentario)
6. Verificar que el cambio no rompe otra cosa
```

**Cuando el método no cubra tu caso, aplica este patrón y escala la decisión.**

Las tres excepciones —**D9** (producto), **D3** en su límite (validez fiscal), y cualquier cálculo tributario o pensional— **no son tuyas**: se presentan o se escalan.
