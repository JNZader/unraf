# 09. Automatización Integral

> **Módulo 6 — Unidad 2 (DIATO, UNRaf Cohorte 5)**
> Docentes: Ing. Ives Minetti (Director TI en Limansky SA) + Ana Lucía Tolini (Lic. RRTT, Analista de Compensaciones e Innovación en Bertolaccini).

> **Nota terminológica:** la cátedra usa **"Automatización Integral"**, **"IA-Driven"** y **"Automatización Agéntica"**. NO usa los términos mainstream "IPA / Hyperautomation / attended / unattended". Cuando este capítulo cite la jerga industrial es a título informativo, pero el vocabulario operativo de DIATO es el de la cátedra.

---

## 1. Concepto

**Automatización Integral**, según la definición cátedra (Part 2, p. 6):

> *"Es el proceso de implementar tecnologías avanzadas para automatizar completamente los flujos de trabajo, operaciones y procesos de negocio, integrando diversos sistemas y tecnologías para lograr una gestión más eficiente y efectiva de los recursos empresariales."*

Lo que la distingue de la **Automatización Tradicional** (Part 2, p. 7):

| Tradicional | Integral |
|-------------|----------|
| Optimiza tareas o actividades **específicas** | Digitaliza y automatiza el **proceso completo**, de inicio a fin |
| Vive dentro de un sistema | **Conecta** sistemas, departamentos y funciones |
| Basada en reglas rígidas | Incorpora IA cuando la regla no alcanza |

Y la frase clave que define el horizonte cátedra:

> *"En la actualidad refiere la implementación de Agentes de IA (Automatización Agéntica). Es la evolución de RPA tradicional + IA (automatización inteligente)."* (Part 2, p. 7)

Esa frase contiene la **progresión cátedra** que vas a usar como columna vertebral de este capítulo:

```
RPA tradicional  →  + IA (Automatización Inteligente)  →  Agentes de IA (Automatización Agéntica)
```

---

## 2. Intuición

Pensá la automatización como **darle palancas a la organización**. La pregunta no es "¿qué tarea elimino?", es **"¿qué cosas pasaban con intervención humana y ahora pasan solas, de punta a punta, sin que nadie copie y pegue entre sistemas?"**.

Una metáfora útil: el ascensor.

- **Sin automatización**: alguien sube y baja la escalera con cada paquete.
- **Automatización tradicional**: ascensor con botones. Vos elegís el piso, el ascensor se mueve. Si el botón se rompe, no se mueve. Si pedís un piso que no existe, no entiende, se queda parado.
- **Automatización integral con IA**: el ascensor predice patrones de uso (a las 9 am la gente va al piso 5, a las 13 al subsuelo del comedor), agrupa pedidos para optimizar viajes, y "entiende" cuando alguien con muletas se acerca para esperar más tiempo.

La cátedra plantea una pregunta reflexiva (Part 2, p. 23) que te conviene tener tatuada:

> *"Piensen en ese proceso que hoy tienen automatizado pero que, cada vez que algo mínimo cambia, se 'rompe' y requiere que una persona intervenga manualmente... ¿Ese proceso es realmente automático o es solo una regla rígida que hoy les está costando tiempo de supervisión?"*

Eso es **la frontera entre automatización tradicional e IA-Driven**: si el sistema se rompe con un cambio mínimo de formato, no es realmente automático.

---

## 3. Cuerpo desarrollado

### 3.1. Pilares y objetivos cátedra

**Tres pilares de la Automatización Integral** (Part 2, p. 6):

1. Eliminar tareas manuales repetitivas.
2. Reducir errores humanos.
3. Permitir ejecución continua sin interrupciones (24/7).

**Cinco objetivos cátedra** (Part 2, p. 8):

1. Eliminación de tareas manuales repetitivas.
2. Mejora de eficiencia operativa.
3. Optimización de toma de decisiones con datos en tiempo real.
4. Interconexión de sistemas y áreas.
5. Escalabilidad **sin aumento proporcional de carga manual**.

El quinto punto es el más estratégico: si tu operación escala pero tu nómina escala igual de rápido, no estás automatizando, estás creciendo. La automatización integral bien hecha **desacopla volumen de negocio de costo operativo lineal**.

### 3.2. Principios cátedra para automatizar bien

(Part 2, p. 9)

- **Alineación con objetivos estratégicos** (crecimiento, eficiencia, experiencia del cliente, rentabilidad).
- **Priorización basada en impacto del negocio** (KPIs).
- **Enfoque en creación de ventaja competitiva.**
- **Gobierno y arquitectura coherente** (negocio + IT).

Y cuatro claves operativas que conviene memorizar:

1. *"No automatizar ineficiencias."*
2. *"Primero rediseñar, luego automatizar."*
3. *"La tecnología habilita, la organización transforma."*
4. *"La automatización impacta roles, competencias y estructura."*

