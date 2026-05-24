# 16 — Cheatsheet de Frameworks DIATO

> Todos los frameworks del curso, juntos, en un solo archivo, para consulta rápida. Esta es la chuleta de bolsillo para repasar antes de defender el TPI o de aplicar un concepto en una reunión real.
>
> Convención por bloque: **NOMBRE** + **cuándo usarlo** + **representación (tabla/ASCII)** + **una línea de aplicación**.
>
> No vas a encontrar acá la teoría de fondo — para eso están los caps 01–14 y el glosario `15`. Acá vas a encontrar la forma del modelo y la situación tipo.

---

## Tabla de contenidos

1. [Datos y analítica](#datos-y-analítica)
   - 5 V del Big Data · Pirámide de Complejidad Analítica · DIKW · 7 criterios de calidad de datos
2. [IA y agentes](#ia-y-agentes)
   - 5 tipos de agentes IA · Componentes de un agente
3. [Prompt engineering y adopción de IAG](#prompt-engineering-y-adopción-de-iag)
   - PERSONA+TAREA+CONTEXTO+FORMATO · ROCEF · Modelo 4E (Explorar/Evaluar/Ejecutar/Escalar)
4. [Procesos](#procesos)
   - AS IS / TO BE · Etapas BPM · Toolkit de mejora (5 por qués, Ishikawa, Pareto, etc.)
5. [Arquitectura software/IT](#arquitectura-softwareit)
   - Modelos de arquitectura software · Modelos cloud · 3 anti-patrones cátedra
6. [Automatización](#automatización)
   - Tradicional vs IA-Driven · Build/Buy/Partner/AIaaS · Arquitectura por criticidad
7. [Ética y gobernanza](#ética-y-gobernanza)
   - 3 capas Agente Profesional · Semáforo de Decisiones · 4 niveles de riesgo EU AI Act · 4 sesgos AAIP · 3 pilares PyMEs
8. [Tendencias](#tendencias)
   - 3 fuerzas tectónicas + 9 shifts McKinsey · 5 tendencias Deloitte 2026

---

# Datos y analítica

## 5 V del Big Data

**Cuándo usarlo**: para diagnosticar el grado de complejidad de un escenario de datos antes de elegir tecnología.

| V | Pregunta | Desafío |
|---|---|---|
| **Volumen** | ¿Cuántos datos? | Capacidad de procesamiento masivo |
| **Velocidad** | ¿A qué ritmo se generan? | Procesar en el momento oportuno (real-time) |
| **Variedad** | ¿De qué tipos/formatos? | Manejar estructurados + semi + no estructurados |
| **Veracidad** | ¿Calidad y confianza? | Detectar errores, faltantes, fuentes discrepantes |
| **Valor** | ¿Para qué sirve? | Convertir datos en decisiones de negocio |

**Aplicación 1 línea**: si un proyecto tropieza en *una* V, todavía es viable; si tropieza en tres, mejor pará y rediseñá.

---

## Pirámide de Complejidad Analítica (4 niveles)

**Cuándo usarlo**: para ubicar el nivel de madurez analítica actual de la organización y trazar el camino hacia donde tiene que llegar.

```
                        ┌───────────────────────┐
                        │  4. PRESCRIPTIVA      │   ¿Qué debería hacer?
                        │  (recomienda acción)  │
                        ├───────────────────────┤
                       ╱│  3. PREDICTIVA        │╲    ¿Qué va a pasar?
                      ╱ │  (modelo ML)          │ ╲
                     ╱  ├───────────────────────┤  ╲
                    ╱   │  2. DIAGNÓSTICA       │   ╲   ¿Por qué pasó?
                   ╱    │  (drill-down)         │    ╲
                  ╱     ├───────────────────────┤     ╲
                 ╱      │  1. DESCRIPTIVA       │      ╲   ¿Qué pasó?
                ╱       │  (dashboard / KPI)    │       ╲
               ╱________└───────────────────────┘________╲
                       VALOR / COMPLEJIDAD →
```

**Aplicación 1 línea**: si tu org todavía discute si los reportes están actualizados, no pierdas tiempo con IA prescriptiva — empezá por la base.

---

## DIKW (Data → Information → Knowledge → Wisdom)

**Cuándo usarlo**: para no confundir "tengo datos" con "tengo conocimiento". Útil al planificar gobernanza, BI y proyectos de IA.

```
                    ╱╲
                   ╱  ╲     SABIDURÍA (Wisdom)
                  ╱W   ╲    Conocimiento + juicio → decisiones
                 ╱──────╲
                ╱        ╲  CONOCIMIENTO (Knowledge)
               ╱   K      ╲ Info aplicable a la acción
              ╱────────────╲
             ╱              ╲ INFORMACIÓN (Information)
            ╱       I        ╲ Dato + contexto → significado
           ╱──────────────────╲
          ╱                    ╲  DATO (Data)
         ╱          D           ╲ Hecho objetivo sin interpretación
        ╱______________________╲
```

**Aplicación 1 línea**: tu CRM tiene *datos* (nombres, tickets); el reporte mensual da *información* (volumen, sentimiento); el patrón "los lunes 9am explota soporte" es *conocimiento*; decidir cambiar el SLA es *sabiduría*.

---

## 7 criterios de calidad de datos

**Cuándo usarlo**: como checklist antes de validar un dataset que va a alimentar IA, BI o procesos críticos.

| # | Criterio | Pregunta de control |
|---|---|---|
| 1 | **Exactitud** (Accuracy) | ¿Refleja la realidad con precisión? |
| 2 | **Completitud** (Completeness) | ¿Faltan campos esenciales? |
| 3 | **Consistencia** (Consistency) | ¿El mismo dato coincide entre sistemas? |
| 4 | **Validez** (Validity) | ¿Cumple reglas de negocio (tipos, rangos)? |
| 5 | **Actualización** (Timeliness) | ¿Refleja la información más reciente? |
| 6 | **Accesibilidad** (Accessibility) | ¿Lo pueden usar los autorizados a tiempo? |
| 7 | **Integridad** (Integrity) | ¿Las relaciones entre tablas son precisas? |

**Aplicación 1 línea**: una IA entrenada con datos que fallan en 3+ criterios va a alucinar con confianza — es la receta clásica del desastre.

---

# IA y agentes

## 5 tipos de agentes IA

**Cuándo usarlo**: para clasificar qué tipo de agente necesitás (o tenés) y justificar por qué uno simple no alcanza o por qué uno complejo es overkill.

| # | Tipo | Característica clave | Ejemplo |
|---|---|---|---|
| 1 | **Reactivo simple** | Estímulo → respuesta, sin memoria | Termostato, robot aspiradora básico |
| 2 | **Con memoria / basado en modelo** | Guarda estado, usa modelo interno | Google Maps con histórico de tráfico |
| 3 | **Basado en objetivos** | Evalúa alternativas para alcanzar una meta | Vehículo autónomo, robot logística |
| 4 | **Basado en utilidad** | Optimiza función de utilidad (riesgo/retorno) | Sistema de inversión, diagnóstico médico |
| 5 | **Con aprendizaje** | Incorpora ML/DL, mejora con experiencia | ChatGPT, asistentes adaptativos |

**Aplicación 1 línea**: subir de nivel cuesta más datos, más compute y más gobernanza — no escales si el problema no lo exige.

---

## Componentes de un Agente IA

**Cuándo usarlo**: para descomponer la arquitectura mínima de cualquier agente al diseñar uno.

```
    ┌──────────────────────────────────────────────┐
    │                ENTORNO (Environment)         │
    │   ┌──────────┐                ┌──────────┐   │
    │   │ SENSORES │ ─── percibe ──>│ AGENTE   │   │
    │   └──────────┘                │          │   │
    │                               │ • Objetivo│   │
    │                               │ • Algoritmo│  │
    │   ┌──────────┐                │   decisión│   │
    │   │ACTUADORES│ <── actúa ──── │ • Aprendizaje│
    │   └──────────┘                └──────────┘   │
    └──────────────────────────────────────────────┘
```

**Aplicación 1 línea**: si te falta uno de los 4 (sensores, objetivo, algoritmo, actuadores) no es un agente — es a lo sumo un script.

---

# Prompt engineering y adopción de IAG

## PERSONA + TAREA + CONTEXTO + FORMATO

**Cuándo usarlo**: como estructura base mínima de cualquier prompt no trivial.

| Componente | Verbos disparadores | Ejemplo |
|---|---|---|
| **PERSONA / ROL** | "Actuá como…" / "Sos especialista en…" | "Sos analista de procesos con 15 años de experiencia." |
| **TAREA / OBJETIVO** | "Hacé / Listá / Estructurá…" | "Listá los 5 cuellos de botella más probables en…" |
| **CONTEXTO** | "Tené presente que…" / "Es una organización que…" | "Es una PyME santafesina del sector agro, 50 empleados…" |
| **FORMATO** | "En una tabla con columnas…" | "Devolveme una tabla con: cuello / impacto / mitigación." |

**Aplicación 1 línea**: si tu prompt no tiene los 4, casi siempre el output va a ser genérico — agregalos antes de quejarte de la IA.

---

## ROCEF (Rol + Objetivo + Contexto + Ejemplo + Formato)

**Cuándo usarlo**: versión evolucionada del anterior cuando tenés un ejemplo de cómo querés la salida (one-shot prompting).

```
┌─ R · ROL ────────────────────────────┐
│   ¿Quién es la IA en este turno?      │
├─ O · OBJETIVO ───────────────────────┤
│   ¿Qué tiene que producir?            │
├─ C · CONTEXTO ───────────────────────┤
│   ¿Qué situación / org / restricción? │
├─ E · EJEMPLO ────────────────────────┤
│   "Algo así:" → muestra de salida     │
├─ F · FORMATO ────────────────────────┤
│   Tabla / lista / informe / markdown  │
└──────────────────────────────────────┘
```

**Aplicación 1 línea**: con un buen Ejemplo, el modelo entiende en segundos lo que con 3 párrafos de instrucciones no captaba.

---

## Modelo 4E (Explorar → Evaluar → Ejecutar → Escalar)

**Cuándo usarlo**: para adoptar ordenadamente una nueva herramienta IA en un equipo u organización, evitando comprar fierros y dejarlos sin usar.

```
          ┌──────────────┐
          │  EXPLORAR    │  ← arranca acá: buscar herramientas
          │  (descubrir) │
          └──────┬───────┘
                 │
                 ▼
          ┌──────────────┐
          │  EVALUAR     │  ← 3 aristas: seguridad/privacidad,
          │  (filtrar)   │     potencia, T&C (características)
          └──────┬───────┘
                 │
                 ▼
          ┌──────────────┐
          │  EJECUTAR    │  ← implementar en el desafío real
          │  (probar)    │
          └──────┬───────┘
                 │
                 ▼
          ┌──────────────┐
          │  ESCALAR     │  ── retroalimenta a EXPLORAR
          │  (extender)  │     (mejora continua)
          └──────────────┘
```

**Aplicación 1 línea**: el error clásico es saltar de Explorar directo a Ejecutar — ahí es donde quedan los pilotos zombies.

---

# Procesos

## AS IS / TO BE

**Cuándo usarlo**: en cualquier proyecto de mejora de procesos antes de tocar tecnología.

```
   ┌─────────────────────┐                ┌─────────────────────┐
   │       AS IS         │   ── mejora──> │        TO BE        │
   │   (proceso ACTUAL)  │     (rediseño) │  (proceso PROPUESTO)│
   │                     │                │                     │
   │ • Cuellos de botella│                │ • Tareas eliminadas │
   │ • Tareas duplicadas │                │ • Automatizaciones  │
   │ • Retrabajos        │                │ • Roles redefinidos │
   │ • Demoras           │                │ • KPIs claros       │
   └─────────────────────┘                └─────────────────────┘
```

**Aplicación 1 línea**: si no mapeás el AS IS, vas a automatizar tus problemas en lugar de resolverlos.

---

## Etapas BPM (Identificación → Modelado → Validación)

**Cuándo usarlo**: como guion para conducir un proyecto de mejora de procesos completo.

| Fase | Identificación | Modelado | Validación |
|---|---|---|---|
| **Relevamiento** | Objetivo / Indicadores / Alcance / Dueño/a / Participantes | Información previa, entrevistas, observación | — |
| **Modelado** | — | AS IS → mejoras → TO BE | — |
| **Documentación** | — | — | Descriptivos, procedimientos |
| **Comunicación** | — | — | Verificación con dueño/a, difusión |

**Aplicación 1 línea**: saltarse la Validación con el dueño/a es la garantía de que el TO BE muera al primer obstáculo.

---

## Toolkit de mejora de procesos

**Cuándo usarlo**: a la hora de analizar y atacar problemas concretos sobre el AS IS.

| Herramienta | Sirve para | En 1 frase |
|---|---|---|
| **5 por qués** | Encontrar causa raíz | Preguntá "¿por qué?" 5 veces hasta tocar el hueso |
| **Ishikawa** (causa-efecto) | Estructurar causas posibles | Espina de pescado: persona/método/máquina/material/medio/medición |
| **Lluvia de ideas** | Generar opciones | Cantidad antes que calidad, después se filtra |
| **Histograma** | Ver distribución | ¿La variable es normal? ¿Bimodal? ¿Sesgada? |
| **Pareto** | Priorizar pocas vitales | 80% del problema lo causa el 20% de las causas |
| **Simulación** | Probar TO BE sin tocar prod | Modelo digital para experimentar |
| **Minería de procesos** | Ver cómo se ejecuta de verdad | Log de eventos → mapa real del proceso |
| **IA Generativa** | Acelerar análisis y modelado | Brainstorming, diagramas, redacción de docs |

**Aplicación 1 línea**: empezá con 5 por qués + Pareto antes de subirte a process mining — son baratísimos y resuelven 80% de los casos.

---

# Arquitectura software/IT

## Modelos de arquitectura software

**Cuándo usarlo**: al elegir cómo armar (o reformar) la base técnica de un sistema.

| Modelo | Ventaja | Limitación | Cuándo |
|---|---|---|---|
| **Monolítica** | Simple al inicio | Difícil escalar / cambiar | MVP, app chica |
| **Microservicios** | Falla aislada, escala independiente | Complejidad operativa | Plataformas grandes con equipos múltiples |
| **SOA** | Integración entre apps distintas | Más pesada que microservicios | Conectar CRM↔ERP↔Legacy |
| **Cloud-Native / Serverless** | Elasticidad, paga-por-uso | Vendor lock-in | Cargas variables, equipos pequeños |

**Aplicación 1 línea**: no migres a microservicios "porque es lo moderno" — migrá cuando el monolito te traba con releases bloqueados.

---

## Modelos de despliegue cloud

**Cuándo usarlo**: al definir dónde corre tu IT.

| Modelo | Quién opera qué | Ejemplo |
|---|---|---|
| **On-Premise** | Vos operás todo | Servidor propio en data center |
| **IaaS** | Vos infraestructura virtualizada, proveedor hardware | AWS EC2, Azure VM |
| **PaaS** | Vos código + datos, proveedor plataforma | Heroku, App Engine |
| **SaaS** | Vos sólo configurás y usás | Gmail, Salesforce, Notion |
| **Híbrida** | Combinación con criterio | Datos críticos on-prem + cargas variables cloud |

**Aplicación 1 línea**: la migración cloud no es binaria — la mayoría de las empresas exitosas terminan en híbrida con criterio por dato/proceso.

---

## 3 anti-patrones cátedra (Arquitectura de Negocios)

**Cuándo usarlo**: como alarma temprana cuando ves uno de estos olores en un proyecto.

| # | Anti-patrón | Síntoma | Riesgo |
|---|---|---|---|
| 1 | **Adaptarse al enlatado** | "El sistema funciona así" → cambiar procesos propios | Perdés diferencial competitivo |
| 2 | **Herencia técnica** (Legacy) | "No se puede porque IT no lo permite" | Estrategia limitada por el pasado |
| 3 | **Automatización de procesos ineficientes** | "Aceleramos con IA un proceso roto" | Hacés MÁS RÁPIDO algo que NO deberías hacer |

**Aplicación 1 línea**: ante cualquiera de los tres, frená el proyecto y volvé al análisis de proceso antes de seguir gastando.

**3 pilares para evitarlos**:
1. Definir requerimientos ANTES que herramientas.
2. Arquitectura de Integración: que ERP/CRM "hablen el mismo idioma".
3. Gobierno de IT en la mesa del directorio (no como soporte, como estrategia).

---

# Automatización

## Tradicional vs IA-Driven

**Cuándo usarlo**: para decidir si tu próximo workflow lo resolvés con reglas duras o con IA.

| Dimensión | Tradicional (reglas) | IA-Driven (aprendizaje) |
|---|---|---|
| **Lógica** | "Si X → entonces Y" | "Aprendé del dato y elegí el mejor camino" |
| **Naturaleza** | Rígida, determinista | Adaptativa, probabilística |
| **Fortaleza** | Eficiencia en lo repetitivo y predecible | NLP, imágenes, detección de anomalías |
| **Limitación** | Se rompe con ambigüedad o cambios | Requiere datos y monitoreo |
| **Mejora** | Vos cambiás reglas | Aprende del propio uso |

**Aplicación 1 línea**: si tu proceso cambia el formato cada 6 meses y siempre se rompe, ya estás pagando IA-Driven sin tenerla.

---

## Build / Buy / Partner / AIaaS

**Cuándo usarlo**: para decidir cómo implementar IA en un proceso concreto.

| Opción | Cuándo SÍ | Cuándo NO |
|---|---|---|
| **Build** (desarrollo interno) | IA es CORE del negocio, privacidad extrema, volumen único | Time-to-market <6 meses, no es core, sin presupuesto sostenido |
| **Buy** (AIaaS) | Funciones transversales commodity (OCR, NLP, sentiment) | Privacidad extrema, dependencia inaceptable |
| **Partner** (consultoría) | Integración profunda ERP/CRM+IA | Conocimiento debe quedar puertas adentro |
| **IA Específica vertical** | Cumplimiento normativo o precisión sectorial alta | Caso muy genérico |

**4 factores de decisión**:
1. Tiempo de implementación
2. Core del negocio (¿propuesta de valor central?)
3. Presupuesto (inicial vs recurrente)
4. Privacidad (sensibilidad de datos)

**Aplicación 1 línea**: la mayoría de empresas exitosas combina — no eligen una, arman ecosistema por criticidad.

---

## Arquitectura por criticidad (Core / Estándar / Orquestación)

**Cuándo usarlo**: para mapear qué hacer con cada componente IA de tu organización.

| Capa | Estrategia | Ejemplo |
|---|---|---|
| **CORE del negocio** | **Build** interno | Predicción de demanda propia, algoritmo industrial único |
| **Funcionalidades estándar** | **Buy** (AIaaS) | Chatbot, traducción, OCR, sentiment, reconocimiento de imágenes |
| **Implementación y orquestación** | **Partner** (consultoría) | Pegamento que une IA con ERP, CRM, WMS |

**Aplicación 1 línea**: si querés desarrollar internamente un chatbot que ya hace OpenAI por dos mangos, estás regalando recursos.

---

# Ética y gobernanza

## 3 capas del Agente Profesional (cátedra Baima / Cáceres)

**Cuándo usarlo**: como arquitectura ética mínima de cualquier agente que va a producción.

```
   ┌──────────────────────────────────────────────────┐
   │  CAPA 3 — BOTÓN ROJO                             │
   │  Supervisión Humana (HITL)                       │
   │  Umbrales críticos → validación obligatoria      │
   ├──────────────────────────────────────────────────┤
   │  CAPA 2 — MURO DE CONTENCIÓN                     │
   │  Privacidad por Diseño                           │
   │  Anonimización, NO "ve" datos sensibles          │
   ├──────────────────────────────────────────────────┤
   │  CAPA 1 — PERÍMETRO DE ACCIÓN                    │
   │  Manual de Conducta (System Prompt)              │
   │  Misión + límites éticos explícitos              │
   └──────────────────────────────────────────────────┘
```

**Aplicación 1 línea**: cualquier agente que toque clientes o decisiones laborales necesita las 3 capas — no son opcionales.

---

## Semáforo de Decisiones (PyMEs)

**Cuándo usarlo**: como herramienta de bolsillo para decidir SÍ/NO/CON SAFEGUARDS frente a un uso concreto de IA.

| Color | Situación tipo | Acción correcta |
|---|---|---|
| 🟥 **ROJO** | Subir balance contable a ChatGPT público | Usar Copilot/NotebookLM privado |
| 🟥 **ROJO** | Asistencia con reconocimiento facial sin consentimiento | Reloj biométrico tradicional o consentimiento escrito + auditoría |
| 🟨 **AMARILLO** | IA filtra CVs | IA solo clasifica, humano revisa SIEMPRE los descartados |
| 🟩 **VERDE** | IA transcribe reuniones internas sin datos sensibles | Adelante, con cláusula de retención |

**Aplicación 1 línea**: si dudás del color, asumí AMARILLO y sumá supervisión — el costo del error de exceso es bajo.

---

## 4 niveles de riesgo EU AI Act

**Cuándo usarlo**: para clasificar un sistema IA al inicio de un proyecto y dimensionar el esfuerzo regulatorio.

```
   ┌─────────────────────────────────────────────────────┐
   │ 4. INACEPTABLE   →  PROHIBIDO                       │
   │    Social scoring, manipulación, reconocimiento     │
   │    emocional en trabajo / educación                 │
   ├─────────────────────────────────────────────────────┤
   │ 3. ALTO          →  REQUISITOS ESTRICTOS            │
   │    Medical devices, credit scoring, infra crítica,  │
   │    vehículos, selección de personal                 │
   ├─────────────────────────────────────────────────────┤
   │ 2. LIMITADO      →  TRANSPARENCIA OBLIGATORIA       │
   │    Chatbots, deepfakes, asistentes virtuales        │
   │    (declarar "estás hablando con IA")               │
   ├─────────────────────────────────────────────────────┤
   │ 1. MÍNIMO        →  SIN REQUISITOS                  │
   │    Filtros de spam, videojuegos, recomendadores     │
   │    de cine                                          │
   └─────────────────────────────────────────────────────┘
```

**Aplicación 1 línea**: aunque Argentina no tenga ley equivalente, los clientes europeos van a exigirte el mapeo igual.

---

## 4 sesgos AAIP (origen)

**Cuándo usarlo**: para auditar dónde se cuela el sesgo en un proyecto de IA.

| # | Tipo | Origen | Ejemplo |
|---|---|---|---|
| 1 | **Percepción** | Sub o sobre-representación en los datos | Dataset con 90% hombres → modelo malo para mujeres |
| 2 | **Técnico** | Limitaciones de la tecnología | Reconocimiento facial menos preciso con piel oscura |
| 3 | **Modelado** | Omisiones en el diseño del algoritmo | No incluir variable "región" en credit scoring |
| 4 | **Activación** | Uso sesgado en el entorno productivo | Operadores que ignoran sistemáticamente recomendaciones para un grupo |

**Aplicación 1 línea**: detectar el sesgo es cuestión de mirada — auditá los 4 antes de cada release crítico.

---

## 3 Pilares Ética PyMEs (Baima / Cáceres)

**Cuándo usarlo**: para vender la inversión en ética como inversión, no como gasto.

| Pilar | Concepto cátedra | Traducción al negocio |
|---|---|---|
| **Privacidad** | Blindaje Industrial | Si filtran tus datos, la competencia sabe cómo fabricás y a quién le vendés |
| **Ética** | Calidad de Marca | Un agente sin sesgos NO discrimina clientes valiosos — la justicia es rentable |
| **Transparencia** | Confianza del Cliente | Poder explicar tu IA es lo que va a hacer que te elijan |

**Aplicación 1 línea**: "ética no es un gasto, es proteger y multiplicar el valor de la empresa".

---

# Tendencias

## 3 fuerzas tectónicas + 9 shifts McKinsey ("State of Organizations 2026")

**Cuándo usarlo**: para mapear los grandes movimientos del entorno organizacional y ubicar tu propio cambio dentro del cuadro grande.

| Fuerza tectónica | Shifts | |
|---|---|---|
| **1. Disrupción tecnológica** | 1 | Unlocking the AI-enabled organization |
| | 2 | Humans + AI agents: new collaboration |
| | 3 | Leveraging AI to rewrite shared services (GBS) |
| **2. Disrupción económica** | 4 | Finding value in a new geopolitical context |
| | 5 | From structure to flow (productividad) |
| | 6 | Focusing on the core (foco) |
| **3. Cambios en fuerza laboral** | 7 | Aiming higher with a new performance edge |
| | 8 | Sharpening focus on diversity and inclusion |
| | 9 | Reinventing leadership: from the inside out |

**Aplicación 1 línea**: ningún cambio organizacional vive solo — si estás haciendo Shift 1 ignorando el 7 (talento), va a fracasar.

---

## 5 tendencias Deloitte Tech Trends 2026

**Cuándo usarlo**: para ubicar tu apuesta tecnológica dentro del horizonte de los próximos 24 meses.

| # | Tendencia | Lectura corta |
|---|---|---|
| 1 | **La IA pasa a lo físico** | Convergencia IA + robótica: humanoides, brazos bimanuales |
| 2 | **La comprobación de realidad agente** | Fuerza laboral basada en silicio: agentes que trabajan al lado del humano |
| 3 | **El ajuste de cuentas de la infraestructura de IA** | Economía de la inferencia: cloud + on-prem + edge convive |
| 4 | **La gran reconstrucción** | Diseñar organización tecnológica nativa de IA (no parche) |
| 5 | **El dilema de la IA** | Ciberseguridad: defender Y aprovechar IA al mismo tiempo |

**Aplicación 1 línea**: ninguna de las 5 se resuelve sola con tecnología — todas requieren un cambio de modelo operativo en paralelo.

---

## Modelo de Decisión: Tradicional → Inteligente → Agéntica (progresión cátedra)

**Cuándo usarlo**: para situar el grado de madurez de automatización actual y la próxima jugada.

```
   RPA tradicional  ──+── IA (NLP, visión, ML) ──→ Automatización Inteligente
                      │                                            │
                      │                                            ▼
                      │                              ┌────────────────────────┐
                      └─────────────────────────────>│ Automatización Agéntica │
                                                    │  (agentes IA que deciden│
                                                    │   y ejecutan con poca   │
                                                    │   supervisión humana)   │
                                                    └────────────────────────┘
```

**Aplicación 1 línea**: saltar de "RPA rígido" a "agente autónomo en producción" sin pasar por inteligente es como aprender a volar sin caminar.

---

## Notas de cierre

- Este cheatsheet es **resumen**, no reemplazo: cuando un framework te quede flojo, andá al capítulo temático correspondiente.
- Si te piden defender una decisión en el TPI, pegá el diagrama ASCII directo en el documento — comunica más rápido que tres párrafos.
- ¿Te falta un framework? Probablemente lo desarrollamos en algún capítulo y se nos pasó traerlo acá — abrí issue o mandá MR (es broma, pero la idea de chuleta abierta queda).

---

➡️ Siguiente: [17-preguntas-guia.md](17-preguntas-guia.md)
