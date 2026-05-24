# 20 — Apoyo al Trabajo Final IA-TO V2 (Caso Plantium)

> Este capítulo es **específico para Javier** (el responsable de la **Sección 6** del Trabajo Final V2 del equipo del caso Plantium).
> No es teoría: es un mapa accionable de qué está hecho, qué falta, qué reutilizar del borrador previo y cómo cerrar la sección sin reinventar la rueda.

---

## 0. TL;DR — Si tenés 3 minutos

- **Vos sos responsable de la Sección 6 (Análisis de proveedores y costos)** — hoy está **VACÍA**, solo tiene la consigna copiada.
- Hay un **borrador previo `.docx (1)`** con material directamente reutilizable para tu sección: Botmaker, Aivo, Twilio, OpenAI, Pinecone, Make/Zapier/n8n con rangos USD-AR.
- Otras secciones pendientes del equipo: **Sección 5 (Nadia, parcial)**, **Sección 7 (Santiago, vacía)**, **3 diagramas en placeholder `[]`**, **resumen ejecutivo de 1 hoja**, **fórmulas LaTeX corruptas en Sección 8 (`\tiempo`)**.
- El V2 está al **~70% de completitud**. Bien encaminado pero con frentes abiertos.
- **Esta guía NO escribe la Sección 6 por vos** — te da el esqueleto, los snippets de pricing verificados online y el material reutilizable del borrador.

---

## 1. Contexto del trabajo

### 1.1 La empresa

| Atributo | Valor |
|---|---|
| **Nombre** | Plantium |
| **Sector** | Agroindustria — agricultura de precisión |
| **Productos** | Tecnologías para siembra, fertilización, automatización y control digital de maquinaria |
| **Ubicación** | Fábrica en Villa Constitución (Santa Fe) + I+D en Rosario |
| **Tamaño** | ~250 empleados |
| **Madurez digital** | Medio-alta en producto; brecha en atención al cliente |

### 1.2 El problema

Sobrecarga del área comercial y servicio técnico por crecimiento sostenido de consultas vía WhatsApp y redes sociales. Modelo manual, no escalable, dependiente del factor humano.

**Métricas estimadas** (del V2, sección 3):
- Volumen: ~6.000 consultas/mes.
- Tiempo medio de respuesta: 8 hs.
- Tasa de escalamiento: 35%.
- Costo operativo anual estimado: USD 216.000.

### 1.3 La solución propuesta

Solución integral basada en IA:

1. **Chatbot WhatsApp Business** con IA conversacional (intent + NLP).
2. **Arquitectura RAG** sobre base de conocimiento técnica (manuales, guías, FAQs).
3. **Clasificación automática** de consultas (técnica / comercial / queja / urgente).
4. **Copiloto interno** para agentes humanos (sugerencias en tiempo real).
5. **Capa de analítica** y dashboards.

### 1.4 El benchmark de referencia

El equipo ya ancló el approach con tres casos comparables (Sección 2 del V2):

- **John Deere — Operations Center PRO Service**: asistente IA sobre documentación técnica, rastreo de revisiones, integración con JDLink.
- **Trimble — Trimble Assistant + Charlie**: IA conversacional anclada en datos de dominio, flujos guiados, voz y texto.
- **Syngenta — Dr. Agro**: asistente de voz para información técnica de semillas, infraestructura Google Assistant, escalamiento a distribuidor humano.

**Por qué importa este benchmark para tu sección (6)**: cuando defendás proveedores y costos, podés referenciar que la elección de un stack RAG + LLM + WhatsApp **no es una apuesta** — los referentes globales del sector ya validaron este approach. Tu trabajo es cuantificarlo para el contexto Plantium.

---

## 2. Mapa actual del documento V2

### 2.1 Estado por sección

| # | Sección | Responsable | Estado | Qué falta |
|---|---|---|---|---|
| 1 | Contexto | Lourdes | **Completo** | Coherencia final con resto |
| 2 | Definición del problema o necesidad | Lourdes | **Completo** | Coherencia final |
| 3 | Análisis del proceso actual (AS IS) | Milena Javela | **Completo en prosa** | **Diagrama de flujo en `[]` (3.3)** |
| 4 | Análisis de mejora (TO BE) | Milena Javela | **Completo en prosa** | **Diagrama TO BE en `[]` (4.3)** |
| 5 | Detalle de la solución | Nadia | **Parcial** | RF + RNF + arquitectura + **diagrama de arquitectura** |
| 6 | Análisis de proveedores y costos | **Javier (vos)** | **VACÍO** | **Todo: tabla comparativa + cálculo CAPEX/OPEX + decisión** |
| 7 | Implementación (GANTT) | Santiago Fernández | **VACÍO** | Cronograma completo + responsables + hitos |
| 8 | Indicadores del Proceso y ROI | Magdalena | **Completo** | **Limpiar artefactos LaTeX (`\tiempo`, fórmulas rotas)** + fórmulas en `[]` |

### 2.2 Trabajos transversales pendientes

| Pendiente | Responsable sugerido | Prioridad |
|---|---|---|
| Diagrama AS IS (sección 3.3) | Milena o quien sepa BPMN del equipo | Alta |
| Diagrama TO BE (sección 4.3) | Milena o el mismo del AS IS | Alta |
| Diagrama de arquitectura (sección 5) | Nadia o quien tenga visión técnica | Alta |
| Resumen ejecutivo (1 hoja, obligatorio TPI) | Coordinador/a + editor/a | Alta |
| Limpieza de artefactos LaTeX en sección 8 | Magdalena o editor/a final | Media |
| Sección 5 — RF/RNF/arquitectura | Nadia | Alta |
| Sección 6 — proveedores y costos | **Vos (Javier)** | **Alta — bloqueante** |
| Sección 7 — cronograma GANTT | Santiago | Alta |
| Edición final (tono homogéneo, ortografía) | Editor/a designado/a | Alta (última semana) |

