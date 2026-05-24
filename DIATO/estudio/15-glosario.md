# 15 — Glosario temático

> Diccionario operativo de la DIATO. NO está ordenado alfabéticamente: está agrupado por **familias conceptuales** para que puedas estudiar por bloque y para que cuando busques un término te encuentres con sus vecinos semánticos. Cada definición es corta (2-4 líneas) y, cuando corresponde, te dice en qué capítulo del estudio (`01`-`14`) se desarrolla en profundidad.

> Convención: **negrita** = término principal. *cursiva* = traducción, sinónimo o sigla en inglés cuando es relevante.

---

## Cómo usar este glosario

- **¿No te acordás de un término?** Buscá con `Ctrl+F` o `/` en tu editor: si no recordás cómo se escribe, mirá la familia conceptual más probable (las 12 secciones de abajo).
- **¿Querés repasar un módulo entero?** Bajá a la sección temática correspondiente y leé los términos en orden — están agrupados para que la lectura siga el flujo lógico de la cátedra.
- **¿Encontrás un término marcado "ver X"?** Es porque la definición canónica vive en otra familia (la jerarquía conceptual mandó).

---

## 1. IA y aprendizaje (núcleo conceptual)

> Capítulos relacionados: `01-introduccion-ia-ml-bigdata.md`, `02-ml-fundamentos.md`, `03-deep-learning-arquitecturas.md`.

**Inteligencia Artificial (IA)** — Disciplina y conjunto de tecnologías que permiten a las máquinas imitar funcionalidades de la inteligencia humana (percepción, razonamiento, aprendizaje, lenguaje, resolución de problemas, producción creativa). Definición operativa de la cátedra basada en UNESCO/COMEST 2019. *Ver cap 01.*

**IA Débil** — *Narrow AI.* La única que existe hoy. Resuelve tareas específicas (clasificar imágenes, responder preguntas). NO entiende el mundo, ejecuta funciones. *Ver cap 01.*

**IA General** — *AGI - Artificial General Intelligence.* Hipotética IA capaz de igualar o superar la inteligencia humana en cualquier dominio. NO existe — es objetivo de investigación, no producto. *Ver cap 01.*

**Singularidad tecnológica** — Hipótesis (Ray Kurzweil) según la cual una IA que se auto-mejore continuamente alcanzaría un punto de no retorno, volviéndose incontrolable para los humanos. Es prospectiva, no estado del arte. *Ver cap 01.*

**Test de Turing** — Evaluación operativa propuesta por Alan Turing (1950) para determinar si una máquina exhibe comportamiento indistinguible del humano. Umbral moderno: >30% de jueces engañados tras 5 minutos de conversación. *Ver cap 01.*

**CAPTCHA** — *Completely Automated Public Turing test to tell Computers and Humans Apart.* Test de Turing inverso: la máquina decide si está interactuando con un humano. *Ver cap 01.*

**Agente IA** — Entidad (software o hardware) que percibe su entorno mediante sensores, procesa información y actúa mediante actuadores para cumplir una meta de manera autónoma o semiautónoma. *Ver cap 01.*

**5 tipos de agentes** — Taxonomía cátedra: (1) Reactivos simples — sin memoria; (2) Con memoria / basados en modelo; (3) Basados en objetivos; (4) Basados en utilidad; (5) Con aprendizaje. Cada nivel suma una capacidad sobre el anterior. *Ver cap 01 + cap 16 (cheatsheet).*

**IA Agéntica** — Evolución de la IA generativa: sistema que percibe, razona, toma decisiones y ACTÚA con poca supervisión humana, coordinando múltiples pasos en sistemas digitales o físicos. Va más allá de responder: ejecuta trabajo real. *Ver cap 01 + cap 11-tendencias.*

**Machine Learning (ML)** — Rama de la IA que dota a las máquinas de capacidad de aprender a partir de datos, identificando patrones sin ser programadas explícitamente para cada caso. Resuelve regresión y clasificación. *Ver cap 02.*

**Deep Learning (DL)** — Subcampo del ML basado en **redes neuronales artificiales** profundas (varias capas ocultas) inspiradas en el cerebro humano. Requiere mucho dato + GPU. *Ver cap 03.*

**Red neuronal artificial** — Modelo de capas de "neuronas" interconectadas que aprenden ajustando pesos a partir del error de predicción. Capa de entrada → capas ocultas → capa de salida. *Ver cap 03.*

**CNN (ConvNet)** — *Convolutional Neural Network.* Red neuronal especializada en patrones espaciales (imágenes, audio, señales, series temporales). *Ver cap 03.*

**Fine-tuning** — Ajustar un modelo preentrenado con datos propios de un dominio específico para que rinda mejor en una tarea concreta sin entrenar desde cero. *Ver cap 11.*

