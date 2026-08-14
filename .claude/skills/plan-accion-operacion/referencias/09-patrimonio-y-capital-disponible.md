# 09 — Patrimonio y capital disponible (Fases 5 y 13)

Dos cosas distintas que se confunden fácil:
- **Patrimonio** = todo lo que el cliente tiene y debe (`Info Patrimonio`)
- **Capital disponible** = el subconjunto que **se puede mover hoy** (`Plan de Acción`)

---

# PARTE A — `Info Patrimonio` (Fase 5)

## 1. La definición que se le explica al cliente

**[E]** *"es importante aclararle al cliente que **el patrimonio es la radiografía como tal de lo que tiene el cliente**. ¿Y esto qué quiere decir? Que el patrimonio está compuesto por **activos menos pasivos, que son las deudas, igual al patrimonio**."*

```
ACTIVOS − PASIVOS = PATRIMONIO
```

## 2. Los cinco bloques

| Bloque | Título | Encabezados | Datos desde |
|---|---|---|---|
| **ACTIVOS LÍQUIDOS** | B5 | fila 6 | fila 7 |
| **ACTIVOS PRODUCTIVOS** | B18 | fila 19 | **fila 20** |
| **ACTIVOS IMPRODUCTIVOS** | B31 | fila 32 | fila 33 |
| **PASIVOS CORTO PLAZO** *(banda roja)* | B45 | fila 46 | fila 47 |
| **PASIVOS LARGO PLAZO** *(banda roja)* | B66 | fila 67 | **fila 68** |

### Columnas de activos
**B** ACTIVO · **C** ENTIDAD · **D** VALOR · **F** COMENTARIO

### Columnas de pasivos
**B** PASIVO · **C** SALDO DE CAPITAL · **D** ENTIDAD · **E** TASA · **F** #CUOTAS PENDIENTES · **G** CUENTA MENSUAL

> ⚠️ La columna **D (ENTIDAD)** de los pasivos alimenta `Desmonte Deudas`!B21 por fórmula.

## 3. Definiciones operativas

### 3.1 Activos líquidos
**[E]** *"todos aquellos que podemos hacer fácil uso, tener fácil uso **para gastar**."*
Cuentas de ahorro de cada uno, efectivo en casa, caja fuerte, dólares.

### 3.2 Activos productivos — **umbral matizado**
**[E]** *(video)* *"todos aquellos que nos generan rentabilidad **en lo posible superior a la inflación, pero a veces no es suficiente. Entonces, de igual forma, antes de que nos genere algo de rentabilidad, lo vamos a colocar acá**."*
**[E]** *(audio)* *"todo lo que genera rentabilidad… llámese cuentas de ahorros, **pero con rentabilidad superior a la inflación o al menos cercana a la inflación**."*

> **Criterio consolidado:** basta con que la **naturaleza** del activo sea generar rendimiento. No exijas que hoy supere la inflación.
> Una cuenta de ahorros **con rentabilidad cercana a la inflación** es productiva; una cuenta corriente sin rendimiento es líquida.

Incluye: acciones, inmuebles de inversión, bodega, bonos, carteras colectivas, casas en renta, CDT, cuentas de inversión, cuentas por cobrar a terceros, empresa, fiduciaria, **AFC**, **pensión obligatoria**.

### 3.3 Activos improductivos
**[E]** *"todos aquellos que **nos generan gastos**."*
**[E]** *"ahí está el carro, de pronto el apartamento donde viven, o fincas o apartamentos que no están rentando."*
También: caballos, joyas, lanchas, local, maquinaria, motos, muebles, terrenos.

### 3.4 Pasivos a corto plazo
**[E]** *"corto plazo es **de uno a cinco años**."*
Consumo, prelibranza, inversión, hipotecario, rotativo, vehículo, terceros, cooperativo, **tarjeta de crédito si es < 5 años**.

### 3.5 Pasivos a largo plazo
Más de 5 años: hipotecario, vehículo, libranza, **deudas a familiares**, préstamo de fondo de empleados.

**[E]** *"desgloso **por tasa, por banco y algunas observaciones**; en largo plazo exactamente igual: si son créditos hipotecarios o créditos de vehículo o **si son deudas a familiares**."*

