# 6. Análisis de proveedores y costos

**Responsable: Javier Zader**

## 6.1 Introducción

La solución definida en la Sección 5 articula un asistente virtual sobre WhatsApp, una arquitectura de Generación Aumentada por Recuperación (RAG), un módulo de clasificación automática, un copiloto interno y una capa de analítica. Cada bloque requiere proveedores con modelos de precios diferenciales que deben evaluarse según el contexto de Plantium. El análisis se ancla en los volúmenes establecidos en la Sección 8: aproximadamente 6.000 conversaciones mensuales, costo operativo anual actual de USD 216.000 y meta de automatización del 70%. Sobre esa base se identifican los proveedores por componente, se comparan mediante criterios ponderados, se propone un stack de referencia y se desagrega la inversión en CAPEX y OPEX, complementando el retorno proyectado en la Sección 8.

A efectos de precisión, se emplea **mensaje** como unidad económica de cobro (WhatsApp adoptó el modelo por mensaje en julio de 2025), **conversación** como unidad de dimensionamiento del negocio (entre 5 y 8 mensajes) y **ventana de servicio** para los mensajes sin costo dentro de las 24 horas iniciadas por el cliente, factor relevante porque la atención posventa de Plantium es mayormente iniciada por el cliente.

## 6.2 Criterios de selección de proveedores

Se aplicaron siete criterios ponderados según la realidad de una PyME industrial argentina, priorizando la integración y la presencia local:

| # | Criterio | Peso |
|---|---|---:|
| 1 | Presencia y soporte en Argentina o LATAM (idioma, huso horario, facturación local) | 15% |
| 2 | Madurez del producto (años en el mercado, casos publicados, clientes de referencia) | 15% |
| 3 | Transparencia del modelo de precios (preferencia por pago por uso en el piloto) | 10% |
| 4 | Capacidad de integración (CRM, WhatsApp Business API y eventual ERP) | 20% |
| 5 | Cumplimiento de la Ley 25.326 (residencia de datos configurable, contrato de tratamiento, exclusión de entrenamiento) | 15% |
| 6 | Escalabilidad (de 6.000 a 15.000 conversaciones mensuales sin cambios estructurales) | 10% |
| 7 | Costo total de propiedad a 3 años, no solo el costo inicial | 15% |

## 6.3 Componentes de la solución

La arquitectura se descompone en **ocho componentes** que requieren un proveedor externo: canal de mensajería (WhatsApp), plataforma de bot y orquestación, motor LLM, base vectorial para RAG, plataforma de automatización, infraestructura de hosting, copiloto interno para los agentes y capa de analítica. Los tres primeros son de criticidad **alta** (punto de contacto, núcleo operativo y capa de inteligencia); el resto, de criticidad **media** (habilitadores y soporte transversal).

## 6.4 Stack tecnológico recomendado

| Componente | Proveedor recomendado | Fundamento |
|---|---|---|
| Canal WhatsApp | **Twilio (vía Botmaker)** | Botmaker gestiona la integración como proveedor oficial (BSP); se elimina la doble facturación. |
| Plataforma de bot | **Botmaker** | Empresa argentina, facturación local, soporte en español, más de 9 años en el mercado e integración nativa de WhatsApp. |
| Motor LLM | **OpenAI GPT-4o-mini (80%) + GPT-4o (20%)** | Mejor relación calidad/precio; la combinación controla los costos manteniendo la calidad en consultas complejas. |
| Generación de embeddings | **OpenAI text-embedding-3-small** | Mejor relación costo/calidad multilingüe; consistencia con el resto del stack OpenAI. |
| Base vectorial | **Pinecone Serverless (capa gratuita → plan Builder)** | La capa gratuita cubre el piloto; el plan Builder (USD 20/mes) se adopta en producción, sin administrar infraestructura. |
| Automatización | **Make.com (plan Business)** | Mejor relación entre precio y capacidad; sustituible por n8n con alojamiento propio en una fase posterior. |
| Copiloto interno | **OpenAI Assistants API integrado al CRM** | Aprovecha la inversión en OpenAI y permite una integración profunda con el CRM existente. |
| Hosting | **DigitalOcean** | Precios predecibles y operación simple, suficiente para los servicios a medida previstos. |
| Analítica | **Power BI Pro** | Se asume un entorno Microsoft 365 ya presente (a validar con el área de TI); Microsoft factura localmente con IVA. |

> El análisis comparativo detallado por componente (alternativas, costos por proveedor, matrices de evaluación ponderadas y comparación de costo total de propiedad a 3 años) se desarrolla en el Anexo 6.A.

## 6.5 Estimación de costos

