# 11 — Inversiones (Fase 15)

**Es el nivel 5 de la pirámide — el último.** No se llega aquí hasta que las coberturas, las anualidades y el fondo de emergencia estén resueltos.

**[E]** *"dentro de la escala, lo primero que recomiendo son las coberturas, el tema de las anualidades, la provisión para el pago de las anualidades, **y luego viene toda la parte de inversiones**."*

---

## 1. El principio: instrumento al final

**[E]** *"lo que se busca es cubrir los objetivos, hacer una planeación, y sobre esa planeación revisar **qué instrumento nos permite llegar a ese objetivo más rápido**."*

```
OBJETIVO  →  PLANEACIÓN  →  INSTRUMENTO
```

**Nunca al revés.** No se parte de un producto y se le busca justificación.

---

## 2. Qué cubre una estrategia de inversión

**[E]** En el ejemplo del video, una sola estrategia de inversión cubre **cuatro cosas a la vez**:

> Objetivo: `Libertad Financiera / Estudios Niños / Jubilación`
> Vehículo: `Inversión`
> Monto: `=1500*H15`

Y además **cubre dos de los siete riesgos**:

**[E]** *"El riesgo inflacionario lo podemos cubrir —el riesgo país— **con inversiones** o en cuentas de alta rentabilidad, fiducia."*

| Riesgo | Cómo lo cubre la inversión |
|---|---|
| **6. Inflacionario** | rendimiento por encima de la inflación |
| **7. País** | moneda dura, diversificación por región |

**[E]** Y el beneficio declarado: *"va a poder generar un ahorro/inversión que le va a permitir **diversificar por moneda, por sector y por región**."*

---

## 3. De dónde sale el monto

**[V]** `Plan de Acción`!G20 = `=1500*H15` — el **1.500 está escrito a mano** en la fórmula.

**[ND]** No hay fórmula que lo derive. Es la **decisión del asesor** sobre cuánto puede invertir el cliente en USD al mes.

**[E]** Cómo se llega a él: *"En principio hice un balance de cuánto podría llegar a ser, y **luego voy ajustando los montos para saber cuál podría ser el monto ideal**."*

**[E]** Y se contrasta con la necesidad real: *"acá son **2.757** [USD que requiere la universidad], pero en el plan de acción, debido a que en su presupuesto por ahora, **lo máximo con lo que podemos llegar a contar para que logre todos sus objetivos por ahora es de 1.500 dólares**."*

### La regla de la brecha

```
NECESIDAD (calculada por objetivo)   vs.   CAPACIDAD (lo que el flujo permite)
                    │
        ┌───────────┴───────────┐
        │ Necesidad ≤ capacidad │ Necesidad > capacidad
        ▼                       ▼
  Se financia completo     Se propone la CAPACIDAD
                           Se documenta LA BRECHA
                           NUNCA se ajusta el cálculo
```

> **Se calculan ambos números, se muestra la diferencia, se propone lo alcanzable.**

---

## 4. La TRM en la conversión

**[E]** *"para el plan de acción y el desarrollo del presupuesto, se debe colocar **una TRM del día más 200 pesos más adicional**. Esto solamente por tener presente que **la TRM puede llegar a crecer** y el presupuesto está ajustado a si hay un crecimiento de la TRM."*

```
Plan de Acción!H15  =  TRM del día  +  200 COP
G20                 =  aporte en USD  ×  H15
```

Es un supuesto conservador: si el peso se devalúa, harán falta más pesos para el mismo aporte en dólares. Presupuestar con la TRM alta evita quedarse corto.

> ⚠️ **[CORR]** La documentación previa decía "+200 a 300". Amanda fija **+200**.

Y para proyecciones a largo plazo, la conversión usa la **TRM del horizonte**, no la de hoy:
**[V]** `ANALISIS`!F24 = `=F23*D10` — USD × TRM proyectada a 25 años.

---

## 5. La hoja `ANALISIS` — comparativa de productos

### 5.1 Para qué sirve

**[E]** *"para poder lograr un muy buen análisis también hice **un comparativo de diferentes productos**."*

Cuantificar escenarios **a igualdad de prima**, para que el cliente decida con números.

### 5.2 Parámetros