### 2.3 Lo que YA está bien y no toques

- La narrativa de las secciones 1 y 2 es sólida y consistente.
- El benchmark John Deere / Trimble / Syngenta está bien armado.
- La estructura de KPIs de Magdalena en sección 8 es correcta (solo necesita limpieza de formato).
- Los cuellos de botella identificados en sección 3 y la propuesta TO BE en sección 4 están alineados.

> **Regla**: lo que está bien, no se toca. La obsesión por "mejorar todo" rompe la coherencia que el equipo ya logró.

---

## 3. Tu sección — Sección 6: Análisis de proveedores y costos

### 3.1 Qué pide la consigna (literal)

```
Identificar proveedores y realizar una estimación de los costos
asociados con la implementación de la solución. Debe incluir de mínima:
- Licencias
- Desarrollo
- Integración
- Capacitación
- Mantenimiento

Pasos sugeridos:
1. Identificar posibles proveedores
2. Comparar funcionalidades y costos
3. Estimar: licencias, desarrollo, integración, infraestructura,
   capacitación, soporte, mantenimiento
4. Construir tabla comparativa de proveedores
5. Definir inversión estimada total (CAPEX y OPEX)
```

### 3.2 Estructura sugerida (esqueleto markdown para llenar)

> Este es el molde. Reemplazá `[...]` con datos. No copies y pegues sin pensarlo — adaptá a Plantium.

```markdown
## 6. Análisis de Proveedores y Costos

**Responsable**: Javier Zader

### 6.1 Criterios de selección de proveedores

Para evaluar las opciones tecnológicas necesarias para implementar la
solución propuesta, se aplicaron los siguientes criterios:

1. **Presencia y soporte en Argentina / LATAM** (idioma, fuso horario,
   facturación local).
2. **Madurez del producto** (años en mercado, casos publicados, clientes
   referenciables).
3. **Modelo de pricing transparente** (preferencia por pricing público,
   pay-per-use sobre licencias fijas para fase piloto).
4. **Capacidad de integración con sistemas existentes** (CRM, WhatsApp
   Business API, eventual ERP de Plantium).
5. **Cumplimiento de privacidad y seguridad** (Ley 25.326 AR, buenas
   prácticas WhatsApp Business).
6. **Escalabilidad** (capacidad de absorber crecimiento de 6.000 a 15.000
   conversaciones/mes en 24 meses).
7. **TCO a 3 años** (no solo costo inicial).

### 6.2 Categorías de proveedores requeridas

La solución requiere componentes en cinco categorías:

| Categoría | Función en la solución |
|---|---|
| **A. Plataforma de bot + WhatsApp BSP** | Recibir y enviar mensajes vía WhatsApp Business API, manejar flujos conversacionales, integración omnicanal |
| **B. Modelos LLM (IA generativa)** | Generar respuestas en lenguaje natural basadas en contexto RAG, clasificar consultas |
| **C. Base vectorial (RAG)** | Almacenar embeddings de la base de conocimiento técnica de Plantium |
| **D. Orquestación / automatización** | Integrar componentes, disparar flujos, mover datos entre sistemas |
| **E. Analítica / dashboard** | KPIs operativos y de negocio para supervisores y gerencia |

### 6.3 Comparativa de proveedores por categoría

[INSERTAR tablas comparativas — ver sección 4.2 de esta guía para los
snippets de pricing verificados]

### 6.4 Stack tecnológico propuesto (decisión final)

Tras la evaluación comparativa, se propone el siguiente stack:

| Categoría | Proveedor elegido | Justificación |
|---|---|---|
| A. Plataforma bot + WhatsApp | [Botmaker o Twilio + custom] | [Por qué] |
| B. LLM | [OpenAI GPT-4o + GPT-4o-mini para clasificación] | [Por qué — costo, calidad, latencia] |
| C. Vector DB | [Pinecone Serverless en piloto, Qdrant self-hosted en producción] | [Por qué] |
| D. Orquestación | [Make.com o n8n self-hosted] | [Por qué] |
| E. Analítica | [Power BI] | Plantium ya lo usa internamente (verificar con Lourdes) |

### 6.5 Estimación de costos — CAPEX (inversión inicial)

[INSERTAR tabla CAPEX — ver template en sección 4.3]

### 6.6 Estimación de costos — OPEX (gasto mensual recurrente)

[INSERTAR tabla OPEX — ver template en sección 4.3]

### 6.7 TCO a 3 años

[INSERTAR tabla TCO 3 años + supuestos]

### 6.8 Supuestos críticos del cálculo

1. Tipo de cambio: USD oficial Argentina al [mes/año de cálculo].
2. Volumen base: 6.000 conversaciones/mes (consistente con sección 3).
3. Tasa de automatización objetivo: 60% (consistente con KPIs sección 8).
4. Tarifa hora desarrollador interno: USD [X] (rango AR pyme).
5. Tarifa hora consultor externo: USD [Y].
6. No incluye inflación ni ajustes de pricing de proveedores en años 2-3.
7. Costos de proveedores extraídos de pricing público vigente al
   [mes/año] — fuentes en bibliografía.

### 6.9 Riesgos asociados a proveedores

| Riesgo | Probabilidad | Impacto | Mitigación |
|---|---|---|---|
| Aumento de pricing OpenAI / Anthropic | Media | Alto | Multi-LLM (fallback a alternativa), monitoreo de gastos |
| Lock-in con Botmaker | Media | Medio | Diseñar capa de abstracción / evaluar exit en mes 12 |
| Cambios en pricing WhatsApp Business | Alta | Alto | Modelar escenarios pesimistas; tener BSP backup |
| Tipo de cambio adverso | Alta | Alto | Cláusulas de revisión semestral en presupuesto |
| Datos sensibles fuera de jurisdicción AR | Media | Medio | Anonimización + retención corta + DPA explícito |

### 6.10 Conclusión de la sección

[Síntesis 1-2 párrafos: inversión total esperada, posicionamiento vs
ROI calculado en sección 8, recomendación para sponsor]
```

