# 6. Análisis de proveedores y costos

**Responsable: Javier Zader**

Sobre la base de la arquitectura definida en la Sección 5 y los volúmenes establecidos en la Sección 8 (aproximadamente 6.000 conversaciones mensuales, costo operativo anual actual de USD 216.000 y meta de automatización del 70%), se propone el siguiente stack tecnológico, evaluado mediante siete criterios ponderados que priorizan la capacidad de integración y la presencia local.

## 6.1 Stack tecnológico recomendado

| Componente | Proveedor | Fundamento |
|---|---|---|
| Canal WhatsApp | **Twilio (vía Botmaker)** | Proveedor oficial (BSP), sin doble facturación. |
| Plataforma de bot | **Botmaker** | Empresa argentina, facturación local y soporte en español. |
| Motor LLM | **OpenAI GPT-4o-mini + GPT-4o (combinación 80/20)** | Mejor relación calidad/precio del mercado. |
| Base vectorial (RAG) | **Pinecone Serverless** | Capa gratuita para el piloto, escalable sin administrar infraestructura. |
| Automatización | **Make.com (plan Business)** | Mejor relación entre precio y capacidad. |
| Copiloto interno | **OpenAI Assistants + CRM** | Aprovecha la inversión en OpenAI. |
| Hosting / Analítica | **DigitalOcean / Power BI Pro** | Precios predecibles; Power BI factura localmente con IVA. |

## 6.2 Inversión estimada

| Concepto | Valor |
|---|---:|
| **CAPEX** (inversión inicial, en línea con la Sección 8) | **USD 50.000** |
| **OPEX** (costo recurrente) | **USD 2.308/mes** (USD 27.696/año) |
| **Costo total de propiedad a 3 años** | **USD 124.928** |

## 6.3 Retorno de la inversión

Con una tasa de automatización del 70%, el ahorro estimado asciende a **USD 118.800 anuales** (55% del costo actual).

| Métrica | Valor |
|---|---:|
| ROI sobre CAPEX (en línea con la Sección 8) | **137,6%** |
| ROI sobre inversión total del primer año | 52,9% |
| Período de recuperación (bruto / neto) | 5,05 / 6,59 meses |

Las cinco métricas son consistentes entre sí y miden dimensiones distintas del retorno: el 137,6% corresponde a la convención clásica sobre CAPEX (Sección 8), mientras que las demás incorporan el costo operativo. El proyecto libera 6,3 puestos de trabajo equivalentes (FTE) de capacidad del equipo técnico para tareas de mayor valor agregado.

## 6.4 Conclusión

El stack propuesto prioriza la presencia local (Botmaker), la transparencia de precios (OpenAI, Pinecone, DigitalOcean) y el cumplimiento de la Ley 25.326 de Protección de Datos Personales. Permite iniciar el proyecto con bajo riesgo financiero, escalar la operación sin rediseñar la arquitectura y transformar el conocimiento de la organización en un activo reutilizable, con una inversión proporcional a la escala de una PyME industrial.

> El análisis comparativo detallado por componente (matrices de evaluación), el desglose completo del CAPEX y el OPEX, el impacto fiscal argentino, el análisis de sensibilidad por volumen y el cumplimiento de la Ley 25.326 se desarrollan en los Anexos 6.A, 6.B y 6.C.
