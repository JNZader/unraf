## 6. Análisis de proveedores y costos

**Responsable: Javier Zader**

### 6.1 Introducción

La solución propuesta en la Sección 5 contempla un sistema integral de atención al cliente basado en Inteligencia Artificial, que articula un asistente virtual sobre WhatsApp, una arquitectura de Generación Aumentada por Recuperación (RAG), un módulo de clasificación automática, un copiloto interno para los agentes y una capa de analítica. Cada uno de estos bloques funcionales requiere proveedores tecnológicos específicos, con modelos de precios y características diferenciales que deben evaluarse en función del contexto operativo de Plantium.

A los efectos de dimensionar la inversión, el análisis se ancla en los volúmenes y supuestos económicos detallados en la Sección 8: aproximadamente 6.000 conversaciones mensuales, un costo operativo anual actual estimado en USD 216.000 y una meta de automatización del 70% de las consultas. Sobre esa base, la presente sección identifica proveedores candidatos por componente, los compara según criterios objetivos, propone un stack tecnológico de referencia y desagrega la inversión total en CAPEX (inversión inicial) y OPEX (costo recurrente), de manera que el modelo económico pueda validarse contra el ROI proyectado por la Sección 8.

### 6.2 Criterios de selección de proveedores

Para evaluar las opciones de cada componente se aplicaron siete criterios, ponderados según la realidad de una PyME industrial argentina:

1. **Presencia y soporte en Argentina o LATAM** (idioma español, fuso horario, facturación local cuando es posible).
2. **Madurez del producto** (años en mercado, casos publicados, clientes referenciables).
3. **Modelo de pricing transparente** (preferencia por precios públicos y pago por uso sobre licencias fijas durante la fase piloto).
4. **Capacidad de integración** con el CRM existente, WhatsApp Business API y el eventual ERP de Plantium.
5. **Cumplimiento de privacidad y seguridad** (Ley 25.326 de Protección de Datos Personales de Argentina y buenas prácticas de WhatsApp Business Platform).
6. **Escalabilidad**, entendida como la capacidad de absorber un crecimiento de 6.000 a 15.000 conversaciones mensuales sin cambios estructurales.
7. **Costo total de propiedad (TCO) a 3 años**, no solo costo inicial.

### 6.3 Componentes de la solución que requieren proveedor

La arquitectura descripta en la Sección 5 se descompone en seis bloques funcionales que requieren un proveedor externo o un componente tecnológico específico:

| Componente | Función en la solución | Criticidad |
|---|---|---|
| Canal de mensajería | Recibir y enviar mensajes vía WhatsApp Business API (interfaz con el cliente) | Alta — único punto de contacto en fase 1 |
| Plataforma de bot y orquestación conversacional | Manejar sesiones, flujos, fallback a humano, métricas de canal | Alta — corazón operativo |
| Motor LLM (IA generativa) | Comprender intención, clasificar consultas, generar respuestas en lenguaje natural | Alta — capa de inteligencia |
| Base vectorial para RAG | Almacenar embeddings de manuales, FAQs e histórico de tickets resueltos | Media — habilita precisión técnica |
| Plataforma de automatización (iPaaS) | Integrar componentes, mover datos entre el bot, el CRM y la base de conocimiento | Media — pegamento del stack |
| Infraestructura de hosting | Alojar servicios custom (copiloto, conectores, eventual self-hosting del vector DB) | Media — soporte transversal |
| Capa de analítica | Dashboards operativos y de negocio para supervisores y gerencia | Media — visibilidad y mejora continua |

### 6.4 Análisis comparativo de proveedores por componente

Para cada componente se evaluaron entre 3 y 5 alternativas, considerando el volumen objetivo de 6.000 conversaciones por mes. Los rangos de costo corresponden a precios públicos verificados en mayo de 2026 (referencias al final de la sección).

#### 6.4.1 Canal WhatsApp Business