### 3.3 Conexión con el resto del documento

| Sección que te alimenta | Qué le pedís |
|---|---|
| **Sección 5 (Nadia)** | Lista definitiva de componentes técnicos para saber qué proveedores cotizar. Si Nadia no terminó, vos cotizá basado en la propuesta de sección 4.2 (que ya tiene capas tecnológicas listadas) y dejá nota "ajustar si cambia el alcance técnico". |
| **Sección 3 (Milena)** | Volumen actual (6.000 consultas/mes) — usalo como base de cálculo. |
| **Sección 4 (Milena)** | Tabla de capas tecnológicas — sirve para mapear cada capa a un proveedor. |
| **Sección 8 (Magdalena)** | Cálculo de ROI usa USD 50k de inversión. Tu cálculo de Sección 6 tiene que cuadrar (o explicar la diferencia). **Coordinen este número entre ambos.** |

### 3.4 Qué le entregás al resto del equipo

1. **Tabla comparativa de proveedores** por las 5 categorías.
2. **CAPEX desagregado** (alineado o explicando diferencias con los USD 50k que aparecen en sección 8).
3. **OPEX mensual + anualizado**.
4. **TCO a 3 años**.
5. **Lista de supuestos** explícita.
6. **Una recomendación de stack** (no dejar opciones abiertas — el sponsor quiere una decisión).

---

## 4. Material reutilizable del borrador `.docx (1)`

El equipo ya hizo trabajo previo sobre proveedores. El `.docx (1)` (borrador anterior) contiene una sección "HERRAMIENTAS CONCRETAS (ARGENTINA + COSTOS)" que **NO migró al V2**. Es oro para vos.

### 4.1 Lo que el `.docx (1)` ya tiene listo

Texto literal del borrador (resumido):

#### A. Chatbot + WhatsApp
- Opciones: Meta WhatsApp Business API + integrador, Botmaker (Argentina), Aivo, Zenvia, Twilio + WhatsApp API.
- Setup: USD 500 – 3.000.
- Mensajes WhatsApp: ~USD 0,03 – 0,07 por conversación.
- Plataforma: USD 100 – 1.000/mes.
- Recomendación del borrador: **Botmaker o Aivo** (preparados para español y empresas locales).

#### B. Motor RAG (base de conocimiento con IA)
- Opciones: OpenAI API + embeddings, Azure OpenAI, Pinecone / Weaviate (bases vectoriales).
- Uso IA: USD 50 – 500/mes (según volumen).
- Base vectorial: USD 0 – 200/mes.
- Alternativa simple: Notion + IA + API (MVP rápido).

#### C. Clasificación automática
- Opciones: OpenAI (clasificación con prompts), Google Vertex AI, AWS Comprehend.
- Costo: muy bajo (incluido en uso IA).

#### D. Copiloto para agentes
- Opciones: integración con CRM (HubSpot, Salesforce) o sistema propio.
- Herramientas: OpenAI (GPT), Microsoft Copilot.
- Costo: USD 20 – 50 por usuario/mes (SaaS tipo Copilot).

#### E. Automatización de procesos
- Opciones: Make (Integromat), Zapier, n8n (open source).
- Costo: USD 0 a 50/mes.

#### F. Analítica
- Opciones: Power BI, Looker Studio, Dashboards propios.

#### Propuesta en 3 fases (del borrador)

- **Fase 1 (rápida y económica)**: Botmaker + WhatsApp + FAQs automatizadas + integración básica.
- **Fase 2 (diferencial)**: RAG con OpenAI + base técnica + clasificación automática.
- **Fase 3 (madurez)**: Copiloto interno + automatización workflows + Dashboard en Power BI.

### 4.2 Qué hacer con este material

1. **Reutilizá los rangos de precio** como ancla (validá con los snippets de la sección 5 de esta guía).
2. **Adoptá la estructura "fases 1-2-3"** porque enganchá con la sección 7 (cronograma de Santiago) y con la sección 8 (KPIs progresivos).
3. **Profundizá lo que el borrador dejó superficial**: el borrador da rangos amplios ("USD 100-1.000/mes"). Vos tenés que cerrar **una cifra concreta** con justificación.
4. **No copies literal** — el borrador tenía tono conversacional ("Te lo dejo práctico para que puedas defenderlo"). El V2 tiene tono académico/empresarial. Reescribí.

---

## 5. Snippets de pricing verificados (2026)

> **Verificado vía búsqueda web 2026**. Igual: contrastá al momento de cerrar, los proveedores cambian planes y el USD-AR fluctúa.
> Las URLs de respaldo están al final de la sección.

### 5.1 Chatbot + WhatsApp Business

| Proveedor | Pricing 2026 | Notas |
|---|---|---|
| **Botmaker** | Gratis hasta 300 sesiones iniciales; planes desde USD 100/mes hasta USD 1.000+/mes según volumen. Setup WhatsApp Business: USD 99 una vez. Notificaciones: costo transparente WhatsApp + 20% fee de servicio. | Plataforma argentina con 9+ años en mercado. Presencia LATAM. |
| **Aivo** | Custom (no publica pricing). Modelo enterprise. | Líder LATAM, fundada en Argentina (2012). Clientes: Sony, Visa, Movistar, GM. Requiere contacto comercial. |
| **Twilio + WhatsApp API** | USD 0,005 por mensaje (fee Twilio) + fees de Meta por template. Customer service window (24h) sin costo de Meta para utility/free-form. | Más flexible pero requiere desarrollo propio. Mejor TCO si hay equipo técnico interno. |
| **Asisteclick / B2Chat / similares** | USD 16-99/mes por agente | Opciones pyme, menos features enterprise. |
| **Aurora CRM / Aurora IA** | USD 99-179/mes (1-2 agentes IA, 800-10.000 respuestas/mes) | Players locales argentinos. |