### 6.5.1 CAPEX (inversión inicial)

| Concepto | Monto USD |
|---|---:|
| Desarrollo de integraciones (Botmaker–CRM, copiloto, tableros de Power BI) | 17.100 |
| Configuración inicial e incorporación (WhatsApp, Botmaker, infraestructura DigitalOcean) | 3.600 |
| Indexación y vectorización de la base de conocimiento (segmentación, embeddings, control de calidad) | 3.000 |
| Diseño conversacional del asistente | 2.500 |
| Capacitación (12 agentes y 3 supervisores) y consultoría de gestión del cambio | 7.700 |
| Pruebas, control de calidad y documentación técnica | 5.600 |
| **Subtotal antes de contingencia** | **39.500** |
| Contingencia (15%) | 5.925 |
| **CAPEX detallado** | **45.425** |
| Ajuste de coherencia con la Sección 8 (licencias adicionales, diagnóstico ISO 27001, reserva de tarifa) | 4.575 |
| **CAPEX de referencia (Sección 8)** | **50.000** |

> **Reconciliación con la Sección 8**: el CAPEX detallado asciende a USD 45.425, mientras que la Sección 8 asume una inversión de USD 50.000. La diferencia de USD 4.575 corresponde a licencias no específicas del proyecto (aproximadamente USD 2.000), un diagnóstico de brechas ISO 27001 (USD 1.500, diagnóstico, no certificación completa) y una reserva de tarifa (USD 1.075). Se adopta USD 50.000 como cifra de referencia por coherencia con la Sección 8. El desglose partida por partida se desarrolla en el Anexo 6.A.

### 6.5.2 OPEX (costo recurrente)

| Concepto | USD/mes | USD/año |
|---|---:|---:|
| Plataforma de bot (Botmaker) | 600 | 7.200 |
| WhatsApp / Twilio (modelo por mensaje, con ventana de servicio gratuita) | 360 | 4.320 |
| Mantenimiento evolutivo del primer año (estabilización) | 840 | 10.080 |
| Motor LLM, copiloto y embeddings (OpenAI) | 155 | 1.860 |
| Hosting (DigitalOcean), Power BI, automatización, base vectorial y observabilidad | 253 | 3.036 |
| Capacitación continua | 100 | 1.200 |
| **Total OPEX** | **2.308** | **27.696** |

> El costo nominal del motor LLM es de aproximadamente USD 16 mensuales; se reserva un techo de USD 65 mensuales (cuatro veces el valor base) como contingencia ante crecimiento y reajustes de precios. El detalle de las doce partidas del OPEX se desarrolla en el Anexo 6.A.

### 6.5.3 Inversión total y costo total de propiedad

- **Primer año**: USD 50.000 (CAPEX) + USD 27.696 (OPEX) = **USD 77.696**.
- **Costo total de propiedad a 3 años**: el mantenimiento se reduce de USD 10.080 a USD 6.000 a partir del segundo año, totalizando **USD 124.928**.
- **Carga fiscal argentina**: el OPEX efectivo en pesos asciende a aproximadamente USD 32.304 anuales (coeficiente de 1,5 sobre los proveedores extranjeros por IVA, percepción de Ganancias y diferencial cambiario). El detalle se desarrolla en el Anexo 6.B.

### 6.5.4 Retorno de la inversión

El costo operativo actual asciende a USD 216.000 anuales. Con una tasa de automatización del 70%, el ahorro es de **USD 118.800 anuales** (55% del costo actual).

| Métrica | Fórmula | Valor |
|---|---|---:|
| ROI sobre CAPEX (convención clásica, en línea con la Sección 8) | (118.800 − 50.000) / 50.000 | **137,6%** |
| ROI sobre inversión total del primer año | (118.800 − 77.696) / 77.696 | 52,9% |
| Beneficio neto operativo del primer año | 118.800 − 50.000 − 27.696 | USD 41.104 |
| Período de recuperación bruto (sobre CAPEX) | 50.000 / (118.800/12) | 5,05 meses |
| Período de recuperación neto (descontando OPEX) | 50.000 / (9.900 − 2.308) | 6,59 meses |

**Lectura de las métricas**: las cinco son consistentes entre sí y miden dimensiones distintas del retorno. El 137,6% que reporta la Sección 8 corresponde a la convención clásica de retorno sobre el CAPEX, en la que el OPEX es costo operativo del nuevo sistema. Esta sección lo complementa con las lecturas que incorporan el costo operativo, ofreciendo a la dirección una visión integral y conservadora.

