## 6. Análisis de proveedores y costos

**Responsable: Javier Zader**

### 6.1 Introducción

La solución propuesta en la Sección 5 contempla un sistema integral de atención al cliente basado en Inteligencia Artificial, que articula un asistente virtual sobre WhatsApp, una arquitectura de Generación Aumentada por Recuperación (RAG), un módulo de clasificación automática, un copiloto interno para los agentes y una capa de analítica. Cada uno de estos bloques funcionales requiere proveedores tecnológicos específicos, con modelos de precios y características diferenciales que deben evaluarse en función del contexto operativo de Plantium[^1].

A los efectos de dimensionar la inversión, el análisis se ancla en los volúmenes y supuestos económicos detallados en la Sección 8: aproximadamente 6.000 conversaciones mensuales, un costo operativo anual actual estimado en USD 216.000 y una meta de automatización del 70% de las consultas. Sobre esa base, la presente sección identifica proveedores candidatos por componente, los compara según criterios objetivos y ponderados, propone un stack tecnológico de referencia y desagrega la inversión total en CAPEX (inversión inicial) y OPEX (costo recurrente), de manera que el modelo económico pueda complementar y desagregar el ROI proyectado por la Sección 8.

El **análisis comparativo detallado por componente** (matrices de evaluación, tablas extendidas de alternativas, TCO comparativo) se encuentra en el **Anexo 6.A**. El **detalle del impacto fiscal argentino y el análisis de sensibilidad por volumen** se encuentra en el **Anexo 6.B**. El **cumplimiento normativo por proveedor** (Ley 25.326) se encuentra en el **Anexo 6.C**.

[^1]: Plantium, con aproximadamente 250 empleados, se clasifica como **PyME Mediana Tramo 2** según la resolución SEPYME vigente para el sector industrial (límite de empleados industria: 660). Aplican las obligaciones y beneficios fiscales de esa categoría.

#### 6.1.1 Definiciones operativas

Para evitar ambigüedades en las unidades económicas, esta sección utiliza los siguientes términos de manera consistente:

- **Mensaje**: cada interacción individual cliente-bot o cliente-agente. Es la **unidad económica primaria** de tarificación de WhatsApp Business Platform desde julio de 2025, cuando Meta migró del modelo per-conversación al modelo por mensaje. Es también la unidad de cobro de Twilio (fee por mensaje, no por conversación).
- **Conversación**: sesión funcional de 24 horas iniciada por un usuario en WhatsApp; contiene en promedio entre 5 y 8 mensajes individuales. Se mantiene como **unidad de referencia operativa** para dimensionar el volumen del negocio, pero **ya no es la unidad de cobro** de WhatsApp.
- **Ventana de servicio**: período de 24 horas que se abre cuando el cliente inicia el contacto. Durante esa ventana, los mensajes de respuesta del negocio (mensajes de servicio) y las plantillas utility son **gratuitas** según el modelo Meta vigente. Esto es central en el caso Plantium porque la atención post-venta es mayormente iniciada por el cliente.
- **Consulta**: necesidad de información o resolución que el usuario plantea; puede materializarse en 1 a 3 conversaciones según complejidad.
- **Ticket**: caso registrado en el CRM que requiere seguimiento posterior por un agente humano.
- **Sesión**: interacción continua entre usuario y bot dentro de una conversación.

Salvo aclaración explícita, todas las referencias económicas a volumen usan **mensaje** como unidad de cobro y **conversación** como unidad de dimensionamiento del negocio.

#### 6.1.2 Glosario técnico

- **BSP** (Business Solution Provider): proveedor oficial autorizado por Meta para revender WhatsApp Business Platform (ej.: Twilio, 360dialog, Botmaker).
- **CAPEX**: gasto de capital, inversión inicial no recurrente.
- **DPA** (Data Processing Agreement): contrato que regula cómo un proveedor procesa datos personales del cliente, requerido por Ley 25.326.
- **FTE** (Full-Time Equivalent): unidad de medida que equivale a una persona trabajando jornada completa (~2.000 horas/año). Se distingue entre **FTE bruto** (capacidad horaria absorbida por automatización) y **FTE costo-equivalente** (costo en USD ahorrado dividido por costo unitario por FTE).
- **FX**: tipo de cambio (foreign exchange); en este documento, peso argentino frente al dólar estadounidense.
- **iPaaS** (Integration Platform as a Service): plataforma cloud para automatizar flujos entre sistemas (ej.: Make.com, n8n, Zapier).
- **LLM** (Large Language Model): modelo de lenguaje de gran escala usado para clasificación y generación de respuestas (ej.: GPT-4o, Claude Sonnet).
- **OPEX**: gasto operativo, costo recurrente mensual o anual.
- **RAG** (Retrieval-Augmented Generation): técnica que combina recuperación semántica desde una base vectorial con generación de respuestas por un LLM.
- **SLA** (Service Level Agreement): acuerdo de nivel de servicio que define disponibilidad, tiempos de respuesta y compensaciones.
- **TCO** (Total Cost of Ownership): costo total de propiedad a un horizonte dado (típicamente 3 años en este análisis).

### 6.2 Criterios de selección de proveedores

Para evaluar las opciones de cada componente se aplicaron siete criterios ponderados según la realidad de una PyME industrial argentina. La ponderación refleja la prioridad estratégica de presencia local y capacidad de integración para Plantium:

| # | Criterio | Peso |
|---|---|---:|
| 1 | Presencia y soporte en Argentina o LATAM (idioma español, huso horario, facturación local cuando es posible) | 15% |
| 2 | Madurez del producto (años en mercado, casos publicados, clientes referenciables) | 15% |
| 3 | Modelo de precios transparente (preferencia por precios públicos y pago por uso sobre licencias fijas durante la fase piloto) | 10% |
| 4 | Capacidad de integración con el CRM existente, WhatsApp Business API y el eventual ERP de Plantium | 20% |
| 5 | Cumplimiento de privacidad y seguridad — Ley 25.326 de Protección de Datos Personales de Argentina, residencia configurable de datos, DPA disponible, opciones de exclusión de entrenamiento | 15% |
| 6 | Escalabilidad, entendida como la capacidad de absorber un crecimiento de 6.000 a 15.000 conversaciones mensuales sin cambios estructurales | 10% |
| 7 | Costo total de propiedad (TCO) a 3 años, no solo costo inicial | 15% |
| | **Total** | **100%** |

### 6.3 Componentes de la solución que requieren proveedor

La arquitectura descripta en la Sección 5 se descompone en **ocho componentes** funcionales que requieren un proveedor externo o un componente tecnológico específico:

| Componente | Función en la solución | Criticidad |
|---|---|---|
| Canal de mensajería | Recibir y enviar mensajes vía WhatsApp Business API (interfaz con el cliente) | Alta — único punto de contacto en fase 1 |
| Plataforma de bot y orquestación conversacional | Manejar sesiones, flujos, derivación al agente humano, métricas de canal | Alta — corazón operativo |
| Motor LLM (IA generativa) | Comprender intención, clasificar consultas, generar respuestas en lenguaje natural | Alta — capa de inteligencia |
| Base vectorial para RAG | Almacenar embeddings de manuales, FAQs e histórico de tickets resueltos | Media — habilita precisión técnica |
| Plataforma de automatización (iPaaS) | Integrar componentes, mover datos entre el bot, el CRM y la base de conocimiento | Media — pegamento del stack |
| Infraestructura de hosting | Alojar servicios a medida (copiloto, conectores, eventual alojamiento propio del vector DB) | Media — soporte transversal |
| Copiloto interno para agentes | Asistir al agente humano con sugerencias de respuesta y resúmenes de caso en tiempo real | Media — palanca de productividad |
| Capa de analítica | Tableros operativos y de negocio para supervisores y gerencia | Media — visibilidad y mejora continua |

### 6.4 Stack tecnológico recomendado

Tras el análisis comparativo y las matrices de evaluación presentadas en el **Anexo 6.A**, se propone el siguiente stack como decisión de diseño. La selección prioriza presencia local, transparencia de precios y TCO a 3 años:

| Componente | Proveedor recomendado | Justificación (síntesis) |
|---|---|---|
| Canal WhatsApp | **Twilio (vía Botmaker)** | Botmaker gestiona la integración WhatsApp como BSP oficial. Se elimina la doble factura. |
| Plataforma de bot | **Botmaker** | Empresa argentina, facturación local, soporte en español, 9+ años en el mercado, integra WhatsApp BSP nativamente. Mejor encaje con el perfil PyME de Plantium. |
| Motor LLM | **OpenAI: GPT-4o-mini (80%) + GPT-4o (20%)** | Mejor relación calidad/precio del mercado. La combinación permite controlar costos manteniendo calidad en consultas complejas con RAG. |
| Embeddings | **OpenAI text-embedding-3-small** | Mejor relación costo/calidad multilingüe; integración natural con el resto del stack OpenAI. |
| Vector DB | **Pinecone Serverless (Free → Builder)** | La capa gratuita alcanza para el piloto. Migración a Builder (USD 20/mes flat) cuando el piloto pase a producción. Sin necesidad de operar infraestructura. |
| Automatización iPaaS | **Make.com (plan Business)** | Mejor balance entre precio y capacidad. Migrable a n8n con alojamiento propio en Fase 3 si los volúmenes lo justifican. |
| Copiloto interno | **OpenAI Assistants API integrado al CRM** | Aprovecha la inversión en OpenAI. Desarrollo a medida permite integración profunda con el CRM existente de Plantium. |
| Hosting backend | **DigitalOcean** | Precios predecibles, simple para una PyME, suficiente para los servicios a medida previstos. |
| Analítica | **Power BI Pro** | Se asume entorno Microsoft 365 ya presente en Plantium (validar con el área de IT). Microsoft factura localmente con IVA, lo que reduce el impacto cambiario respecto de otros SaaS extranjeros. |