Las cuatro funcionan como un **antídoto contra el anti-patrón 3 del capítulo 08** ("Automatización de Procesos Ineficientes"). Antes de automatizar un proceso, preguntate: *¿este proceso debería existir tal como está, o lo que necesito es rediseñarlo?*

### 3.3. Priorización de procesos a automatizar

(Part 2, p. 10) — orden de prioridad cátedra:

1. **Impacto estratégico** — ¿este proceso afecta directamente a un KPI de directorio?
2. **Impacto en experiencia del cliente** — ¿el cliente final percibe la mejora?
3. **Eficiencia operativa** — ¿libera capacidad para tareas de mayor valor?

Y considerar especialmente procesos que:
- Generan ventaja competitiva.
- Liberan capacidad para tareas de mayor valor.
- Reducen fricción organizacional.

### 3.4. La progresión cátedra: Tradicional → Inteligente → Agéntica

#### Nivel 1 — Automatización Tradicional (basada en reglas)

| Dimensión | Característica |
|-----------|---------------|
| ADN | *"Si ocurre X, entonces hacé Y"* |
| Naturaleza | Rígida, determinista |
| Fortaleza | Alta eficiencia en tareas repetitivas y predecibles |
| Limitación | *"Se rompe ante la ambigüedad o cambios en el formato de los datos"* |
| Ejemplos | Macros de Excel, scripts batch, Zaps simples, reglas de Outlook |

#### Nivel 2 — Automatización IA-Driven (Inteligente)

| Dimensión | Característica |
|-----------|---------------|
| ADN | *"Aprende de los datos y decide el mejor camino"* |
| Naturaleza | Adaptativa, probabilística |
| Fortaleza | NLP, visión por computadora, detección de anomalías, OCR con tolerancia |
| Valor agregado | *"No solo ejecuta, sino que aprende de las excepciones para mejorar el próximo ciclo"* |
| Ejemplos | Lectura de facturas con OCR + LLM, clasificación de tickets por sentimiento, mantenimiento predictivo |

#### Nivel 3 — Automatización Agéntica (Agentes de IA)

El horizonte actual según la cátedra. Un **agente de IA** no es solo "un modelo que responde", es un sistema que:

- **Percibe** el entorno (lee inputs, consulta APIs, observa estado).
- **Razona** sobre objetivos (planifica pasos, decide herramientas a usar).
- **Actúa** ejecutando herramientas (envía emails, modifica registros en CRM, escala a humanos).
- **Aprende** de los resultados para próximas ejecuciones.

Diferencia clave con Nivel 2: un agente **decide qué hacer**, no solo ejecuta una predicción. Por ejemplo, un agente de cuentas a pagar no solo "lee la factura": decide si conciliarla, si pedir aclaración al proveedor, si escalarla al gerente o si marcarla como sospechosa de fraude, **encadenando varias acciones**.

> **Lectura honesta**: el módulo nombra Automatización Agéntica como horizonte y referencia conceptual, pero **no enseña construcción de agentes**. Eso queda como tema para módulos posteriores o profundización autónoma.

### 3.5. Plataformas digitales de automatización (iPaaS)

**Definición cátedra** (Part 2, p. 14):

> *"Tienen como objetivo la automatización de flujos de trabajo conectando aplicaciones y automatizando tareas repetitivas, con un entorno amigable y sin necesidad de programar desde cero."*

**Cuatro funciones principales** (Part 2, p. 14):

1. **Integración de aplicaciones** — nodos predefinidos para CRM, email, BBDD, redes sociales.
2. **Automatización basada en triggers / disparadores** — ej: recibir un correo, un nuevo registro en una tabla, un webhook entrante.
3. **Manipulación de datos y lógica** — If/Else, Loops, transformaciones.
4. **Gestión de IA** — integración directa para agentes autónomos o entrenamiento de modelos.

#### Plataformas (Part 2, p. 15)

**n8n** *(énfasis cátedra)* — *"Herramienta 'fair-code' enfocada en auto-alojamiento (self-hosted), ideal para desarrolladores que buscan control total, flexibilidad y menores costos a gran escala."*

Características:
- **Self-hosting** real (Docker, Kubernetes). Tus datos no salen de tu infraestructura si no querés.
- **Modelo fair-code** (Sustainable Use License) — uso libre interno, restricciones para revender como SaaS.
- **+1300 nodos** de integración (HTTP, bases de datos, LLMs, CRMs).
- **Editor visual** con código JavaScript embebido cuando el visual no alcanza.
- Soporte de primera para **agentes de IA y LLMs** (nodos nativos para OpenAI, Anthropic, LangChain, vector stores).
- Comunidad activa que aporta nodos custom.

