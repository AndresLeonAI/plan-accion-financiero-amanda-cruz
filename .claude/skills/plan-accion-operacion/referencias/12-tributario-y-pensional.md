# 12 — Tributario y pensional (Fase 16)

Dos áreas que Amanda resuelve **en herramientas externas** que el agente no tiene.

> **Tu trabajo aquí es recopilar, estructurar y escalar. No calcular.**

---

# PARTE A — PLANEACIÓN TRIBUTARIA

## 1. Dónde encaja

Es el **nivel 4 de la pirámide financiera** — entre el presupuesto y las inversiones.

**[E]** *"lo que yo hago **de forma separada** es **entrar a un link de una planeación tributaria**."*

## 2. Qué revisa Amanda

**[E]** *"basados en los ingresos del cliente: qué tanto ingreso tiene, es decir, por ingreso de **salario integral u ordinario**; reviso si hace **aportes a AFC** o si hace **aportes a pensión voluntaria**, si tiene **dependientes**, reviso el tema de **pago a seguridad social**, también chequeo… **la medicina prepagada**, porque esto le va a ayudar a **minimizar la base gravable**."*

## 3. ⭐ LAS CUATRO DEDUCCIONES

**[E]** *"las deducciones que en general le ayudan a bajar esa base gravable **son cuatro ítems**: dependientes, intereses de vivienda en un año, si hace aportes a pensiones voluntarias, AFC si tiene, el tema de la medicina prepagada."*

Amanda dice *"cuatro"* pero enumera cinco conceptos. **[V] La evidencia visual lo resuelve:** la columna Z de `Desprendibles de nom.` contiene exactamente cuatro anotaciones —**AFC y Pensión Voluntaria van juntas**:

| # | Deducción | Anotación en la plantilla |
|---|---|---|
| **1** | **Dependientes** | `Dependientes` |
| **2** | **Intereses de vivienda** (anuales) | `Interes de Vivienda` |
| **3** | **AFC + Pensión Voluntaria** | `AFC, PV` |
| **4** | **Medicina prepagada** | `Medi. Prepagada` |

> Esto cierra un `[ND]` de la auditoría anterior: aquellas anotaciones sueltas **eran las categorías de deducción**.

## 4. Datos a recopilar — checklist de captura

| Dato | Dónde se encuentra |
|---|---|
| **Tipo de salario** (integral / ordinario / prestación de servicios) | `INFORMACION Seg soc`!C20 · lista en E32:E34 |
| **Ingreso anual total** | `Presupuesto` fila 11 × 12 + fila 77 |
| **Aportes a seguridad social** | `Presupuesto` filas 44-49 · `Desprendibles` |
| **1. Dependientes** | número y parentesco — archivo Word |
| **2. Intereses de vivienda pagados en el año** | certificado del banco |
| **3. Aportes a AFC + Pensión Voluntaria** | `Desprendibles` (Aporte AFC) · `Info Patrimonio` |
| **4. Medicina prepagada** | `INFORMACION Seg soc`!F9 · `Presupuesto` |
| **¿Es declarante de renta?** | `INFORMACION Seg soc`!C24 |
| **Retención en la fuente mensual** | `Desprendibles` — promedio |
| **¿Recibe comisiones mensuales?** | determina el método — ver §6 |

## 5. El proceso de Amanda

**[E]** *"teniendo presente estos ítems, yo hago **una proyección de cuánto debe pagar en promedio para el siguiente año**, y hago **una provisión mensual o anual** si es del caso."*

```
Ingresos + aportes a seguridad social
        − las 4 deducciones
        ↓
   BASE GRAVABLE reducida
        ↓
   [herramienta externa]
        ↓
   Impuesto proyectado del año siguiente
        ↓
   PROVISIÓN mensual o anual
        ↓
   Presupuesto: Impuestos → "Declaración de Renta"  (fila 101)
```

## 6. Caso especial — clientes con comisiones mensuales

**[E]** *"Hay algunos casos puntuales donde los clientes **reciben comisiones mensuales**. Entonces reviso cuánto es **la retención mensual**, **la proyecto al cabo de un año**, cuánto estarían pagando, **y lo comparo con el resultado proyectado**. Y la diferencia es lo que hago la proyección, para que el cliente sepa en promedio cuánto va a estar pagando y cuánto le haría falta ajustar en materia tributaria."*