### 5.2 Modelos LLM (APIs)

| Proveedor / Modelo | Input (USD / 1M tokens) | Output (USD / 1M tokens) | Notas |
|---|---|---|---|
| **OpenAI GPT-4o** | 2,50 | 10,00 | Mejor calidad/precio para tareas complejas. Cached input 50% off. |
| **OpenAI GPT-4o-mini** | 0,15 | 0,60 | **16× más barato que GPT-4o**. Ideal para clasificación, intent detection. |
| **Anthropic Claude Haiku 4.5** | 1,00 | 5,00 | Rápido y barato, calidad alta para tareas conversacionales. |
| **Anthropic Claude Sonnet 4.6** | 3,00 | 15,00 | Equivalente a GPT-4o en calidad, ligeramente más caro en output. |
| **Anthropic Claude Opus 4.7** | 5,00 | 25,00 | Top tier, reservar para tareas que justifiquen el costo. |

> Batch API (procesamiento asincrónico 24h) en ambos proveedores: **50% off**.
> Output tokens cuestan **5× más** que input — diseñar prompts para minimizar respuestas verbosas.

#### Estimación práctica para Plantium (6.000 conv/mes)

Asumiendo:
- 1 clasificación + 1 generación por conversación.
- Clasificación: GPT-4o-mini con prompt ~500 tokens, output ~50 tokens.
- Generación con RAG: GPT-4o con contexto ~3.000 tokens (input), respuesta ~300 tokens (output).

| Cálculo | Cantidad mensual | Costo USD |
|---|---|---|
| GPT-4o-mini input (clasificación) | 6.000 × 500 = 3M tokens | 3 × 0,15 = 0,45 |
| GPT-4o-mini output (clasificación) | 6.000 × 50 = 300K tokens | 0,3 × 0,60 = 0,18 |
| GPT-4o input (generación) | 6.000 × 3.000 = 18M tokens | 18 × 2,50 = 45,00 |
| GPT-4o output (generación) | 6.000 × 300 = 1,8M tokens | 1,8 × 10 = 18,00 |
| **Total LLM mensual** | | **~USD 64** |

> **Comentario**: el LLM no es el costo dominante. Lo será la plataforma de bot + WhatsApp + soporte. No te obsesiones con afinar tokens — afinar prompts para reducir output (que cuesta 5× input) es la palanca real.

### 5.3 Vector DB (RAG)

| Proveedor | Pricing 2026 | Recomendación caso Plantium |
|---|---|---|
| **Pinecone Serverless** | Free starter; pago: USD 0,33/GB/mes + USD 0,33/1M reads. Plan Builder flat USD 20/mes. | Ideal para piloto (free tier alcanza con ~50k vectores y queries moderadas). |
| **Pinecone Builder** | USD 20/mes flat | Para producción inicial. |
| **Pinecone Standard** | Desde USD 50/mes mínimo | Si crece volumen. |
| **Qdrant Cloud** | Free tier (0,5 vCPU, 1GB RAM); planes desde USD 30/mes. | Alternativa LATAM-friendly. |
| **Qdrant self-hosted** | USD 20-50/mes VPS (Hetzner / DigitalOcean) — hasta 10M vectores | **Mejor TCO si Plantium tiene equipo técnico** que opere el VPS. |
| **Weaviate Cloud (Flex)** | Desde USD 45/mes | Alternativa, ligeramente más cara que Qdrant. |

#### Estimación caso Plantium

Base de conocimiento estimada: manuales de producto + FAQs + histórico de tickets resueltos.

| Documento | Páginas estimadas | Chunks (~500 tokens) | Vectores |
|---|---|---|---|
| Manuales de producto | 500 | 2.500 | 2.500 |
| FAQs | 100 | 500 | 500 |
| Histórico de tickets | 2.000 | 10.000 | 10.000 |
| **Total** | | | **~13.000 vectores** |

13k vectores entra holgado en Pinecone Free / Qdrant Free. **Costo año 1 piloto: USD 0** (free tier).

Cuando crezca a >100k vectores: Pinecone Serverless ~USD 5-15/mes o Qdrant Cloud free tier ampliado.

### 5.4 Automatización / orquestación

| Proveedor | Pricing 2026 | Recomendación |
|---|---|---|
| **Make.com** | Desde USD 9/mes (10k operaciones); planes empresa USD 50-200/mes | Mejor balance precio/poder. 60-70% más barato que Zapier a iguales casos. |
| **Zapier** | USD 20-100/mes business tiers | Más caro pero ecosistema 7.000+ apps. Solo justifica si necesitás integraciones poco comunes. |
| **n8n cloud** | EUR 20-667/mes (por ejecución, no por nodo) | Ventaja: una ejecución cuenta como 1 sin importar nodos. |
| **n8n self-hosted** | USD 5/mes VPS, ejecuciones ilimitadas | **Mejor TCO** si Plantium opera infra. Open source. |

> **Para Plantium**: Make.com para piloto (paga lo justo por operación). Migrar a n8n self-hosted en fase 3 si los volúmenes crecen.

### 5.5 Copiloto interno para agentes

Opciones:

| Opción | Pricing | Notas |
|---|---|---|
| **OpenAI Assistants API** | Costo de uso (tokens). Setup propio. | Más flexible, requiere desarrollo. |
| **Microsoft 365 Copilot** | USD 30 / usuario / mes | Solo si Plantium ya usa entorno Microsoft. |
| **Custom build sobre GPT-4o** | Costo de tokens + desarrollo (40-100 hs) | Mejor integración con CRM custom. |