Por qué la cátedra le da énfasis: **n8n es la plataforma iPaaS más alineada con el perfil DIATO** (PYME / mediana, datos sensibles que no querés mandar a SaaS de terceros, costos predecibles que no escalan por ejecución).

**Zapier** — *"La herramienta más popular para conectar aplicaciones web cotidianas y crear flujos de trabajo sencillos conocidos como 'Zaps'."*

- **+7000 apps integradas** (la biblioteca más grande del mercado).
- **Pricing por tarea ejecutada** (escala costosamente a alto volumen).
- **Cero código** real — pensado para personas de negocio, no devs.
- 100% SaaS — sin opción on-premise. Tus datos pasan por servidores de Zapier.

**Make** (ex-Integromat) — *"Interfaz visual más avanzada y flexible para diseñar flujos complejos."*

- Editor visual muy potente con **routers, iteradores, agregadores**.
- Pricing por **operaciones** (no por Zap), suele ser más económico que Zapier a volumen.
- SaaS también, sin self-hosting.
- Sweet spot entre Zapier (simple) y n8n (técnico).

**Microsoft Power Automate** — *"Para ecosistema Microsoft."*

- Integración nativa con M365, Dynamics, SharePoint, Teams.
- Dos modos: **Cloud flows** (iPaaS clásico) y **Desktop flows** (RPA real sobre UI).
- Incluye **AI Builder** para OCR, clasificación, análisis de sentimiento embebidos.
- Excelente si la organización ya vive en M365. Si no, no tiene sentido.

**Google Workspace Studio + Apps Script** — *"Para ecosistema Google."*

- **AppSheet** para apps no-code sobre Google Sheets.
- **Apps Script** para código JS/TS sobre Workspace (Gmail, Drive, Sheets, Docs, Calendar).
- **Workspace Flows** (en evolución) como capa de orquestación.
- Sweet spot para organizaciones cloud-first sobre Google Workspace.

#### Comparativa práctica 2026

| Dimensión | Zapier | Make | n8n | Power Automate | Apps Script |
|-----------|--------|------|-----|----------------|-------------|
| **Curva de aprendizaje** | Muy baja | Media | Media-alta | Media | Alta (requiere código) |
| **Self-hosting** | No | No | **Sí** | No (Azure) | No |
| **Apps integradas** | +7000 | +1900 | +1300 | +700 (M365 nativo) | M365 vía API |
| **Modelo de pricing** | Por tarea | Por operación | Workflow ilimitado (self-host gratis) | Por usuario / por flujo | Gratis con cuota |
| **Soporte IA / Agentes** | Básico | Bueno | **Excelente (nativo)** | AI Builder | Vía Vertex AI |
| **Sweet spot** | Negocio sin IT | Flujos visuales complejos | PYME con perfil técnico, datos sensibles | Empresas M365 | Equipos en Google Workspace |
| **Riesgo principal** | Costo a escala, datos en SaaS | Costo a escala, datos en SaaS | Requiere mantener infra | Lock-in con Microsoft | Lock-in con Google |

> Esta comparativa sintetiza la lectura cátedra del material complementario, que explícitamente dice: *"n8n (mejor para agentes IA y self-hosting), Make (flujos visuales complejos) y Zapier (facilidad de uso)"* (Material complementario, Part 1).

### 3.6. Los 3 casos cátedra: tradicional vs IA-Driven

#### Caso 1 — Cuentas a Pagar (ERP)

**Tradicional:**
> Si CUIT + monto coinciden exactos con la OC, aprueba. *"Si hay un centavo de diferencia o el formato del PDF cambia, el sistema arroja error y requiere un humano."*

**IA-Driven (IA Generativa + OCR):**
> *"La IA 'lee' la factura aunque sea una foto de baja calidad o tenga un formato nuevo. Si hay una discrepancia de centavos, entiende que es un error de redondeo tributario, la concilia automáticamente y alerta solo si detecta un patrón de fraude o anomalía estadística."*

**Impacto cátedra:** *"Reducción en la intervención manual de Administración."*

**Cómo se ve en arquitectura concreta:**
1. Email entrante con factura adjunta → trigger en n8n.
2. Nodo OCR (puede ser AIaaS — AWS Textract, Google Document AI, Azure Form Recognizer).
3. Nodo LLM (OpenAI / Claude / Gemini) que extrae estructura: emisor, CUIT, items, total, fecha.
4. Validación contra ERP (vía API) para encontrar OC asociada.
5. Lógica: si coincide → aprobar. Si discrepancia < umbral X → conciliar. Si > X → escalar a humano. Si patrón anómalo → alertar a Auditoría.
6. Registro en ERP + notificación al proveedor.

#### Caso 2 — Atención al Cliente y Ventas (CRM)

**Tradicional:**
> Chatbot de opciones ("Presione 1..."), bucle infinito si el cliente sale del menú.