| Proveedor | Modelo de pricing | Costo mensual estimado (6.000 conv/mes) | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **Twilio + WhatsApp API** | USD 0,005 por mensaje (fee Twilio) + tarifa Meta por conversación (utility/marketing) | USD 300 – 450 | Flexibilidad máxima, ecosistema robusto, documentación amplia | Requiere desarrollo propio, sin UI de gestión incluida |
| **Meta Cloud API directo** | Solo tarifa Meta (sin fee de BSP intermediario) | USD 200 – 350 | Costo más bajo posible | Sin SLA empresarial directo, soporte limitado, sin UI |
| **360dialog** | USD 49 – 99/mes plataforma + fees Meta | USD 280 – 450 | BSP oficial Meta, fuerte en LATAM, foco enterprise | Sin oficina en Argentina, soporte vía partners |
| **Wati** | USD 49 – 99/mes plataforma + fees Meta | USD 250 – 400 | UI lista para PyME, multi-agente | Foco más comercial que técnico |

#### 6.4.2 Plataforma de bot y orquestación

| Proveedor | Modelo de pricing | Costo mensual estimado | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **Botmaker (Argentina)** | Plan gratuito hasta 300 sesiones; planes pagos desde USD 100/mes hasta USD 1.000+/mes según volumen; setup WhatsApp Business: USD 99 one-time | USD 500 – 800 | Empresa argentina con 9+ años, facturación local, soporte en español, integra WhatsApp BSP nativamente | Lock-in moderado por configuración de flujos |
| **Aivo (Argentina/LATAM)** | Pricing custom (no público), modelo enterprise | USD 800 – 2.000 (estimado) | Líder LATAM, clientes referenciables (Sony, Visa, Movistar, GM), oferta enterprise consolidada | Sin pricing transparente, ticket alto para PyME |
| **Voiceflow** | Desde USD 50/mes (Pro), USD 800/mes (Teams) | USD 800 – 1.200 | UX de diseño conversacional superior, integración nativa con LLMs | Foco voz/multicanal, sin partner local |
| **Custom sobre n8n + LLM** | Costo de infraestructura + horas de desarrollo iniciales | USD 100 – 300 (infra) | TCO más bajo a 3 años, sin lock-in, control total | Requiere capacidad técnica interna sostenida |

#### 6.4.3 Motor LLM (IA generativa)

Para el cálculo se asume el siguiente mix por conversación: una clasificación con modelo económico (prompt ~500 tokens, respuesta ~50 tokens) y, cuando la consulta lo amerita, una generación con modelo de alta capacidad sobre contexto RAG (prompt ~3.000 tokens, respuesta ~300 tokens).

| Proveedor / Modelo | Input (USD / 1M tokens) | Output (USD / 1M tokens) | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **OpenAI GPT-4o** | 2,50 | 10,00 | Calidad de referencia, gran ecosistema, SDK maduro | Datos procesados fuera de Argentina |
| **OpenAI GPT-4o-mini** | 0,15 | 0,60 | 16× más barato que GPT-4o, ideal para clasificación e intención | Calidad inferior en generación compleja |
| **Anthropic Claude Sonnet 4.6** | 3,00 | 15,00 | Calidad equivalente a GPT-4o, fuerte en razonamiento técnico | Output 50% más caro que OpenAI |
| **Anthropic Claude Haiku 4.5** | 1,00 | 5,00 | Buena relación calidad/precio para tareas conversacionales | Menos eficiente que GPT-4o-mini para clasificación pura |
| **Azure OpenAI** | Igual a OpenAI + sobrecosto Azure (~10-15%) | Igual base | Cumplimiento empresarial, integración con Microsoft 365 | Más caro, requiere contrato Azure |
| **Google Vertex AI (Gemini)** | Comparable a OpenAI | Comparable | Integración con Google Workspace | Ecosistema menos desarrollado en habla hispana |

**Estimación de costo LLM mensual para 6.000 conversaciones (mix recomendado 80/20: 80% resuelto con GPT-4o-mini, 20% con GPT-4o + RAG):**