**[E]** *"así fila por fila, rubro por rubro, **lo más desglosado posible**."*

## 4. La columna COMENTARIO es obligatoria

**[E]** *"si se tiene que hacer algún comentario u observaciones… se debe colocar las observaciones por cada ítem de acuerdo a la fila donde se encuentre."*

Ejemplos reales del video y lo que significan:

| Comentario | Consecuencia operativa |
|---|---|
| `GSU no vesting;` | acciones **no consolidadas** → verificar si son realmente disponibles |
| `731 semanas` · `122 semanas` | **semanas cotizadas** → alimentan la proyección pensional |
| `40 mill para dejarlo ok con acabados` | **inversión pendiente** → se convierte en objetivo del plan |

> **Estos matices deciden después si un activo entra o no al capital disponible.** Sin ellos, la fase 13 se hace a ciegas.

## 5. Dato crítico: las semanas cotizadas

**[E]** *"esas semanas cotizadas **van en los dos**: tanto en la primera hoja de seguridad social como en la del patrimonio."*

| Sitio | Qué se registra |
|---|---|
| `INFORMACION Seg soc`!**H14** | semanas cotizadas del titular (y equivalente del cónyuge) |
| `Info Patrimonio` COMENTARIO | en la fila de la pensión obligatoria: `731 semanas` |

Alimentan la proyección de mesada pensional — ver [12](12-tributario-y-pensional.md).

## 6. Dato bloqueante: las deudas

Sin **saldo + tasa + cuotas pendientes + cuota mensual** de cada crédito, **no se puede hacer el análisis de deuda** y toda la fase 10 se cae.

> Si falta alguno, **detente y pídelo. No estimes una tasa "de mercado".**

---

# PARTE B — Capital disponible (Fase 13)

## 7. Qué es

**[E]** *"vamos a pasar… a **una segunda fase, y es el capital disponible de una persona. El capital disponible lo que me hace referencia es a qué tanto dinero tengo hoy disponible para gastar.**"*

**[E]** *"estos ítems **son sacados del registro de la información del patrimonio**."*

**[E]** Su propósito: *"se trajo los que puede utilizar el cliente **para poder crear una estrategia para el plan de acción que le permita cumplir sus objetivos**."*

## 8. El filtro — activo por activo

**[E]** *"acá lo que tenemos que tener en cuenta es **cuál de estos puede utilizar y cuáles no**."*

Amanda lo hace preguntando en voz alta, uno por uno:

| Activo | ¿Entra? | Fundamento **[E]** |
|---|---|---|
| Cuentas de ahorro | **SÍ** | *"¿Cuenta de ahorros puede utilizar? Sí."* |
| Cuentas de inversión (Global 66, brokers) | **SÍ** | *"¿Lo de Global? Sí."* |
| **AFC** | **SÍ — con destino restringido** | ver §9 |
| Acciones | **SÍ** | *"¿Lo de las acciones se pueden utilizar? Sí."* |
| **Pensión obligatoria** | **NO** | *"¿Lo de la pensión obligatoria de él y de ella se puede utilizar? **No. Entonces no lo relacionamos.**"* |
| **Activos improductivos** | **NO**, salvo excepción | *"**No, a menos de que el cliente diga: voy a vender el carro**… o voy a vender el apartamento. Entonces hay que relacionarlo en el capital disponible **en dado caso que venda**."* |
| **Bono / prima anual** | **SÍ — aunque no esté en el patrimonio** | *"este no está en la información del patrimonio, pero sabemos que hay un bono anual de él… Acá puede ser una prima también, una prima anualizada que esté relacionada en el presupuesto, una prima que se entrega semestral en junio o en diciembre, **o todas las bonificaciones anualizadas se deben colocar acá**."* |

### Reglas derivadas

1. **La pensión obligatoria nunca entra.** No es disponible.
2. **Los activos improductivos solo entran si el cliente declaró intención de vender.** No los incluyas "por si acaso".
3. **Las bonificaciones anuales entran aunque no figuren como activo** — son flujo futuro cierto.
4. **Revisa el COMENTARIO antes de decidir.** Un activo marcado `no vesting` puede no ser disponible. **Ante la duda, pregunta.**