| Celda | Campo |
|---|---|
| **D7** | **TRM Hoy** (la real) |
| D8 | EDAD titular |
| D9 | EDAD cónyuge |
| **D10** | **TRM 25 AÑOS** ← `PROYECTADO TRM` |
| **D11** | **TRM 20 AÑOS** ← `PROYECTADO TRM` |

**[E]** *"acá coloqué la TRM del momento, la edad de los dos clientes, la TRM a 25 años, a 20 años."*

### 5.3 Los tres escenarios

| Escenario | Cols | Composición | Prima |
|---|---|---|---|
| **1** | E | RL 360 (Inversión Pura) | **1.500 USD** |
| **2 — Nasdaq Conservadora** | F · G · H | RL 360 + BMI titular + BMI cónyuge | **1.000 + 250 + 250** |
| **3 — Proyección Nasdaq** | I · J · K | RL 360 + BMI titular + BMI cónyuge | **1.000 + 250 + 250** |

**[E]** *"un escenario 1 donde solamente fuera inversión —los 1.500 dólares llevados a **una inversión pura** con una compañía—. Luego revisé un escenario 2 llevándolo un NASDAQ… el NASDAQ 100 **de modo conservador**, con **una mezcla de inversión pura más una cobertura de protección con acumulación para él y una cobertura de protección con acumulación en dólares para ella**. … Y en el escenario 3, la proyección del indicador bursátil, **que ya no es tan conservadora, pero son valores reales**."*

### 5.4 ⚠️ [CORR] El reparto de la prima

El audio del video dice *"1.500 para inversión pura, 250 para él y 250 para ella"*. **La pantalla muestra 1.000 / 250 / 250.**

**[V]** Fila 30 (Prima Mensual USD): E = 1.500 · F = 1.000 · G = 250 · H = 250
**[V]** Fila 31 (total): **1.500 en los tres escenarios**

> **La condición que hace válida la comparación es que la prima total sea idéntica.** Si no lo es, la comparación no significa nada.

### 5.5 Filas comparadas

| Fila | Concepto |
|---|---|
| 14 / 15 | Cobertura de Vida inicial — USD / COP |
| 16 / 17 | Cobertura vida año 20 — USD / COP |
| **18 / 19** | **Valor Acumulado año 20** — USD / COP |
| **20** | **Total 20 años** por escenario |
| 21 / 22 | Cobertura vida año 25 — USD / COP |
| **23 / 24** | **Valor Acumulado año 25** — USD / COP — `F24 = =F23*D10` **[V]** |
| **25** | **Total 25 años** por escenario |
| **30 / 31** | **Prima Mensual USD** / total |

### 5.6 Resultados del ejemplo a 25 años (COP)

| Escenario | Valor acumulado |
|---|---|
| 1 — Inversión pura | **11.620.890.260** ← el mayor |
| 2 — Nasdaq conservadora | 10.592.013.585 |
| 3 — Proyección Nasdaq | 11.461.579.693 |

---

## 6. ⭐ El criterio de recomendación — la acumulación máxima NO gana

**[E]** *"Esto les va a permitir saber cuánto en general logran hacer en cada escenario… y cuál puede ser la mejor alternativa. **A veces la mejor acumulación, la mayor acumulación, no está dada** —acá nos muestra que es exclusivamente inversión pura—, **pero cuando se hace una mezcla de dos productos podemos generar no solamente una acumulación, sino también una diversificación por moneda, por sector, por región, una muy buena cobertura para los padres, una acumulación en una moneda fuerte** —no solamente dólares: dólares, libras esterlinas… **hasta en siete tipos de monedas diferentes**."*

### Los cinco criterios, no uno

| Criterio | Inversión pura | Mezcla con cobertura |
|---|---|---|
| **Acumulación bruta** | ✅ mayor | menor |
| **Cobertura de vida** | ❌ ninguna | ✅ incluida |
| **Diversificación** (moneda, sector, región) | limitada | ✅ hasta **7 monedas** |
| **Moneda fuerte** | dólares | ✅ dólares, libras, otras |
| **Optimización tributaria** | ❌ | ✅ **[E]** *(audio)* |

### ⭐ El quinto criterio viene del audio