**IA-Driven (NLP + Análisis de Sentimiento):**
> *"Identifica si el cliente está enojado, prioriza su ticket automáticamente y le ofrece una solución personalizada basada en su historial de compras, no en un menú fijo."*

**Impacto cátedra:** *"Mejora drástica en satisfacción del cliente y conversión de ventas."*

**Cómo se ve en arquitectura concreta:**
1. Mensaje entrante (WhatsApp, email, chat web) → trigger.
2. Análisis de sentimiento y categorización con LLM.
3. Recuperación del historial del cliente desde el CRM (vía API).
4. Si sentimiento = enojo + cliente VIP → prioridad alta, ruteo directo a humano senior.
5. Si consulta = estándar → respuesta automática con LLM enriquecida con contexto del cliente.
6. Si conversión potencial → notificar a equipo comercial.

#### Caso 3 — Mantenimiento Bienes de Uso (IIoT)

**Tradicional:**
> Alerta cada 1.000 horas de uso (preventivo). *"A veces cambiamos piezas que aún servían, o peor, la máquina falla a las 800 horas y la producción se frena."*

**IA-Driven (Mantenimiento Predictivo):**
> *"Sensores de vibración y temperatura envían datos constantes. La IA detecta una micro-variación sónica imperceptible para el oído humano que predice una falla en las próximas horas. Envía la orden de repuesto al ERP antes de que ocurra el daño."*

**Impacto cátedra:** *"Eliminación de paradas de planta no programadas y optimización del ciclo de vida del activo."*

**Cómo se ve en arquitectura concreta:**
1. Sensores IIoT → broker MQTT → time-series database (InfluxDB / TimescaleDB).
2. Modelo de ML (entrenado con históricos de fallas) procesa stream en tiempo real.
3. Detección de anomalía → trigger en orquestador.
4. Cruzado con calendario de producción para encontrar ventana óptima.
5. Generación automática de OT (orden de trabajo) en el sistema de Mantenimiento.
6. Pedido de repuesto al ERP si stock < mínimo.
7. Notificación al jefe de planta con explicación y ventana propuesta.

### 3.7. Framework Construir / Alquilar / Delegar

(Part 2, p. 25-30)

> *"La empresa debe decidir si construye, alquila o delega. Esta decisión no es solo técnica, sino financiera y estratégica."*

**4 factores de decisión cátedra:**

1. **Tiempo de implementación** — ¿necesito esto en semanas, meses o tengo años?
2. **Core de negocio** — ¿la IA es parte de mi propuesta de valor central o es accesoria?
3. **Presupuesto** — ¿qué puedo invertir inicialmente vs cuánto puedo sostener en costo recurrente?
4. **Privacidad** — ¿los datos pueden salir de mi perímetro a un tercero?

#### Construir (Desarrollo interno)

**Cuándo SÍ:**
- IA es **ventaja competitiva** (el corazón del producto).
- **Privacidad extrema** (datos clínicos, militares, financieros sensibles).
- **Volumen de datos únicos** que solo vos tenés.
- Costo proyectado de API / suscripción **prohibitivo al escalar**.

**Cuándo NO:**
- Time-to-market < 6 meses.
- IA no es núcleo del negocio (*"ej. un bot para RRHH en una fábrica de acero"*, Part 2 p. 27).
- Sin presupuesto para equipo técnico **al menos 3 años**.

#### Alquilar (AIaaS — AI as a Service)

> *"AIaaS son modelos de IA pre-entrenados consumidos como API: pagás por uso, no por desarrollo ni por hardware."*

**Proveedores principales:**
- **OpenAI** (GPT-5, embeddings, DALL-E, Whisper).
- **Anthropic** (Claude Opus / Sonnet / Haiku).
- **Google Cloud AI** (Vertex AI, Gemini, Document AI, Speech-to-Text).
- **AWS** (Bedrock, SageMaker, Comprehend, Textract, Rekognition).
- **Microsoft Azure AI** (Azure OpenAI Service, AI Document Intelligence, Cognitive Services).

**Ventajas cátedra (Part 2, p. 28):**
- **Bajo costo de entrada** — sin hardware ni licencias.
- **Velocidad** — *"puedes integrar una API de reconocimiento facial o un modelo de lenguaje en una tarde. Un equipo interno tardaría meses."*
- **Actualización constante** — el proveedor mejora el modelo, vos pagás lo mismo.
- **Escalabilidad infinita** — de 100 a 1.000.000 transacciones por día sin comprar servidores.

**Desventajas cátedra (Part 2, p. 29):**
- **Vendor lock-in** — cambiar de proveedor implica re-arquitectar.
- **Privacidad y soberanía** — los datos viajan a servidores del proveedor (típicamente fuera de Argentina).
- **Costos variables a escala** — *"a veces, llega un punto donde el pago por uso es más caro que mantener un servidor propio."*
- **Caja negra** — *"no tenés acceso a los pesos del modelo ni a cómo fue entrenado."*