**Prompting** — Diseño de instrucciones en lenguaje natural para guiar la respuesta de un LLM. La calidad del prompt determina la calidad del output (basura entra → basura sale). *Ver cap 04.*

**Alucinación** — Respuesta de un LLM que SUENA convincente pero es **falsa** (datos inventados, citas inexistentes, lógica fabricada). NO está "mitigada" en sentido fuerte — está atenuada con técnicas como RAG y citaciones. *Ver cap 04 + cap 12-etica.*

**Sesgo** — Distorsión sistemática en los datos o el modelo que produce resultados injustos o erróneos. La AAIP distingue 4 tipos (ver familia 11). *Ver cap 12.*

**Fuente** — En IA generativa: documento, dataset o referencia desde donde el modelo extrae información para responder. Una de las "3 alertas" de la cátedra Della Torre. *Ver cap 04.*

**Embeddings** — Representación vectorial numérica de un texto, imagen o concepto que captura su significado en un espacio matemático. Base de RAG y de la búsqueda semántica. *Ver cap 11.*

**RAG** — *Retrieval Augmented Generation.* Arquitectura que combina un LLM con una base de conocimiento propia: ante una pregunta, primero recupera fragmentos relevantes y después genera la respuesta. Reduce alucinaciones, permite usar info privada/actualizada. *Ver cap 04 + cap 11.*

**Modelos fundacionales** — *Foundation models.* Modelos grandes preentrenados con datos masivos (GPT, Claude, Gemini, LLaMA) que sirven como base para múltiples tareas downstream. *Ver cap 04 + cap 11.*

---

## 2. Big Data y datos

> Capítulos relacionados: `01-introduccion-ia-ml-bigdata.md`, `07-datos-fundamentos.md`.

**Big Data** — Fenómeno científico-tecnológico que combina ciencia y tecnología para transformar la complejidad en simplicidad mediante grandes volúmenes de datos. Origen del término: Doug Laney (Gartner, 2001). Traducción: macrodatos / datos masivos. *Ver cap 01 + cap 07.*

**Las 5 V del Big Data** — Framework canónico: **Volumen** (escala), **Velocidad** (tasa de generación/procesamiento), **Variedad** (tipos y formatos), **Veracidad** (calidad), **Valor** (utilidad de negocio). Las 3 originales (Volumen+Velocidad+Variedad) sumaron las 2 actuales (Veracidad+Valor). *Ver cap 01 + cap 07 + cap 16.*

**Datos estructurados** — Datos con modelo definido y campos fijos. Viven en tablas relacionales. Ejemplo: fichas de clientes, transacciones comerciales. *Ver cap 07.*

**Datos semiestructurados** — Sin formato fijo pero con atributos o etiquetas que permiten parsearlos. Ejemplo: JSON, XML, logs, emails con cabecera. *Ver cap 07.*

**Datos no estructurados** — Sin modelo predefinido. Ejemplo: videos, fotografías, audios, texto libre. Constituyen el ~80% de los datos del mundo. *Ver cap 07.*

**Data Lake** — Repositorio que guarda datos crudos (estructurados, semi y no estructurados) sin procesar a su llegada. "Tirá todo acá y después vemos." Schema-on-read. *Ver cap 07.*

**Data Warehouse** — Repositorio analítico de datos estructurados, limpios, históricos y agregados, organizado para reportes y BI. Schema-on-write. *Ver cap 07.*

**ETL / ELT** — *Extract, Transform, Load* (clásico, transformás antes de cargar) vs *Extract, Load, Transform* (moderno, cargás crudo al lake y transformás después). *Ver cap 07.*

**DIKW (Pirámide)** — Jerarquía conceptual: **Dato** (hecho objetivo sin contexto) → **Información** (dato con significado) → **Conocimiento** (información aplicable a la acción) → **Sabiduría** (conocimiento + juicio para decidir). Marco de Ferrario/Barbero. *Ver cap 07 + cap 16.*

**Datos sintéticos** — Datos generados artificialmente (por IA) que imitan la estadística de datos reales. Útiles cuando hay escasez o privacidad. Riesgo: **colapso del modelo** si se entrenan IAs solo con datos sintéticos. *Ver cap 11.*

**Metadatos** — Datos sobre los datos: fuente, fecha, autor, formato, esquema. Críticos para gobierno y auditoría. *Ver cap 07.*

**Web scraping** — Extracción automatizada de datos publicados en sitios web. Útil para recolección masiva; cuidar términos de uso y legalidad. *Ver cap 07.*

---

## 3. Machine Learning (algoritmos y tipos)

> Capítulo principal: `02-ml-fundamentos.md`.