| Cálculo | Volumen mensual | Costo USD |
|---|---|---|
| GPT-4o-mini input (clasificación, 6.000 conv) | 3.000.000 tokens | 0,45 |
| GPT-4o-mini output (clasificación) | 300.000 tokens | 0,18 |
| GPT-4o-mini input (generación simple, 4.800 conv) | 14.400.000 tokens | 2,16 |
| GPT-4o-mini output (generación simple) | 1.440.000 tokens | 0,86 |
| GPT-4o input (generación compleja RAG, 1.200 conv) | 3.600.000 tokens | 9,00 |
| GPT-4o output (generación compleja RAG) | 360.000 tokens | 3,60 |
| **Total LLM mensual** | | **~USD 16 – 65** |

El rango USD 16 – 65 mensuales contempla escenarios desde un mix conservador (solo GPT-4o-mini) hasta el mix recomendado con generación compleja. Para el presupuesto se adopta el valor superior (USD 65/mes) como referencia.

#### 6.4.4 Base vectorial para RAG

Dimensionamiento estimado de la base de conocimiento de Plantium: aproximadamente 500 páginas de manuales de producto, 100 páginas de FAQs y 2.000 tickets históricos, lo que se traduce en unos 13.000 vectores en chunks de 500 tokens.

| Proveedor | Modelo de pricing | Costo mensual estimado | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **Pinecone Serverless (Free)** | Gratis hasta 100k vectores y queries moderadas | USD 0 | Cubre el dimensionamiento inicial sin costo | Free tier puede cambiar políticas |
| **Pinecone Builder** | USD 20/mes flat | USD 20 | Producción inicial con SLA, gestionado | Lock-in moderado |
| **Qdrant Cloud** | Free tier (0,5 vCPU, 1GB RAM); planes desde USD 30/mes | USD 0 – 30 | Alternativa LATAM-friendly, open source | Comunidad más chica |
| **Qdrant self-hosted** | USD 20-50/mes en VPS (Hetzner, DigitalOcean) | USD 25 | Mejor TCO a 3 años si Plantium opera el VPS | Requiere capacidad técnica interna |
| **Weaviate Cloud (Flex)** | Desde USD 45/mes | USD 45 | Búsqueda híbrida nativa | Más caro que Qdrant a iguales features |
| **pgvector (PostgreSQL)** | Costo del Postgres ya existente | USD 0 incremental | Integración con stack relacional existente | Performance inferior a vector DBs especializadas en >100k vectores |

#### 6.4.5 Plataforma de automatización (iPaaS)

| Proveedor | Modelo de pricing | Costo mensual estimado | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **Make.com** | Desde USD 9/mes (10k operaciones); plan Business USD 50/mes (40k operaciones) | USD 50 | Mejor relación precio/poder, 60-70% más barato que Zapier | Curva de aprendizaje para flujos complejos |
| **Zapier** | USD 20-100/mes para tiers de negocio | USD 70 | Ecosistema de 7.000+ apps | Costoso por operación; solo justifica si se necesitan integraciones poco comunes |
| **n8n self-hosted** | USD 5-20/mes de VPS, ejecuciones ilimitadas | USD 20 | Mejor TCO, open source, sin lock-in | Requiere operar infraestructura |
| **n8n Cloud** | EUR 20-50/mes (plan starter) | USD 25 | Misma flexibilidad sin operar infra | Cuenta por ejecución, no por nodo |

#### 6.4.6 Hosting de infraestructura backend

Necesario para alojar conectores custom, el copiloto interno y, opcionalmente, n8n y el vector DB self-hosted.