#### Delegar (Consultoría externa)

**Aporta:**
- Mejores prácticas de la industria.
- Curva de aprendizaje acelerada.
- Equipo dimensionado a demanda.

**Riesgo:**
- **Fuga de conocimiento** si no se transfiere a equipo interno.
- Dependencia continua del consultor.

#### IA Específica (Vertical AI)

Soluciones llave en mano diseñadas para un sector específico (mantenimiento predictivo industrial, detección de fraude bancario, dictado médico). Vienen pre-entrenadas con datos del sector.

**Cuándo:** cumplimiento normativo o precisión técnica del sector son extremadamente altos.

#### Matriz cátedra "¿Cuál es el camino correcto?" (Part 2, p. 31)

| Camino | Cuándo |
|--------|--------|
| **Desarrollo interno** | Si la solución es el "corazón" de tu ventaja competitiva |
| **AIaaS** | Para funciones transversales (análisis de sentimiento, OCR, chatbots) que *"no requieren reinventar la rueda"* |
| **Consultoría** | Cuando la arquitectura de negocios es compleja y requiere integración profunda ERP/CRM + IA |
| **IA Específica** | Cuando cumplimiento normativo o precisión técnica del sector son extremadamente altos |

### 3.8. Arquitectura de Decisión: Integración Inteligente

(Part 2, p. 32) — la síntesis estratégica de la cátedra:

> *"La mayoría de las empresas exitosas no 'eligen' una alternativa, sino que construyen un ecosistema basado en la criticidad del proceso."*

Tres capas:

1. **El Core del Negocio → Desarrollo Interno.**
   Algoritmos de predicción de demanda, procesos industriales únicos, IP propia. *"Aquí reside la ventaja competitiva y la propiedad intelectual."*

2. **Funcionalidades Estándar → AIaaS.**
   NLP, chatbots, reconocimiento de imágenes, traducción, análisis de sentimiento. *"No tiene sentido desarrollar internamente lo que Microsoft, Google o OpenAI ya ofrecen a una fracción del costo."*

3. **Implementación y Orquestación → Consultoría.**
   *"El 'pegamento' que une la IA con el ERP y el CRM."*

**Conclusión cátedra:** la decisión no es binaria. Una organización madura construye un **ecosistema híbrido** donde cada capa usa la estrategia más adecuada a su criticidad.

### 3.9. Lectura puente con frameworks externos

La matriz cátedra es consistente con frameworks Build vs Buy vs Partner conocidos:

- **Gartner** clasifica desde hace años las decisiones de software como "Build / Buy / Partner / Outsource" usando criterios similares (diferenciación competitiva, complejidad, time-to-market, costo total de propiedad).
- **MIT Sloan Management Review** publica desde 2015 análisis del costo oculto del "Build" (subestimación de mantenimiento, talento, deuda técnica) y del "Buy" (vendor lock-in, customización imposible).
- La regla práctica de Wardley Maps: **"Build" si la actividad está en zona Génesis o Custom (alto valor diferencial). "Buy" si está en zona Product o Commodity (estándar y maduro).**

El criterio cátedra cae claramente en esta tradición y la baja a vocabulario PYME.

---

## 4. Caso real organizacional

**PYME argentina de servicios logísticos — 80 empleados, sede en Rosario, opera courier B2B a 4 provincias.**

**Situación inicial (2024):**
- Recepción de pedidos por **WhatsApp y email** (sin formulario estructurado).
- Una persona dedicada full-time a cargar los pedidos manualmente en el WMS.
- Facturación al final del mes a partir de un Excel armado a mano por la administrativa.
- Quejas frecuentes de clientes por demoras en confirmación de recepción del pedido.

**Punto de dolor en frase de gerencia:**
> "Si vendemos más, tenemos que contratar más administrativos. La operación no escala."

**Análisis cátedra aplicado:**

| Pregunta | Respuesta |
|----------|-----------|
| ¿Es Core de negocio? | No. El core es la red logística física, no la carga de pedidos. |
| ¿Time-to-market? | Necesitan resultados en menos de 3 meses. |
| ¿Privacidad? | Datos comerciales sensibles pero no PII regulada por Ley 25.326 en formato crítico. |
| ¿Volumen? | 400-600 pedidos / día. Manejable con AIaaS sin costos prohibitivos. |

**Camino elegido**: Alquilar (AIaaS) + n8n self-hosted como orquestador.

**Solución implementada:**