**Aprendizaje supervisado** — Aprende de datos **etiquetados**: conocés la variable resultado y entrenás un modelo para predecirla en datos nuevos. Resuelve clasificación (etiqueta) y regresión (número). *Ver cap 02.*

**Aprendizaje no supervisado** — Trabaja con datos **sin etiquetar**: el algoritmo descubre patrones, agrupaciones o anomalías por sí mismo. *Ver cap 02.*

**Aprendizaje semi-supervisado** — Combina pocos datos etiquetados con muchos no etiquetados. Útil cuando etiquetar es caro. *Ver cap 02.*

**Aprendizaje por refuerzo** — *Reinforcement Learning (RL).* Un agente aprende interactuando con un entorno: recibe recompensas (acción correcta) o penalizaciones (incorrecta), y optimiza su política. Base de robots, AlphaGo y muchos asistentes modernos. *Ver cap 02.*

**Clasificación** — Predecir la pertenencia de una observación a una clase (binaria: spam/no spam; multiclase: gato/perro/conejo). *Ver cap 02.*

**Regresión** — Predecir una variable cuantitativa (cantidad, precio, temperatura). *Ver cap 02.*

**Clustering** — Agrupamiento no supervisado: armar grupos de observaciones similares. *Ver cap 02.*

**Naive Bayes** — Clasificador probabilístico basado en el teorema de Bayes que asume independencia entre variables ("naive" = inocente). Rápido, simple, baseline clásico. *Ver cap 02.*

**KNN** — *K-Nearest Neighbors.* Clasifica/regresa basándose en los K vecinos más cercanos en el espacio de características. Lazy learner: no entrena, busca al momento de predecir. *Ver cap 02.*

**Árbol de decisión** — Modelo en forma de árbol que divide los datos con preguntas binarias. Interpretable: ves exactamente por qué decidió lo que decidió. *Ver cap 02.*

**Random Forest** — *Bosque aleatorio.* Combina muchos árboles entrenados en subconjuntos aleatorios y vota. Técnica = **bagging**. Robusto, popular en industria. *Ver cap 02.*

**SVM** — *Support Vector Machine.* Encuentra el hiperplano que mejor separa las clases en el espacio de características. Usa **kernels** para problemas no lineales. *Ver cap 02.*

**K-Means** — Algoritmo de clustering que agrupa los datos en K clusters minimizando la distancia al centroide del cluster. El analista define K. *Ver cap 02.*

**ACP** — *Análisis de Componentes Principales (PCA).* Técnica de reducción de dimensionalidad: transforma muchas variables correlacionadas en pocas no correlacionadas que conservan la mayor varianza. *Ver cap 02.*

**Apriori** — Algoritmo de reglas de asociación que descubre qué ítems aparecen juntos (clásico "market basket analysis": pañales y cerveza). *Ver cap 02.*

**Z-Score / Isolation Forest** — Detección de anomalías: el primero estadístico, el segundo basado en árboles. Útiles para fraude, intrusión, fallos. *Ver cap 02.*

**Validación cruzada** — *Cross-validation.* Técnica que entrena y evalúa el modelo en distintos fragmentos del dataset para estimar mejor su rendimiento real. *Ver cap 02.*

**Bagging** — *Bootstrap Aggregating.* Entrenar varios modelos sobre subconjuntos aleatorios y combinar predicciones (Random Forest es bagging de árboles). *Ver cap 02.*

---

## 4. Pirámide analítica

> Capítulo principal: `01-introduccion-ia-ml-bigdata.md` (bloque B Alvear).

**Analítica descriptiva** — ¿Qué pasó? Reportes históricos, dashboards, métricas. El nivel base de madurez analítica. *Ver cap 01.*

**Analítica diagnóstica** — ¿Por qué pasó? Drill-down, análisis causal, análisis de varianza. Explica los descriptivos. *Ver cap 01.*

**Analítica predictiva** — ¿Qué va a pasar? Modelos de ML que proyectan: forecast de ventas, churn, score de riesgo. *Ver cap 01.*

**Analítica prescriptiva** — ¿Qué debería hacer? Sistemas que recomiendan o ejecutan acciones óptimas: pricing dinámico, ruta óptima, oferta personalizada. Nivel máximo de madurez analítica. *Ver cap 01.*

---

## 5. IA Generativa

> Capítulos relacionados: `04-prompt-engineering-iag.md`, `11-tendencias-2026.md`.

**IA Generativa (IAG)** — Rama de la IA que genera contenido nuevo (texto, imagen, audio, video, código) en respuesta a indicaciones en lenguaje natural, en lugar de solo clasificar o predecir sobre datos existentes. *Ver cap 04.*