### 5.6 Analítica / dashboard

| Opción | Pricing | Notas |
|---|---|---|
| **Power BI Pro** | USD 14 / usuario / mes | Si Plantium ya tiene Microsoft 365, suele ser default. |
| **Looker Studio** | Gratis | Google Cloud opcional. |
| **Tableau** | USD 75 / usuario / mes (Creator) | Enterprise, más caro. |

### 5.7 Costos de desarrollo y consultoría AR 2026

Rangos orientativos para presupuestar (verificá tarifas con proveedores reales):

| Concepto | Rango USD |
|---|---|
| Hora dev junior interno | 20-30 |
| Hora dev senior interno | 35-60 |
| Hora consultor externo (pyme local) | 35-80 |
| Hora consultor especializado IA (LATAM remoto) | 50-150 |
| Proyecto chatbot WhatsApp básico (bot rule-based + 1 canal) | 1.500-3.000 |
| Proyecto chatbot WhatsApp con IA gen + integración CRM | 3.500-6.000 (algunos refs dan hasta 5.000) |
| Proyecto enterprise (multi-canal + ERP + IA gen) | 6.000-15.000+ |
| Jornada de capacitación (6-8 hs) | 800-2.000 |

### 5.8 Fuentes de pricing (para citar en bibliografía)

- Botmaker: <https://botmaker.com/en/prices>
- Aivo: <https://www.aivo.co/> (sin pricing público — contacto comercial)
- Twilio WhatsApp: <https://www.twilio.com/en-us/whatsapp/pricing>
- OpenAI API: <https://openai.com/api/pricing/>
- Anthropic Claude API: <https://www.anthropic.com/pricing>
- Pinecone: <https://www.pinecone.io/pricing/>
- Qdrant: <https://qdrant.tech/pricing/>
- Weaviate: <https://weaviate.io/pricing>
- Make.com: <https://www.make.com/en/pricing>
- Zapier: <https://zapier.com/pricing>
- n8n: <https://n8n.io/pricing/>
- Power BI: <https://powerbi.microsoft.com/en-us/pricing/>
- Casos comparativos AR: <https://www.artics.com.ar/cuanto-cuesta-chatbot-ia-para-empresas-argentina/>
- Casos comparativos AR (chatbot WhatsApp 2026): <https://www.aimoova.com/post/chatbot-whatsapp-empresa-precio-cuanto-cuesta-2026>

---

## 6. Plantilla concreta para tu CAPEX/OPEX (para Plantium)

### 6.1 CAPEX propuesto (inversión inicial)

> Llená los `[?]` con números que cierren con sección 5 (Nadia) y sección 8 (Magdalena). Si ROI de Magdalena asume USD 50k de inversión, tu CAPEX debe acercarse a ese número (o explicar la diferencia).

| Rubro | Descripción | Cantidad | Costo unitario (USD) | Total (USD) |
|---|---|---|---|---|
| Setup WhatsApp Business Platform + verificación Meta | One-time | 1 | 99 | 99 |
| Setup Botmaker enterprise | Activación + onboarding | 1 | 1.500 | 1.500 |
| Desarrollo integraciones (Botmaker ↔ CRM Plantium) | Desarrollo custom | 120 hs | 45 | 5.400 |
| Indexación inicial RAG | Procesamiento y embedding de 13k chunks | 1 | 2.000 | 2.000 |
| Desarrollo copiloto interno (módulo CRM) | Custom + integración OpenAI Assistants | 150 hs | 45 | 6.750 |
| Configuración dashboards Power BI | Diseño + conexión datos | 60 hs | 45 | 2.700 |
| Capacitación equipo operativo (12 personas) | 2 jornadas de 6 hs | 2 | 1.500 | 3.000 |
| Capacitación supervisores (3 personas) | 1 jornada + materiales | 1 | 1.200 | 1.200 |
| Consultor externo gestión del cambio | 40 hs distribuidas | 40 | 80 | 3.200 |
| Diseño visual + UX del bot (personalidad Plantium) | Branding conversacional | 1 | 1.500 | 1.500 |
| QA + pruebas de carga | Testing pre go-live | 80 hs | 35 | 2.800 |
| Documentación técnica + manual de operación | Entregables | 1 | 1.500 | 1.500 |
| Buffer 10% (imprevistos) | Reserva | 1 | 3.165 | 3.165 |
| **CAPEX TOTAL** | | | | **~34.814** |

> **Comentario**: este CAPEX (~USD 35k) es **menor** a los USD 50k que asume Magdalena en sección 8. Tenés dos opciones:
>
> 1. **Coordinar con Magdalena** para que ajuste su cálculo a USD 35k (lo que mejora aún más el ROI).
> 2. **Subir tu CAPEX a USD 50k** agregando: más capacitación, infraestructura on-prem (servidor para n8n self-hosted), redundancia, certificaciones de seguridad, presupuesto de contingencia más amplio.
>
> Cualquiera de las dos rutas es defendible — lo importante es que los números cierren entre las secciones.

### 6.2 OPEX propuesto (gasto mensual recurrente)

| Rubro | Descripción | Cantidad | Costo unitario (USD/mes) | Total (USD/mes) |
|---|---|---|---|---|
| Botmaker plan empresa | Plataforma bot | 1 | 600 | 600 |
| WhatsApp Business — conversaciones | 6.000 conv/mes × USD 0,05 promedio | 6.000 | 0,05 | 300 |
| OpenAI API (clasificación + generación) | Ver cálculo 5.2 | — | — | 65 |
| Pinecone Builder | Vector DB managed | 1 | 20 | 20 |
| Make.com plan business | Orquestación | 1 | 50 | 50 |
| Power BI Pro (5 supervisores) | Licencias dashboard | 5 | 14 | 70 |
| Microsoft 365 Copilot (3 agentes piloto) | Copiloto interno | 3 | 30 | 90 |
| Hosting + backups + monitoreo | Infra mínima propia | 1 | 80 | 80 |
| Mantenimiento evolutivo | 12 hs/mes consultor externo | 12 | 60 | 720 |
| Re-indexación RAG (mensual) | Procesamiento incremental | 1 | 50 | 50 |
| Observabilidad / logging | Stack ELK o equivalente | 1 | 30 | 30 |
| **OPEX TOTAL / mes** | | | | **~2.075** |
| **OPEX ANUALIZADO** | | | | **~24.900** |

