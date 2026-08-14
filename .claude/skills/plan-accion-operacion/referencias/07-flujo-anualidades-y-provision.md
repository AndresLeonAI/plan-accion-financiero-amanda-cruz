# 07 — Flujo de caja, anualidades y provisión (Fase 9)

El corazón aritmético del método. Aquí se decide **la arquitectura del plan**.

---

## 1. Los dos circuitos

El método separa el dinero en dos circuitos que se calculan por separado y luego se conectan:

```
CIRCUITO MENSUAL                        CIRCUITO ANUAL
  Ingresos mensuales    (fila 11)         Ingresos anuales   (fila 77)
− Egresos mensuales     (fila 67)       − Gastos anuales     (fila 104)
─────────────────────────────           ────────────────────────────────
= INGRESOS − EGRESOS    (fila 69)       = diferencia         (fila 106)
                                          ÷ 12
                                        = PROVISIÓN MENSUAL  (fila 105)

                    ↓ se conectan ↓
        Excedente neto (fila 107) = fila 69 − fila 105
```

**Por qué están separados:** los gastos anuales (seguros, matrículas, impuestos, viajes) no se pagan cada mes, pero **hay que tener el dinero cuando lleguen**. El método los aísla, calcula si los ingresos anuales los cubren, y solo si no, los convierte en una carga mensual.

---

## 2. El circuito mensual

### 2.1 Estructura verificada

| Fila | Contenido | Fórmula |
|---|---|---|
| **11** | TOTAL INGRESOS | suma de filas 6-10 |
| **67** | TOTAL EGRESOS | **suma de los 11 subtotales azules** (14, 17, 20, 25, 37, 40, 43, 50, 56, 59, 64) |
| **68** | *(sin etiqueta)* | replica la fila 11 |
| **69** | **INGRESOS − EGRESOS** *(amarilla)* | `= fila 68 − fila 67` |

**[V]** Verificación en la columna C del ejemplo: 4.968.093 + 380.000 + 360.000 + 5.105.800 + 2.000.000 + 0 + 34.655.200 + 2.844.444 + 35.620 + 5.698.542 + 0 = **56.047.699 = C67** ✓

**[E]** *"En la celda C68 nos muestra al final cuántos son los ingresos, y en la celda C69 coloca la diferencia entre los ingresos menos los gastos mensuales."*

### 2.2 La fila 66 — "Egreso no Identificado"

**[V][ND]** Espeja **exactamente** el valor de la fila 69 en las cuatro columnas del ejemplo. **No entra en el total de la fila 67.**

**[I]** Rotula el excedente como *"gasto que el cliente no logró identificar"* — es un **indicador de diagnóstico**: dinero que entra y del que no se sabe adónde va.

> **El video nunca la menciona y Amanda no la explicó en el audio.**
> **Regla: no la modifiques.** Se recalcula sola. Si tienes que reportarla, dila como lo que es: la parte del ingreso sin destino declarado.

### 2.3 Qué es la fila 69

Es la **capacidad de ahorro mensual bruta**: lo que sobra cada mes antes de considerar las obligaciones anuales.

**Alimenta:** `Plan de Acción`!G6 → G11 (la bolsa mensual).

---

## 3. El circuito anual

### 3.1 Estructura

| Fila | Contenido |
|---|---|
| **77** | **TOTAL INGRESOS ANUALES** — bono anual, primas, extraprimas, dividendos anuales, comisiones grandes, utilidades |
| **80** | Seguros: |
| **86** | Anualidades Fijas: |
| **91** | Anualidades Presupuestadas: |
| **98** | Impuestos: |
| **104** | **TOTAL ANUALIDADES** — `=G80+G86+G91+G98` **[V]** |
| **105** | **PROVISIÓN MENSUAL** — `=SI(C104>0;(C104-C77)/12;"")` **[V]** |
| **106** | **[I]** `= fila 77 − fila 104` — la diferencia sin dividir |
| **107** | **[I]** `= fila 69 − fila 105` — excedente mensual **neto de provisión** |

### 3.2 Los tres tipos de anualidad