```
Retención mensual × 12   vs.   Impuesto proyectado
              │
    ┌─────────┴─────────┐
    │ Retención < impuesto      │ Retención > impuesto
    ▼                           ▼
 Provisionar la diferencia   SALDO A FAVOR
```

**[E]** *"hay clientes que definitivamente **con los ajustes que le hacen de retención mensual cubren ese pago tributario y a veces le queda un saldo a favor**."*

> **[V]** Esto explica un caso del video: *"en la celda C101 aparece en blanco pero el comentario es que **estaba con un saldo a favor**."*

## 7. ⛔ LÍMITE OPERACIONAL

**[ND]** La herramienta de proyección tributaria es **un link externo no documentado ni disponible**.

| Sí haces | No haces |
|---|---|
| Recopilar los datos de §4 | **Calcular el impuesto** |
| Verificar cuáles de las 4 deducciones aplican | Estimar la base gravable |
| Estructurarlo en una ficha para Amanda | Aplicar tablas o tarifas de renta |
| Registrar en `Presupuesto`!101 la provisión **que Amanda determine** | Inventar un porcentaje |
| Marcar `Analizar Estrategia` mientras no llegue | Aplicar **15 %** por defecto |

**[E]** Sobre la fórmula del 15 %, Amanda no la dio: *"si no lo entiendes, **yo te voy a compartir un video más adelante**… te cuento cómo yo lo hago entrando a un link puntual."*
> **El 15 % del ejemplo era el caso de ese cliente, no una constante del método.**

## 8. Conexión con las inversiones

**[E]** *(tramo recuperado del audio)* *"le doy una propuesta de seguro de vida que le permite estar protegido, pero a la vez generar una acumulación en dólares… **y que le sirve para optimizar la parte tributaria**."*

> Los productos de **cobertura con acumulación** tienen un tercer beneficio además de la protección y el rendimiento: **ventaja fiscal**. Es una de las razones por las que la mayor acumulación bruta no gana automáticamente en la comparativa — ver [11](11-inversiones.md).

## 9. Ficha tributaria a entregar

```
PLANEACIÓN TRIBUTARIA — «Cliente»                    [PARA REVISIÓN DE AMANDA]

Declarante de renta:            Sí / No
Tipo de contrato:               integral / ordinario / prestación de servicios
Ingreso anual estimado:         $
  Mensual × 12:                 $
  Anual (bonos, primas):        $
Aportes a seguridad social:     $

DEDUCCIONES QUE BAJAN LA BASE GRAVABLE
  1. Dependientes:              n.º ___   parentesco ___      [fuente]
  2. Intereses de vivienda:     $                             [fuente]
  3. AFC + Pensión Voluntaria:  $                             [fuente]
  4. Medicina prepagada:        $                             [fuente]

RETENCIÓN
  Retención mensual promedio:   $        (de Desprendibles)
  Proyectada a 12 meses:        $
  ¿Recibe comisiones mensuales? Sí / No

PENDIENTE DE AMANDA
  [ ] Proyección del impuesto del año siguiente (herramienta externa)
  [ ] Determinación de la provisión mensual o anual
  [ ] Confirmación de si hay saldo a favor

DATOS FALTANTES
  ...
```

---

# PARTE B — PROYECCIÓN PENSIONAL

## 10. Qué hace Amanda

**[E]** *"al final lo que yo hago con esos datos es hacer **una proyección de mesada pensional**, donde **yo ingreso a un link puntual**, le digo cuánto genera de ingreso el cliente, cuántas semanas tiene, desde cuándo empezó a hacer los aportes de pensión, y **hasta qué edad va a generar ese pago —hasta edad 62— y cuánto sería su mesada pensional a futuro**."*

## 11. Los cuatro insumos