| Proveedor | Modelo de pricing | Costo mensual estimado | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **AWS** | Pay-per-use, EC2 t3.medium ~USD 30/mes | USD 80 – 150 | Líder del mercado, máxima cobertura de servicios | Curva de aprendizaje, costos pueden escalar |
| **Microsoft Azure** | Comparable a AWS | USD 80 – 150 | Buena integración con Microsoft 365 / Power BI | Mismo orden de complejidad |
| **DigitalOcean** | Droplets desde USD 6/mes; Managed Services desde USD 15/mes | USD 40 – 80 | Pricing predecible, ideal para PyME | Menos servicios gestionados |
| **Hetzner Cloud** | Servidores cloud desde EUR 5/mes | USD 25 – 60 | El más barato de la lista, excelente performance/USD | Sin presencia en LATAM (data centers en Europa) |

#### 6.4.7 Capa de analítica

| Proveedor | Modelo de pricing | Costo mensual estimado (5 supervisores) | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **Power BI Pro** | USD 14 / usuario / mes | USD 70 | Si Plantium ya usa Microsoft 365, se suma sin fricción | Requiere licencia base Microsoft |
| **Looker Studio (Google)** | Gratis | USD 0 | Sin costo de licencia, integración nativa con Google Workspace | Funciones avanzadas limitadas |
| **Tableau Creator** | USD 75 / usuario / mes | USD 375 | Líder en visualización avanzada | Sobreescala para el caso de uso |
| **Dashboard nativo del CRM** | Incluido | USD 0 incremental | Sin costo adicional | Suele ser limitado en flexibilidad |

### 6.5 Stack tecnológico recomendado

Tras el análisis comparativo, se propone el siguiente stack como decisión de diseño. La selección prioriza presencia local, transparencia de pricing y TCO a 3 años:

| Componente | Proveedor recomendado | Justificación (síntesis) |
|---|---|---|
| Canal WhatsApp | **Twilio (vía Botmaker)** | Botmaker gestiona la integración WhatsApp como BSP oficial. Se elimina la doble factura. |
| Plataforma de bot | **Botmaker** | Empresa argentina, facturación local, soporte en español, 9+ años en el mercado, integra WhatsApp BSP nativamente. Mejor encaje con el perfil PyME de Plantium. |
| Motor LLM | **OpenAI: GPT-4o-mini (80%) + GPT-4o (20%)** | Mejor relación calidad/precio del mercado. Mix permite controlar costos manteniendo calidad en consultas complejas con RAG. |
| Vector DB | **Pinecone Serverless (Free → Builder)** | Free tier alcanza para piloto. Migración a Builder (USD 20/mes flat) cuando el piloto pase a producción. Sin necesidad de operar infraestructura. |
| Automatización iPaaS | **Make.com (plan Business)** | Mejor balance entre precio y capacidad. Migrable a n8n self-hosted en Fase 3 si los volúmenes lo justifican. |
| Copiloto interno | **OpenAI Assistants API integrado al CRM** | Aprovecha la inversión en OpenAI. Desarrollo custom permite integración profunda con el CRM existente de Plantium. |
| Hosting backend | **DigitalOcean** | Pricing predecible, simple para una PyME, suficiente para los servicios custom previstos. |
| Analítica | **Power BI Pro** | Se asume entorno Microsoft 365 ya presente en Plantium (validar con el área de IT). |

### 6.6 Estimación de costos — Desglose completo

#### 6.6.1 CAPEX (inversión inicial, one-time)

| Concepto | Detalle | Monto USD |
|---|---|---|
| Setup WhatsApp Business Platform | Verificación Meta + Botmaker WhatsApp Business | 100 |
| Onboarding Botmaker enterprise | Activación + configuración inicial | 1.500 |
| Desarrollo integraciones Botmaker ↔ CRM Plantium | 120 horas desarrollador senior @ USD 45/h | 5.400 |
| Indexación inicial RAG | Digitalización de manuales + chunking + generación de embeddings (~13k vectores) | 3.000 |
| Desarrollo del copiloto interno (módulo CRM) | Custom + integración OpenAI Assistants, 180 horas @ USD 45/h | 8.100 |
| Configuración de dashboards Power BI | Diseño + conexión a datos, 80 horas @ USD 45/h | 3.600 |
| Diseño UX y personalidad conversacional del bot | Branding conversacional + flujos críticos | 2.500 |
| Capacitación equipo operativo (12 personas) | 2 jornadas de 6 horas | 3.000 |
| Capacitación supervisores (3 personas) | 1 jornada especializada + materiales | 1.500 |
| Consultoría externa de gestión del cambio | 40 horas @ USD 80/h | 3.200 |
| Setup de infraestructura backend (DigitalOcean) | Configuración inicial servidores, CI/CD, observabilidad | 2.000 |
| Testing y QA | Pruebas funcionales, de carga y de aceptación (80 hs @ USD 45/h) | 3.600 |
| Documentación técnica y manual de operación | Entregables del proyecto | 2.000 |
| Contingencia (15%) | Reserva para imprevistos | 4.945 |
| **TOTAL CAPEX** | | **~USD 44.445** |

