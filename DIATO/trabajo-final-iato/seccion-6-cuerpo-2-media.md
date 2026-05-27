# 6. Análisis de proveedores y costos

**Responsable: Javier Zader**

> **Versión MEDIA (~2-3 páginas)** — pensada para el cuerpo del trabajo. El evaluador entiende la decisión completa sin ir al anexo. El análisis comparativo por componente (matrices de scoring), el impacto fiscal argentino, la sensibilidad por volumen y el cumplimiento de la Ley 25.326 se desarrollan en el **Anexo 6** ([versión completa publicada](https://jnzader.github.io/unraf/trabajo-final-iato/seccion-6-v3-fix2-final.html)).

A partir de la arquitectura definida en la Sección 5 y los volúmenes de la Sección 8 (≈6.000 conversaciones mensuales, costo operativo anual actual de USD 216.000 y meta de automatización del 70%), esta sección identifica los proveedores por componente, propone un stack de referencia y desagrega la inversión en CAPEX (inicial) y OPEX (recurrente), complementando el ROI de la Sección 8.

## 6.1 Criterios de selección de proveedores

Cada componente se evaluó con siete criterios ponderados según la realidad de una PyME industrial argentina, priorizando integración y presencia local:

| # | Criterio | Peso |
|---|---|---:|
| 1 | Presencia y soporte en Argentina/LATAM | 15% |
| 2 | Madurez del producto | 15% |
| 3 | Pricing transparente (pago por uso) | 10% |
| 4 | Capacidad de integración (CRM, WhatsApp, ERP) | 20% |
| 5 | Cumplimiento Ley 25.326 (DPA, residencia, opt-out) | 15% |
| 6 | Escalabilidad (6.000 → 15.000 conv/mes) | 10% |
| 7 | TCO a 3 años | 15% |

## 6.2 Stack tecnológico recomendado

| Componente | Proveedor recomendado | Justificación |
|---|---|---|
| Canal WhatsApp | **Twilio (vía Botmaker)** | BSP oficial gestionado por Botmaker; elimina la doble factura. |
| Plataforma de bot | **Botmaker** | Empresa argentina, facturación local, soporte en español, 9+ años, integra WhatsApp BSP nativo. |
| Motor LLM | **OpenAI GPT-4o-mini (80%) + GPT-4o (20%)** | Mejor relación calidad/precio; el mix controla costos sin perder calidad en consultas complejas. |
| Embeddings | **OpenAI text-embedding-3-small** | Mejor costo/calidad multilingüe; consistencia con el stack OpenAI. |
| Vector DB | **Pinecone Serverless (Free → Builder)** | Free tier para el piloto; Builder (USD 20/mes) en producción, sin operar infraestructura. |
| Automatización iPaaS | **Make.com (Business)** | Mejor balance precio/capacidad; migrable a n8n en Fase 3. |
| Copiloto interno | **OpenAI Assistants API + CRM** | Aprovecha la inversión OpenAI; integración profunda con el CRM. |
| Hosting backend | **DigitalOcean** | Pricing predecible, simple para una PyME. |
| Analítica | **Power BI Pro** | Se asume Microsoft 365 presente; Microsoft factura local con IVA, reduciendo el impacto cambiario. |

> Las matrices de scoring ponderadas, las alternativas evaluadas por componente y el TCO comparativo están en el **Anexo 6.A**.

## 6.3 Inversión estimada: CAPEX y OPEX

**CAPEX (inversión inicial, one-time)** — principales partidas:

| Concepto | Monto USD |
|---|---:|
| Desarrollo de integraciones (CRM, copiloto, dashboards, conectores) | ~21.000 |
| Indexación y vectorización RAG (chunking, embeddings, QA) | ~3.000 |
| Capacitación y gestión del cambio (15 personas) | ~7.700 |
| UX conversacional, testing/QA y documentación | ~8.100 |
| Setup (WhatsApp, Botmaker, infraestructura) | ~3.600 |
| **Subtotal antes de contingencia** | **39.500** |
| Contingencia (15%) | 5.925 |
| **CAPEX detallado** | **45.425** |
| Ajuste de coherencia con Sección 8 (licencias, gap-analysis ISO 27001, reserva de tarifa) | 4.575 |
| **CAPEX de referencia (Sección 8)** | **50.000** |

**OPEX (recurrente)** — total mensual **≈ USD 2.308** (USD 27.696/año):

| Concepto | USD/mes |
|---|---:|
| Plataforma Botmaker | 600 |
| WhatsApp/Twilio (modelo per-mensaje, ventana de servicio gratuita) | 360 |
| Mantenimiento evolutivo año 1 (estabilización) | 840 |
| Copiloto + LLM + embeddings (OpenAI) | 155 |
| Hosting, Power BI, iPaaS, vector DB, observabilidad | 253 |
| Capacitación continua | 100 |
| **Total OPEX nominal** | **2.308** |

**Inversión total año 1**: USD 50.000 (CAPEX) + USD 27.696 (OPEX) = **USD 77.696**.
**TCO a 3 años** (mantenimiento baja de USD 10.080 a USD 6.000 desde el año 2): **USD 124.928**.

> El desglose CAPEX línea por línea (15 partidas), el detalle OPEX completo y el ajuste fiscal argentino (OPEX efectivo ≈ USD 32.304/año) están en el **Anexo 6.A y 6.B**.

## 6.4 Retorno de la inversión

El costo operativo actual (AS IS) es de USD 216.000/año. Con 70% de automatización, el ahorro estimado es de **USD 118.800/año** (55% del costo actual). Se presentan cinco lecturas complementarias del retorno:

| Métrica | Valor |
|---|---:|
| ROI sobre CAPEX (convención clásica, alineada con Sección 8) | **137,6%** |
| ROI sobre inversión total año 1 (incluye OPEX) | 52,9% |
| Beneficio neto operativo año 1 | USD 41.104 |
| Payback bruto (sobre CAPEX) | 5,05 meses |
| Payback neto (descontando OPEX) | 6,59 meses |

**Interpretación honesta**: las cinco métricas son verdaderas y miden cosas distintas; ninguna invalida a las otras. El 137,6% que reporta la Sección 8 responde a la convención clásica de retorno sobre CAPEX; esta sección lo complementa con las lecturas que incorporan el OPEX, dando al directorio un panorama transparente.

**Ahorro en personal**: el ahorro libera **6,3 FTE de capacidad bruta** (4,95 FTE costo-equivalentes) del equipo técnico, reasignables a ventas consultivas, mantenimiento proactivo y capacitación de clientes.

> El por qué 70% de automatización rinde 55% de ahorro (consultas no automatizadas más complejas + costos fijos de supervisión), la distinción FTE bruto vs costo-equivalente y el análisis de sensibilidad por volumen se desarrollan en el **Anexo 6.B**.

## 6.5 Riesgos principales del modelo

| Riesgo | Prob. | Impacto | Mitigación |
|---|---|---|---|
| Devaluación del peso frente al USD | Alta | Alto | Plan anual pre-pagado (fija precio USD 12 meses), reserva en USD, revisión semestral. |
| Cambios de pricing WhatsApp | Alta | Alto | Modelo per-mensaje vigente; BSP de respaldo (360dialog/Meta) preconfigurado. |
| Volumen duplicado en cosecha | Alta | Medio | Pricing variable absorbe el crecimiento; el ROI **mejora** en años de buena cosecha (ver Anexo 6.B). |
| Datos sensibles fuera de AR | Media | Medio | Anonimización en cliente, retención corta, DPA por proveedor; opción Vertex AI región São Paulo. |

## 6.6 Conclusión

El stack se construyó priorizando **presencia local y soporte en español** (Botmaker como ancla), **transparencia de pricing y TCO controlable** (OpenAI mix 80/20, Pinecone free→Builder, DigitalOcean, Make.com) y **cumplimiento de la Ley 25.326**. Permite iniciar el piloto con bajo riesgo financiero, escalar a producción cloud-native y evolucionar componentes individuales sin reescribir el sistema.

La inversión no es solo optimización de costos: habilita la escalabilidad de la atención (hasta 15.000 conv/mes sin re-arquitectura), libera capacidad del equipo para tareas de mayor valor, convierte el conocimiento en un activo reutilizable (la base RAG se enriquece con cada ticket) y posiciona a Plantium en una madurez digital comparable a sus referentes del sector, con un ticket de inversión adecuado a su escala.