### 6.3 TCO a 3 años

| Año | CAPEX | OPEX anual | Total año | Acumulado |
|---|---|---|---|---|
| 1 | 34.814 | 24.900 | 59.714 | 59.714 |
| 2 | — | 24.900 | 24.900 | 84.614 |
| 3 | — | 24.900 (no incluye inflación) | 24.900 | 109.514 |

### 6.4 Comparativo TCO vs ahorro

Si el costo operativo actual es USD 216.000/año (sección 3) y la solución reduce 55% (USD 118.800/año, sección 8):

| Año | Ahorro acumulado | TCO acumulado | Ahorro neto acumulado |
|---|---|---|---|
| 1 | 118.800 | 59.714 | 59.086 |
| 2 | 237.600 | 84.614 | 152.986 |
| 3 | 356.400 | 109.514 | 246.886 |

> ROI a 3 años = (Ahorro acumulado - TCO acumulado) / CAPEX × 100 ≈ **709%** a tres años. Año 1 ya cubre la inversión.

---

## 7. Sección 5 (Nadia, parcial) — Cómo destrabar

### 7.1 Estado actual

La sección 5 tiene prosa introductoria, pero los puntos concretos están como **bullets pendientes**:

- Requisitos funcionales — no desarrollados.
- Requisitos no funcionales — no desarrollados.
- Arquitectura — no desarrollada.
- Diagrama de arquitectura — placeholder `[]`.

### 7.2 Qué le podés sugerir a Nadia (sin pisar su trabajo)

1. **Compartile el capítulo 19 de esta guía**, bloque (e) — tiene plantilla ERS y plantilla de arquitectura listas para llenar.
2. **Mandale el capítulo 08 del estudio** (Arquitectura tecnológica organizacional) — tiene el marco teórico que necesita.
3. **Coordiná con ella la lista definitiva de componentes** porque vos los tenés que cotizar en sección 6. Si no se ponen de acuerdo, vas a estar cotizando una cosa y ella documentando otra.
4. **Ofrecete a hacer el diagrama de arquitectura** vos si tenés mejor mano con BPMN / draw.io — es un favor que paga porque tu sección depende de esto.

### 7.3 Lista mínima de componentes que Nadia debería documentar

Basado en la solución propuesta en sección 4 del V2, los componentes son:

1. Capa de canales — WhatsApp Business API + redes sociales.
2. Orquestador conversacional — Botmaker (o equivalente).
3. Clasificador de consultas — modelo LLM (OpenAI / Claude).
4. Motor RAG — LangChain o LlamaIndex.
5. Vector DB — Pinecone / Qdrant.
6. LLM generativo — OpenAI GPT-4o / Claude Sonnet.
7. CRM — sistema actual de Plantium.
8. Copiloto interno — OpenAI Assistants integrado al CRM.
9. Capa de analítica — Power BI.
10. Capa de seguridad y compliance.

---

## 8. Sección 7 (Santiago, vacía) — Cronograma

### 8.1 Qué se espera

Cronograma de implementación con fases, responsables, duración y dependencias. Puede ser GANTT.

### 8.2 Estructura sugerida para Santiago

Tomá el esqueleto de cronograma del **capítulo 19, bloque (g)** y adaptalo así para Plantium:

| Fase | Duración | Responsable interno | Soporte externo |
|---|---|---|---|
| 1. Análisis y descubrimiento | 3 semanas | Jefe Comercial + Jefe Servicio Técnico | Consultor externo |
| 2. Diseño + arquitectura | 3 semanas | Equipo IT Plantium | Arquitecto IA |
| 3. Desarrollo + integración | 10 semanas | Equipo IT Plantium + dev contratado | Botmaker support |
| 4. Indexación RAG + pruebas | 3 semanas | IT + product manager | Especialista RAG |
| 5. Capacitación | 2 semanas | RRHH + IT | Consultor gestión del cambio |
| 6. Piloto (3 personas, 1 canal) | 4 semanas | Equipo comercial seleccionado | Soporte intensivo proveedor |
| 7. Go-live full | 1 semana | Todo el equipo + sponsor | War room técnico |
| 8. Estabilización | 6 semanas | IT + supervisor operaciones | Mantenimiento evolutivo |

**Duración total**: ~32 semanas (~7 meses).

### 8.3 Hitos clave

- **Hito 0**: Kickoff (semana 1).
- **Hito 1**: Aprobación de arquitectura y proveedores (semana 6).
- **Hito 2**: Demo MVP funcional (semana 14).
- **Hito 3**: Inicio piloto (semana 22).
- **Hito 4**: Go-live full (semana 26).
- **Hito 5**: Revisión KPIs 30/60/90 días post go-live.

### 8.4 Herramientas que Santiago puede usar para el GANTT

- **Google Sheets** — simple, todos lo abren. Plantilla con formato condicional.
- **GanttProject** — gratis, genera visualización profesional.
- **ClickUp / Notion** — si el grupo ya las usa.

---

## 9. Pendientes transversales

### 9.1 Diagramas (3 placeholders `[]`)

#### Diagrama 3.3 — AS IS

**Qué representar**: el flujo actual del proceso de atención al cliente (manual, no escalable).