> **Nota de coherencia con Sección 8**: la Sección 8 (Magdalena) asume una inversión inicial de USD 50.000. El CAPEX detallado en esta sección llega a USD 44.445, dentro del mismo orden de magnitud. Se adopta el valor de USD 50.000 como cifra de referencia para el cálculo de ROI, incorporando una reserva adicional de aproximadamente USD 5.500 para licencias de software corporativo, certificaciones de seguridad y eventual ajuste cambiario.

#### 6.6.2 OPEX (costos recurrentes mensuales y anuales)

| Concepto | Proveedor | Costo mensual USD | Costo anual USD |
|---|---|---|---|
| Plataforma de bot | Botmaker (plan empresa) | 600 | 7.200 |
| WhatsApp Business — conversaciones | 6.000 conv/mes × USD 0,05 promedio (mix utility/service) | 300 | 3.600 |
| LLM (OpenAI API) | Mix GPT-4o-mini + GPT-4o (cálculo en 6.4.3) | 65 | 780 |
| Vector DB | Pinecone Builder | 20 | 240 |
| iPaaS automatización | Make.com (plan Business) | 50 | 600 |
| Hosting backend | DigitalOcean (droplets + managed services) | 80 | 960 |
| Power BI Pro | 5 licencias supervisores × USD 14 | 70 | 840 |
| Copiloto interno (uso OpenAI Assistants) | Tokens adicionales para los 12 agentes | 90 | 1.080 |
| Re-indexación RAG (mensual) | Procesamiento incremental de nuevos documentos | 50 | 600 |
| Observabilidad y logging | Stack mínimo (Grafana Cloud o equivalente) | 30 | 360 |
| Mantenimiento evolutivo | 12 horas/mes consultor externo @ USD 60/h | 720 | 8.640 |
| Soporte y mantenimiento del software (~10% CAPEX/año) | Ya incluido en línea anterior | — | — |
| Capacitación continua | Cursos + horas internas | 100 | 1.200 |
| **TOTAL OPEX** | | **~USD 2.175 / mes** | **~USD 26.100 / año** |

#### 6.6.3 Inversión total estimada — Año 1

| Categoría | USD |
|---|---|
| CAPEX | 50.000 |
| OPEX 12 meses | 26.100 |
| **Total año 1** | **76.100** |

#### 6.6.4 Proyección TCO a 3 años

Sin considerar inflación ni ajustes de precio de proveedores en años 2 y 3:

| Año | CAPEX | OPEX anual | Total año | Acumulado |
|---|---|---|---|---|
| 1 | 50.000 | 26.100 | 76.100 | 76.100 |
| 2 | — | 26.100 | 26.100 | 102.200 |
| 3 | — | 26.100 | 26.100 | 128.300 |

#### 6.6.5 Comparación con costo actual y validación del ROI

Según la Sección 8, el costo operativo anual actual del proceso AS IS asciende a USD 216.000 (6.000 consultas/mes × 15 minutos promedio × USD 12/hora de colaborador × 12 meses). Con la solución propuesta y una tasa de automatización del 70%, el ahorro bruto estimado es de USD 118.800 anuales (55% del costo actual).