**Relación entre la tasa de automatización (70%) y el ahorro de costos (55%)**: las consultas no automatizadas (30%) son las más complejas y consumen mayor costo por caso, y existen costos fijos de supervisión que no se reducen de manera lineal. El ahorro libera 6,3 puestos de trabajo equivalentes (FTE) de capacidad bruta —4,95 puestos en términos de costo equivalente— del equipo técnico, reasignables a ventas consultivas, mantenimiento proactivo y capacitación de clientes.

## 6.6 Supuestos clave

1. Volumen base: 6.000 conversaciones mensuales (aproximadamente 42.000 mensajes), consistente con la Sección 8.
2. Automatización objetivo: 70% de las consultas resueltas sin intervención humana (Sección 8).
3. Combinación de modelos: 80% GPT-4o-mini y 20% GPT-4o.
4. WhatsApp como único canal en el primer año, bajo el modelo por mensaje con aprovechamiento de la ventana de servicio.
5. Precios en dólares según las tarifas públicas de los proveedores (mayo de 2026).
6. Hora de desarrollador: USD 45; consultoría especializada: USD 60-80.
7. Base vectorial: aproximadamente 13.000 vectores (dentro de la capa gratuita de Pinecone).
8. Mantenimiento: primer año, cerca del 22% del CAPEX; segundo y tercer año, cerca del 12% (USD 6.000 anuales).
9. El costo total de propiedad base asume precios en dólares constantes; el contexto inflacionario argentino puede elevarlo entre 25% y 35% a 3 años, a contemplar en la presupuestación.
10. Se asume un entorno Microsoft 365 presente y un CRM en la nube con API REST (a validar); un CRM heredado sumaría entre 80 y 150 horas adicionales (USD 3.600 a 6.750).

## 6.7 Riesgos principales del modelo

| Riesgo | Probabilidad | Impacto | Mitigación |
|---|---|---|---|
| Devaluación del peso frente al dólar | Alta | Alto | Plan anual prepago (fija el precio en dólares por 12 meses), reserva en dólares y revisión semestral. |
| Cambios en el modelo de precios de WhatsApp Business | Alta | Alto | Modelo por mensaje vigente; proveedor de respaldo (360dialog o Meta) preconfigurado; análisis de un escenario adverso del +50%. |
| Duplicación del volumen en temporada de cosecha | Alta | Medio | El modelo de precios variable absorbe el crecimiento sin rediseño; el retorno mejora en años de buena cosecha (Anexo 6.B). |
| Aumento de los precios de OpenAI o Anthropic | Media | Medio | Estrategia multimodelo con capa de abstracción (alternativa de respaldo en Claude o Gemini); margen de contingencia incorporado en el OPEX. |
| Procesamiento de datos sensibles fuera de Argentina | Media | Medio | Anonimización previa al envío, retención breve y contrato de tratamiento de datos por proveedor; alternativa de procesamiento en la región de São Paulo. |
| Dependencia del proveedor Botmaker | Media | Medio | Capa de abstracción sobre su API; costo de migración estimado entre USD 5.000 y 8.000; evaluación en el mes 12. |

## 6.8 Conclusión

El stack tecnológico se construyó priorizando la presencia local y el soporte en español (Botmaker como eje del canal y la plataforma de bot), la transparencia de precios y el control del costo total de propiedad (OpenAI con la combinación 80/20, Pinecone, DigitalOcean y Make.com) y el cumplimiento de la Ley 25.326 (proveedores con contrato de tratamiento de datos, anonimización previa al envío y residencia de datos configurable). Esta combinación permite iniciar el proyecto con bajo riesgo financiero, escalar la operación sin rediseñar la arquitectura y evolucionar los componentes de manera individual —por ejemplo, migrar a n8n con alojamiento propio en una fase posterior— sin reescribir el sistema.

El enfoque —datos centralizados, automatización conversacional, integración profunda con el CRM y analítica embebida— está alineado con los referentes globales del sector (John Deere, Trimble, Syngenta); las herramientas difieren por escala, adoptando el mismo paradigma con un instrumental apropiado para una PyME industrial de 250 empleados. Desde una perspectiva estratégica, la inversión habilita la escalabilidad de la atención (hasta 15.000 conversaciones mensuales sin rediseño), libera capacidad del equipo para tareas de mayor valor agregado, transforma el conocimiento en un activo reutilizable —la base vectorial se enriquece con cada consulta resuelta— y posiciona a Plantium en un nivel de madurez digital comparable al de sus referentes. Las cinco lecturas del retorno ofrecen a la dirección una visión integral; aun con la carga fiscal argentina, el ROI sobre la inversión total se mantiene en torno al 44% y el período de recuperación neto en aproximadamente 7 meses (Anexo 6.B), lo que confirma la viabilidad financiera del proyecto.