1. **n8n self-hosted** en un VPS local (US$ 20/mes en DigitalOcean). Razón: querían control de datos y costo predecible.
2. **Trigger WhatsApp Business Cloud API** (gratis hasta cierto volumen, después tier económico).
3. **Trigger Gmail** para los pedidos por email.
4. **Nodo OpenAI GPT-4o-mini** (costo bajo) para extraer estructura del mensaje: cliente, dirección origen, dirección destino, descripción del paquete, urgencia.
5. **Nodo Google Maps API** para validar direcciones y estimar tiempo.
6. **Nodo HTTP** al WMS para crear el pedido.
7. **Nodo WhatsApp** de respuesta automática al cliente con confirmación y número de seguimiento.
8. **Escalado a humano** si la IA tiene confianza < 0.7 en algún campo (umbral configurado).

**Costo total mensual:**
- VPS n8n: US$ 20.
- OpenAI API: ~US$ 35 (calculado con su volumen).
- WhatsApp Business API: ~US$ 30.
- Google Maps API: ~US$ 15.
- **Total: ~US$ 100/mes.**

**vs Costo evitado:**
- Sueldo administrativo full-time que iba a contratar: ~US$ 1.500/mes.
- ROI: 15× en costos directos, sin contar la mejora en NPS por confirmaciones inmediatas.

**Por qué NO eligieron UiPath o Blue Prism:**
- Licenciamiento enterprise (US$ 4.000-12.000/año por bot) imposible de justificar a su escala.
- Curva de aprendizaje y necesidad de developer RPA dedicado.
- Para un caso de uso de iPaaS clásico (orquestar APIs, no automatizar UI legacy), **n8n hace exactamente lo mismo a costo cero de licencia**.

**Lecciones cátedra aplicadas:**
- **Rediseño primero**: definieron el flujo objetivo antes de tocar herramientas (el formulario de WhatsApp estructurado en lenguaje natural reemplazó copia y pega).
- **Build vs Buy vs Partner**: AIaaS + iPaaS sin desarrollo interno.
- **Caja negra controlada**: usan OpenAI (caja negra) pero solo para extracción, no para decisiones críticas; las reglas de negocio viven en n8n donde son auditables.

---

## 5. Aplicación a la transformación organizacional

### 5.1. Decidir Construir / Alquilar / Delegar — protocolo práctico

Cuando aparezca una iniciativa con "IA" en el título, aplicá este protocolo antes de aprobar presupuesto:

**Paso 1 — Caracterizar la iniciativa.**
- ¿Es Core o Estándar? (test rápido: ¿alguien ya tiene una API que hace esto?)
- ¿Cuánto tiempo tenemos?
- ¿Qué pasa con los datos? (residencia, sensibilidad, regulación)

**Paso 2 — Aplicar la matriz cátedra.**

```
Core + Tiempo largo + Datos sensibles      → Construir
Estándar + Tiempo corto + Datos no críticos → Alquilar (AIaaS)
Complejo + Integración profunda             → Delegar (Consultoría)
Vertical específico + Compliance alto       → IA Específica
```

**Paso 3 — Calcular TCO honesto, no precio.**

| Componente | A 1 año | A 3 años |
|-----------|---------|----------|
| Licencias / suscripciones | | |
| Infraestructura (cloud / on-prem) | | |
| Equipo (devs, ML eng, ops) | | |
| Mantenimiento y mejora continua | | |
| Costo de salida / migración | | |

**Paso 4 — Diseñar el ecosistema (no la solución única).**

La conclusión cátedra: no elijas una sola estrategia. Construí un **ecosistema híbrido**:
- Core interno donde está tu IP.
- AIaaS para todo lo estándar.
- Orquestador (n8n / Power Automate) como pegamento.
- Consultoría para los puentes complejos.

### 5.2. Impacto organizacional — no es solo tecnología

Como dice la cátedra: *"La automatización impacta roles, competencias y estructura."*

Cosas que cambian cuando automatizás integralmente:

- **Roles**: el administrativo que cargaba pedidos pasa a **supervisar el proceso y atender las excepciones**. Necesita formación para leer dashboards y entender qué le está reportando el sistema.
- **Competencias**: aparece la necesidad de un **process owner** que entienda el flujo end-to-end y de un **automation lead** que pueda iterar n8n cuando el negocio cambia.
- **Estructura**: muchas organizaciones crean un **Centro de Excelencia de Automatización (CoE)** transversal, en vez de dejar que cada área haga sus propios bots descoordinadamente.

Sin trabajo de cambio organizacional, la automatización integral no escala: queda como islas que cada área inventó y nadie mantiene.

---

## 6. Errores comunes / mitos

**1. "Compramos UiPath para automatizar todo."**
UiPath / Blue Prism / Automation Anywhere son herramientas **enterprise RPA** que pueden costar entre US$ 4.000 y US$ 20.000 por año por bot, más infraestructura, más developers RPA dedicados. Para la mayoría de las PYMEs argentinas, **n8n self-hosted hace el 90% de los casos de uso a costo cercano a cero**. Solo justificás enterprise RPA si tenés que automatizar UIs de Legacy muy específicos a escala industrial.

