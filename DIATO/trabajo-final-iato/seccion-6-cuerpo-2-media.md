# 6. Análisis de proveedores y costos

**Responsable: Javier Zader**

A partir de la arquitectura definida en la Sección 5 y los volúmenes establecidos en la Sección 8 (aproximadamente 6.000 conversaciones mensuales, costo operativo anual actual de USD 216.000 y meta de automatización del 70%), esta sección identifica los proveedores por componente, propone un stack tecnológico de referencia y desagrega la inversión en CAPEX (inversión inicial) y OPEX (costo recurrente), complementando el retorno proyectado en la Sección 8.

## 6.1 Criterios de selección de proveedores

Cada componente se evaluó mediante siete criterios ponderados según la realidad de una PyME industrial argentina, priorizando la integración y la presencia local:

| # | Criterio | Peso |
|---|---|---:|
| 1 | Presencia y soporte en Argentina o LATAM | 15% |
| 2 | Madurez del producto | 15% |
| 3 | Transparencia del modelo de precios (pago por uso) | 10% |
| 4 | Capacidad de integración (CRM, WhatsApp, ERP) | 20% |
| 5 | Cumplimiento de la Ley 25.326 (contrato de tratamiento de datos, residencia, exclusión de entrenamiento) | 15% |
| 6 | Escalabilidad (de 6.000 a 15.000 conversaciones mensuales) | 10% |
| 7 | Costo total de propiedad a 3 años | 15% |

## 6.2 Stack tecnológico recomendado

| Componente | Proveedor recomendado | Fundamento |
|---|---|---|
| Canal WhatsApp | **Twilio (vía Botmaker)** | Botmaker gestiona la integración como proveedor oficial (BSP); se elimina la doble facturación. |
| Plataforma de bot | **Botmaker** | Empresa argentina, facturación local, soporte en español, más de 9 años en el mercado e integración nativa de WhatsApp. |
| Motor LLM | **OpenAI GPT-4o-mini (80%) + GPT-4o (20%)** | Mejor relación calidad/precio; la combinación controla los costos sin perder calidad en consultas complejas. |
| Generación de embeddings | **OpenAI text-embedding-3-small** | Mejor relación costo/calidad multilingüe; consistencia con el resto del stack OpenAI. |
| Base vectorial | **Pinecone Serverless (capa gratuita → plan Builder)** | La capa gratuita cubre el piloto; el plan Builder (USD 20/mes) se adopta en producción, sin administrar infraestructura. |
| Automatización | **Make.com (plan Business)** | Mejor relación entre precio y capacidad; sustituible por n8n en una fase posterior. |
| Copiloto interno | **OpenAI Assistants API integrado al CRM** | Aprovecha la inversión en OpenAI y permite una integración profunda con el CRM. |
| Hosting | **DigitalOcean** | Precios predecibles y operación simple para una PyME. |
| Analítica | **Power BI Pro** | Se asume un entorno Microsoft 365 ya presente; Microsoft factura localmente con IVA, lo que reduce el impacto cambiario. |

> Las matrices de evaluación ponderadas, las alternativas analizadas por componente y la comparación de costo total de propiedad se desarrollan en el Anexo 6.A.

## 6.3 Inversión estimada: CAPEX y OPEX

**CAPEX (inversión inicial)** — principales partidas:

| Concepto | Monto USD |
|---|---:|
| Desarrollo de integraciones (CRM, copiloto, tableros) | ~21.000 |
| Indexación y vectorización de la base de conocimiento | ~3.000 |
| Capacitación y gestión del cambio (15 personas) | ~7.700 |
| Diseño conversacional, pruebas y documentación | ~8.100 |
| Configuración inicial (WhatsApp, Botmaker, infraestructura) | ~3.600 |
| **Subtotal antes de contingencia** | **39.500** |
| Contingencia (15%) | 5.925 |
| **CAPEX detallado** | **45.425** |
| Ajuste de coherencia con la Sección 8 (licencias, diagnóstico ISO 27001, reserva de tarifa) | 4.575 |
| **CAPEX de referencia (Sección 8)** | **50.000** |

**OPEX (costo recurrente)** — total mensual aproximado de **USD 2.308** (USD 27.696 anuales):