> El análisis comparativo detallado por componente (alternativas evaluadas, costos por proveedor, matrices de evaluación ponderadas, TCO comparativo a 3 años) se desarrolla en el **Anexo 6.A**.

### 6.5 Estimación de costos

#### 6.5.1 CAPEX (inversión inicial, por única vez)

| Concepto | Detalle | Monto USD |
|---|---|---:|
| Configuración inicial WhatsApp Business Platform | Verificación Meta + Botmaker WhatsApp Business | 100 |
| Incorporación Botmaker empresarial | Activación + configuración inicial | 1.500 |
| Desarrollo integraciones Botmaker ↔ CRM Plantium | 120 horas desarrollador senior @ USD 45/h (asume CRM en la nube con API REST tipo Salesforce, HubSpot, Zoho — confirmar en relevamiento técnico inicial) | 5.400 |
| Indexación inicial RAG — segmentación + preparación | 30 horas @ USD 45/h (digitalización, limpieza, segmentación de manuales) | 1.350 |
| Indexación inicial RAG — generación de embeddings | 6,5M tokens × USD 0,02/1M (OpenAI text-embedding-3-small) | ~1 |
| Vectorización base de conocimiento — infraestructura y QA | Validación de calidad de recuperación + ajustes de segmentación | 1.650 |
| Desarrollo del copiloto interno (módulo CRM) | A medida + integración OpenAI Assistants, 180 horas @ USD 45/h | 8.100 |
| Configuración de dashboards Power BI | Diseño + conexión a datos, 80 horas @ USD 45/h | 3.600 |
| Diseño UX y personalidad conversacional del bot | Branding conversacional + flujos críticos | 2.500 |
| Capacitación equipo operativo (12 personas) | 2 jornadas de 6 horas | 3.000 |
| Capacitación supervisores (3 personas) | 1 jornada especializada + materiales | 1.500 |
| Consultoría externa de gestión del cambio | 40 horas @ USD 80/h | 3.200 |
| Configuración inicial de infraestructura backend (DigitalOcean) | Provisión de servidores, CI/CD, observabilidad | 2.000 |
| Testing y QA | Pruebas funcionales, de carga y de aceptación (80 hs @ USD 45/h) | 3.600 |
| Documentación técnica y manual de operación | Entregables del proyecto | 2.000 |
| **Subtotal CAPEX antes de contingencia** | | **39.500** |
| Contingencia (15%) | Reserva para imprevistos | 5.925 |
| **TOTAL CAPEX detallado** | | **45.425** |
| Ajuste de coherencia con Sección 8 (licencias adicionales, análisis de brechas ISO 27001, reserva de tarifa) | Ver nota | 4.575 |
| **CAPEX REFERENCIA SECCIÓN 8** | | **50.000** |

> **Nota de reconciliación con Sección 8**: la Sección 8 (Magdalena) asume una inversión inicial de USD 50.000. El CAPEX detallado en esta sección llega a USD 45.425. La brecha de USD 4.575 se compone de: aproximadamente USD 2.000 en licencias adicionales no proyecto-específicas (Office, antivirus corporativo, herramientas de desarrollo), USD 1.500 para un **análisis de brechas de ISO 27001** (diagnóstico de brechas, no certificación completa — la certificación completa requeriría 12-18 meses adicionales y un presupuesto del orden de USD 25.000) y USD 1.075 como reserva adicional para ajuste de tarifa de proveedores durante la implementación. Se adopta USD 50.000 como cifra de referencia para el ROI por coherencia con la Sección 8.
>
> **Nota técnica adicional sobre el CRM**: la línea de 120 horas para integración Botmaker ↔ CRM asume un CRM en la nube con API REST documentada. Si en el relevamiento técnico se identifica que Plantium opera un CRM heredado o a medida, deben agregarse entre **80 y 150 horas adicionales (USD 3.600 a 6.750)** que se imputarán contra la contingencia o se elevarán como ajuste de presupuesto.

#### 6.5.2 OPEX (costos recurrentes mensuales y anuales)

| Concepto | Proveedor | Costo mensual USD | Costo anual USD |
|---|---|---:|---:|
| Plataforma de bot | Botmaker (plan empresa) | 600 | 7.200 |
| WhatsApp Business — mensajería | 6.000 conv/mes (~42.000 mensajes); modelo por mensaje vigente: mensajes de servicio dentro de ventana 24h gratis + utility templates fuera de ventana + fee Twilio USD 0,005/mensaje | 360 | 4.320 |
| LLM nominal (OpenAI API, combinación 80/20) | Cálculo base: USD 16/mes. Se reserva techo de USD 65/mes como contingencia (4×) | 65 | 780 |
| Embeddings — re-indexación mensual | ~200 docs/mes × 500 tokens/fragmento = 100k tokens × USD 0,02/1M | <1 (despreciable) | 0 |
| Vector DB | Pinecone Builder | 20 | 240 |
| iPaaS automatización | Make.com (plan Business) | 50 | 600 |
| Hosting backend | DigitalOcean (droplets + managed services) | 80 | 960 |
| Power BI Pro (Microsoft, facturación local con IVA) | 5 licencias supervisores × USD 14 | 70 | 840 |
| Copiloto interno (uso OpenAI Assistants) | Tokens adicionales para los 12 agentes | 90 | 1.080 |
| Observabilidad y logging | Stack mínimo (Grafana Cloud) + gestión de secretos | 33 | 396 |
| Mantenimiento evolutivo año 1 (estabilización) | 14 horas/mes consultor externo local @ USD 60/h | 840 | 10.080 |
| Capacitación continua | Cursos + horas internas | 100 | 1.200 |
| **TOTAL OPEX nominal** | | **~USD 2.308 / mes** | **~USD 27.696 / año** |

> **Nota sobre el modelo de precios de WhatsApp**: Meta migró del modelo per-conversación al modelo **por mensaje** el 1 de julio de 2025. Adicionalmente, en abril de 2026 incorporó ARS (peso argentino) como moneda de facturación. En el caso Plantium, la atención post-venta es mayormente iniciada por el cliente, lo que permite aprovechar la **ventana de servicio de 24 horas** durante la cual los mensajes de respuesta del negocio y los utility templates son gratuitos. El costo se concentra en (a) los utility templates proactivos fuera de ventana (~10% del volumen), (b) eventuales campañas marketing (acotadas en fase 1) y (c) el fee por mensaje de Twilio. La estimación de USD 360/mes es conservadora y debe revalidarse al firmar con el BSP antes de implementación.
>
> **Nota sobre el LLM**: el cálculo base de la combinación 80/20 da USD 16/mes. Se mantiene un buffer del 4× (USD 65/mes) para absorber crecimiento, variación de tokens y eventual aumento de precios. Si tras 6 meses de operación el consumo real se mantiene cerca de USD 16, este ítem puede reducirse en la revisión semestral.
>
> **Nota sobre mantenimiento**: el primer año contempla una carga superior por estabilización (USD 10.080 ≈ 22% del CAPEX). A partir del año 2, esta línea se reduce a 8-10 hs/mes (USD 480-600/mes) equivalente al 10-13% del CAPEX anualizado, alineado con el supuesto 9 de 6.6. La proyección TCO de 6.5.4 refleja esta reducción.

#### 6.5.3 Inversión total estimada — Año 1

| Categoría | USD |
|---|---:|
| CAPEX (referencia Sección 8) | 50.000 |
| OPEX 12 meses (nominal) | 27.696 |
| **Total año 1 (nominal)** | **77.696** |

#### 6.5.4 Proyección TCO a 3 años

Considerando la reducción de mantenimiento del año 2 en adelante (de USD 10.080 a USD 6.000 anuales por estabilización):

| Año | CAPEX | OPEX anual | Total año | Acumulado |
|---|---:|---:|---:|---:|
| 1 | 50.000 | 27.696 | 77.696 | 77.696 |
| 2 | — | 23.616 | 23.616 | 101.312 |
| 3 | — | 23.616 | 23.616 | 124.928 |

> **Importante**: el TCO base asume precios nominales en USD sin ajuste de inflación o reajuste de precios del proveedor. El supuesto 10 de 6.6 detalla las implicancias. El análisis de impacto fiscal argentino sobre el TCO se desarrolla en el **Anexo 6.B.1**.

#### 6.5.5 Comparación con costo actual y validación del ROI — Cinco lecturas complementarias