**2. "Automatizamos el proceso tal cual está."**
Anti-patrón 3 del módulo: *"Estamos haciendo más rápido algo que no deberíamos estar haciendo"*. **Rediseñá primero, automatizá después.**

**3. "AIaaS es siempre lo más barato."**
Es lo más barato **al inicio**. A volúmenes altos (millones de llamadas al mes), el pricing variable de OpenAI / AWS / Azure puede superar al de un modelo propio en GPU dedicada. La cátedra lo dice explícito: *"a veces llega un punto donde el pago por uso es más caro que mantener un servidor propio"* (Part 2, p. 29).

**4. "Self-hosting es gratis."**
n8n self-hosted no tiene costo de licencia, pero **sí tiene costo de infraestructura, mantenimiento y operación**. Calculá VPS + backups + actualizaciones + tiempo del equipo. A escala chica es muy conveniente. A escala enterprise compará contra n8n Cloud o Make.

**5. "Con LLMs no hace falta diseñar reglas."**
Un LLM no es un sustituto de las reglas de negocio. Sirve para **interpretar entradas no estructuradas** (lenguaje, imágenes, audio). Las reglas de qué hacer con esa interpretación tienen que vivir en código o en una plataforma de orquestación auditable. *"Caja negra todo el flujo"* es receta para que nadie entienda por qué se rechazó una factura.

**6. "Vamos a pasar de cero a Agentes IA en 6 meses."**
Saltar Nivel 1 → Nivel 3 sin pasar por Nivel 2 termina mal. La progresión cátedra (RPA tradicional → Inteligente → Agéntica) refleja madurez organizacional acumulada: gobierno de datos, equipo capacitado, casos de uso probados. Querer hacer agentes sin haber automatizado nada tradicional antes es como querer correr Fórmula 1 sin haber sacado el registro.

**7. "No calculamos TCO completo."**
Comparar US$ 200/mes de un SaaS contra "es gratis hacerlo internamente" sin contar al developer es el cálculo más común y más equivocado. Un developer en Argentina cuesta entre US$ 30.000 y US$ 90.000/año cargado. Si el "build" toma 3 meses, el costo real de esos 3 meses puede ser US$ 7.500 a US$ 22.500, comparable a 3-9 años del SaaS.

**8. "Empezamos por el proceso más grande."**
Empezá por uno **medible, contenido y de bajo riesgo**. Mostrá ROI rápido para ganar credibilidad. Después escalá. Empezar por "automatizar todo el proceso de ventas" sin victorias chicas previas es matar la iniciativa antes de empezar.

---

## 7. Checklist

**Antes de aprobar una iniciativa de Automatización Integral:**
- [ ] ¿El proceso fue rediseñado o lo estoy automatizando "tal como está"?
- [ ] ¿Tengo identificado el KPI estratégico que esta automatización va a mover?
- [ ] ¿Apliqué los 4 factores cátedra (Tiempo / Core / Presupuesto / Privacidad)?
- [ ] ¿Pasé por la matriz Construir / Alquilar / Delegar / IA Específica?
- [ ] ¿Calculé TCO a 3 años, no solo costo inicial?
- [ ] ¿Definí qué pasa con los datos: residencia, anonimización, compliance?

**Para elegir plataforma iPaaS:**
- [ ] ¿Mi caso de uso requiere self-hosting (datos sensibles)? → n8n / Power Automate on-prem.
- [ ] ¿Mi organización vive en M365? → Power Automate por defecto.
- [ ] ¿Mi organización vive en Workspace? → Apps Script / Workspace flows.
- [ ] ¿Necesito pocas integraciones pero usuarios no técnicos? → Zapier.
- [ ] ¿Necesito flujos visuales complejos a costo medio? → Make.
- [ ] ¿Tengo perfil técnico, datos sensibles y agentes IA en el horizonte? → **n8n**.

**Para diseñar un flujo automatizado:**
- [ ] ¿Identifiqué triggers, condiciones y acciones?
- [ ] ¿Definí qué pasa con los datos (loops, transformaciones, persistencia)?
- [ ] ¿Diseñé el manejo de errores y el escalado a humano?
- [ ] ¿Hay observabilidad (logs, métricas, alertas) para cuando algo se rompa?
- [ ] ¿Está documentado quién es el process owner?
- [ ] ¿Defini criterios para deprecar el flujo si el proceso cambia?