| Concepto | USD |
|---|---|
| Costo operativo actual anual (AS IS) | 216.000 |
| Ahorro operativo bruto anual (según Sección 8) | 118.800 |
| Inversión inicial (CAPEX) | 50.000 |
| OPEX anual de la solución | 26.100 |
| **Beneficio neto año 1 (ahorro bruto − CAPEX)** | **68.800** |
| **ROI año 1** = (Beneficio − Inversión) / Inversión | **137,6%** |
| **Payback estimado** | 5 a 6 meses |
| **Ahorro neto acumulado a 3 años** (ahorro × 3 − TCO 3 años) | **228.100** |

El **ROI del 137,6%** reportado por la Sección 8 surge de aplicar la fórmula clásica `(Beneficio anual − Inversión) / Inversión × 100` sobre un beneficio de USD 118.800 y una inversión de USD 50.000: `(118.800 − 50.000) / 50.000 × 100 = 137,6%`. La interpretación es que cada peso invertido se recupera durante el año 1 y, además, genera un retorno adicional de USD 1,38 por encima de la inversión original. Esta sección 6 valida el cálculo de la Sección 8 y respalda el modelo económico propuesto.

> **Nota técnica complementaria**: el OPEX anual de USD 26.100 calculado en esta sección no se descuenta del cálculo de ROI año 1 porque corresponde a costo operativo del nuevo sistema, no a inversión. El ROI mide retorno sobre inversión inicial. Si en años posteriores se quisiera medir el beneficio neto operativo (ahorro − OPEX), el cálculo sería USD 118.800 − USD 26.100 = USD 92.700 de margen operativo neto recurrente, lo que sostiene un ROI acumulado a 3 años superior al 450%.

### 6.7 Supuestos clave del modelo de costos

Las cifras presentadas se sostienen sobre los siguientes supuestos explícitos:

1. **Volumen base**: 6.000 conversaciones mensuales, consistente con la Sección 8.
2. **Tasa de automatización objetivo**: 70% de consultas resueltas por IA sin escalado humano (consistente con Sección 8 KPI 1.6).
3. **Mix de modelos LLM**: 80% de generaciones con GPT-4o-mini (clasificación y respuestas simples) y 20% con GPT-4o (consultas complejas con RAG).
4. **Tokens promedio por conversación**: clasificación ~550 tokens (input+output); generación simple ~600 tokens; generación compleja con RAG ~3.300 tokens.
5. **WhatsApp como único canal operativo en el año 1**. La incorporación de redes sociales se evalúa para el año 2.
6. **Tipo de cambio**: precios en USD oficiales según pricing público de los proveedores en mayo de 2026.
7. **Tarifa de hora de desarrollador**: USD 45/hora (senior interno o contratado) y USD 60-80/hora para consultoría especializada.
8. **Base de conocimiento RAG**: ~13.000 vectores (500 pág. manuales + 100 pág. FAQs + 2.000 tickets), dimensión que cabe en el free tier de Pinecone.
9. **Mantenimiento evolutivo**: equivalente al 10-12% del CAPEX anualizado (≈ USD 8.640/año).
10. **Sin inflación ni ajustes de pricing de proveedores en años 2 y 3**: supuesto conservador para el TCO base.
11. **Plantium ya cuenta con Microsoft 365** (a validar con el área de IT). Si no fuera el caso, agregar USD 12-22/usuario/mes de licencias base.

### 6.8 Riesgos del modelo de costos