| # | Dato | Dónde se registra |
|---|---|---|
| **1** | **Ingreso del cliente** | `Presupuesto` fila 6 |
| **2** | **Semanas cotizadas** | `INFORMACION Seg soc`!**H14** **y** COMENTARIO de `Info Patrimonio` |
| **3** | **Fecha de inicio de aportes a pensión** | `INFORMACION Seg soc` — pedir si no está |
| **4** | **Edad hasta la que cotizará: 62 años** | supuesto de Amanda |

**[E]** *"esas semanas cotizadas **van en los dos**."*

## 12. Datos complementarios ya en la plantilla

| Dato | Dónde |
|---|---|
| **AFP** (fondo de pensiones) | `INFORMACION Seg soc`!F13 |
| **Saldo AFP** | `INFORMACION Seg soc`!F14 *(celda amarilla)* |
| **¿Cotizó al ISS?** | `INFORMACION Seg soc`!F15 |
| Pensión obligatoria como activo | `Info Patrimonio` — activos productivos, con las semanas en COMENTARIO |
| Fondo de cesantías y su saldo | `INFORMACION Seg soc`!F11 / F12 |

## 13. ⚠️ El supuesto de la edad

**[AMB]** Amanda menciona **62 años** de forma general.

En Colombia la edad de pensión es **62 para hombres** y **57 para mujeres**.

> **Regla:** usa **62** como Amanda indica. **Si el cliente es mujer, señálalo explícitamente** en el informe para que Amanda confirme qué edad aplicar. **No lo cambies por tu cuenta.**

## 14. ⛔ LÍMITE OPERACIONAL

**[ND]** La herramienta es **un link externo no disponible**.

**[E]** Amanda lo reconoce: *"Si tú no tienes de pronto la capacidad para hacer ese análisis, te agradezco me dejes saber… **y yo te comparto un video de cómo lo hago yo**."*

| Sí haces | No haces |
|---|---|
| Recopilar los 4 insumos | **Calcular la mesada** |
| Registrar semanas en **ambos** sitios | Estimar la brecha pensional |
| Verificar que el saldo AFP esté | Aplicar fórmulas de régimen |
| Estructurar la ficha y **escalar** | Recomendar traslado de régimen |

## 15. Qué **no** cubre el método

**[ND]** El video y el audio **no desarrollan**:
- Cálculo de la brecha pensional
- Estrategia para cerrarla
- Comparación entre régimen de prima media y ahorro individual
- Tratamiento de la hoja `Proyeccion Retiro` (fuera de alcance)

> Si el cliente pregunta por su pensión, **recopila y escala**. No improvises.

## 16. Ficha pensional a entregar

```
PROYECCIÓN PENSIONAL — «Cliente»                     [PARA REVISIÓN DE AMANDA]

TITULAR
  Ingreso mensual:                $
  AFP:
  Saldo AFP:                      $
  Semanas cotizadas:              ___    [registrado en H14 y en Info Patrimonio]
  Fecha de inicio de aportes:
  ¿Cotizó al ISS?:                Sí / No
  Edad actual:                    ___
  Edad de cotización final:       62      [supuesto de Amanda]
  ⚠️ Si es mujer: confirmar edad aplicable

CÓNYUGE  (si aplica — mismos campos)

PENDIENTE DE AMANDA
  [ ] Proyección de mesada pensional (herramienta externa)
  [ ] Diagnóstico de brecha, si procede

DATOS FALTANTES
  ...
```

---

## Checklist de la fase 16

### Tributario
- [ ] Tipo de contrato identificado
- [ ] Ingreso anual total calculado
- [ ] **Las 4 deducciones** verificadas una por una, con su fuente
- [ ] Retención mensual promedio extraída de `Desprendibles`
- [ ] Identificado si recibe **comisiones mensuales**
- [ ] Ficha tributaria redactada
- [ ] **Ningún impuesto calculado por el agente**
- [ ] **Ningún 15 % aplicado por defecto**

### Pensional
- [ ] Semanas cotizadas en **`H14` y en `Info Patrimonio`**
- [ ] Fecha de inicio de aportes obtenida
- [ ] Saldo AFP registrado
- [ ] Edad 62 aplicada; **caso mujer señalado si procede**
- [ ] Ficha pensional redactada
- [ ] **Ninguna mesada calculada por el agente**