Según la Sección 8, el costo operativo anual actual del proceso AS IS asciende a USD 216.000 (6.000 consultas/mes × 15 minutos promedio × USD 12/hora de colaborador × 12 meses). Con la solución propuesta y una tasa de automatización del 70%, el ahorro bruto estimado es de USD 118.800 anuales (55% del costo actual).

**Relación entre la tasa de automatización (70%) y el ahorro de costos (55%)**: la automatización del 70% es un KPI de **volumen** — el 70% de las consultas se resuelven sin escalado humano. El ahorro del 55% del costo refleja dos efectos distintos. Primero, las consultas que no se automatizan (30%) son las **más complejas**, con mayor duración promedio por caso que el ticket medio del AS IS, por lo que consumen una fracción del costo superior a su fracción de volumen. Segundo, existen **costos fijos de supervisión, calidad y excepciones** que no se reducen linealmente con la automatización (el supervisor sigue existiendo aunque los agentes manejen menos tickets). Por eso 70% de volumen automatizado se traduce en 55% de costo ahorrado.

A continuación se presentan **cinco métricas complementarias** de retorno; cada una mide algo distinto y debe leerse en conjunto:

| Métrica | Fórmula | Valor |
|---|---|---:|
| **ROI sobre CAPEX** (convención clásica, alineada con Sección 8) | (Ahorro anual − CAPEX) / CAPEX = (118.800 − 50.000) / 50.000 | **137,6%** |
| **ROI sobre inversión total año 1** (incluye OPEX) | (Ahorro anual − Inversión total año 1) / Inversión total año 1 = (118.800 − 77.696) / 77.696 | **52,9%** |
| **Beneficio neto operativo año 1** (más conservador) | Ahorro anual − CAPEX − OPEX año 1 = 118.800 − 50.000 − 27.696 | **USD 41.104** |
| **Payback bruto** (sobre CAPEX, sin OPEX) | CAPEX / (Ahorro mensual) = 50.000 / (118.800/12) | **5,05 meses** |
| **Payback neto** (descontando OPEX mensual) | CAPEX / (Ahorro mensual − OPEX mensual) = 50.000 / (9.900 − 2.308) | **6,59 meses** |

**Lectura de las métricas**: el ROI del **137,6%** que reporta la Sección 8 es válido y responde a la convención clásica de retorno sobre CAPEX, donde el OPEX es costo operativo del nuevo sistema y no se descuenta de la inversión inicial. Esta sección 6 **complementa y desagrega** ese indicador, presentando además las otras cuatro lecturas que dan una visión más completa: el ROI sobre inversión total del 52,9%, el beneficio neto operativo del año 1 de USD 41.104, el payback bruto de 5,05 meses y el payback neto de 6,59 meses. Las cinco métricas son verdaderas; las cinco son consistentes entre sí. La que se enfatice depende del público objetivo del análisis (directorio, banco, auditor).

**Traducción del ahorro en FTE — capacidad bruta vs costo-equivalente**: el costo AS IS de USD 216.000/año equivale a aproximadamente 18.000 horas/año (6.000 conv/mes × 15 min × 12 meses), es decir **9 FTE equivalentes** asumiendo 2.000 horas/año por colaborador. Sobre esta base se distinguen dos magnitudes que suelen confundirse:

- **Capacidad bruta automatizada: 6,3 FTE** (70% × 9 FTE totales en atención). Es la **capacidad horaria** que la automatización absorbe del proceso.
- **FTE costo-equivalentes: 4,95 FTE** (USD 118.800 ahorrados / (USD 216.000 / 9 FTE) = 118.800 / 24.000). Es el **equivalente económico** del ahorro reconocido en la Sección 8.

La brecha entre 6,3 FTE de capacidad bruta y 4,95 FTE costo-equivalentes refleja: (a) las consultas no automatizadas son las más complejas y consumen más tiempo por caso; (b) existen costos fijos de supervisión y excepciones que no se reducen linealmente con la automatización.

**Consistencia con la dotación operativa**: Plantium cuenta con **12 agentes operativos** en las áreas comercial y servicio técnico, con una dedicación efectiva al canal de atención post-venta equivalente a **9 FTE** (~75% de su jornada). El resto de su tiempo lo asignan a tareas administrativas, capacitación y excepciones que no entran en el alcance de la automatización. La reasignación operativa apunta a liberar capacidad bruta para ventas consultivas, mantenimiento proactivo de equipos en campo, capacitación de clientes y monitoreo de calidad de las respuestas automatizadas.

**Ahorro neto acumulado a 3 años** (ahorro × 3 − TCO 3 años): USD 356.400 − USD 124.928 = **USD 231.472**.

> El análisis del impacto fiscal argentino sobre las métricas de retorno y el análisis de sensibilidad por volumen de conversaciones se desarrollan en el **Anexo 6.B**.

### 6.6 Supuestos clave del modelo de costos

Las cifras presentadas se sostienen sobre los siguientes supuestos explícitos:

1. **Volumen base**: 6.000 conversaciones mensuales (~42.000 mensajes), consistente con la Sección 8.
2. **Tasa de automatización objetivo**: 70% de consultas resueltas por IA sin escalado humano (consistente con Sección 8 KPI 1.6).
3. **Combinación de modelos LLM**: 80% de generaciones con GPT-4o-mini (clasificación y respuestas simples) y 20% con GPT-4o (consultas complejas con RAG).
4. **Tokens promedio por conversación**: clasificación ~550 tokens (entrada+salida); generación simple ~600 tokens; generación compleja con RAG ~3.300 tokens.
5. **WhatsApp como único canal operativo en el año 1** y modelo **por mensaje** vigente (post-julio 2025), con aprovechamiento intensivo de la ventana de servicio gratuita de 24h. La incorporación de redes sociales se evalúa para el año 2.
6. **Tipo de cambio**: precios en USD oficiales según precios públicos de los proveedores en mayo de 2026.
7. **Tarifa de hora de desarrollador**: USD 45/hora (senior interno o contratado) y USD 60-80/hora para consultoría especializada.
8. **Base de conocimiento RAG**: ~13.000 vectores (500 pág. manuales + 100 pág. FAQs + 2.000 tickets), dimensión que cabe en la capa gratuita de Pinecone.
9. **Mantenimiento evolutivo**: año 1 entre 18% y 22% del CAPEX por estabilización (USD 10.080/año); años 2 y 3 entre 10% y 13% del CAPEX (USD 6.000/año).
10. **Supuesto simplificador (NO conservador) sobre inflación**: el TCO base asume precios USD planos en años 2 y 3. En la práctica, el contexto inflacionario argentino y la tendencia de tarifas SaaS USD pueden elevar el TCO real entre **10% y 20% año-año**, lo que equivale a un sobrecosto acumulado del **25% al 35% a 3 años**. Debe contemplarse en la presupuestación corporativa.
11. **Plantium ya cuenta con Microsoft 365** (a validar con el área de IT). Si no fuera el caso, agregar USD 12-22/usuario/mes de licencias base.
12. **CRM objetivo**: la estimación de 120 horas para integración asume CRM en la nube con API REST. CRM heredado/a medida suma 80-150 hs adicionales (USD 3.600 a 6.750), a confirmar en relevamiento.

### 6.7 Riesgos del modelo de costos

| Riesgo | Probabilidad | Impacto | Mitigación |
|---|---|---|---|
| Volumen real duplicado en temporada alta (cosecha) | Alta | Medio | Precios variables de WhatsApp y LLM absorben el crecimiento sin re-arquitectura. Pinecone Serverless escala bajo demanda. Escenario modelado en **Anexo 6.B.2**. |
| Aumento de precios OpenAI / Anthropic | Media | Medio | Multi-LLM con capa de abstracción (alternativa de respaldo: Claude o Gemini). Monitoreo mensual de gasto vs presupuesto. Buffer de 4× ya incorporado en OPEX. |
| Dependencia del proveedor Botmaker | Media | Medio | Diseñar capa de abstracción sobre la API de Botmaker. **Costo estimado de salida: USD 5.000 a 8.000** (40-60 hs de remigración a stack alternativo n8n + 20 hs de re-entrenamiento de equipo). Evaluar salida en mes 12. |
| Dependencia del proveedor Pinecone | Baja | Bajo | **Costo de salida estimado USD 500-1.000**: datos exportables vía API, índices recreables en Qdrant en 2-5 días. |
| Dependencia del proveedor Make.com | Baja | Bajo | **Costo de salida estimado USD 2.000-3.000**: escenarios migrables a n8n en 1-2 semanas. |
| Cambios en precios de WhatsApp Business Platform | Alta | Alto | Modelo por mensaje vigente desde julio 2025; modelar escenarios pesimistas (+50%). Tener BSP de respaldo (360dialog o Meta directo) preconfigurado. |
| Devaluación del peso argentino frente al USD | Alta | Alto | **Negociar plan anual con descuento por pre-pago** (típicamente 10-20% off, fija el precio USD para 12 meses). Mantener reserva financiera trimestral en USD para absorber FX. Re-evaluar proveedores cada 6 meses con perspectiva FX y disponibilidad de cobertura cambiaria. |
| Datos sensibles procesados fuera de jurisdicción AR | Media | Medio | **Anonimización en cliente antes de enviar al LLM**. Retención corta (30-60 días). DPA explícito con cada proveedor (ver **Anexo 6.C**). Si el riesgo es alto, evaluar migración del LLM a Vertex AI región sa-east1 (São Paulo). |
| Costos de mantenimiento subestimados | Media | Medio | Reserva del 15% en CAPEX. Mantenimiento año 1 ya elevado a 22% del CAPEX (supuesto 9). Revisión trimestral del OPEX real vs proyectado. |
| Inyección de prompts y abuso del bot | Media | Medio | Guardrails de entrada/salida, moderación con OpenAI Moderation API (gratuita), monitoreo de comportamiento anómalo, limitación de tasa por número de teléfono. Costo cubierto por la línea de mantenimiento evolutivo. |
| Pérdida o corrupción de la base vectorial | Baja | Alto | Copias de seguridad automáticas de Pinecone, respaldo mensual del conjunto de documentos fuente, capacidad de reindexar en menos de 24 horas con presupuesto < USD 5. |
| Carga fiscal AR mayor a la proyectada | Media | Medio | Coeficiente 1,5× ya incorporado en **Anexo 6.B.1**. Negociar facturación local con proveedores cuando exista (Botmaker, Microsoft). Recupero activo de percepciones de Ganancias en la DDJJ. |

