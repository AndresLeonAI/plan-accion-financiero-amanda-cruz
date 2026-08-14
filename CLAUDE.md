# Plan de Acción Financiero — Amanda Cruz González

Este repositorio **es** el sistema operacional. No es documentación sobre un sistema: es el sistema.

Su único propósito es que un agente construya **Planes de Acción Financiero Personalizados** siguiendo el método de Amanda Cruz González (asesora de finanzas personales, Colombia), con fidelidad y sin inventar nada.

---

## Lo primero que debes hacer, siempre

Antes de tocar cualquier archivo del cliente, **carga las dos skills en este orden**:

1. **`plan-accion-contexto`** — quién es Amanda, qué es el entregable, la filosofía, los límites, la jerarquía de fuentes, las reglas anti-invención.
2. **`plan-accion-operacion`** — el SOP de 18 fases, el mapa celda por celda, las 20 fórmulas verificadas, el control de calidad.

Están en [.claude/skills/](.claude/skills/) y Claude Code las descubre automáticamente. Puedes invocarlas con `/plan-accion-contexto` y `/plan-accion-operacion`.

**Nunca operes solo con la de operación.** Sin el contexto, el SOP se convierte en llenado mecánico de celdas y se pierden precisamente las reglas que evitan el daño.

---

## Los insumos del cliente

| # | Insumo | Obligatorio | Qué aporta |
|---|---|---|---|
| 1 | **Plantilla de Excel** | Sí | la estructura del método — ~19 hojas con fórmulas encadenadas |
| 2 | **Levantamiento de información** | Sí | **todos los datos**: ingresos, gastos, objetivos, patrimonio, deudas |
| 3 | **Archivo Word de observaciones** | Sí cuando existe | el contexto humano |
| 4 | Reunión de sensibilización | Opcional | encuadre comercial — **no aporta cifras** |

> ⚠️ La reunión de sensibilización **no es** una reunión de datos. Es donde Amanda explica cómo trabaja. Todo el insumo cuantitativo sale del levantamiento y del Word.

---

## Las reglas que no se negocian

### No inventar
- Ningún dato del cliente. El marcador oficial de dato faltante es literalmente **`Analizar Estrategia`**.
- Ninguna metodología financiera por analogía con "lo que suele hacerse".
- Ningún cálculo tributario ni de mesada pensional — **son herramientas externas de Amanda**. Recopila, estructura y escala.
- **Nunca apliques 15 % de retención por defecto.** Ese número era el caso de un cliente concreto.

### Preservar la plantilla
- No borres ni sobrescribas fórmulas con valores fijos.
- No elimines filas — hay filas agrupadas ocultas.
- No renombres hojas ni muevas bloques.
- No diligencies las 8 hojas de diagnóstico previo.

### Las cinco trampas
| # | Trampa | Regla |
|---|---|---|
| 1 | **Signo de la provisión mensual** | `(anualidades − ingresos anuales)/12` · **negativo = sobra** · **positivo = falta** |
| 2 | **Ahorro AFC vs. deuda AFC** | cuota → *Servicio a la deuda* · excedente → *Ahorro* |
| 3 | **Tarjeta de crédito** | casi nunca es gasto: duplicaría lo ya registrado |
| 4 | **Orden del análisis de deuda** | se simula **antes** de escribir el plan |
| 5 | **Una sola TRM** | `PROYECTADO TRM` = la del día · todo lo demás = **día + 200** |

### Los dos cuadres innegociables
```
1. Ambas bolsas llegan a saldo 0
2. H49 (suma de saldos por activo) == G60 (fondo de emergencia)
```

### No mencionar
**AXIA** y **UNITED FINANCIAL CONSULTANTS.** son el bróker y la agencia. No aparecen en el plan ni se mencionan al cliente.

---

## Cuándo detenerte y escalar

Escala a revisión humana cuando:

- Falta información que **cambia la arquitectura** del plan.
- Hay una **discrepancia entre fuentes** que la jerarquía no resuelve.
- El caso **no está cubierto** por el método documentado.
- Los números **no tienen sentido** financiero.
- La decisión corresponde **al cliente** (elección de producto, venta de activos).
- La decisión corresponde **a Amanda** (recortes sensibles, priorización entre objetivos, proyección tributaria o pensional).

**Marcar un hueco es correcto. Rellenarlo con una suposición es un daño.**

---

## Estructura del repositorio

```
.claude/skills/
├── plan-accion-contexto/SKILL.md          identidad operacional
└── plan-accion-operacion/
    ├── SKILL.md                           SOP maestro — 18 fases
    └── referencias/                       19 referencias especializadas

README.md      qué es el paquete, flujo operacional, instalación en Cowork
VERSION.md     versionado, fuentes, trazabilidad y limitaciones
CLAUDE.md      este archivo
```

Las carpetas bajo `.claude/skills/` son exactamente lo que se sube a **Claude Cowork**. La misma copia sirve para ambos entornos.

---

## Procedencia del conocimiento

Todo procede de **dos materiales de Amanda**: un video de entrenamiento de 1 h 59 min y un audio de respuestas de 24 min. **No está triangulado con fuentes externas.**

Cada afirmación lleva marca de procedencia. Respétala:

| Marca | Significado | Cómo tratarlo |
|---|---|---|
| **[E]** | Explícito — dicho por Amanda | aplícalo tal cual |
| **[V]** | Verificado — contra pantalla, aritmética o segunda fuente | lo más sólido que hay |
| **[I]** | Inferencia razonable | aplícalo, pero decláralo si te preguntan |
| **[ND]** | No determinado | **pregunta; no decidas** |
| **[AMB]** | Ambiguo | **marca y escala** |

---

> **La fidelidad al método vale más que la completitud aparente.**
> Un plan con huecos marcados es entregable. Un plan completo con datos inventados es un daño.