**LLM** — *Large Language Model.* Modelo de lenguaje grande entrenado con miles de millones de parámetros sobre corpus masivos de texto. GPT, Claude, Gemini, LLaMA. *Ver cap 04.*

**GPT** — *Generative Pre-trained Transformer.* Familia de LLMs de OpenAI; por extensión, marca de los modelos conversacionales más populares. *Ver cap 04.*

**Ventana de contexto** — *Context window.* Cantidad máxima de tokens (≈palabras) que un LLM puede "leer" y "recordar" en una misma interacción. Más ventana = más documento podés cargar, más diálogo retiene. *Ver cap 04.*

**Prompt** — Instrucción en lenguaje natural enviada al modelo. *Ver cap 04.*

**ROCEF** — Framework de prompt-engineering cátedra: **R**ol + **O**bjetivo + **C**ontexto + **E**jemplo + **F**ormato. Evolución del clásico `PERSONA + TAREA + CONTEXTO + FORMATO`. *Ver cap 04 + cap 16.*

**Modelo 4E** — Ciclo de adopción de herramientas IA (Della Torre): **Explorar** (buscar herramientas) → **Evaluar** (3 aristas: potencia, seguridad/privacidad, T&C) → **Ejecutar** (implementar) → **Escalar** (extender a otros procesos, retroalimentar). *Ver cap 04 + cap 16.*

**Gemini Deep Research** — Funcionalidad de Gemini para investigación en profundidad sobre documentos del usuario y la web; produce reportes estructurados. *Ver cap 04.*

**Gems** — Expertos de IA personalizados de Google: un asistente especializado en una tarea (revisor de mails, consultor de estrategia, etc.). Primera aproximación a agentes. *Ver cap 04.*

**Canvas** — Espacio de trabajo colaborativo en Gemini/ChatGPT donde editás documentos junto con el modelo. *Ver cap 04.*

**MCP / A2A / ACP** — Protocolos emergentes para que los agentes IA hablen entre sí o con datos: **MCP** (Model Context Protocol, Anthropic), **A2A** (Agent-to-Agent, Google), **ACP** (Agent Communication Protocol, abierto). *Ver cap 11.*

---

## 6. Estrategia tecnológica

> Capítulo principal: `05-estrategia-tecnologica.md`.

**Estrategia tecnológica** — Proceso de adopción y ejecución de decisiones sobre políticas, planes y acciones relacionadas con la creación, difusión y uso de la tecnología en la organización. Transversal a todas las áreas. *Ver cap 05.*

**Capacidad de absorción** — *Absorptive capacity.* Habilidad organizacional para identificar, asimilar y explotar conocimiento del entorno (Cohen & Levinthal 1990; Lane, Koka & Pathak 2006). Predice quién logra realmente capturar valor de tecnologías nuevas. *Ver cap 05.*

**Ambidestreza organizacional** — *Organizational ambidexterity.* Capacidad de **explotar** las capacidades actuales (eficiencia, optimización del core) Y al mismo tiempo **explorar** nuevas competencias (innovación, apuestas de futuro). O'Reilly & Tushman 1996/2016. *Ver cap 05.*

**IA como socia de pensamiento** — Modo de uso de IA en la **definición** de la estrategia (input cognitivo, brainstorming, prospectiva). *Ver cap 05.*

**IA intrínseca a la estrategia** — IA en la **puesta en valor** de la estrategia (ejecución, automatización, decisiones aumentadas). *Ver cap 05.*

**Brecha digital** — Gap entre quienes acceden, usan y aprovechan tecnologías digitales/IA y quienes no. A nivel macro: países; a nivel meso: empresas; a nivel micro: equipos/personas. *Ver cap 05.*

**Brecha digital de IA** — Etiqueta cátedra para los datos Thomson Reuters: solo 22% de empresas tienen estrategia de IA clara; 46% invirtió en tecnología pero solo 38% espera impacto este año. *Ver cap 05.*

**Paradoja de la generación IA** — Casi 8 de cada 10 empresas implementaron IA, pero el mismo porcentaje no reporta impacto material en ganancias. Alta adopción, bajo impacto. *Ver cap 06 + cap 14.*

---

## 7. Procesos

> Capítulo principal: `06-gestion-procesos-bpm.md`.

**Proceso** — Secuencia ordenada de actividades, con entradas y salidas, que agrega valor a los clientes (internos o externos). *Ver cap 06.*

**Gestión basada en procesos** — Comprensión y gestión de los procesos interrelacionados como un sistema, buscando eficacia y eficiencia. *Ver cap 06.*

**BPM** — *Business Process Management.* Disciplina y conjunto de prácticas para diseñar, ejecutar, monitorear y optimizar procesos de negocio. *Ver cap 06.*