**Para automatización con IA:**
- [ ] ¿Distinguí qué partes del flujo requieren IA (interpretación) vs reglas (decisión)?
- [ ] ¿Las decisiones críticas son auditables (no caja negra completa)?
- [ ] ¿Hay umbral de confianza para escalar a humano cuando la IA duda?
- [ ] ¿Tengo plan de evaluación continua del modelo?
- [ ] ¿Estoy pagando por uso y monitoreando consumo?

---

## 8. Para profundizar

**Documentación oficial de plataformas:**
- n8n: `docs.n8n.io` — documentación completa, guías de self-hosting, biblioteca de nodos.
- n8n Community: `community.n8n.io` — workflows compartidos, casos de uso reales.
- Zapier University: `zapier.com/university` — formación gratuita.
- Make Academy: `academy.make.com`.
- Microsoft Power Automate Learn: `learn.microsoft.com/power-automate/`.
- Google Apps Script: `developers.google.com/apps-script`.
- Google Workspace Flows: `workspace.google.com`.

**AIaaS — documentación de proveedores:**
- OpenAI Platform: `platform.openai.com/docs`.
- Anthropic Claude API: `docs.anthropic.com`.
- Google Cloud Vertex AI: `cloud.google.com/vertex-ai/docs`.
- AWS Bedrock: `docs.aws.amazon.com/bedrock/`.
- Microsoft Azure AI: `learn.microsoft.com/azure/ai-services/`.

**Frameworks Build vs Buy:**
- Gartner — reportes sobre "Application Strategy" y "Buy vs Build" (algunos públicos, otros bajo suscripción).
- MIT Sloan Management Review — buscar "Build vs Buy software" para análisis con casos reales.
- Wardley Maps: `learnwardleymapping.com` — método visual para decidir Build / Buy / Outsource según madurez de la actividad.

**Lecturas estructurales:**
- Daniel Susskind & Richard Susskind, *"The Future of the Professions"* (Oxford, 2015) — impacto de la automatización en roles cognitivos.
- Erik Brynjolfsson & Andrew McAfee, *"The Second Machine Age"* (W.W. Norton, 2014) — economía de la automatización con IA.
- Tom Davenport, *"The AI Advantage"* (MIT Press, 2018) — adopción de IA en organizaciones (casos prácticos).

**Comunidades y newsletters relevantes:**
- LangChain blog y documentación — para entender agentes IA.
- "TLDR AI", "The Batch" (Andrew Ng) — newsletters semanales del estado del arte.
- Foros de n8n y r/automation en Reddit para casos PYME.

**Material complementario explícito de la cátedra:**
- *"Automatización con IA: n8n vs Make vs Zapier (Guía 2026)"* — comparativa práctica recomendada por el módulo.
- Comparativa CRMs PYMEs Argentina 2026 (recomendada por la cátedra).

---

## Próximo paso

Ya tenés clara la **arquitectura tecnológica** (capítulo 08) y la **automatización integral** (este capítulo 09). El próximo paso es la pieza que sostiene todo lo anterior: **los datos**. Sin gobierno de datos serio, ninguna automatización IA-Driven funciona, porque los modelos son tan buenos como los datos con los que los alimentás. En el capítulo siguiente vas a ver cómo se organiza la gestión estratégica de datos en una organización moderna: catálogos, calidad, ciclo de vida, ownership y cómo conectar todo esto con la arquitectura y la automatización que ya conocés.

→ Seguir con **[10. Gestión estratégica de datos](./10-gestion-estrategica-datos.md)**

---

## Referencias

- DIATO Módulo 6 — Parte 2 (Tema 7), pp. 6-32. Ing. Ives Minetti & Ana Lucía Tolini.
- DIATO Módulo 6 — Material complementario, *"Automatización con IA: n8n vs Make vs Zapier (Guía 2026)"*.
- n8n Documentation. `docs.n8n.io`.
- Zapier Help & Documentation. `zapier.com/help`.
- Make Documentation. `make.com/help`.
- Microsoft Power Automate Documentation. `learn.microsoft.com/power-automate/`.
- Google Apps Script Reference. `developers.google.com/apps-script`.
- OpenAI Platform Docs. `platform.openai.com/docs`.
- Anthropic Claude API Docs. `docs.anthropic.com`.
- Google Cloud Vertex AI. `cloud.google.com/vertex-ai/docs`.
- AWS Bedrock. `docs.aws.amazon.com/bedrock/`.
- Microsoft Azure AI Services. `learn.microsoft.com/azure/ai-services/`.
- Wardley, S. *Wardley Maps*. `learnwardleymapping.com`.
- Brynjolfsson, E. & McAfee, A. (2014). *The Second Machine Age*. W.W. Norton.
- Davenport, T. (2018). *The AI Advantage*. MIT Press.
- Susskind, D. & Susskind, R. (2015). *The Future of the Professions*. Oxford University Press.
- Ley 25.326 — Protección de Datos Personales (Argentina).