### 6.8 Conclusión

El stack tecnológico recomendado se construyó priorizando tres factores: **presencia local y soporte en español** (Botmaker como ancla del canal y la plataforma de bot), **transparencia de precios y TCO controlable** (OpenAI con combinación 80/20, Pinecone (capa gratuita→Builder), DigitalOcean, Make.com Business) y **cumplimiento de la Ley 25.326** (proveedores con DPA disponible, anonimización en cliente, residencia configurable cuando aplica). Esta combinación permite iniciar el piloto con bajo riesgo financiero, escalar a producción con arquitectura en la nube y mantener flexibilidad para evolucionar componentes individuales (por ejemplo, migrar a n8n con alojamiento propio en Fase 3) sin reescribir el sistema.

El **enfoque** del stack —datos centralizados, automatización conversacional, integración profunda con CRM y analítica embebida— está alineado con los referentes globales del sector citados en la Sección 2 (John Deere, Trimble, Syngenta). Las **herramientas específicas difieren por escala**: esos referentes operan plataformas propias desarrolladas de forma interna o plataformas empresariales (Salesforce Einstein, Microsoft Dynamics + Copilot Studio) con presupuestos varias órdenes de magnitud mayores. La propuesta para Plantium adopta el mismo paradigma con herramientas apropiadas para una PyME industrial de 250 empleados.

Desde una perspectiva estratégica, la inversión propuesta no es únicamente una optimización de costos: habilita la **escalabilidad** de la atención al cliente (capaz de absorber un crecimiento de 6.000 a 15.000 conversaciones/mes sin re-arquitectura, según **Anexo 6.B.2**), libera **6,3 FTE de capacidad bruta** (equivalentes a 4,95 FTE costo-equivalentes) del equipo técnico para tareas de mayor valor agregado (ventas consultivas, mantenimiento proactivo, capacitación a clientes), sistematiza el conocimiento de la organización en un **activo reutilizable** (la base vectorial RAG se enriquece con cada ticket resuelto) y posiciona a Plantium en una madurez digital comparable a sus referentes internacionales en el paradigma operativo, aunque con un ticket de inversión adecuado a su escala.

Las cinco lecturas del retorno presentadas en 6.5.5 —ROI sobre CAPEX (137,6%), ROI sobre inversión total año 1 (52,9%), beneficio neto operativo (USD 41.104), payback bruto (5,05 meses) y payback neto (6,59 meses)— ofrecen al directorio un panorama transparente y conservador del impacto económico, complementando el indicador agregado reportado en la Sección 8. El análisis adicional del impacto fiscal argentino (**Anexo 6.B.1**) muestra que aun con el coeficiente de carga 1,5× sobre proveedores extranjeros, el ROI sobre inversión total se mantiene en torno al **44%** y el payback neto bajo carga AR en aproximadamente **7 meses**, manteniendo la viabilidad financiera del proyecto.

### 6.9 Fuentes consultadas

**Primarias (sitios oficiales de cada proveedor):**

- Botmaker (2026). *Plans and Pricing*. <https://botmaker.com/en/prices> [Consultado: 24 mayo 2026]
- Aivo (2026). *Sitio corporativo* (sin pricing público, contacto comercial). <https://www.aivo.co/> [Consultado: 24 mayo 2026]
- Twilio (2026). *WhatsApp Messaging Pricing*. <https://www.twilio.com/en-us/whatsapp/pricing> [Consultado: 24 mayo 2026]
- Meta (2026). *WhatsApp Business Platform Pricing — Per-message rates*. <https://developers.facebook.com/docs/whatsapp/pricing> [Consultado: 24 mayo 2026]
- Meta (2026). *Argentina billing currency (ARS) — effective April 2026*. <https://developers.facebook.com/documentation/business-messaging/whatsapp/pricing> [Consultado: 24 mayo 2026]
- OpenAI (2026). *API Pricing*. <https://openai.com/api/pricing/> [Consultado: 24 mayo 2026]
- Anthropic (2026). *Claude API Pricing*. <https://www.anthropic.com/pricing> [Consultado: 24 mayo 2026]
- Pinecone (2026). *Pricing*. <https://www.pinecone.io/pricing/> [Consultado: 24 mayo 2026]
- Qdrant (2026). *Cloud Pricing*. <https://qdrant.tech/pricing/> [Consultado: 24 mayo 2026]
- Weaviate (2026). *Pricing*. <https://weaviate.io/pricing> [Consultado: 24 mayo 2026]
- Make.com (2026). *Pricing*. <https://www.make.com/en/pricing> [Consultado: 24 mayo 2026]
- Zapier (2026). *Pricing*. <https://zapier.com/pricing> [Consultado: 24 mayo 2026]
- n8n (2026). *Pricing*. <https://n8n.io/pricing/> [Consultado: 24 mayo 2026]
- DigitalOcean (2026). *Pricing*. <https://www.digitalocean.com/pricing> [Consultado: 24 mayo 2026]
- Microsoft (2026). *Power BI Pricing*. <https://powerbi.microsoft.com/en-us/pricing/> [Consultado: 24 mayo 2026]
- Microsoft (2026). *Copilot Studio Pricing*. <https://www.microsoft.com/en-us/microsoft-copilot/microsoft-copilot-studio> [Consultado: 24 mayo 2026]
- Hetzner (2026). *Cloud Pricing*. <https://www.hetzner.com/cloud/> [Consultado: 24 mayo 2026]
- Cohere (2026). *API Pricing*. <https://cohere.com/pricing> [Consultado: 24 mayo 2026]

**Secundarias (referencias comparativas y análisis de mercado):**

- Artics (2026). *¿Cuánto cuesta un chatbot con IA para empresas en Argentina?* <https://www.artics.com.ar/cuanto-cuesta-chatbot-ia-para-empresas-argentina/> [Consultado: 24 mayo 2026]
- Aimoova (2026). *Chatbot WhatsApp empresa precio: cuánto cuesta 2026*. <https://www.aimoova.com/post/chatbot-whatsapp-empresa-precio-cuanto-cuesta-2026> [Consultado: 24 mayo 2026]
- Twilio Help Center (2026). *Understanding WhatsApp Pricing*. <https://help.twilio.com/articles/360029359354> [Consultado: 24 mayo 2026]
- Engagelab (2026). *WhatsApp Business API Pricing 2026 Complete Cost Guide*. <https://www.engagelab.com/blog/whatsapp-business-api-pricing> [Consultado: 24 mayo 2026]
- AFIP / ARCA (2026). *Régimen de servicios digitales — IVA y percepciones*. <https://www.afip.gob.ar/iva/servicios-digitales/> [Consultado: 24 mayo 2026]
- SEPYME (2025). *Clasificación PyME — Tramos por sector*. Resolución vigente para sector industrial. [Consultado: 24 mayo 2026]

---

## Anexo 6.A — Análisis comparativo detallado por componente

Para cada componente se evaluaron entre 3 y 5 alternativas, considerando el volumen objetivo de 6.000 conversaciones por mes (~42.000 mensajes). Los rangos de costo corresponden a precios públicos verificados en mayo de 2026. Al cierre de cada componente principal se incluye una matriz de evaluación (1 = muy débil; 5 = excelente) ponderada con los pesos definidos en 6.2.

### A.1 Canal WhatsApp Business

Desde el 1 de julio de 2025, Meta migró de precios per-conversación a **precios por mensaje**. Las categorías son cuatro:
- **Service** (respuestas dentro de la ventana de 24h iniciada por el cliente): **gratuitas**.
- **Utility** dentro de ventana de servicio: **gratuitas**; fuera de ventana: USD 0,004 – 0,046 por mensaje según país.
- **Authentication** (2FA, OTP): tarifa más baja (Meta promueve este uso).
- **Marketing**: tarifa más alta, USD 0,01 – 0,14 por mensaje según país (Brasil ref. USD 0,0625).