**BPMN** — *Business Process Model and Notation.* Notación gráfica estandarizada para modelar procesos. Símbolos universales (rombo = decisión, óvalo = inicio/fin, rectángulo = actividad). *Ver cap 06.*

**AS IS** — Proceso ACTUAL, tal como se ejecuta hoy (con sus dolores). Punto de partida del rediseño. *Ver cap 06.*

**TO BE** — Proceso FUTURO/propuesto, después del rediseño. Punto de llegada. *Ver cap 06.*

**Transformación digital** — Cambios que se producen por la aplicación y utilización de la tecnología digital con foco en mejorar experiencias, hacer más eficientes operaciones y procesos y crear nuevas oportunidades de negocio. Rediseña procesos, no solo digitaliza. *Ver cap 06.*

**Digitalización** — Convertir datos analógicos a formato digital (escaneo, formulario online). NO es transformación digital — es su prerrequisito. *Ver cap 06.*

**Efecto silo** — Patología organizacional: cada área trabaja aislada con sus propias expectativas, sin visión compartida ni del proceso transversal ni del cliente final. *Ver cap 06.*

**Enfoque por procesos** — Antídoto del silo: visión horizontal que atraviesa áreas para entregar valor al cliente. *Ver cap 06.*

**Mapa de procesos** — Representación visual de los procesos de la organización y sus interrelaciones. *Ver cap 06.*

**Jerarquía de procesos** — Niveles macro / operativo / tarea. *Ver cap 06.*

**Cuello de botella** — Punto de congestión que reduce el ritmo del flujo porque la capacidad ahí está limitada. *Ver cap 06.*

**5 por qués** — Herramienta de análisis causal: ante un problema, preguntá "¿por qué?" cinco veces seguidas para llegar a la causa raíz, no a los síntomas. *Ver cap 06 + cap 16.*

**Ishikawa** — *Diagrama causa-efecto* o "espina de pescado". Estructura las causas posibles de un problema en categorías (personas, métodos, máquinas, materiales, medio, medición). *Ver cap 06 + cap 16.*

**Pareto** — *Regla del 80/20.* El 20% de las causas genera el 80% de los efectos. Priorizá las pocas vitales sobre las muchas triviales. *Ver cap 06 + cap 16.*

**Minería de procesos** — *Process mining.* Análisis automatizado de logs de eventos (ERP, CRM, WMS) para descubrir cómo se ejecutan REALMENTE los procesos vs cómo creen los responsables que se ejecutan. Herramienta clásica: **Disco Fluxicon**. *Ver cap 06.*

---

## 8. Arquitectura tecnológica

> Capítulo principal: `08-arquitectura-software-it.md`.

**ERP** — *Enterprise Resource Planning.* Sistema integral de gestión administrativa y financiera (back-office). Unifica departamentos, base de datos única, automatiza procesos cruzados (venta → despacho → contabilidad). *Ver cap 08.*

**CRM** — *Customer Relationship Management.* Gestión de la relación y ciclo de vida del cliente (front-office). Contactos, ventas, marketing, post-venta, analítica. *Ver cap 08.*

**WMS** — *Warehouse Management System.* Gestión y optimización operativa de depósitos y logística. Stock en tiempo real, picking, trazabilidad, integración con escáneres/RFID. *Ver cap 08.*

**Legacy** — Sistema antiguo (muchas veces a medida) que sigue siendo crítico para la operación. "La verdad incómoda" de la transformación digital: probado y amortizado, pero difícil de integrar y con talento escaso (programadores Cobol). *Ver cap 08.*

**IoT** — *Internet of Things.* Red de objetos cotidianos con sensores que recolectan datos (cámaras, temperatura, presencia). *Ver cap 08.*

**IIoT** — *Industrial IoT.* IoT en entornos industriales con requisitos mucho más estrictos de precisión, latencia y seguridad. *Ver cap 08.*

**Arquitectura monolítica** — Toda la aplicación en una sola unidad desplegable. Simple al inicio, difícil de escalar y modificar. *Ver cap 08.*

**Microservicios** — Aplicación dividida en servicios pequeños, independientes, comunicados por API. Si uno falla, el resto sigue. Ideal para integrar IA específica sin tocar el núcleo. *Ver cap 08.*

**SOA** — *Service-Oriented Architecture.* Arquitectura orientada a servicios; integración entre aplicaciones distintas (CRM↔ERP). Predecesor conceptual de microservicios. *Ver cap 08.*

**Cloud-Native / Serverless** — Aplicaciones diseñadas para correr en la nube, aprovechando elasticidad, contenedores y funciones serverless. *Ver cap 08.*

**On-Premise** — Infraestructura propia, en las instalaciones de la organización. Control total, alta inversión inicial. *Ver cap 08.*