## 9. Restricción de destino del AFC

**[E]** *"la fuente va a ser la FC de Andrés, el objetivo va a ser pago del crédito hipotecario, inyección a capital como vehículo al crédito hipotecario, **porque esa plata definitivamente de la FC solamente puede ser llevada para crédito hipotecario**."*

> **El AFC no es de libre destinación.** Va obligatoriamente al crédito hipotecario.
> *(Además tiene efecto tributario: es una de las cuatro deducciones — ver [12](12-tributario-y-pensional.md).)*

## 10. Montar el bloque (filas 36-49)

| Col | Contenido |
|---|---|
| **F** | nombre del activo — enlázalo: `=+'Info Patrimonio'!B20` **[V]** |
| **G** | valor actual — enlázalo: `=+Presupuesto!D73` **[V]** |
| **H** | saldo que queda tras aplicar las estrategias |
| **F49 / G49 / H49** | **Totales** *(amarillo)* |

**Usa enlaces, no valores tecleados**, siempre que el dato exista en otra hoja.

*(Filas 43-48 están agrupadas/ocultas: el salto visible es 42 → 49.)*

## 11. La doble contabilidad por activo

**[E]** *"en la celda H41 voy colocando la celda a la que hace referencia —las anualidades—; le resto el valor de las anualidades que describí en la celda G56, y el total me queda registrado en la casilla H41, **para ir sabiendo cuánto va quedando de saldo en cada uno de esos ítems**."*

```
H(activo)  =  G(activo)  −  Σ (asignaciones que salieron de ese activo)
```

**[V]** Verificaciones del ejemplo:

| Activo | G | Asignado | **H** |
|---|---|---|---|
| Cta. Ahorro | 8.696.474 | 8.000.000 | **696.474** ✓ |
| Global 66 (cónyuge) | 3.777.120 | 0 | **3.777.120** ✓ |
| Global 66 (titular) | 10.974.082 | 8.000.000 | **2.974.082** ✓ |
| AFC | 27.335.256 | 27.335.256 | **0** ✓ |
| Acciones | 379.978.719 | 40.000.000 | **339.978.719** ✓ |
| Bono anual | 47.846.500 | 46.617.989 | **1.228.511** ✓ |
| **Total H49** | | | **348.654.906** |

> Nota cómo la estrategia de 16.000.000 (`Cta. Ahorros + Global`) se **repartió 8 M + 8 M** entre dos activos. Cuando una estrategia toma de varias fuentes, **el reparto debe quedar reflejado en la columna H de cada una**.

## 12. ⚠️ EL CUADRE MAESTRO

```
H49  (suma de saldos individuales)  ==  G60  (monto del fondo de emergencia)
```

**[E]** *"Si me doy cuenta, el total de lo que queda en cada rubro son 348.6, **que equivale al mismo ítem que aparece en la celda G60**."*

**[V]** 696.474 + 3.777.120 + 2.974.082 + 0 + 339.978.719 + 1.228.511 = **348.654.906** ✓

**Si estos dos números no coinciden, hay un error de asignación. No sigas hasta cuadrarlo.**

---

## Checklist de patrimonio y capital

### `Info Patrimonio`
- [ ] Los cinco bloques diligenciados
- [ ] Activos clasificados por naturaleza, no por rentabilidad actual
- [ ] Pasivos con **saldo, tasa, cuotas pendientes y cuota mensual**
- [ ] Pasivos separados por plazo (corte en 5 años)
- [ ] COMENTARIO usado en todo activo con matiz
- [ ] **Semanas cotizadas registradas aquí y en `INFORMACION Seg soc`!H14**

### Capital disponible
- [ ] Cada activo filtrado con la pregunta "¿puede utilizarlo?"
- [ ] **Pensión obligatoria excluida**
- [ ] Improductivos excluidos salvo venta declarada
- [ ] **Bonificaciones anuales incluidas** aunque no estén en el patrimonio
- [ ] Comentarios revisados antes de decidir
- [ ] Enlaces por fórmula donde el dato existe en otra hoja
- [ ] **Restricción del AFC respetada**
- [ ] Doble contabilidad completa en la columna H
- [ ] **`H49 == G60`** ✓