En abril de 2026, Meta incorporó ARS (peso argentino) como moneda de facturación para Argentina y aplicó tarifas locales reducidas para utility y authentication efectivas desde octubre 2025.

Cuando se opera a través de un BSP como Twilio, se suma un fee adicional del BSP de **USD 0,005 por mensaje** (entrante o saliente). Para Plantium (6.000 conv/mes ≈ 42.000 mensajes/mes), con atención mayormente iniciada por el cliente, la combinación BSP + Meta se estima en **USD 300 – 450/mes**.

| Proveedor | Modelo de precios | Costo mensual estimado (42k msg/mes) | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **Twilio + WhatsApp API** | USD 0,005 por mensaje (fee Twilio) + tarifa Meta por mensaje por categoría | USD 300 – 450 | Flexibilidad máxima, ecosistema robusto, documentación amplia, facturación en ARS disponible | Requiere desarrollo propio, sin interfaz de gestión incluida |
| **Meta Cloud API directo** | Solo tarifa Meta por mensaje (sin fee de BSP intermediario) | USD 200 – 350 | Costo más bajo posible | Sin SLA empresarial directo, soporte limitado, sin UI |
| **360dialog** | USD 49 – 99/mes plataforma + fees Meta por mensaje | USD 280 – 450 | BSP oficial Meta, fuerte en LATAM, foco empresarial | Sin oficina en Argentina, soporte vía partners |
| **Wati** | USD 49 – 99/mes plataforma + fees Meta por mensaje | USD 250 – 400 | UI lista para PyME, multi-agente | Foco más comercial que técnico |

**Matriz de decisión (canal WhatsApp)** — pesos ajustados para este componente: integración 25%, precios 20%, presencia AR 20%, cumplimiento 15%, madurez 10%, escalabilidad 10%.

| Alternativa | Integración (25%) | Precios (20%) | Pres. AR (20%) | Cumplimiento (15%) | Madurez (10%) | Escala (10%) | Puntuación |
|---|:---:|:---:|:---:|:---:|:---:|:---:|---:|
| Twilio (vía Botmaker) | 5 | 4 | 4 | 4 | 5 | 5 | **4,45** |
| Meta Cloud API directo | 3 | 5 | 2 | 4 | 4 | 5 | **3,65** |
| 360dialog | 4 | 4 | 3 | 4 | 4 | 4 | **3,80** |
| Wati | 4 | 4 | 2 | 3 | 3 | 4 | **3,35** |

Cálculo Twilio: 5×0,25 + 4×0,20 + 4×0,20 + 4×0,15 + 5×0,10 + 5×0,10 = 1,25 + 0,80 + 0,80 + 0,60 + 0,50 + 0,50 = **4,45**.

Ganador: **Twilio operado a través de Botmaker** — combina la robustez técnica de Twilio con facturación y soporte local de Botmaker, eliminando la doble factura.

### A.2 Plataforma de bot y orquestación

| Proveedor | Modelo de precios | Costo mensual estimado | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **Botmaker (Argentina)** | Plan gratuito hasta 300 sesiones; planes pagos desde USD 100/mes hasta USD 1.000+/mes según volumen; configuración inicial WhatsApp Business: USD 99 por única vez | USD 500 – 800 | Empresa argentina con 9+ años, facturación local, soporte en español, integra WhatsApp BSP nativamente | Dependencia del proveedor moderada por configuración de flujos |
| **Aivo (Argentina/LATAM)** | Precios a medida (no públicos), modelo empresarial | USD 800 – 2.000 (estimado) | Líder LATAM, clientes referenciables (Sony, Visa, Movistar, GM), oferta empresarial consolidada | Sin precios transparentes, ticket alto para PyME |
| **Voiceflow** | Desde USD 50/mes (Pro), USD 800/mes (Teams) | USD 800 – 1.200 | UX de diseño conversacional superior, integración nativa con LLMs | Foco voz/multicanal, sin partner local |
| **A medida sobre n8n + LLM** | Costo de infraestructura + horas de desarrollo iniciales | USD 100 – 300 (infra) | TCO más bajo a 3 años, sin dependencia del proveedor, control total | Requiere capacidad técnica interna sostenida |

**Matriz de decisión (plataforma de bot)** — pesos completos según 6.2.

| Alternativa | Pres. AR (15%) | Madurez (15%) | Precios (10%) | Integración (20%) | Cumplimiento (15%) | Escala (10%) | TCO (15%) | Puntuación |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
| Botmaker | 5 | 5 | 4 | 5 | 4 | 4 | 4 | **4,50** |
| Aivo | 5 | 5 | 2 | 4 | 4 | 5 | 2 | **3,90** |
| Voiceflow | 2 | 4 | 3 | 4 | 3 | 4 | 3 | **3,30** |
| A medida n8n | 3 | 3 | 5 | 4 | 4 | 4 | 5 | **3,95** |

Cálculo Botmaker: 5×0,15 + 5×0,15 + 4×0,10 + 5×0,20 + 4×0,15 + 4×0,10 + 4×0,15 = 0,75 + 0,75 + 0,40 + 1,00 + 0,60 + 0,40 + 0,60 = **4,50**.

Ganador: **Botmaker** — único proveedor que combina presencia local, madurez probada e integración WhatsApp BSP nativa.

### A.3 Motor LLM (IA generativa)

Para el cálculo se asume la siguiente combinación por conversación: una clasificación con modelo económico (prompt ~500 tokens, respuesta ~50 tokens) y, cuando la consulta lo amerita, una generación con modelo de alta capacidad sobre contexto RAG (prompt ~3.000 tokens, respuesta ~300 tokens).

| Proveedor / Modelo | Input (USD / 1M tokens) | Output (USD / 1M tokens) | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **OpenAI GPT-4o** | 2,50 | 10,00 | Calidad de referencia, gran ecosistema, SDK maduro | Datos procesados fuera de Argentina |
| **OpenAI GPT-4o-mini** | 0,15 | 0,60 | 16× más barato que GPT-4o, ideal para clasificación e intención | Calidad inferior en generación compleja |
| **Anthropic Claude Sonnet 4.6** | 3,00 | 15,00 | Calidad equivalente a GPT-4o, fuerte en razonamiento técnico, no usa datos API para entrenamiento por defecto | Output 50% más caro que OpenAI |
| **Anthropic Claude Haiku 4.5** | 1,00 | 5,00 | Buena relación calidad/precio para tareas conversacionales | Menos eficiente que GPT-4o-mini para clasificación pura |
| **Azure OpenAI** | Igual a OpenAI + sobrecosto Azure (~10-15%) | Igual base | Cumplimiento empresarial, integración con Microsoft 365 | Más caro, requiere contrato Azure |
| **Google Vertex AI (Gemini)** | Comparable a OpenAI | Comparable | Integración con Google Workspace | Ecosistema menos desarrollado en habla hispana |

**Estimación de costo LLM mensual para 6.000 conversaciones (combinación recomendada 80/20)**:

| Cálculo | Volumen mensual | Costo USD |
|---|---|---|
| GPT-4o-mini input (clasificación, 6.000 conv) | 3.000.000 tokens | 0,45 |
| GPT-4o-mini output (clasificación) | 300.000 tokens | 0,18 |
| GPT-4o-mini input (generación simple, 4.800 conv) | 14.400.000 tokens | 2,16 |
| GPT-4o-mini output (generación simple) | 1.440.000 tokens | 0,86 |
| GPT-4o input (generación compleja RAG, 1.200 conv) | 3.600.000 tokens | 9,00 |
| GPT-4o output (generación compleja RAG) | 360.000 tokens | 3,60 |
| **Subtotal nominal LLM mensual** | | **~USD 16,25** |

El cálculo base da **USD 16/mes**. Para el presupuesto OPEX se adopta un **techo conservador de USD 65/mes** (4×) que absorbe: (a) variación de tokens cuando los manuales RAG son más extensos; (b) crecimiento estacional de volumen durante la cosecha; (c) eventual aumento de precios de OpenAI.

**Matriz de decisión (motor LLM)** — pesos completos según 6.2.

| Alternativa | Pres. AR (15%) | Madurez (15%) | Precios (10%) | Integración (20%) | Cumplimiento (15%) | Escala (10%) | TCO (15%) | Puntuación |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
| OpenAI GPT-4o + 4o-mini (combinación) | 2 | 5 | 5 | 5 | 4 | 5 | 5 | **4,40** |
| Anthropic Claude Sonnet 4.6 + Haiku | 2 | 5 | 3 | 4 | 5 | 5 | 3 | **3,85** |
| Azure OpenAI | 2 | 5 | 3 | 5 | 5 | 5 | 3 | **4,05** |
| Google Vertex AI (Gemini) | 3 | 4 | 4 | 4 | 4 | 5 | 4 | **3,95** |
| AWS Bedrock multi-LLM | 2 | 4 | 4 | 4 | 4 | 5 | 4 | **3,80** |
| Local open-source (Llama 3 con alojamiento propio) | 3 | 3 | 5 | 3 | 5 | 3 | 4 | **3,65** |