**Insumos**: la descripción en prosa que ya está en sección 3 + cuellos de botella identificados.

**Recomendación**: usar **bpmn.io** (gratis, sin login). Exportar como SVG y como PNG (1080p mínimo).

**Diagrama base sugerido** (basado en el ASCII del borrador `.docx (1)`):

```
Cliente → WhatsApp / Redes
   ↓
Empleado recibe mensaje
   ↓
Interpreta consulta manualmente
   ↓
Busca info (manuales / compañeros)
   ↓
Responde al cliente
   ↓
(Si no sabe) → Escala a otro sector
   ↓
Respuesta final / Cierre
```

Convertir esto a BPMN con: 1 lane "Cliente", 1 lane "Operador atención", 1 lane "Especialista técnico", gateways para "¿conoce respuesta?" y "¿requiere escalamiento?".

#### Diagrama 4.3 — TO BE

**Qué representar**: el flujo propuesto con IA insertada en cada punto crítico.

**Diagrama base** (también del borrador):

```
Cliente → WhatsApp / Redes
   ↓
🤖 IA recibe mensaje
   ↓
🧠 Clasifica consulta automáticamente
   ↓
📚 Consulta base de conocimiento (RAG)
   ↓
💬 Responde automáticamente (si aplica)
   ↓
🙋 Escala a humano (solo si es complejo)
   ↓
👨‍💻 Agente usa copiloto IA para responder mejor
```

Convertir a BPMN con lanes nuevos: "Cliente", "IA conversacional", "RAG / Knowledge base", "Agente humano + copiloto", "Backoffice".

#### Diagrama de arquitectura (sección 5)

**Qué representar**: las capas tecnológicas y cómo se interconectan (no el flujo del proceso — eso ya está en TO BE).

**Ejemplo de capas**:

```
┌──────────────────────────────────────┐
│ Capa de canales                       │
│ (WhatsApp Business + Redes)          │
└──────────────┬───────────────────────┘
               │
┌──────────────▼───────────────────────┐
│ Plataforma de bot (Botmaker)         │
│ + Clasificador (GPT-4o-mini)         │
└──────┬─────────────────────┬─────────┘
       │                     │
┌──────▼─────────┐  ┌────────▼──────────┐
│ Motor RAG       │  │ CRM Plantium      │
│ (LangChain)    │  │ + Copiloto interno│
└──────┬─────────┘  └────────┬──────────┘
       │                     │
┌──────▼─────────┐  ┌────────▼──────────┐
│ Vector DB       │  │ Dashboards        │
│ (Pinecone)     │  │ (Power BI)        │
└────────────────┘  └───────────────────┘

         ┌─────────────────────┐
         │ Capa de seguridad   │  (transversal)
         │ Logging + DPA + KMS │
         └─────────────────────┘
```

**Herramienta sugerida**: draw.io / diagrams.net (mejor para diagramas de arquitectura tipo capas).

### 9.2 Resumen ejecutivo (1 hoja, OBLIGATORIO)

No existe en el V2. Hay que crearlo. Plantilla en el **capítulo 19, Apéndice A.1**.

**Quién lo escribe**: idealmente el coordinador/a o editor/a, en la última semana, cuando todas las secciones estén consolidadas.

**Por qué importa**: es lo primero que lee el evaluador. Si el resumen está flojo, predispone mal toda la lectura.

### 9.3 Limpieza de artefactos LaTeX (sección 8)

Magdalena tiene fórmulas como:
```
6000×15=900006000 \tiempo 15 = 900006000×15=90000
```

Estos son **artefactos de copia desde un editor LaTeX** (Word / Docs no renderiza LaTeX nativo). Hay que limpiarlos.

**Opciones**:

1. **Reescribir en texto plano** con notación markdown:
   ```
   6.000 conversaciones × 15 minutos = 90.000 minutos
   ```

2. **Usar el editor de ecuaciones de Word/Google Docs**: insertar como objeto matemático nativo.

3. **Exportar como imagen** desde un renderizador LaTeX online (overleaf.com) y pegarla en el documento.

**Recomendación**: opción 1 (texto plano con formato). Es lo más simple y se lee bien.

**Fórmulas que faltan renderizar** (en placeholders `[]` de las secciones 2.4, 2.5, 2.6 de la sección 8):

- Fórmula del ROI: `ROI (%) = (Beneficio neto / Inversión) × 100`
- Cálculo del ROI proyectado: `ROI = (118.800 - 0) / 50.000 × 100 = 237%` — verificar con cálculo real (el V2 dice 137,6%).
- Payback: `Payback (meses) = Inversión / Beneficio mensual = 50.000 / (118.800/12) = 5,05 meses` ≈ 5-6 meses.

> **Detectado**: hay inconsistencia. El V2 dice "ROI 137,6%" pero con los números base (USD 118.800 ahorro, USD 50k inversión) el cálculo da 237%. Coordiná con Magdalena cuál es la fórmula correcta. Posiblemente Magdalena restó el OPEX anual del beneficio antes de calcular.

---

## 10. Coherencia narrativa entre secciones (revisión cruzada)

Antes de cerrar el documento, verificá que estos números cuadren entre secciones:

| Dato | Sección 3 (AS IS) | Sección 6 (vos) | Sección 8 (ROI) | OK? |
|---|---|---|---|---|
| Volumen consultas/mes | 6.000 | 6.000 (base cálculo) | 6.000 | □ |
| Tasa de automatización meta | (no aparece) | 60% (supuesto) | 60% (KPI 1.6) | □ |
| Inversión total (CAPEX) | — | USD ~35k o 50k según ajuste | USD 50k | □ |
| OPEX anual | — | USD ~25k | (no aparece explícito) | □ |
| Ahorro anual estimado | — | (no es tu rol calcular) | USD 118.800 | □ |
| ROI proyectado año 1 | — | (no es tu rol) | 137,6% (a verificar) | □ |
| Payback | — | (no es tu rol) | 5-6 meses | □ |
| Tipo de cambio asumido | — | (declarar) | (declarar) | □ |