**[E]** *(tramo recuperado)* *"hago recomendación para reforzar el tema de cobertura de vida **sin depender de uno como beneficio de la compañía**… le doy una propuesta de seguro de vida **que le permite estar protegido, pero a la vez generar una acumulación en dólares** que puede tener un retorno muy potente a futuro con una rentabilidad alta, **y que le sirve para optimizar la parte tributaria**."*

> **[V]** Esto identifica qué son los productos **BMI** de los escenarios 2 y 3: **cobertura de vida con acumulación en dólares**. Y añade el beneficio fiscal que el video no mencionaba.
>
> **Un producto mixto resuelve simultáneamente: riesgo de vida (1), riesgo inflacionario (6), riesgo país (7) y optimización tributaria (nivel 4 de la pirámide).** Por eso puede ganar aunque acumule menos.

---

## 7. Quién decide

**[E]** *"y pues ya acá **el cliente elige el producto a seleccionar**."*

> **Tú presentas escenarios cuantificados. La elección es del cliente.**
> **Nunca** declares un producto "el mejor". **Nunca** prometas una rentabilidad.

Lo que sí haces: explicar **qué resuelve cada escenario** más allá del monto final.

---

## 8. Los vehículos que usa el método

Observados en las columnas *Vehículo* del `Plan de Acción`:

| Vehículo | Para qué objetivo |
|---|---|
| `Inyección a Capital` | pago de deudas — cuando el destino fino aún no está decidido |
| `Inyección a Capital C. Hipotecario` | destino específico (obligatorio para el AFC) |
| `Inyección a Capital TC` | tarjeta de crédito con tasa alta |
| `Inversión` | libertad financiera, estudios, jubilación |
| `Ctas Alta Rentabilidad, Fiduciaria, FICS, Global 66` | fondo de emergencia |
| `Ctas Alta Rentabilidad, Fiduciaria, FICS, Bolsillo` | anualidades |
| `Remodelación Apto. Nvo.` | objetivo puntual |
| `Mismos lugares` | remanentes que se quedan donde están |

**[E]** Sobre el fondo de emergencia: *"el vehículo hacia donde se puede llevar es una cuenta de alta rentabilidad, una fiducia, un FIC o un Global 66, **o bueno, la mejor recomendación que se dé**."*
→ **Se listan alternativas, no se impone una.**

**[E]** Sobre el pago de deudas cuando falta decidir: *"el vehículo va a ser inyección a capital, **porque no sabemos a qué deuda se le va a inyectar**… pero de igual forma coloqué que sea inyección a capital."*
→ **Es legítimo dejar el vehículo genérico** cuando el destino depende del análisis de deuda.

---

## 9. ⛔ Origen de las cifras de producto

**[E]** *"acá les muestro los valores que me dan **las diferentes cotizaciones**."*

**[ND]** Las cifras de cobertura, acumulación y rendimiento de cada producto vienen de **cotizaciones externas de las compañías**. No hay fórmula en la plantilla que las genere.

> **Pídelas. No las estimes ni las proyectes tú.**

**[E]** Y las compañías se tramitan a través de **AXIA** (agencia) y **UNITED FINANCIAL CONSULTANTS.** (bróker) — pero **no se mencionan en el plan ni al cliente**.

---

## Checklist de inversiones

- [ ] Coberturas, anualidades y fondo de emergencia **resueltos antes** de llegar aquí
- [ ] Monto de inversión derivado de contrastar **necesidad vs. capacidad**
- [ ] **Brecha documentada** si la necesidad supera la capacidad
- [ ] `H15` = TRM del día **+ 200**
- [ ] `G20` = aporte USD × `H15`
- [ ] Conversión a largo plazo con la **TRM del horizonte**
- [ ] **Prima total idéntica** en los tres escenarios
- [ ] Cifras de producto obtenidas de **cotizaciones reales**
- [ ] Los cinco criterios presentados, no solo la acumulación
- [ ] **Ningún producto declarado "el mejor"**
- [ ] **Ninguna rentabilidad prometida**
- [ ] AXIA / United Financial **no mencionados**
- [ ] Riesgos 6 y 7 marcados como cubiertos por la estrategia de inversión
