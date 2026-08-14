# Paquete de Skills para Claude Cowork
## Plan de Acción Financiero Personalizado — Amanda Cruz González

**Versión 1.0.0** · Consolidada el 12 de agosto de 2026

---

## 1. Qué contiene este paquete

```
CLAUDE-COWORK-PACKAGE/
│
├── CLAUDE.md                        ← instrucciones de arranque para el agente
├── README.md                        ← este archivo
├── VERSION.md                       ← versionado, fuentes y trazabilidad
├── .gitignore                       ← blindaje: ningún dato de cliente se versiona
│
└── .claude/skills/
    │
    ├── plan-accion-contexto/
    │   └── SKILL.md                 ← manual de identidad operacional
    │
    └── plan-accion-operacion/
        ├── SKILL.md                 ← SOP maestro (orquestador)
        └── referencias/             ← 19 referencias especializadas
        ├── 01-intake-y-fuentes.md
        ├── 02-contexto-humano.md
        ├── 03-plantilla-mapa-de-hojas.md
        ├── 04-captura-de-datos.md
        ├── 05-ingresos-y-nomina.md
        ├── 06-gastos-y-optimizacion.md
        ├── 07-flujo-anualidades-y-provision.md
        ├── 08-deudas.md
        ├── 09-patrimonio-y-capital-disponible.md
        ├── 10-riesgos-y-coberturas.md
        ├── 11-inversiones.md
        ├── 12-tributario-y-pensional.md
        ├── 13-plan-de-accion.md
        ├── 14-calculadoras-auxiliares.md
        ├── 15-escenarios-alternativos.md
        ├── 16-modelo-de-decision.md
        ├── 17-reglas-y-excepciones.md
        ├── 18-discrepancias-resueltas.md
        └── 19-control-de-calidad.md
```

**El paquete es autocontenido.** No depende de rutas locales, archivos externos, scripts ni material de investigación.

---

## 2. Qué hace cada skill

### `plan-accion-contexto` — el QUIÉN y el POR QUÉ

Manual de identidad operacional. Responde: *¿quién soy, para quién trabajo, qué estoy construyendo y bajo qué estándares?*

Contiene: quién es Amanda · el rol y los límites del agente · qué es un Plan de Acción · la pirámide financiera · los siete riesgos · el modelo de las dos reuniones · los cuatro insumos · la jerarquía de fuentes · el orden de prioridad del plan · las reglas anti-invención · los estándares de calidad · cuándo escalar.

**Se carga siempre primero.**

### `plan-accion-operacion` — el CÓMO

SOP maestro con 18 fases y 19 referencias especializadas. Contiene el mapa celda por celda de la plantilla, las **20 fórmulas verificadas**, el análisis financiero completo (ingresos, gastos, flujo, deudas, patrimonio, inversiones, tributario, pensional), el contexto humano, el modelo de decisión de Amanda, las **16 discrepancias resueltas** y el control de calidad.

**Se carga después del contexto.**

---

## 3. Inputs que Claude Cowork debe recibir

| # | Input | Obligatorio | Qué aporta |
|---|---|---|---|
| **1** | **Plantilla de Excel** | **Sí** | la estructura del método — ~19 hojas con fórmulas encadenadas |
| **2** | **Levantamiento de información** | **Sí** | **todos los datos del cliente**: ingresos, gastos, objetivos, patrimonio, deudas |
| **3** | **Archivo Word de observaciones** | **Sí cuando existe** | el contexto humano: hijos y grados, coberturas especiales, propósitos de pago, deudas a revisar |
| **4** | Reunión de sensibilización | Opcional | encuadre del servicio — **no aporta cifras** |

### Soportes documentales a solicitar

Desprendibles de nómina del año · fecha de ingreso a la compañía · semanas cotizadas y fecha de inicio de aportes · saldo AFP y cesantías · **saldo, tasa, cuotas pendientes y cuota de cada crédito** · extractos de cuentas e inversiones · las 4 deducciones tributarias · pólizas de coberturas.

> ⚠️ **La reunión de sensibilización NO es una reunión de datos.** Es la reunión comercial donde Amanda explica cómo trabaja. Todo el insumo sale del **levantamiento de información** y del **archivo Word**.

---

## 4. Flujo operacional

```
                    INPUTS
       (plantilla + levantamiento + Word)
                       │
                       ▼
            ┌──────────────────────┐
            │  SKILL CONTEXTO      │  identidad, filosofía, límites
            └──────────┬───────────┘
                       ▼
            ┌──────────────────────┐
            │  SKILL OPERACIÓN     │  SOP de 18 fases
            └──────────┬───────────┘
                       ▼
       ┌───────────────────────────────────┐
       │  CAPTURA          fases 0 – 5     │  las 4 hojas base
       │  ⛔ barrera ⛔                     │
       │  ANÁLISIS         fases 6 – 11    │  promedios, optimización,
       │                                   │  flujo, deudas, riesgos
       │  CONSTRUCCIÓN     fases 12 – 17   │  estrategias, fondo,
       │                                   │  inversiones, escenarios
       └───────────────┬───────────────────┘
                       ▼
            ┌──────────────────────┐
            │  PLAN DE ACCIÓN      │  Excel completo
            └──────────┬───────────┘
                       ▼
            ┌──────────────────────┐
            │  QA — fase 18        │  52 comprobaciones
            └──────────┬───────────┘
                       ▼
            ┌──────────────────────┐
            │  REVISIÓN HUMANA     │  Amanda → PowerPoint → PDF
            └──────────────────────┘
```