| Riesgo | Probabilidad | Impacto | Mitigación |
|---|---|---|---|
| Volumen real duplicado en temporada alta (cosecha) | Alta | Medio | Pricing variable de WhatsApp y LLM absorbe el crecimiento sin re-arquitectura. Pinecone Serverless escala bajo demanda. |
| Aumento de pricing OpenAI / Anthropic | Media | Medio | Multi-LLM con capa de abstracción (fallback a Claude o Gemini). Monitoreo mensual de gasto vs presupuesto. |
| Lock-in con Botmaker | Media | Medio | Diseñar capa de abstracción sobre la API de Botmaker. Evaluar exit en mes 12 con n8n self-hosted como plan B. |
| Cambios en pricing WhatsApp Business Platform | Alta | Alto | Modelar escenarios pesimistas (+50%). Tener BSP de respaldo (360dialog o Meta directo) preconfigurado. |
| Devaluación del peso argentino frente al USD | Alta | Alto | Cláusula de revisión semestral del presupuesto. Negociar plan anual con Botmaker para fijar precio. |
| Datos sensibles procesados fuera de jurisdicción AR | Media | Medio | Anonimización en cliente antes de enviar al LLM. Retención corta. Data Processing Agreement (DPA) explícito con cada proveedor. |
| Costos de mantenimiento subestimados | Media | Medio | Reserva del 15% en CAPEX. Revisión trimestral del OPEX real vs proyectado. |

### 6.9 Conclusión

La inversión total estimada para el año 1 asciende a USD 76.100 (USD 50.000 de CAPEX + USD 26.100 de OPEX), con un OPEX recurrente anual de USD 26.100 a partir del segundo año. Comparado contra el costo operativo actual de USD 216.000 anuales, el modelo propuesto genera un ahorro bruto de USD 118.800 anuales (55% según Sección 8), lo que se traduce en un **beneficio neto del año 1 de USD 68.800**, un **ROI del 137,6%** y un **payback estimado de 5 a 6 meses**, en línea con los valores reportados en la Sección 8.

El stack tecnológico recomendado —Botmaker + Twilio para canal WhatsApp, OpenAI para LLM, Pinecone para vector DB, Make.com para orquestación, DigitalOcean para hosting y Power BI para analítica— combina presencia local, transparencia de pricing y madurez de producto, y se alinea con el patrón validado por los referentes globales del sector citados en la Sección 2 (John Deere, Trimble y Syngenta). Esta selección permite iniciar el piloto con bajo riesgo financiero, escalar a producción con una arquitectura cloud-native y mantener flexibilidad para evolucionar componentes individuales (por ejemplo, migrar a n8n self-hosted en Fase 3) sin reescribir el sistema.

Desde una perspectiva estratégica, la inversión propuesta no es únicamente una optimización de costos: habilita la escalabilidad de la atención al cliente, libera capacidad del equipo técnico para tareas de mayor valor agregado, sistematiza el conocimiento de la organización en un activo reutilizable y posiciona a Plantium en el mismo nivel de madurez digital que sus referentes internacionales. La coherencia entre los costos calculados en esta sección y los indicadores de ROI proyectados en la Sección 8 valida la viabilidad económica del proyecto y respalda su aprobación para fase de implementación.

### 6.10 Fuentes de pricing consultadas (mayo 2026)

- Botmaker — <https://botmaker.com/en/prices>
- Aivo — <https://www.aivo.co/> (sin pricing público, contacto comercial)
- Twilio WhatsApp Business — <https://www.twilio.com/en-us/whatsapp/pricing>
- Meta WhatsApp Business Platform — <https://developers.facebook.com/docs/whatsapp/pricing>
- OpenAI API — <https://openai.com/api/pricing/>
- Anthropic Claude API — <https://www.anthropic.com/pricing>
- Pinecone — <https://www.pinecone.io/pricing/>
- Qdrant — <https://qdrant.tech/pricing/>
- Weaviate — <https://weaviate.io/pricing>
- Make.com — <https://www.make.com/en/pricing>
- Zapier — <https://zapier.com/pricing>
- n8n — <https://n8n.io/pricing/>
- DigitalOcean — <https://www.digitalocean.com/pricing>
- Power BI — <https://powerbi.microsoft.com/en-us/pricing/>
- Referencias comparativas chatbot AR — <https://www.artics.com.ar/cuanto-cuesta-chatbot-ia-para-empresas-argentina/> y <https://www.aimoova.com/post/chatbot-whatsapp-empresa-precio-cuanto-cuesta-2026>
