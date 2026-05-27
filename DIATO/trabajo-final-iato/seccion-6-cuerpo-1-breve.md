# 6. Análisis de proveedores y costos

**Responsable: Javier Zader**

> **Versión BREVE (~1 página)** — solo lo esencial para el cuerpo del trabajo. Todo el detalle (criterios ponderados, matrices de scoring, desglose CAPEX, fiscal argentino, sensibilidad y Ley 25.326) vive en el **Anexo 6** ([versión completa publicada](https://jnzader.github.io/unraf/trabajo-final-iato/seccion-6-v3-fix2-final.html)).

Sobre la arquitectura de la Sección 5 y los volúmenes de la Sección 8 (≈6.000 conversaciones/mes, costo actual USD 216.000/año, meta de automatización del 70%), se propone el siguiente stack, evaluado con siete criterios ponderados que priorizan integración y presencia local.

## Stack tecnológico recomendado

| Componente | Proveedor | Por qué |
|---|---|---|
| Canal WhatsApp | **Twilio (vía Botmaker)** | BSP oficial, sin doble factura. |
| Plataforma de bot | **Botmaker** | Argentina, facturación local, soporte en español. |
| Motor LLM | **OpenAI GPT-4o-mini + GPT-4o (mix 80/20)** | Mejor calidad/precio del mercado. |
| Vector DB (RAG) | **Pinecone Serverless** | Free tier para piloto, escalable sin operar infra. |
| Automatización | **Make.com (Business)** | Mejor balance precio/capacidad. |
| Copiloto interno | **OpenAI Assistants + CRM** | Aprovecha la inversión OpenAI. |
| Hosting / Analítica | **DigitalOcean / Power BI Pro** | Pricing predecible; Power BI factura local con IVA. |

## Inversión estimada

| Concepto | Valor |
|---|---:|
| **CAPEX** (inversión inicial, alineado con Sección 8) | **USD 50.000** |
| **OPEX** (recurrente) | **USD 2.308/mes** (USD 27.696/año) |
| **TCO a 3 años** | **USD 124.928** |

## Retorno de la inversión

Con 70% de automatización, el ahorro estimado es de **USD 118.800/año** (55% del costo actual).

| Métrica | Valor |
|---|---:|
| ROI sobre CAPEX (alineado con Sección 8) | **137,6%** |
| ROI sobre inversión total año 1 | 52,9% |
| Payback (bruto / neto) | 5,05 / 6,59 meses |

Las métricas son complementarias: el 137,6% es la convención clásica sobre CAPEX (Sección 8); las demás incorporan el OPEX. El proyecto libera **6,3 FTE de capacidad** del equipo técnico para tareas de mayor valor.

## Conclusión

El stack prioriza presencia local (Botmaker), pricing transparente (OpenAI, Pinecone, DigitalOcean) y cumplimiento de la Ley 25.326. Permite iniciar con bajo riesgo financiero, escalar sin re-arquitectura y convertir el conocimiento de la empresa en un activo reutilizable, con una inversión adecuada a la escala de una PyME industrial.