| Rubro | Naturaleza | Ejemplos |
|---|---|---|
| **Seguros (80)** | coberturas de pago anualizado | SOAT, todo riesgo, arrendamiento, salud o carro si se pagan al año |
| **Anualidades Fijas (86)** | obligaciones anuales de **monto conocido** | mantenimiento, revisión técnico-mecánica, matrícula + uniformes, donaciones anuales |
| **Anualidades Presupuestadas (91)** | gasto anual **estimado** | ropa, **viajes**, regalos de cumpleaños y navidad |
| **Impuestos (98)** | | predial, vehículo, declaración de renta, predial de otros inmuebles |

**[E]** Sobre las presupuestadas: *"vamos a colocar ropa de forma anualizada, **en promedio cuánto se gasta** la familia. En viajes, cuánto se han venido gastando, **se gastaron el año pasado** en viajes."*

**[E]** Regla de clasificación: *"hay una donación proyecto unión, **pero esta donación no es mensual, es una donación anual; por esa razón va en anualidades fijas, no en mensuales**."*

---

## 4. ⚠️ LA PROVISIÓN MENSUAL — la trampa del signo

### 4.1 La fórmula real

```
fila 105  =  SI(fila104 > 0 ; (fila104 − fila77) / 12 ; "")
                              ANUALIDADES − INGRESOS ANUALES
```

**[CORR]** El audio del video la describe al revés: *"coge el valor de los ingresos C77, le resta el total de las anualidades C104, y a ese resultado lo divide en 12"*.
**La pantalla manda.** Y Amanda misma reconcilia el signo al leer el resultado:

> *"**Aparece negativo, pero en realidad es algo que estaría quedando de forma mensualizada.** Porque los ingresos anuales superan los gastos anuales, y lo que queda se divide en 12."*

### 4.2 Cómo leer el signo

| Resultado | Significado | Acción |
|---|---|---|
| **NEGATIVO** | los ingresos anuales **cubren** los gastos anuales y **sobra** | **No hay que provisionar** |
| **POSITIVO** | **falta dinero** para cubrir las anualidades | **Ese es el importe mensual a provisionar** |
| **Vacío** | no hay anualidades registradas | revisar: es improbable |

### 4.3 Verificaciones aritméticas [V]

| Columna | Cálculo | Resultado |
|---|---|---|
| C | (36.617.989 − 47.846.500)/12 | **−935.709** ✓ |
| D | (46.617.989 − 47.846.500)/12 | **−102.376** ✓ |
| E | (46.617.989 − 47.846.500)/12 | **−102.376** ✓ |
| F | (49.517.989 − 47.846.500)/12 | **+139.291** ✓ |

**[E]** Lectura de Amanda del caso F: *"los ingresos anuales siguen iguales, pero los gastos anuales se aumentan, lo que quiere decir que acá en la casilla F105 nos muestra que **hay que generar ya una provisión mensual de 139.000**."*

---

## 5. LA REGLA DE LAS ANUALIDADES — decide la arquitectura del plan

**[E]** *"lo que debemos revisar es **primero, sí o sí, separar el valor de las anualidades. Eso es algo que es súper importante tener presente.**"*

**[E]** *"si el valor de sus ingresos anuales supera sus gastos anuales, **debe salir de esas anualidades los gastos**. En dado caso que… no alcance para cubrir los gastos anuales, **o no haya ingresos anuales** para cubrir los gastos anuales, entonces se deberá tener en cuenta esta provisión mensual dentro de la estrategia del plan de acción **en la parte del recurso mensual**."*

### La bifurcación

```
                    ¿fila 77  >  fila 104?
                    (ingresos anuales > gastos anuales)
                              │
        ┌─────────────────────┴─────────────────────┐
        │ SÍ                                        │ NO
        │ (fila 105 negativa)                       │ (fila 105 positiva)
        ▼                                           ▼
  BLOQUE CAPITAL DISPONIBLE                  BLOQUE CAPACIDAD MENSUAL
  Estrategia 1 (fila 56):                    Una línea de estrategia con:
    Fuente:   Bono anual                       Fuente:   Capacidad Ahorro Mensual
    Objetivo: Anualidades                      Objetivo: Anualidades / Provisión
    Monto:    = Presupuesto!D104               Monto:    = Presupuesto!D105
    Vehículo: Ctas Alta Rentabilidad,          Vehículo: Ctas Alta Rentabilidad,
              Fiduciaria, FICS, Bolsillo                 Fiduciaria, FICS, Bolsillo
```