| Concepto | USD/mes |
|---|---:|
| Plataforma Botmaker | 600 |
| WhatsApp / Twilio (modelo por mensaje, con ventana de servicio gratuita) | 360 |
| Mantenimiento evolutivo del primer año (estabilización) | 840 |
| Copiloto, motor LLM y embeddings (OpenAI) | 155 |
| Hosting, Power BI, automatización, base vectorial y observabilidad | 253 |
| Capacitación continua | 100 |
| **Total OPEX** | **2.308** |

**Inversión total del primer año**: USD 50.000 (CAPEX) + USD 27.696 (OPEX) = **USD 77.696**.
**Costo total de propiedad a 3 años** (el mantenimiento se reduce de USD 10.080 a USD 6.000 a partir del segundo año): **USD 124.928**.

> El desglose del CAPEX partida por partida, el detalle completo del OPEX y el ajuste por carga fiscal argentina (OPEX efectivo de aproximadamente USD 32.304 anuales) se desarrollan en los Anexos 6.A y 6.B.

## 6.4 Retorno de la inversión

El costo operativo actual del proceso asciende a USD 216.000 anuales. Con una tasa de automatización del 70%, el ahorro estimado es de **USD 118.800 anuales** (55% del costo actual). Se presentan cinco métricas complementarias del retorno:

| Métrica | Valor |
|---|---:|
| ROI sobre CAPEX (convención clásica, en línea con la Sección 8) | **137,6%** |
| ROI sobre inversión total del primer año (incluye OPEX) | 52,9% |
| Beneficio neto operativo del primer año | USD 41.104 |
| Período de recuperación bruto (sobre CAPEX) | 5,05 meses |
| Período de recuperación neto (descontando OPEX) | 6,59 meses |

**Lectura de las métricas**: las cinco son consistentes entre sí y miden dimensiones distintas del retorno. El 137,6% que reporta la Sección 8 corresponde a la convención clásica de retorno sobre el CAPEX; esta sección lo complementa con las lecturas que incorporan el costo operativo, ofreciendo a la dirección una visión integral. La métrica que se enfatice dependerá del destinatario del análisis (directorio, entidad financiera o auditoría).

**Impacto en la dotación**: el ahorro libera 6,3 puestos de trabajo equivalentes (FTE) de capacidad del equipo técnico —4,95 puestos en términos de costo equivalente—, reasignables a ventas consultivas, mantenimiento proactivo y capacitación de clientes.

> El fundamento de la relación entre la automatización (70%) y el ahorro de costos (55%), la distinción entre capacidad bruta y costo equivalente, y el análisis de sensibilidad por volumen se desarrollan en el Anexo 6.B.

## 6.5 Riesgos principales del modelo

| Riesgo | Probabilidad | Impacto | Mitigación |
|---|---|---|---|
| Devaluación del peso frente al dólar | Alta | Alto | Plan anual prepago (fija el precio en dólares por 12 meses), reserva en dólares y revisión semestral. |
| Cambios en el modelo de precios de WhatsApp | Alta | Alto | Modelo por mensaje vigente; proveedor de respaldo (360dialog o Meta) preconfigurado. |
| Duplicación del volumen en temporada de cosecha | Alta | Medio | El modelo de precios variable absorbe el crecimiento; el retorno mejora en años de buena cosecha (Anexo 6.B). |
| Procesamiento de datos sensibles fuera de Argentina | Media | Medio | Anonimización previa al envío, retención breve y contrato de tratamiento de datos por proveedor; alternativa de procesamiento en la región de São Paulo. |

## 6.6 Conclusión

El stack tecnológico se construyó priorizando tres factores: la presencia local y el soporte en español (Botmaker como eje del canal y la plataforma de bot), la transparencia de precios y el control del costo total de propiedad (OpenAI con la combinación 80/20, Pinecone, DigitalOcean y Make.com) y el cumplimiento de la Ley 25.326. Esta combinación permite iniciar el proyecto con bajo riesgo financiero, escalar la operación sin rediseñar la arquitectura y evolucionar los componentes de manera individual sin reescribir el sistema.

La inversión no constituye únicamente una optimización de costos: habilita la escalabilidad de la atención al cliente (hasta 15.000 conversaciones mensuales sin rediseño), libera capacidad del equipo para tareas de mayor valor agregado, sistematiza el conocimiento de la organización en un activo reutilizable —la base vectorial se enriquece con cada consulta resuelta— y posiciona a Plantium en un nivel de madurez digital comparable al de sus referentes del sector, con una inversión proporcional a su escala.