Cálculo OpenAI: 2×0,15 + 5×0,15 + 5×0,10 + 5×0,20 + 4×0,15 + 5×0,10 + 5×0,15 = 0,30 + 0,75 + 0,50 + 1,00 + 0,60 + 0,50 + 0,75 = **4,40**.

Ganador: **OpenAI GPT-4o + 4o-mini con combinación 80/20** — mejor relación calidad/precio del mercado y SDK más maduro.

### A.4 Base vectorial para RAG

Dimensionamiento estimado de la base de conocimiento de Plantium: aproximadamente 500 páginas de manuales de producto, 100 páginas de FAQs y 2.000 tickets históricos, lo que se traduce en unos 13.000 vectores en fragmentos de 500 tokens.

| Proveedor | Modelo de precios | Costo mensual estimado | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **Pinecone Serverless** | Capa gratuita hasta 100k vectores; plan Builder USD 20/mes flat para producción inicial | USD 0 – 20 | Cubre el dimensionamiento inicial sin costo, gestionado, SLA en plan pago | Dependencia del proveedor moderada, datos en USA |
| **Qdrant Cloud** | Capa gratuita (0,5 vCPU, 1GB RAM); planes desde USD 30/mes | USD 0 – 30 | Alternativa LATAM-friendly, open source, residencia configurable | Comunidad más chica |
| **Weaviate Cloud (Flex)** | Desde USD 45/mes | USD 45 | Búsqueda híbrida nativa | Más caro que Qdrant a iguales features |
| **pgvector (PostgreSQL)** | Costo del Postgres ya existente | USD 0 incremental | Integración con stack relacional existente | Performance inferior a vector DBs especializadas en >100k vectores |

**Embeddings — comparativa breve y selección**

| Modelo | Costo (USD / 1M tokens) | Calidad en español | Comentario |
|---|---|---|---|
| **OpenAI text-embedding-3-small** | 0,02 | Alta (multilingüe) | Mejor relación calidad/precio; integración natural con stack OpenAI |
| **OpenAI text-embedding-3-large** | 0,13 | Muy alta | 6,5× más caro; justifica solo si la calidad small es insuficiente |
| **Cohere embed-multilingual-v3** | 0,10 | Alta | Buena alternativa multiproveedor |
| **sentence-transformers multilingual-e5** | 0 (alojamiento propio) | Alta | Open source; ahorra licencia pero requiere VPS y mantenimiento |

Se recomienda **OpenAI text-embedding-3-small** por costo, calidad en español y consistencia con el resto del stack OpenAI.

**Matriz de decisión (Vector DB)** — pesos completos según 6.2.

| Alternativa | Pres. AR (15%) | Madurez (15%) | Precios (10%) | Integración (20%) | Cumplimiento (15%) | Escala (10%) | TCO (15%) | Puntuación |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
| Pinecone Serverless | 2 | 5 | 5 | 5 | 3 | 5 | 4 | **4,10** |
| Qdrant Cloud | 3 | 4 | 4 | 4 | 4 | 4 | 4 | **3,85** |
| Weaviate Cloud | 2 | 4 | 3 | 4 | 4 | 4 | 3 | **3,45** |
| pgvector (PostgreSQL) | 4 | 4 | 5 | 4 | 5 | 3 | 5 | **4,30** |

Cálculo Pinecone: 2×0,15 + 5×0,15 + 5×0,10 + 5×0,20 + 3×0,15 + 5×0,10 + 4×0,15 = 0,30 + 0,75 + 0,50 + 1,00 + 0,45 + 0,50 + 0,60 = **4,10**.
Cálculo pgvector: 4×0,15 + 4×0,15 + 5×0,10 + 4×0,20 + 5×0,15 + 3×0,10 + 5×0,15 = 0,60 + 0,60 + 0,50 + 0,80 + 0,75 + 0,30 + 0,75 = **4,30**.

Aunque pgvector obtiene mayor puntuación por TCO y cumplimiento, se elige **Pinecone Serverless** por su capa gratuita inicial sin costo, escalabilidad superior bajo demanda y eliminación de la operación de infraestructura, factores críticos para una PyME en fase piloto. pgvector queda como plan B documentado para Fase 3 si los volúmenes crecen y se quiere consolidar el stack sobre Postgres.

### A.5 Plataforma de automatización (iPaaS)

| Proveedor | Modelo de precios | Costo mensual estimado | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **Make.com** | Desde USD 9/mes (10k operaciones); plan Business USD 50/mes (40k operaciones) | USD 50 | Mejor relación precio/poder, 60-70% más barato que Zapier | Curva de aprendizaje para flujos complejos |
| **Zapier** | USD 20-100/mes para tiers de negocio | USD 70 | Ecosistema de 7.000+ apps | Costoso por operación; solo justifica si se necesitan integraciones poco comunes |
| **n8n con alojamiento propio** | USD 5-20/mes de VPS, ejecuciones ilimitadas | USD 20 | Mejor TCO, open source, sin dependencia del proveedor | Requiere operar infraestructura |
| **n8n Cloud** | USD 22-54/mes (plan inicial, EUR 20-50 al cambio 1,08 USD/EUR) | USD 25 | Misma flexibilidad sin operar infra | Cuenta por ejecución, no por nodo |

**Matriz de decisión (iPaaS)** — pesos completos según 6.2.

| Alternativa | Pres. AR (15%) | Madurez (15%) | Precios (10%) | Integración (20%) | Cumplimiento (15%) | Escala (10%) | TCO (15%) | Puntuación |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
| Make.com | 3 | 4 | 5 | 5 | 4 | 4 | 4 | **4,15** |
| Zapier | 3 | 5 | 3 | 5 | 4 | 4 | 3 | **3,95** |
| n8n con alojamiento propio | 3 | 4 | 5 | 4 | 4 | 4 | 5 | **4,10** |
| n8n Cloud | 3 | 4 | 4 | 4 | 4 | 4 | 4 | **3,85** |

Cálculo Make.com: 3×0,15 + 4×0,15 + 5×0,10 + 5×0,20 + 4×0,15 + 4×0,10 + 4×0,15 = 0,45 + 0,60 + 0,50 + 1,00 + 0,60 + 0,40 + 0,60 = **4,15**.
Cálculo n8n con alojamiento propio: 3×0,15 + 4×0,15 + 5×0,10 + 4×0,20 + 4×0,15 + 4×0,10 + 5×0,15 = 0,45 + 0,60 + 0,50 + 0,80 + 0,60 + 0,40 + 0,75 = **4,10**.

Empate técnico entre Make.com y n8n con alojamiento propio. Se elige **Make.com (plan Business)** por menor carga operativa (no requiere mantener VPS), velocidad de implementación en fase piloto y mejor experiencia visual para flujos simples. n8n con alojamiento propio queda como plan B para Fase 3 cuando el volumen de operaciones supere el cap del plan Business y/o se quiera reducir TCO.

### A.6 Hosting de infraestructura backend

Necesario para alojar conectores a medida, el copiloto interno y, opcionalmente, n8n y el vector DB con alojamiento propio.

| Proveedor | Modelo de precios | Costo mensual estimado | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **AWS** | Pay-per-use, EC2 t3.medium ~USD 30/mes | USD 80 – 150 | Líder del mercado, máxima cobertura de servicios | Curva de aprendizaje, costos pueden escalar |
| **Microsoft Azure** | Comparable a AWS | USD 80 – 150 | Buena integración con Microsoft 365 / Power BI | Mismo orden de complejidad |
| **DigitalOcean** | Droplets desde USD 6/mes; Managed Services desde USD 15/mes | USD 40 – 80 | Precios predecibles, ideal para PyME | Menos servicios gestionados |
| **Hetzner Cloud** | Servidores cloud desde USD 5,40/mes (EUR 5 al cambio 1,08 USD/EUR) | USD 25 – 60 | El más barato de la lista, excelente performance/USD | Sin presencia en LATAM (data centers en Europa) |

**Matriz de decisión (Hosting)** — pesos completos según 6.2.

| Alternativa | Pres. AR (15%) | Madurez (15%) | Precios (10%) | Integración (20%) | Cumplimiento (15%) | Escala (10%) | TCO (15%) | Puntuación |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
| AWS | 3 | 5 | 3 | 5 | 5 | 5 | 3 | **4,20** |
| Microsoft Azure | 3 | 5 | 3 | 5 | 5 | 5 | 3 | **4,20** |
| DigitalOcean | 3 | 4 | 4 | 4 | 4 | 4 | 4 | **3,85** |
| Hetzner Cloud | 2 | 4 | 5 | 3 | 4 | 4 | 5 | **3,75** |

Cálculo AWS: 3×0,15 + 5×0,15 + 3×0,10 + 5×0,20 + 5×0,15 + 5×0,10 + 3×0,15 = 0,45 + 0,75 + 0,30 + 1,00 + 0,75 + 0,50 + 0,45 = **4,20**.
Cálculo DigitalOcean: 3×0,15 + 4×0,15 + 4×0,10 + 4×0,20 + 4×0,15 + 4×0,10 + 4×0,15 = 0,45 + 0,60 + 0,40 + 0,80 + 0,60 + 0,40 + 0,60 = **3,85**.