Pasá esta checklist con Magdalena y Lourdes para validar.

---

## 11. Checklist de cierre del Trabajo Final V2

### Contenido

- [ ] **Sección 6** (vos) redactada con tabla comparativa de proveedores + CAPEX + OPEX + TCO 3 años + supuestos.
- [ ] **Sección 5** (Nadia) completa con RF + RNF + arquitectura + diagrama.
- [ ] **Sección 7** (Santiago) con cronograma + responsables + hitos.
- [ ] **Diagrama AS IS** (3.3) reemplazando placeholder.
- [ ] **Diagrama TO BE** (4.3) reemplazando placeholder.
- [ ] **Diagrama de arquitectura** (sección 5).
- [ ] **Resumen ejecutivo** de 1 hoja creado y pegado al inicio.
- [ ] **Artefactos LaTeX limpiados** en sección 8.
- [ ] **Fórmulas en placeholders `[]`** de sección 8 reemplazadas por texto plano o ecuaciones.
- [ ] **Coherencia numérica** verificada entre secciones 3, 6 y 8.
- [ ] **Bibliografía** consolidada con fuentes de pricing (sección 5.8 de esta guía) + benchmarks (John Deere, Trimble, Syngenta).

### Formato

- [ ] Resumen ejecutivo en 1 hoja (no se pasa).
- [ ] Desarrollo (secciones 1-8) no excede 12 hojas. Si excede, mover material a anexos.
- [ ] Anexos identificados claramente.
- [ ] Portada con nombre del trabajo, integrantes (Lourdes, Milena, Nadia, Javier, Santiago, Magdalena), cohorte, fecha.
- [ ] Índice / tabla de contenidos.
- [ ] Numeración de páginas.
- [ ] Tipografía y tamaños homogéneos.
- [ ] Tablas y figuras numeradas con título y fuente.

### Última semana

- [ ] **Editor/a designado/a** pasa lectura completa por coherencia narrativa.
- [ ] Corrector ortográfico ejecutado.
- [ ] PDF final generado y validado en otra computadora (a veces fuentes / imágenes se rompen).
- [ ] Versión editable guardada en backup compartido.
- [ ] Subido al Campus Virtual UNRaf por **uno** del equipo (1 entrega por grupo).
- [ ] Captura de confirmación de entrega guardada.

---

## 12. Cierre — Recordatorios prácticos para Javier

1. **Tu sección está vacía pero no estás solo**: el `.docx (1)` te dejó la mayor parte del trabajo de investigación hecho. Tu valor es **profundizar, validar números 2026 y dar una recomendación concreta** (no rangos abiertos).
2. **Coordiná los números con Magdalena**: USD 50k de inversión vs los USD 35k que sale el CAPEX detallado. Eligen uno y lo defienden juntos.
3. **No te pelees con Nadia por la sección 5**: ofrecele plantillas (cap. 19 bloque e) y ayudala con el diagrama. Cuanto antes ella cierre RF/RNF/arquitectura, antes podés vos cerrar la cotización.
4. **El benchmark John Deere/Trimble/Syngenta es tu aliado**: cuando defendás "elegimos Botmaker + OpenAI + Pinecone", apoyate en que "es el patrón que adoptaron los líderes del sector".
5. **Declará todos los supuestos**: tipo de cambio, volumen, tarifa hora, tasa de automatización. Un docente que ve números sin supuestos asume que están inventados.
6. **No te obsesiones con precios milimétricos**: rangos razonables con sensibilidad son más defendibles que precisión falsa.
7. **Buffer 10% siempre**: en presupuestos reales se mete contingencia. Hacelo también acá.
8. **Antes de entregar**, leé el documento entero **una vez de corrido**. Si te suena Frankenstein, llamá al editor/a.

> **Última recomendación**: marcate un **deadline interno del 09/06/2026** (una semana antes del 16/06). Esa última semana es para que el editor/a pula el documento, no para que vos sigas escribiendo. Si llegás con contenido nuevo a esa semana, el documento va a salir mal cosido.

---

## Fuentes consultadas

- Borrador previo: `Trabajo final Diplomatura IA(1).docx`
- Versión actual: `Trabajo final Diplomatura IA-TO V2.docx`
- Consigna oficial: `TPI_5tacohorte-1.pdf`
- Pricing 2026 verificado vía búsqueda web (mayo 2026):
  - Botmaker: <https://botmaker.com/en/prices>
  - Aivo: <https://www.aivo.co/>
  - Twilio WhatsApp: <https://www.twilio.com/en-us/whatsapp/pricing>
  - OpenAI API: <https://openai.com/api/pricing/>
  - Anthropic Claude: <https://www.anthropic.com/pricing>
  - Pinecone: <https://www.pinecone.io/pricing/>
  - Qdrant: <https://qdrant.tech/pricing/>
  - Weaviate: <https://weaviate.io/pricing>
  - Make.com: <https://www.make.com/en/pricing>
  - Zapier: <https://zapier.com/pricing>
  - n8n: <https://n8n.io/pricing/>
  - Power BI: <https://powerbi.microsoft.com/en-us/pricing/>
- Casos de pricing AR 2026:
  - <https://www.artics.com.ar/cuanto-cuesta-chatbot-ia-para-empresas-argentina/>
  - <https://www.aimoova.com/post/chatbot-whatsapp-empresa-precio-cuanto-cuesta-2026>
  - <https://asisteclick.com/blog/chatbot-whatsapp-precio-empresas/>

---

[← 19 — Guía paso a paso del TPI](19-guia-tpi.md) · [Volver al índice](README.md)