### El orden de prioridad del plan

| Capacidad de ahorro positiva | Capacidad negativa o nula |
|---|---|
| 1. **Coberturas** (los 7 riesgos) | 1. **Pago de deudas** |
| 2. **Anualidades** + provisión | 2. **Anualidades** |
| 3. **Fondo de emergencia** | 3. **Fondo mínimo** |
| 4. **Inversiones** y objetivos | — *nada más* — |

---

## 5. Reglas críticas

### No inventar
- Ningún dato del cliente. El marcador oficial es **`Analizar Estrategia`**
- Ninguna metodología financiera por analogía
- Ningún impuesto ni mesada pensional — **son herramientas externas de Amanda**
- **Nunca aplicar 15 % de retención por defecto** — era el caso de un cliente

### Respetar la metodología
- La pirámide se recorre de abajo arriba: objetivos → protecciones → presupuesto → impuestos → inversiones
- **Objetivo → Planeación → Instrumento**, nunca al revés
- Recortar es la excepción; la calidad de vida del cliente acota los recortes
- Los supuestos siempre se eligen del lado conservador

### Preservar la plantilla
- No borrar ni sobrescribir fórmulas
- No eliminar filas (hay agrupadas ocultas)
- No renombrar hojas ni mover bloques
- **No diligenciar las 8 hojas de diagnóstico previo**

### Detectar discrepancias
- Cinco pasos: detectar → no ocultar → no inventar → señalar → resolver solo con información suficiente
- Ninguna discrepancia se cierra en silencio
- Ver `18-discrepancias-resueltas.md` para las 16 ya resueltas

### Escalar incertidumbres
Se escala cuando: falta información que cambia la arquitectura · hay discrepancia irresoluble · el caso no está cubierto · los números no tienen sentido · la decisión corresponde al cliente o a Amanda.

### Validar resultados
Los dos cuadres innegociables:
```
1. Ambas bolsas llegan a saldo 0
2. H49 (suma de saldos por activo) == G60 (fondo de emergencia)
```

### No mencionar
**AXIA** y **UNITED FINANCIAL CONSULTANTS.** son el bróker y la agencia. **No aparecen en el plan ni se mencionan al cliente.**

---

## 6. Las cinco trampas del método

| # | Trampa | Regla |
|---|---|---|
| **1** | **Signo de la provisión mensual** | `(anualidades − ingresos anuales)/12`. **Negativo = sobra, no provisionar. Positivo = falta, provisionar** |
| **2** | **Ahorro AFC vs. deuda AFC** | cuota → *Servicio a la deuda* · excedente → *Ahorro* |
| **3** | **Tarjeta de crédito** | casi nunca es gasto: duplicaría lo ya registrado |
| **4** | **Orden del análisis de deuda** | se simula **antes** de escribir el plan |
| **5** | **Una sola TRM** | `PROYECTADO TRM` = día · todo lo demás = **día + 200** |

---

## 7. Instalación y uso

Las skills viven en **`.claude/skills/`**. Esa es la ruta que ambos entornos esperan, así que la misma copia sirve para los dos — no hay versiones paralelas que puedan desincronizarse.

### En Claude Code
Clona el repo y ábrelo. Las skills se descubren automáticamente y `CLAUDE.md` se carga como instrucciones del proyecto.

```bash
git clone git@github.com:AndresLeonAI/plan-accion-financiero-amanda-cruz.git
cd plan-accion-financiero-amanda-cruz
claude
```

### En Claude Cowork
Sube al proyecto las dos carpetas de skills:

```
.claude/skills/plan-accion-contexto/
.claude/skills/plan-accion-operacion/
```

### Invocación
Las skills son `user-invocable`. Se activan por descripción o explícitamente:
- `/plan-accion-contexto`
- `/plan-accion-operacion`

**Ambas se cargan juntas, siempre en ese orden.**

---

## 7 bis. Qué NO va en este repositorio

`.gitignore` bloquea por diseño: plantillas y planes de clientes (`.xlsx`, `.docx`, `.pdf`), material de investigación (video, audio), credenciales y carpetas de trabajo.

> **Este repositorio contiene el método, nunca los datos de un cliente.**
> Los planes se construyen en local, sobre copias de la plantilla que no se versionan.

---

## 8. Estado y limitaciones

**11 de 14 preguntas de auditoría resueltas · 1 parcial · 2 pendientes.**

### Pendiente de material adicional
| # | Qué falta | Impacto |
|---|---|---|
| 1 | Fórmula/método del cálculo tributario (Amanda enviará video) | El agente recopila y escala — el flujo funciona |
| 2 | Si un escenario distinto de la columna D sustituye el plan o coexiste | Se aplica regla conservadora y se escala |

### Fuera de alcance por diseño
Proyección tributaria · proyección de mesada pensional · las 8 hojas de diagnóstico · conversión a PowerPoint/PDF · elección del producto de inversión.

En todos estos casos **el agente recopila, estructura y escala**.

### Fuente única
Todo el conocimiento procede de **dos materiales de Amanda Cruz González**: un video de entrenamiento de 1 h 59 min y un audio de respuestas de 24 min. **No está triangulado con fuentes externas.** El método documentado es el de Amanda, no doctrina financiera universal.

---

> **La fidelidad al método vale más que la completitud aparente.**
> Un plan con huecos marcados es entregable. Un plan completo con datos inventados es un daño.