**[E]** *"podremos coger en el capital disponible, **separar las anualidades para ser cubiertas con los ingresos anuales**."*

### De dónde sale la provisión cuando hace falta

**[E]** *"debería salir de la parte mensual; **pero pues como acá hay un excedente de 12.4 millones de pesos, de ahí puede salir**."*

→ La provisión se financia con el **excedente mensual** (fila 69). Si el excedente no alcanza, es una señal de alarma: **escalar**.

---

## 6. La fila 107 — el excedente real

**[I, verificado en 4 columnas]** `fila 107 = fila 69 − fila 105`

| Columna | fila 69 | fila 105 | **fila 107** |
|---|---|---|---|
| C | 8.896.291 | (935.709) | **9.831.999,81** ✓ |
| D | 11.896.812 | (102.376) | **11.999.188,14** ✓ |
| E | 360.004 | (102.376) | **462.379,47** ✓ |
| F | 980.004 | 139.291 | **840.712,81** ✓ |

**Qué significa:** el dinero que realmente queda libre cada mes **después** de haber apartado lo necesario para las anualidades.

- Si la provisión es **negativa** (sobra), la fila 107 es **mayor** que la 69 — el excedente anual refuerza el mensual
- Si la provisión es **positiva** (falta), la fila 107 es **menor** que la 69 — la carga anual come excedente mensual

> **La fila 107 es el número más honesto del presupuesto.** Úsalo para el diagnóstico, aunque la bolsa del plan se cargue con la fila 69.

---

## 7. La distribución de anualidades (filas 109-112)

**[V]** Debajo del bloque hay un desglose porcentual por rubro, con gráficos de torta:

| Rubro | % del ejemplo (col. C) |
|---|---|
| Seguros | 9,52 % |
| Anualidades Fijas | 13,75 % |
| Anualidades Presupuestadas | **65,81 %** |
| Impuestos | 10,92 % |

**[ND]** Su uso no se explica.
**[I]** Sirve para mostrarle al cliente en qué se le va la carga anual. En el ejemplo, dos tercios son gasto **discrecional** (ropa, viajes, regalos) — que es exactamente donde hay margen de ajuste si hace falta provisionar.

> Úsalo como **lectura de diagnóstico**, no como palanca automática.

---

## 8. Diagnóstico del flujo — qué mirar

Con las seis cifras de cierre puedes leer la salud financiera del hogar:

| Señal | Lectura | Acción |
|---|---|---|
| fila 69 **negativa** | gasta más de lo que ingresa | **verificar captura primero**; luego orden de prioridad reducido |
| fila 69 positiva pero fila 107 **negativa** | el excedente mensual no cubre la carga anual | ajustar anualidades o reducir gasto mensual |
| fila 105 **positiva y grande** | las obligaciones anuales están desfinanciadas | prioridad 2 del plan |
| fila 66 **grande** | mucho ingreso sin destino identificado | revisar si falta capturar gasto |
| Anualidades Presupuestadas > 60 % | la carga anual es mayoritariamente discrecional | hay margen de ajuste |
| fila 69 ≫ fila 107 | las anualidades se están comiendo el flujo | separar anualidades es prioritario |

---

## Checklist del flujo

- [ ] `fila 67` = suma de los 11 subtotales azules
- [ ] `fila 69` = `fila 68` − `fila 67`
- [ ] `fila 66` sin modificar
- [ ] `fila 104` = `fila 80` + `fila 86` + `fila 91` + `fila 98`
- [ ] `fila 105` calculada con la fórmula correcta
- [ ] **Signo de la fila 105 leído correctamente**
- [ ] `fila 107` verificada
- [ ] **Regla de las anualidades aplicada** — bifurcación resuelta
- [ ] Si la provisión es positiva: comprobado que el excedente mensual la cubre
- [ ] Diagnóstico del flujo redactado para el informe