**SaaS** — *Software as a Service.* Software listo, accesible vía navegador, pagás suscripción (Gmail, Salesforce). *Ver cap 08.*

**PaaS** — *Platform as a Service.* Plataformas para que desarrolladores construyan apps sin gestionar infraestructura (Heroku, App Engine). *Ver cap 08.*

**IaaS** — *Infrastructure as a Service.* Recursos básicos (cómputo, storage, red) alquilados (AWS EC2, Azure VMs). *Ver cap 08.*

**Híbrida** — Combinación de on-premise + cloud (y a veces edge): seguridad para datos críticos + agilidad para cargas variables. *Ver cap 08.*

**Arquitectura híbrida 3 niveles** (Deloitte 2026) — Cloud para elasticidad + On-premise para consistencia (alto volumen previsible) + Edge para inmediatez (latencia <10ms). *Ver cap 11.*

---

## 9. Automatización

> Capítulo principal: `09-automatizacion-integral.md`.

**Automatización Integral** — Implementación de tecnologías para automatizar **completamente** los flujos de trabajo, integrando sistemas y áreas. Eliminación de tareas manuales repetitivas, reducción de errores, ejecución continua. *Ver cap 09.*

**Automatización tradicional (basada en reglas)** — "Si ocurre X, entonces hacé Y". Rígida y determinista. Alta eficiencia en tareas predecibles, se rompe con la ambigüedad. *Ver cap 09.*

**Automatización IA-Driven** — "Aprende de los datos y decide el mejor camino." Adaptativa y probabilística. Maneja NLP, imágenes, anomalías. *Ver cap 09.*

**Automatización Agéntica** — Implementación de Agentes de IA que perciben, deciden y ejecutan. Evolución actual: **RPA tradicional + IA = automatización inteligente → agéntica**. *Ver cap 09.*

**RPA** — *Robotic Process Automation.* Bots de software que imitan acciones humanas en interfaces (clicks, copy-paste, formularios). Reglas duras, sin aprendizaje. *Ver cap 09.*

**n8n** — Plataforma de automatización fair-code, **self-hosted**, ideal para desarrolladores que buscan control total, flexibilidad y menores costos a gran escala. Comunidad muy fuerte para agentes IA. *Ver cap 09.*

**Zapier** — La plataforma más popular para conectar apps web cotidianas con flujos sencillos ("Zaps"). Bajo umbral de entrada, costoso a gran escala. *Ver cap 09.*

**Make** — Plataforma con interfaz visual más avanzada y flexible que Zapier, para flujos complejos. *Ver cap 09.*

**Power Automate** — Plataforma de automatización para el ecosistema Microsoft. *Ver cap 09.*

**AIaaS** — *AI as a Service.* Consumir capacidades de IA como API (Google, AWS, Azure, OpenAI). Sin hardware ni licencias propias. Riesgos: vendor lock-in, soberanía de datos, caja negra. *Ver cap 09.*

**Build / Buy / Partner / AIaaS** — Framework cátedra de decisión: **construir** internamente (core del negocio), **alquilar** (AIaaS para commodity), **delegar** a consultoría (integración compleja), comprar **IA específica vertical** (cumplimiento/precisión sectorial). *Ver cap 09 + cap 16.*

**Adaptarse al enlatado** — *Anti-patrón 1 cátedra.* Cambiar tus procesos para que encajen con el software, incluso los que eran tu diferencial competitivo. Resultado: perdés identidad. *Ver cap 09 + cap 16.*

**Herencia técnica** — *Anti-patrón 2 cátedra.* "No se puede porque el sistema no lo permite". La estrategia limitada por las paredes del Legacy. *Ver cap 09 + cap 16.*

**Automatización de procesos ineficientes** — *Anti-patrón 3 cátedra.* Acelerar con IA un proceso que ya estaba mal diseñado. "Estamos haciendo más rápido algo que no deberíamos estar haciendo." *Ver cap 09 + cap 16.*

**Triggers / Disparadores** — Eventos que ejecutan acciones automáticamente en plataformas low-code (recibir email, llegar webhook, cambio en base de datos). *Ver cap 09.*

---

## 10. Datos y calidad

> Capítulo principal: `07-datos-fundamentos.md`.

**Cuantitativos** — Datos numéricos, medibles. Encuestas con escala 1-10, transacciones. *Ver cap 07.*

**Cualitativos** — Datos descriptivos, percepciones, atributos. Entrevistas, observación. *Ver cap 07.*

**Triangulación** — Cruzar múltiples fuentes o métodos para validar un hallazgo (ej: encuesta + entrevista + observación). *Ver cap 07.*