A pesar de que AWS y Azure obtienen una puntuación superior, se elige **DigitalOcean** por **precios predecibles** (factor crítico para una PyME), curva de aprendizaje más corta y menor riesgo de sorpresas en la facturación. AWS y Azure se reservan como opciones para Fase 3 si la integración profunda con Microsoft 365 (Azure) o servicios avanzados (AWS) lo justifica.

### A.7 Copiloto interno (asistente de agentes)

El copiloto interno asiste al agente humano sugiriendo respuestas y resúmenes de caso en tiempo real, apalancando el mismo motor LLM y la base RAG del bot externo.

| Alternativa | Modelo de precios | Costo mensual estimado | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **OpenAI Assistants API + integración CRM** | Pago por uso (mismos precios GPT-4o-mini/4o) | USD 90 incremental | Aprovecha inversión OpenAI; control total de la integración; sin licencia por usuario | Requiere desarrollo a medida (180 hs estimadas) |
| **Microsoft Copilot Studio** | USD 200 / mes / 25.000 mensajes + licencia M365 | USD 200 – 400 | Integración nativa M365 si Plantium ya lo usa; UI baja de barrera | Dependencia del proveedor Microsoft; costos por mensaje suben rápido |
| **A medida con LangChain/LlamaIndex + LLM elegido** | Costo LLM + horas dev | USD 80 (uso) | Máximo control y portabilidad multi-LLM | Mayor esfuerzo de mantenimiento (~12-18 hs/mes) |
| **Botmaker AI Agent Studio** | Incluido en plan Botmaker empresarial | USD 0 incremental | Sin instrumental adicional; ya incluido en la plataforma | Funcionalidad más limitada para resúmenes y análisis profundo |

**Matriz de decisión (copiloto interno)** — pesos completos según 6.2.

| Alternativa | Pres. AR (15%) | Madurez (15%) | Precios (10%) | Integración (20%) | Cumplimiento (15%) | Escala (10%) | TCO (15%) | Puntuación |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
| OpenAI Assistants API + CRM | 3 | 5 | 5 | 5 | 4 | 5 | 4 | **4,40** |
| Microsoft Copilot Studio | 3 | 5 | 3 | 4 | 5 | 4 | 3 | **3,90** |
| A medida LangChain + LLM | 3 | 4 | 4 | 5 | 4 | 5 | 4 | **4,15** |
| Botmaker AI Agent Studio | 5 | 4 | 5 | 4 | 4 | 3 | 4 | **4,15** |

Cálculo OpenAI Assistants: 3×0,15 + 5×0,15 + 5×0,10 + 5×0,20 + 4×0,15 + 5×0,10 + 4×0,15 = 0,45 + 0,75 + 0,50 + 1,00 + 0,60 + 0,50 + 0,60 = **4,40**.

Ganador: **OpenAI Assistants API integrado al CRM** — máxima flexibilidad y aprovechamiento de la inversión LLM ya realizada.

### A.8 Capa de analítica

| Proveedor | Modelo de precios | Costo mensual estimado (5 supervisores) | Pros para Plantium | Contras / riesgos |
|---|---|---|---|---|
| **Power BI Pro** | USD 14 / usuario / mes | USD 70 | Si Plantium ya usa Microsoft 365, se suma sin fricción. Microsoft factura localmente con IVA, reduciendo el impacto cambiario | Requiere licencia base Microsoft |
| **Looker Studio (Google)** | Gratis | USD 0 | Sin costo de licencia, integración nativa con Google Workspace | Funciones avanzadas limitadas |
| **Tableau Creator** | USD 75 / usuario / mes | USD 375 | Líder en visualización avanzada | Sobreescala para el caso de uso |
| **Tablero nativo del CRM** | Incluido | USD 0 incremental | Sin costo adicional | Suele ser limitado en flexibilidad |

**Matriz de decisión (analítica)** — pesos completos según 6.2.

| Alternativa | Pres. AR (15%) | Madurez (15%) | Precios (10%) | Integración (20%) | Cumplimiento (15%) | Escala (10%) | TCO (15%) | Puntuación |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|---:|
| Power BI Pro | 4 | 5 | 4 | 5 | 5 | 5 | 4 | **4,60** |
| Looker Studio | 3 | 4 | 5 | 4 | 4 | 3 | 5 | **4,00** |
| Tableau Creator | 3 | 5 | 2 | 4 | 5 | 4 | 2 | **3,65** |
| Tablero nativo CRM | 3 | 3 | 5 | 5 | 4 | 3 | 5 | **4,05** |

Cálculo Power BI: 4×0,15 + 5×0,15 + 4×0,10 + 5×0,20 + 5×0,15 + 5×0,10 + 4×0,15 = 0,60 + 0,75 + 0,40 + 1,00 + 0,75 + 0,50 + 0,60 = **4,60**.

Ganador: **Power BI Pro** — máxima integración con stack Microsoft 365 (asumido presente en Plantium), facturación local con IVA y madurez probada.

### A.9 TCO comparativo a 3 años — Componentes más caros

Para los tres componentes con mayor peso económico, se compara el costo total a 3 años entre la opción recomendada y la mejor alternativa:

| Componente | Opción recomendada | TCO 3 años (USD) | Mejor alternativa | TCO 3 años (USD) | Diferencial |
|---|---|---:|---|---:|---:|
| Plataforma de bot | Botmaker (USD 600/mes + incorporación 1.500) | 23.100 | A medida n8n (USD 100/mes + dev 8.000) | 11.600 | +11.500 (Botmaker) |
| Hosting backend | DigitalOcean (USD 80/mes + configuración inicial 2.000) | 4.880 | Hetzner (USD 40/mes + configuración inicial 2.500) | 3.940 | +940 (DigitalOcean) |
| iPaaS | Make.com Business (USD 50/mes) | 1.800 | n8n con alojamiento propio (USD 20/mes + configuración inicial 800) | 1.520 | +280 (Make.com) |

El diferencial de USD 11.500 en favor de Botmaker se justifica por **menor riesgo técnico, soporte local en español, facturación AR y velocidad de implementación**. La opción n8n a medida queda preregistrada como **plan B para Fase 3** si los volúmenes crecen y el ahorro acumulado lo amortiza.

---

## Anexo 6.B — Análisis de costo argentino

### 6.B.1 Carga fiscal y costo financiero

Las cifras de OPEX presentadas en 6.5.2 corresponden al **costo nominal en USD** que cobra cada proveedor. El costo **efectivo en pesos** para Plantium difiere significativamente por la carga fiscal y el costo financiero argentino vigente en mayo de 2026:

| Concepto | Tasa aplicable | Aplica a |
|---|---|---|
| **IVA** | 21% | Servicios facturados localmente (Botmaker AR, Microsoft Power BI). También se aplica en servicios digitales del exterior bajo el régimen de percepción AFIP. |
| **Percepción a cuenta de Ganancias** | 30% | Pagos al exterior con tarjeta corporativa por servicios digitales (recuperable como pago a cuenta en la DDJJ anual). |
| **Diferencial cambiario** | 5% – 15% | Diferencia entre dólar oficial y MEP/CCL según mecanismo de pago utilizado. |
| **Costo financiero tarjeta corporativa** | 4% – 5% adicional | Si se paga con tarjeta corporativa con financiación en lugar de débito directo. |

> **Nota actualizada**: el **Impuesto PAIS** quedó sin efecto a partir del 23 de diciembre de 2024 y fue formalmente eliminado del marco regulatorio en enero de 2026, por lo que **no aplica** a este análisis. La carga vigente se concentra en IVA + percepción de Ganancias + diferencial cambiario.

**Coeficiente de conversión a costo efectivo**: combinando IVA (21%) + percepción Ganancias (30%, recuperable a 12-18 meses) + diferencial cambiario (10% promedio) + costo financiero (4%), el OPEX de proveedores extranjeros se multiplica por aproximadamente **1,5×** para llegar al desembolso efectivo en pesos al tipo oficial.

**Desglose corregido de proveedores extranjeros vs locales**:

**Proveedores extranjeros (pagos al exterior, sujetos al coeficiente 1,5×)**:

| Concepto | USD anual |
|---|---:|
| WhatsApp / Twilio (BSP US) | 4.320 |
| LLM OpenAI | 780 |
| Pinecone | 240 |
| Make.com | 600 |
| DigitalOcean | 960 |
| Power BI (Microsoft factura local con IVA, precios en USD) | 840 |
| Copiloto OpenAI Assistants | 1.080 |
| Observabilidad (Grafana Cloud) | 396 |
| **Subtotal extranjeros** | **9.216** |

**Proveedores locales AR (facturan en pesos con IVA 21%, sin percepción ni diferencial adicional)**:

| Concepto | USD anual |
|---|---:|
| Botmaker (empresa argentina) | 7.200 |
| Mantenimiento (consultor externo local) | 10.080 |
| Capacitación (cursos + horas internas) | 1.200 |
| **Subtotal locales** | **18.480** |

**OPEX efectivo con carga fiscal AR**:

| Componente OPEX | Valor nominal USD/año | Coeficiente | Valor efectivo USD/año |
|---|---:|---:|---:|
| Proveedores extranjeros | 9.216 | 1,5× | 13.824 |
| Proveedores locales | 18.480 | 1,0× (ya con IVA) | 18.480 |
| **OPEX efectivo total** | **27.696** | | **~32.304** |

