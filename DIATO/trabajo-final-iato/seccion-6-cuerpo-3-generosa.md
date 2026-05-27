# 6. Análisis de proveedores y costos

**Responsable: Javier Zader**

> **Versión GENEROSA (~4-5 páginas)** — cuerpo completo con criterios, componentes, costos, supuestos y riesgos. El análisis comparativo por componente con matrices de scoring (Anexo A), el impacto fiscal argentino y la sensibilidad por volumen (Anexo B) y el cumplimiento de la Ley 25.326 (Anexo C) se desarrollan en el **Anexo 6** ([versión completa publicada](https://jnzader.github.io/unraf/trabajo-final-iato/seccion-6-v3-fix2-final.html)).

## 6.1 Introducción

La solución de la Sección 5 articula un asistente sobre WhatsApp, una arquitectura RAG, clasificación automática, un copiloto interno y una capa de analítica. Cada bloque requiere proveedores con modelos de precios diferenciales que deben evaluarse según el contexto de Plantium. El análisis se ancla en los volúmenes de la Sección 8: ≈6.000 conversaciones mensuales, costo operativo anual actual de USD 216.000 y meta de automatización del 70%. Sobre esa base se identifican proveedores por componente, se comparan con criterios ponderados, se propone un stack de referencia y se desagrega la inversión en CAPEX y OPEX, complementando el ROI de la Sección 8.

**Definiciones operativas clave**: se usa **mensaje** como unidad económica de cobro (WhatsApp migró al modelo per-mensaje en julio de 2025), **conversación** como unidad de dimensionamiento del negocio (5-8 mensajes), y **ventana de servicio** para los mensajes gratuitos dentro de las 24 h iniciadas por el cliente — central para Plantium, cuya atención post-venta es mayormente customer-initiated.

## 6.2 Criterios de selección de proveedores

Siete criterios ponderados según la realidad de una PyME industrial argentina, priorizando integración y presencia local:

| # | Criterio | Peso |
|---|---|---:|
| 1 | Presencia y soporte en Argentina/LATAM (idioma, huso, facturación local) | 15% |
| 2 | Madurez del producto (años, casos publicados, clientes referenciables) | 15% |
| 3 | Pricing transparente (preferencia por pago por uso en piloto) | 10% |
| 4 | Capacidad de integración (CRM, WhatsApp Business API, eventual ERP) | 20% |
| 5 | Cumplimiento Ley 25.326 (residencia configurable, DPA, opt-out de training) | 15% |
| 6 | Escalabilidad (de 6.000 a 15.000 conv/mes sin cambios estructurales) | 10% |
| 7 | TCO a 3 años, no solo costo inicial | 15% |

## 6.3 Componentes de la solución

La arquitectura se descompone en **ocho componentes** que requieren proveedor externo: canal de mensajería (WhatsApp), plataforma de bot y orquestación, motor LLM, base vectorial para RAG, plataforma de automatización (iPaaS), infraestructura de hosting, copiloto interno para agentes y capa de analítica. Los tres primeros son de criticidad **alta** (punto de contacto, corazón operativo y capa de inteligencia); el resto, criticidad **media** (habilitadores y soporte transversal).

## 6.4 Stack tecnológico recomendado

| Componente | Proveedor recomendado | Justificación (síntesis) |
|---|---|---|
| Canal WhatsApp | **Twilio (vía Botmaker)** | Botmaker gestiona la integración como BSP oficial; se elimina la doble factura. |
| Plataforma de bot | **Botmaker** | Empresa argentina, facturación local, soporte en español, 9+ años, WhatsApp BSP nativo. |
| Motor LLM | **OpenAI GPT-4o-mini (80%) + GPT-4o (20%)** | Mejor relación calidad/precio; el mix controla costos manteniendo calidad en consultas complejas. |
| Embeddings | **OpenAI text-embedding-3-small** | Mejor costo/calidad multilingüe; integración natural con el stack OpenAI. |
| Vector DB | **Pinecone Serverless (Free → Builder)** | Free tier para el piloto; Builder (USD 20/mes) en producción, sin operar infraestructura. |
| Automatización iPaaS | **Make.com (Business)** | Mejor balance precio/capacidad; migrable a n8n self-hosted en Fase 3. |
| Copiloto interno | **OpenAI Assistants API + CRM** | Aprovecha la inversión OpenAI; integración profunda con el CRM existente. |
| Hosting backend | **DigitalOcean** | Pricing predecible y simple, suficiente para los servicios custom previstos. |
| Analítica | **Power BI Pro** | Se asume Microsoft 365 presente (validar con IT); Microsoft factura local con IVA. |

> El análisis comparativo detallado por componente (alternativas, costos por proveedor, matrices de scoring ponderadas, TCO comparativo a 3 años) se desarrolla en el **Anexo 6.A**.

## 6.5 Estimación de costos

### 6.5.1 CAPEX (inversión inicial, one-time)

| Concepto | Monto USD |
|---|---:|
| Desarrollo de integraciones (Botmaker↔CRM, copiloto, dashboards Power BI) | 17.100 |
| Setup y onboarding (WhatsApp, Botmaker enterprise, infraestructura DigitalOcean) | 3.600 |
| Indexación y vectorización RAG (chunking, embeddings, QA) | 3.000 |
| UX conversacional del bot | 2.500 |
| Capacitación (12 operativos + 3 supervisores) + consultoría de gestión del cambio | 7.700 |
| Testing/QA + documentación técnica | 5.600 |
| **Subtotal antes de contingencia** | **39.500** |
| Contingencia (15%) | 5.925 |
| **CAPEX detallado** | **45.425** |
| Ajuste de coherencia con Sección 8 (licencias adicionales, gap-analysis ISO 27001, reserva de tarifa) | 4.575 |
| **CAPEX de referencia (Sección 8)** | **50.000** |

> **Reconciliación con Sección 8**: el CAPEX detallado llega a USD 45.425; la Sección 8 asume USD 50.000. La brecha de USD 4.575 se compone de licencias no proyecto-específicas (~USD 2.000), un gap-analysis de ISO 27001 (USD 1.500, diagnóstico, no certificación full) y reserva de tarifa (USD 1.075). Se adopta USD 50.000 como referencia por coherencia con la Sección 8. El desglose línea por línea (15 partidas) está en el **Anexo 6.A**.

### 6.5.2 OPEX (recurrente)

| Concepto | USD/mes | USD/año |
|---|---:|---:|
| Plataforma de bot (Botmaker) | 600 | 7.200 |
| WhatsApp/Twilio (per-mensaje, ventana de servicio gratuita) | 360 | 4.320 |
| Mantenimiento evolutivo año 1 (estabilización) | 840 | 10.080 |
| LLM + copiloto + embeddings (OpenAI) | 155 | 1.860 |
| Hosting (DigitalOcean) + Power BI + iPaaS + vector DB + observabilidad | 253 | 3.036 |
| Capacitación continua | 100 | 1.200 |
| **Total OPEX nominal** | **2.308** | **27.696** |

> El LLM nominal es de ~USD 16/mes; se reserva un techo de USD 65/mes (4×) como contingencia por crecimiento y repricing. El detalle completo de las 12 partidas OPEX está en el **Anexo 6.A**.

### 6.5.3 Inversión total y TCO

- **Año 1 (nominal)**: USD 50.000 (CAPEX) + USD 27.696 (OPEX) = **USD 77.696**.
- **TCO a 3 años**: el mantenimiento baja de USD 10.080 a USD 6.000 desde el año 2 → **USD 124.928** nominal.
- **Carga fiscal argentina**: el OPEX efectivo en pesos sube a ~USD 32.304/año (coeficiente 1,5× sobre proveedores extranjeros por IVA + percepción Ganancias + spread cambiario). El detalle está en el **Anexo 6.B**.

### 6.5.4 Retorno de la inversión — cinco lecturas

El costo AS IS es de USD 216.000/año. Con 70% de automatización, el ahorro es de **USD 118.800/año** (55% del costo actual).

| Métrica | Fórmula | Valor |
|---|---|---:|
| ROI sobre CAPEX (convención clásica, alineada con Sección 8) | (118.800 − 50.000) / 50.000 | **137,6%** |
| ROI sobre inversión total año 1 | (118.800 − 77.696) / 77.696 | 52,9% |
| Beneficio neto operativo año 1 | 118.800 − 50.000 − 27.696 | USD 41.104 |
| Payback bruto (sobre CAPEX) | 50.000 / (118.800/12) | 5,05 meses |
| Payback neto (descontando OPEX) | 50.000 / (9.900 − 2.308) | 6,59 meses |

**Interpretación honesta**: las cinco métricas son verdaderas y miden cosas distintas; ninguna invalida a las otras. El 137,6% que reporta la Sección 8 responde a la convención clásica de retorno sobre CAPEX, donde el OPEX es costo operativo del nuevo sistema. Esta sección lo complementa con las lecturas que incorporan el OPEX, dando al directorio un panorama transparente y conservador.

**Por qué 70% de automatización rinde 55% de ahorro**: las consultas no automatizadas (30%) son las más complejas y consumen más costo por caso, y existen costos fijos de supervisión que no bajan linealmente. El ahorro libera **6,3 FTE de capacidad bruta** (4,95 FTE costo-equivalentes) del equipo técnico, reasignables a ventas consultivas, mantenimiento proactivo y capacitación de clientes.

## 6.6 Supuestos clave

1. Volumen base: 6.000 conversaciones/mes (~42.000 mensajes), consistente con Sección 8.
2. Automatización objetivo: 70% sin escalado humano (Sección 8, KPI 1.6).
3. Mix LLM: 80% GPT-4o-mini + 20% GPT-4o.
4. WhatsApp como único canal en año 1, modelo per-mensaje con aprovechamiento de la ventana de servicio.
5. Precios en USD según pricing público de proveedores (mayo 2026).
6. Hora de desarrollador: USD 45/h; consultoría especializada USD 60-80/h.
7. Base RAG: ~13.000 vectores (cabe en el free tier de Pinecone).
8. Mantenimiento: año 1 ~22% del CAPEX; años 2-3 ~12% (USD 6.000/año).
9. El TCO base asume precios USD planos; el contexto inflacionario AR puede elevarlo 25-35% a 3 años (a contemplar en la presupuestación).
10. Se asume Microsoft 365 presente y CRM cloud-native con API REST (a validar en discovery; un CRM legacy sumaría 80-150 h, USD 3.600-6.750).

## 6.7 Riesgos principales del modelo

| Riesgo | Prob. | Impacto | Mitigación |
|---|---|---|---|
| Devaluación del peso frente al USD | Alta | Alto | Plan anual pre-pagado (fija precio USD 12 meses), reserva en USD, revisión semestral con perspectiva FX. |
| Cambios de pricing WhatsApp Business | Alta | Alto | Modelo per-mensaje vigente; BSP de respaldo (360dialog/Meta directo) preconfigurado; modelar escenario +50%. |
| Volumen duplicado en temporada de cosecha | Alta | Medio | Pricing variable absorbe el crecimiento sin re-arquitectura; el ROI **mejora** en años de buena cosecha (Anexo 6.B). |
| Aumento de pricing OpenAI/Anthropic | Media | Medio | Multi-LLM con capa de abstracción (fallback Claude/Gemini); buffer 4× en OPEX. |
| Datos sensibles fuera de jurisdicción AR | Media | Medio | Anonimización en cliente, retención corta, DPA por proveedor; opción Vertex AI región São Paulo. |
| Lock-in con Botmaker | Media | Medio | Capa de abstracción sobre su API; costo de exit estimado USD 5.000-8.000; evaluar en mes 12. |

## 6.8 Conclusión

El stack se construyó priorizando **presencia local y soporte en español** (Botmaker como ancla del canal y la plataforma de bot), **transparencia de pricing y TCO controlable** (OpenAI mix 80/20, Pinecone free→Builder, DigitalOcean, Make.com) y **cumplimiento de la Ley 25.326** (proveedores con DPA, anonimización en cliente, residencia configurable). Permite iniciar el piloto con bajo riesgo financiero, escalar a producción cloud-native y evolucionar componentes individuales (por ejemplo, migrar a n8n self-hosted en Fase 3) sin reescribir el sistema.

El enfoque —datos centralizados, automatización conversacional, integración profunda con CRM y analítica embebida— está alineado con los referentes globales del sector (John Deere, Trimble, Syngenta); las herramientas difieren por escala, adoptando el mismo paradigma con tooling apropiado para una PyME industrial de 250 empleados. Desde lo estratégico, la inversión habilita la escalabilidad de la atención (hasta 15.000 conv/mes sin re-arquitectura), libera capacidad del equipo para tareas de mayor valor, convierte el conocimiento en un activo reutilizable (la base RAG se enriquece con cada ticket) y posiciona a Plantium en una madurez digital comparable a sus referentes, con un ticket de inversión adecuado a su escala. Las cinco lecturas del retorno ofrecen al directorio un panorama transparente; aun con la carga fiscal argentina, el ROI sobre inversión total se mantiene en torno al 44% y el payback neto en ~7 meses (Anexo 6.B), confirmando la viabilidad financiera del proyecto.