**7 criterios de calidad de datos** — Marco cátedra: **Exactitud** (refleja la realidad) / **Completitud** (sin elementos esenciales faltantes) / **Consistencia** (igual en todos los sistemas) / **Validez** (cumple reglas de negocio, tipos, rangos) / **Actualización** (timeliness, refleja info reciente) / **Accesibilidad** (disponible para usuarios autorizados) / **Integridad** (relaciones precisas entre conjuntos). *Ver cap 07 + cap 16.*

**Anonimización** — Eliminar irreversiblemente los identificadores personales de un dataset. *Ver cap 12.*

**Seudonimización** — Reemplazar identificadores con seudónimos reversibles solo con la clave (menos fuerte que anonimización). *Ver cap 12.*

**Inferencia de datos** — Derivar conclusiones a partir de un modelo entrenado. *Ver cap 12.*

**Reidentificación** — Riesgo de volver a identificar a una persona en un dataset anonimizado cruzando con info externa. *Ver cap 12.*

---

## 11. Ética y legal

> Capítulo principal: `12-etica-privacidad-gobernanza.md`.

**Ley 25.326** — Ley argentina de **Protección de Datos Personales** (2000). Vigente pero desactualizada para IA. Sus 7 principios: licitud, consentimiento, finalidad, calidad, seguridad, confidencialidad, minimización. *Ver cap 12.*

**AAIP** — *Agencia de Acceso a la Información Pública.* Autoridad de aplicación de la Ley 25.326 en Argentina. Ente autárquico en Jefatura de Gabinete. *Ver cap 12.*

**Resolución AAIP 161/2023** — Crea el **Programa Nacional de Transparencia y Protección de Datos Personales en el uso de la IA**. Base de la "Guía AAIP" (junio 2024). *Ver cap 12.*

**Convenio 108+** — Versión modernizada del Convenio 108 del Consejo de Europa sobre tratamiento automatizado de datos personales. Argentina lo ratificó por Ley 27.699 (2022). *Ver cap 12.*

**GDPR / RGPD** — *General Data Protection Regulation / Reglamento General de Protección de Datos.* Norma europea (2016/2018). Estándar de oro mundial. Regula tratamiento automatizado, perfilado, decisiones automatizadas, derecho al olvido. *Ver cap 12.*

**EU AI Act** — Reglamento (UE) 2024/1689. Primera norma comprensiva mundial sobre IA. Vigor: 1-ago-2024; plena aplicación: 2-ago-2026 (con etapas). Enfoque basado en riesgo. *Ver cap 12.*

**4 niveles de riesgo (EU AI Act)** — **Inaceptable** (prohibidos: social scoring, manipulación, reconocimiento emocional en trabajo/educación) / **Alto** (estricto: medical devices, credit scoring, infra crítica) / **Limitado** (transparencia: chatbots, deepfakes deben declararse) / **Mínimo** (sin requisitos: spam filters, juegos). *Ver cap 12 + cap 16.*

**4 sesgos AAIP** — Tipología cátedra: **Percepción** (sub o sobre-representación de un grupo en los datos) / **Técnico** (limitaciones de la tecnología) / **Modelado** (omisiones en el diseño del algoritmo) / **Activación** (uso sesgado en el entorno productivo). *Ver cap 12 + cap 16.*

**Ficha de transparencia** — Instrumento AAIP: documento público con 3 secciones (caracterización general / tecnológica / interacción ciudadana) que describe un sistema de IA. *Ver cap 12.*

**HITL** — *Human In The Loop.* Diseño donde un humano valida decisiones críticas del sistema IA antes de que se ejecuten. *Ver cap 12.*

**Habeas data** — Acción judicial (Art. 43 CN argentina) para acceder, rectificar o eliminar datos personales propios en bases públicas o privadas. *Ver cap 12.*

**Privacy by design** — *Privacidad por diseño.* Incorporar la protección de datos desde la concepción del sistema, no como capa posterior. Principio Ann Cavoukian, recogido por GDPR y AAIP. *Ver cap 12.*

**Responsabilidad proactiva y demostrada** — *Accountability.* No alcanza con cumplir: hay que poder demostrar el cumplimiento con documentación, evaluaciones y trazabilidad. *Ver cap 12.*

**EIPD** — *Evaluación de Impacto en Protección de Datos.* Matriz de riesgo (probabilidad × impacto) que se hace desde el diseño en sistemas de alto riesgo. *Ver cap 12.*

**Discriminación algorítmica** — Decisión automatizada que perjudica injustamente a un grupo protegido (género, etnia, edad, discapacidad). ILEGAL en Argentina aun sin intencionalidad (Art. 16 CN + Ley 23.592). *Ver cap 12.*