**Impacto en métricas de retorno cuando se usa OPEX efectivo AR**:

| Métrica | Valor con OPEX nominal | Valor con OPEX efectivo AR |
|---|---:|---:|
| OPEX anual | 27.696 | 32.304 |
| Inversión total año 1 | 77.696 | 82.304 |
| Beneficio neto operativo año 1 | 41.104 | **36.496** |
| ROI sobre CAPEX | 137,6% | 137,6% (CAPEX local, sin carga FX significativa) |
| ROI sobre inversión total año 1 | 52,9% | **44,3%** |
| Payback bruto (CAPEX / ahorro mensual) | 5,05 meses | 5,05 meses |
| Payback neto (CAPEX / (ahorro mensual − OPEX mensual efectivo)) | 6,59 meses | **6,94 meses** |

Cálculo payback neto con carga AR: OPEX mensual efectivo = 32.304 / 12 = USD 2.692/mes; ahorro mensual neto = 9.900 − 2.692 = USD 7.208; payback = 50.000 / 7.208 = **6,94 meses**.

**TCO 3 años con carga fiscal AR**:

| Año | CAPEX | OPEX efectivo AR | Total año | Acumulado |
|---|---:|---:|---:|---:|
| 1 | 50.000 | 32.304 | 82.304 | 82.304 |
| 2 | — | 28.224 | 28.224 | 110.528 |
| 3 | — | 28.224 | 28.224 | 138.752 |

(OPEX año 2-3: extranjeros 9.216 × 1,5 = 13.824 + locales reducidos 14.400 = 28.224, considerando reducción de mantenimiento de 10.080 a 6.000).

El **ROI sobre CAPEX (137,6%) se mantiene intacto** porque el CAPEX está dominado por horas de desarrollo locales sin carga fiscal cambiaria significativa. Las métricas operativas (ROI sobre inversión total y payback neto) se degradan moderadamente pero **siguen demostrando viabilidad financiera robusta** del proyecto bajo escenarios fiscales realistas.

Estas cifras son orientativas y deben validarse con el área de Finanzas de Plantium en función del esquema de pago efectivamente adoptado (tarjeta vs transferencia, recupero de percepciones, cobertura cambiaria, etc.).

### 6.B.2 Análisis de sensibilidad de OPEX por volumen

Los costos varían con el volumen real de conversaciones. La regla de incremento por conversación adicional sobre la base es:

| Componente | Incremento por conversación adicional |
|---|---|
| WhatsApp (BSP + Meta por mensaje) | ~USD 0,06/conv |
| LLM (combinación 80/20) | ~USD 0,003/conv (USD 16/mes base / 6.000 conv) |
| Copiloto OpenAI Assistants | ~USD 0,015/conv (USD 90/mes base / 6.000) |
| Embeddings re-indexación | despreciable |
| Otros costos fijos (Botmaker, observabilidad, mantenimiento, hosting, Power BI, iPaaS, vector DB) | No cambian (plan empresa absorbe hasta 20k conv) |

Incremento total: **~USD 0,078 por conversación adicional**.

**Escenario base: 6.000 conv/mes**
- OPEX mensual: **USD 2.308**
- Ahorro mensual: USD 9.900
- Payback bruto: 50.000 / 9.900 = **5,05 meses**
- Payback neto: 50.000 / (9.900 − 2.308) = **6,59 meses**

**Escenario crecimiento sostenido: 10.000 conv/mes** (+4.000 sobre base)
- Incrementos: WhatsApp +240 + LLM +12 + Copiloto +60 = **+USD 312/mes**
- OPEX mensual: 2.308 + 312 = **USD 2.620**
- Ahorro mensual escala proporcional: (10.000 / 6.000) × 9.900 = **USD 16.500**
- Payback bruto: 50.000 / 16.500 = **3,03 meses**
- Payback neto: 50.000 / (16.500 − 2.620) = **3,60 meses**

**Escenario pico estacional cosecha: 15.000 conv/mes durante ~3 meses al año** (+9.000 sobre base solo en pico)

**IMPORTANTE**: este escenario NO se anualiza como si fuera constante todo el año. El pico estacional dura aproximadamente 3 meses (cosecha gruesa); los 9 meses restantes operan en escenario base. La métrica relevante es la **combinación anual**:

- **Durante 3 meses de pico**:
  - Incrementos OPEX vs base: 9.000 conv × USD 0,078 = +USD 702/mes → OPEX pico ≈ **USD 3.010/mes**
  - Ahorro pico (proporcional al volumen): (15.000 / 6.000) × 9.900 = **USD 24.750/mes**
- **Durante 9 meses base**:
  - OPEX base: **USD 2.308/mes**
  - Ahorro base: **USD 9.900/mes**

| Métrica anual mixta | Cálculo | Valor |
|---|---|---:|
| OPEX anual mixto | (3.010 × 3) + (2.308 × 9) | **USD 29.802** |
| Ahorro anual mixto | (24.750 × 3) + (9.900 × 9) | **USD 163.350** |
| Beneficio neto año pico | 163.350 − 50.000 − 29.802 | **USD 83.548** |
| ROI sobre CAPEX año pico | (163.350 − 50.000) / 50.000 | **226,7%** |
| ROI sobre inversión total año pico | (163.350 − 79.802) / 79.802 | **104,7%** |

**Conclusión clave**: el pico estacional de cosecha aumenta el OPEX en aproximadamente **+7,6% anual** pero aumenta el ahorro en **+37,5% anual**, por lo que **el ROI y el payback MEJORAN sustancialmente en años con buena cosecha**. El modelo económico es robusto frente a la estacionalidad porque el crecimiento del costo es sublineal respecto del crecimiento del ahorro.

**Síntesis de los tres escenarios**:

| Escenario | Conv/mes | OPEX anual USD | Ahorro anual USD | ROI s/ CAPEX | Payback neto |
|---|---:|---:|---:|---:|---:|
| **Base** (constante) | 6.000 | 27.696 | 118.800 | 137,6% | 6,59 meses |
| **Crecimiento sostenido** (constante) | 10.000 | 31.440 | 198.000 | 296,0% | 3,60 meses |
| **Combinación anual con pico de cosecha** | 6.000 base + 15.000 pico (3 meses) | 29.802 | 163.350 | 226,7% | n/a (mixto) |

El crecimiento del OPEX es **sublineal** respecto del volumen porque varios componentes son flat (Botmaker plan empresa, Pinecone Builder, Power BI, hosting); solo escalan WhatsApp, LLM y copiloto. Esto refuerza la robustez económica del modelo: si el volumen crece, el payback se acorta.

---

## Anexo 6.C — Cumplimiento Ley 25.326 por proveedor

La Ley 25.326 de Protección de Datos Personales de Argentina exige garantías sobre tratamiento, residencia, finalidad y retención de datos personales. La siguiente tabla sintetiza la postura de los proveedores seleccionados:

| Proveedor | Residencia de datos | DPA disponible | Exclusión de entrenamiento | Retención configurable |
|---|---|---|---|---|
| **OpenAI** | USA (multi-región opcional empresarial) | Validar disponibilidad de DPA contractual empresarial antes de firma | Sí, disponible vía API (no usa datos API para entrenamiento por defecto) | Retención 30 días por defecto; configurable a 0 días en plan empresarial |
| **Anthropic** | USA | Validar disponibilidad de DPA contractual | No usa datos API para entrenamiento por defecto | Retención configurable; logs para monitoreo de abuso 30 días |
| **Pinecone** | USA o EU (selección al crear índice) | Validar disponibilidad de DPA contractual | N/A (no usa datos cliente para entrenamiento) | Datos persisten hasta que el cliente los elimina |
| **Botmaker** | Argentina (data centers locales declarados) | Validar disponibilidad de DPA local en español | N/A | Configurable por cliente |
| **Make.com** | EU (GDPR compliant) | Validar disponibilidad de DPA GDPR | N/A | Logs de ejecución 7-30 días según plan |
| **DigitalOcean** | Configurable (USA, EU, Asia) | Validar disponibilidad de DPA contractual | N/A | Cliente controla retención |
| **Microsoft (Power BI)** | Configurable por región Azure | Validar disponibilidad de DPA empresarial | N/A | Cliente controla retención |

> **Nota sobre DPA**: la columna "DPA disponible" se reformuló como "validar disponibilidad" porque la firma de DPA depende del plan contratado (free vs paid vs empresarial) y de la jurisdicción del cliente. Antes del paso a producción debe confirmarse con cada proveedor la disponibilidad efectiva del DPA y, en lo posible, obtener una versión en español para revisión legal.

Independientemente del proveedor, la implementación debe contemplar: **anonimización en cliente antes de enviar datos al LLM** (eliminación o tokenización de DNI, teléfono, email del cuerpo del prompt cuando no son necesarios), **retención corta de logs operativos** (30-60 días salvo requerimiento legal), **firma de DPA con cada proveedor antes del paso a producción** y **registro de tratamiento de datos** ante la Dirección Nacional de Protección de Datos Personales si la base supera el umbral aplicable a Plantium.