**Caja negra** — *Black box.* Sistema cuyos mecanismos internos no son visibles ni explicables. Inaceptable cuando afecta derechos: la persona debe poder entender por qué fue clasificada/rechazada. *Ver cap 12.*

**Semáforo de decisiones (PyMEs)** — Herramienta operativa cátedra: ROJO (prohibido: subir balances a ChatGPT público, reconocimiento facial para asistencia) / AMARILLO (con safeguards: IA filtra CVs pero humano revisa descartados) / VERDE (autorizado). *Ver cap 12 + cap 16.*

**3 pilares ética PyMEs** — Framework cátedra: **Privacidad = Blindaje** (proteger datos = proteger el secreto del negocio) / **Ética = Calidad de Marca** (justicia es rentable) / **Transparencia = Confianza** (poder explicar tu IA es lo que hace que te elijan). *Ver cap 12 + cap 16.*

---

## 12. Tendencias

> Capítulo principal: `11-tendencias-2026.md`.

**IA Física** — Convergencia IA + robótica: robots que ven, entienden lenguaje y actúan en el mundo físico (humanoides bípedos, brazos bimanuales). Tendencia #1 Deloitte 2026. *Ver cap 11.*

**Modelos VLA** — *Vision-Language-Action.* Modelos multimodales que combinan visión, comprensión de lenguaje y control motor. Base de la IA física. *Ver cap 11.*

**IA Agente (escala)** — Predicciones Gartner: 15% de decisiones diarias serán autónomas vía agentes para 2028; 33% de apps empresariales incluirán agentes para 2028 (vs <1% actual). *Ver cap 11.*

**Economía de la inferencia** — Inversión de la economía cloud: el costo por inferencia bajó 280x en 2 años, pero el gasto total se disparó por explosión del uso. On-premise vuelve a ser competitivo cuando cloud supera 60-70% del costo. *Ver cap 11.*

**P&P Organizations** — *People + Performance organizations.* Categoría McKinsey: empresas que mantienen alto rendimiento Y cuidan personas en paralelo. 4,3x más probables de sostener top performance 9/10 años. *Ver cap 14.*

**9 shifts McKinsey** — Marco "State of Organizations 2026": 9 cambios estructurando organizaciones, agrupados en 3 fuerzas tectónicas (tecnológica, económica, fuerza laboral). *Ver cap 14 + cap 16.*

**3 fuerzas tectónicas McKinsey** — (1) Disrupción tecnológica (IA gen + agente); (2) Disrupción económica (geopolítica, regulación, comercio); (3) Cambios en la fuerza laboral (expectativas, demografía, modelos de trabajo). *Ver cap 14.*

**Shadow AI** — *IA en la sombra.* Equipos usando IA no autorizada por la organización. 40% de empleados comparte info sensible con IA sin que el empleador sepa. Riesgo de fuga + compliance. *Ver cap 11.*

**Workslop** — Contenido generado por IA que se ve "completo" pero baja la eficiencia real de procesos (mails inflados, docs largos pero vacíos, código pulcro pero roto). *Ver cap 11.*

**Vibe coding** — Modo de programar dirigiendo a un agente con lenguaje natural y "vibe" más que con detalle técnico. Steve Yegge, Sourcegraph. *Ver cap 11.*

**GEO** — *Generative Engine Optimization.* Sucesor del SEO: optimizar contenido para que aparezca en respuestas de motores generativos (ChatGPT, Perplexity, Gemini). Las plataformas IA ya generan 6.5% del tráfico orgánico. *Ver cap 11.*

**FinOps para agentes** — Disciplina emergente: monitoreo, etiquetado y autoescalado de costos de agentes IA en producción. *Ver cap 11.*

**Red teaming** — Pruebas adversariales sistemáticas para encontrar vulnerabilidades/fallas en modelos antes que las exploten atacantes. *Ver cap 11 + cap 12.*

**Datos sintéticos (riesgo)** — Hacia 2028 el 80% de los datos usados por IA serán sintéticos (vs 20% hoy). Riesgo: **colapso del modelo** si las IAs se entrenan recursivamente con su propio output. *Ver cap 11.*

---

## Notas finales

- Si un término te suena pero no lo encontrás acá, probablemente esté en el **capítulo temático** correspondiente con definición ampliada — usá este glosario como índice de entrada, no como bibliografía.
- Los marcos completos (5V, 4E, ROCEF, ciclo BPM, etapas EU AI Act, etc.) viven con su diagrama en `16-frameworks-cheatsheet.md`.
- Cuando tengas dudas conceptuales antes del examen final o del TPI, mirá `17-preguntas-guia.md`.

---

➡️ Siguiente: [16-frameworks-cheatsheet.md](16-frameworks-cheatsheet.md)
