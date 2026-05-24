# 17 — Preguntas guía para auto-examen

> Esto NO es un examen oficial. Son **preguntas-disparadoras** organizadas por capítulo del estudio (`01`-`14`). Sirven para tres cosas: (1) repasar antes del TPI/final, (2) detectar dónde tenés huecos conceptuales, (3) entrenar la defensa oral de tus elecciones técnicas.

> **Reglas del juego**:
> - **No hay respuestas acá.** Ese es el punto. Si la querés, andá al capítulo correspondiente y construilá vos.
> - Cada bloque tiene 4 tipos de preguntas, mezclados: **definiciones precisas**, **diferenciaciones**, **aplicaciones prácticas**, **trampas conceptuales y errores comunes**.
> - Si una pregunta te suena rara, no la descartes — esas son las que más enseñan.
> - Si pudieras responder cada una en 60-90 segundos, en voz alta, sin papel y sin googlear: estás en condiciones de defender el TPI.

> **Cómo trabajarlo**: agarrá una sección por sesión de estudio (~30 min), respondé en voz alta o por escrito, y marcá con ✅/⚠️/❌ tu confianza. Lo que quede en ❌ va de vuelta al capítulo.

---

## Capítulo 01 — Introducción a IA, ML y Big Data

1. ¿Cómo define la UNESCO/COMEST 2019 la Inteligencia Artificial? Mencioná al menos 4 capacidades humanas que debe imitar.
2. ¿Qué diferencia hay entre **IA débil**, **IA general** y **singularidad tecnológica**? ¿Cuál existe hoy y cuál es prospectiva?
3. ¿Por qué el **Test de Turing** sigue siendo relevante en 2026? ¿Cuál es el umbral operativo moderno?
4. Explicá los **5 tipos de agentes IA** y dame un ejemplo de cada uno (sin repetir los del PDF).
5. ¿En qué se diferencia un **chatbot tradicional** de un **agente IA agéntico**? Dame un caso de negocio para cada uno.
6. ¿Por qué la **IA agéntica** reduce "costos de transacción"? ¿Qué es un costo de transacción?
7. Definí **Machine Learning** y nombrá las dos familias de problemas que resuelve.
8. Explicá la relación entre **IA → ML → DL** como subconjuntos.
9. ¿Por qué el Deep Learning recién explota en los últimos 10-15 años si los conceptos son de los 80? Dos razones.
10. ¿Qué son las **5 V del Big Data** y por qué la "Veracidad" es la que más proyectos hace fracasar?
11. Diferenciá **datos estructurados, semi-estructurados y no estructurados** con un ejemplo de cada uno.
12. ¿Cuáles son los **4 niveles de la Pirámide Analítica** y qué pregunta responde cada uno? Dame un ejemplo de retail para cada nivel.

---

## Capítulo 02 — Machine Learning: fundamentos

1. ¿Qué diferencia hay entre **aprendizaje supervisado**, **no supervisado**, **semi-supervisado** y **por refuerzo**?
2. ¿En qué se diferencian un problema de **clasificación** de uno de **regresión**? Dame un ejemplo de negocio de cada uno.
3. Explicá el **algoritmo Naive Bayes** y por qué se llama "naive" (inocente).
4. ¿Qué hace **KNN** y por qué se le dice "lazy learner"?
5. Ventaja principal de los **árboles de decisión** sobre las redes neuronales en contextos de negocio donde hay que justificar la decisión.
6. ¿Qué es **Random Forest**? Explicá qué es "bagging" en ese contexto.
7. ¿Para qué sirve un **SVM** y qué es un "kernel"?
8. ¿Cómo funciona **K-Means** y quién decide el valor de K?
9. ¿Qué es **PCA / ACP** y cuándo lo usarías?
10. ¿Qué hace un algoritmo de **asociación** tipo Apriori? Dame el clásico ejemplo del supermercado.
11. ¿Para qué sirve la **detección de anomalías**? Dos casos de negocio.
12. ¿Qué es **validación cruzada** y por qué evita el sobreajuste?
13. **Trampa**: "MÁS datos = MEJOR modelo" — ¿en qué condiciones esto NO es cierto?

---

## Capítulo 03 — Deep Learning y arquitecturas

1. ¿Qué es una **red neuronal artificial** y de qué se inspira biológicamente?
2. Diferencia entre **capa de entrada, capas ocultas y capa de salida**.
3. ¿Cómo "aprende" una red neuronal? Explicá el ajuste de pesos.
4. ¿Por qué necesitan **GPUs** y no alcanzaba con CPUs?
5. ¿Qué hace una **CNN** distinto de una red neuronal "vanilla"? ¿Para qué tipos de datos es ideal?
6. ¿Qué tipo de problemas resuelve mejor el **NLP** con redes neuronales que con métodos clásicos?
7. ¿Qué es un **modelo fundacional** y por qué cambió las reglas del juego?
8. Diferencia conceptual entre **entrenar desde cero** vs **fine-tuning** vs **prompting**.
9. **Trampa**: "Más capas siempre = mejor modelo." ¿Por qué es falso?
10. ¿Qué problemas éticos específicos introduce el Deep Learning frente a algoritmos más simples (caja negra, sesgos amplificados)?

---

## Capítulo 04 — Prompt Engineering e IA Generativa

1. Definí **prompt** y **ingeniería de prompts** con tus propias palabras.
2. ¿Cuáles son los 4 componentes mínimos del framework **PERSONA + TAREA + CONTEXTO + FORMATO**?
3. ¿Qué letra agrega **ROCEF** que el anterior no tenía, y cuándo es crítica esa adición?
4. Explicá las **buenas prácticas** de prompting que propone Della Torre (4 prácticas).
5. Diferenciá **IA** (tradicional) e **IA Generativa**.
6. ¿Cuáles son las **3 alertas de la IA Generativa** según la cátedra? ¿Cuál discute la docente como "mitigada" y por qué eso es cuestionable?
7. ¿Qué es una **alucinación** y qué técnicas la atenúan (no resuelven completamente)?
8. ¿Qué hace el **Modelo 4E** (Explorar/Evaluar/Ejecutar/Escalar)?
9. ¿Qué 3 aristas tiene la **guía de evaluación** del 4E? ¿Por qué los T&C son tan importantes en uso corporativo?
10. ¿Qué diferencia hay entre **Gemini Deep Research**, **Gems** y **Canvas**?
11. **Trampa**: ¿Por qué un prompt de 5 líneas a veces da peor resultado que uno de 50? Y al revés: ¿cuándo un prompt corto gana?
12. ¿Por qué la cátedra insiste en "LA ÚLTIMA PALABRA LA TENEMOS QUIENES PREGUNTAMOS"? ¿Qué problema busca prevenir?

---

## Capítulo 05 — Estrategia Tecnológica

1. ¿Qué diferencia hay entre **estrategia** y **estrategia tecnológica**?
2. Definí **capacidad de absorción** (Cohen & Levinthal). ¿Por qué predice mejor el éxito tecnológico que el presupuesto?
3. ¿Qué significa **ambidestreza** organizacional (O'Reilly & Tushman) y por qué la mayoría de empresas falla en lograrla?
4. Diferenciá **IA como socia de pensamiento** vs **IA intrínseca a la estrategia**.
5. ¿Qué dice el informe Thomson Reuters sobre la "brecha digital de IA" en empresas? Dame al menos 3 estadísticas.
6. ¿Cuáles son los principales **tipos de errores** en uso de IA según la cátedra (5)?
7. ¿Por qué la cátedra dice que "los errores en IA son parte" y no obstáculo? ¿Qué actitud organizacional implica?
8. ¿Qué oportunidades y obstáculos describe el reporte para empresas con vs sin estrategia clara?
9. ¿Cómo se aplica el modelo **ROCEF** específicamente al ejercicio "estrategia + tendencias"?
10. **Trampa**: si la IA "redefine el modelo de negocio", ¿por qué la mayoría de empresas la usa solo para tareas tácticas? ¿Cuál es el cuello de botella?

---

## Capítulo 06 — Gestión de Procesos y BPM

1. Diferenciá **digitalización** y **transformación digital** con un ejemplo de cada uno.
2. Definí **proceso** según la cátedra (entradas, actividades, salidas, valor).
3. ¿Qué significa **gestión basada en procesos** y cómo combate el **efecto silo**?
4. Diferenciá **mapa de procesos** de **jerarquía de procesos**.
5. ¿Qué son **AS IS** y **TO BE**? ¿Por qué saltearse el AS IS es uno de los errores más comunes?
6. ¿Qué diferencia hay entre **BPM** y **BPMN**?
7. Listá las **5 fases del roadmap de transformación digital**.
8. ¿Qué es la **paradoja de la generación IA**? ¿Qué dice de la implementación actual?
9. ¿Qué son **cuellos de botella** y cómo se detectan en un proceso?
10. Listá las herramientas del **toolkit de mejora de procesos** (8 mencionadas) y dame un caso de uso para 4.
11. ¿Qué hace la **minería de procesos** que un workshop con post-its no puede hacer? ¿Por qué Disco Fluxicon es el clásico del aula?
12. **Trampa**: software enlatado vs software a medida — ¿por qué la cátedra advierte contra adaptar tus procesos al enlatado?
13. ¿Qué frentes prioritarios identifica la cátedra para procesos en 2026 (5)?

---

## Capítulo 07 — Datos: fundamentos

1. Explicá la **pirámide DIKW** con un ejemplo del mundo real (idealmente NO el del PDF de salud).
2. Diferenciá **dato**, **información** y **conocimiento**.
3. ¿Qué son los **7 criterios de calidad de datos** y qué pregunta de control va con cada uno?
4. Diferenciá **datos cuantitativos** y **cualitativos** con ejemplos de cada uno.
5. Listá métodos de recolección **cuantitativos** (3) y **cualitativos** (4).
6. ¿Qué es la **triangulación de datos** y para qué se usa?
7. ¿Cuáles son las **3 V originales** del Big Data y qué 2 V se agregaron después (y por qué)?
8. ¿Quién acuñó por primera vez el término Big Data y cuándo?
9. Diferenciá **datos estructurados, semi y no estructurados** con ejemplos sin repetir los del Cap 01.
10. ¿Qué diferencia hay entre **Data Lake** y **Data Warehouse**? ¿Cuándo usarías uno vs el otro?
11. Diferenciá **ETL** y **ELT**. ¿Por qué ELT ganó terreno con Big Data?
12. ¿Qué consideraciones éticas en la recolección de datos identifica la cátedra (4)?

---

## Capítulo 08 — Arquitectura de software / IT

1. Diferenciá **ERP**, **CRM** y **WMS** en términos de qué problema central resuelven.
2. ¿Por qué los sistemas **Legacy** son "la verdad incómoda" de la transformación digital? Mencioná 2 pros y 2 contras.
3. Diferenciá **IoT** y **IIoT**. ¿Por qué los requisitos no son los mismos?
4. ¿Qué es un **requerimiento funcional** y uno **no funcional**? Dame un ejemplo de cada uno para un WMS.
5. ¿Qué información debe contener una **ERS** (Especificación de Requerimientos)?
6. Diferenciá **arquitectura monolítica**, **microservicios**, **SOA** y **Cloud-Native**. ¿Cuándo cada una?
7. Diferenciá **SaaS**, **PaaS** e **IaaS** con un ejemplo concreto de cada una.
8. ¿En qué casos la **arquitectura híbrida** es superior a "todo cloud" o "todo on-prem"?
9. Cuáles son los **3 anti-patrones de arquitectura** que advierte la cátedra y por qué son letales.
10. ¿Cuáles son los **3 pilares** para evitar los anti-patrones?
11. **Trampa**: "Vamos a microservicios porque escala mejor." ¿En qué casos esto es una falsa premisa?
12. ¿Por qué la cátedra dice que "el gobierno de IT debe estar en la mesa del directorio"? ¿Qué pasa si no está?

---

## Capítulo 09 — Automatización integral

1. Diferenciá **automatización tradicional** y **automatización integral** según la cátedra.
2. ¿Cuáles son los **3 pilares** de la automatización integral?
3. ¿Qué significa **"RPA tradicional + IA = Automatización Inteligente → Agéntica"**?
4. Diferenciá **automatización basada en reglas** y **automatización IA-Driven** (5 dimensiones).
5. Describí el **Caso 1 (Cuentas a Pagar)**: cómo lo resolvía RPA y cómo lo resuelve IA-Driven.
6. Describí el **Caso 2 (Atención al Cliente)**: limitación del chatbot tradicional vs ventaja del NLP+sentiment.
7. Describí el **Caso 3 (Mantenimiento)**: alerta preventiva fija vs mantenimiento predictivo con IA.
8. ¿Qué hace una **plataforma low-code** tipo n8n, Zapier o Make? ¿Qué tienen en común?
9. Diferenciá **n8n**, **Zapier**, **Make** y **Power Automate** según fortaleza primaria.
10. Listá los **4 factores de decisión** del framework Build/Buy/Partner.
11. ¿Cuándo SÍ y cuándo NO desarrollar IA internamente?
12. Ventajas y desventajas de **AIaaS** (al menos 3 de cada lado).
13. ¿Qué es **vendor lock-in** y por qué es un riesgo crítico en AIaaS?
14. Explicá la **Arquitectura por Criticidad** (Core / Estándar / Orquestación) y dame ejemplos de cada capa.
15. **Trampa**: "Automaticemos el proceso para hacerlo más rápido." ¿En qué casos es la peor idea?

---

## Capítulo 10 — Control de gestión basado en datos

> *Si tu cohorte está cursando este módulo en paralelo a redactar el TPI, estas preguntas te sirven de check.*

1. Diferenciá **dashboard operativo**, **táctico** y **estratégico**.
2. ¿Qué hace un **KPI** distinto de una métrica cualquiera? Mencioná los criterios de un buen KPI (SMART o similar).
3. ¿Cómo se enlaza la **pirámide analítica** (descriptivo → prescriptivo) con los **niveles de dashboard**?
4. ¿Qué hace un **Sistema de Soporte de Decisión (DSS)** que un BI tradicional no hace?
5. ¿Por qué un buen tablero pierde valor si los datos no cumplen los **7 criterios de calidad**?
6. **Trampa**: "Más métricas = mejor control." ¿Por qué a partir de cierto número se vuelve contraproducente?
7. ¿Cómo cambia el rol del controller con la entrada de IA generativa en análisis ad-hoc?

---

## Capítulo 11 — Tendencias 2026

1. ¿Cuáles son las **5 tendencias** del Deloitte Tech Trends 2026?
2. ¿Qué es la **economía de la inferencia** y por qué pone en duda la lógica "todo a la nube"?
3. ¿Qué umbral señala Deloitte para que **on-premise** sea más rentable que cloud?
4. ¿En qué consiste la **arquitectura híbrida de 3 niveles** (cloud/on-prem/edge)?
5. ¿Qué son **MCP**, **A2A** y **ACP** y para qué problema son la solución?
6. ¿Cuáles son los **4 dominios de riesgo de seguridad** según Deloitte para sistemas IA?
7. ¿Qué es **Shadow AI**, qué porcentaje de empleados la usan y cuál es el riesgo principal?
8. ¿Qué dice Gartner sobre el % de proyectos IA agéntica que se cancelarán para 2027 y por qué?
9. ¿Qué es **GEO** (Generative Engine Optimization) y por qué amenaza al SEO clásico?
10. Mencioná **3 frentes emergentes** de infraestructura que la cátedra resalta (neuromórfica, óptica, cuántica, orbital, etc.).
11. ¿Qué riesgo introduce el uso masivo de **datos sintéticos** para entrenar modelos?
12. **Trampa**: "La IA agéntica reemplazará al humano." ¿Por qué la propia industria recomienda HITL aun para procesos automatizados?

---

## Capítulo 12 — Ética, privacidad y gobernanza

1. Diferenciá **tecnología tradicional** (CRM, ERP clásicos) e **IA** según el criterio cátedra.
2. Enumerá los **3 pilares de Ética y Privacidad para PyMEs** (Privacidad/Ética/Transparencia) y la traducción de cada uno al lenguaje de negocio.
3. ¿Qué cubre la **Ley 25.326** en Argentina y por qué se considera desactualizada para IA?
4. ¿Qué hace la **AAIP** y qué creó la **Resolución 161/2023**?
5. ¿Qué es el **Convenio 108+** y cuándo lo ratificó Argentina?
6. ¿Qué tres aportes principales hace el **EU AI Act** que la Ley 25.326 NO contempla?
7. Enumerá los **4 niveles de riesgo** del EU AI Act con un ejemplo de cada uno.
8. Enumerá los **4 tipos de sesgos** que define la AAIP (origen) y dame un ejemplo de cada uno.
9. ¿Qué exigen los principios de **Privacidad por Diseño** y **por Defecto**?
10. ¿Qué es **HITL (Human In The Loop)** y por qué es no negociable en decisiones que afectan derechos?
11. Explicá la **Arquitectura de un Agente Profesional** (3 capas: Perímetro / Muro / Botón Rojo).
12. Usá el **Semáforo de Decisiones** para resolver: (a) subir balance contable a ChatGPT público, (b) IA filtra CVs.
13. ¿Cuáles son las **4 etapas del ciclo de vida** del sistema IA según la Guía AAIP?
14. ¿Qué 3 secciones tiene una **Ficha de Transparencia** del sistema IA?
15. **Trampa**: "Pero el algoritmo no tiene intención de discriminar." ¿Por qué eso NO es defensa válida en Argentina (Art. 16 CN + Ley 23.592)?
16. ¿Por qué Argentina es **la única nación del G20** que no firmó la Declaración sobre Regulación de IA, y qué implica eso para empresas que quieran exportar?

---

## Capítulo 13 — IA aplicada a casos sectoriales (agro, salud, finanzas, retail, educación)

1. Dame **2 casos de IA aplicada al agro** mencionados por la cátedra y qué tecnología usan (visión artificial, IoT, etc.).
2. ¿Por qué el agro tiene gran potencial de retorno (PIB mundial / países menos adelantados)?
3. ¿Cuáles son los principales casos de **IA en salud**? Dame un dilema ético específico.
4. ¿Qué hace la IA en **finanzas / banca** (al menos 3 casos)?
5. ¿En qué se usa la IA en **retail / e-commerce** (al menos 3 casos)?
6. ¿Cómo se aplica la IA al **deporte**? Dame 2 casos de la cátedra.
7. ¿Qué hace distinto un caso de IA en una **PyME argentina** vs una multinacional? (Recursos, datos, gobernanza.)
8. **Trampa**: aplicar IA al agro sin entender el ciclo agronómico — ¿qué falla típica predice ese gap?

---

## Capítulo 14 — Transformación organizacional y futuro del trabajo

1. ¿Cuáles son las **3 fuerzas tectónicas** que identifica McKinsey "State of Organizations 2026"?
2. Enumerá los **9 shifts** y agrupalos en las 3 fuerzas.
3. ¿Qué % de organizaciones reporta NO estar lista para los cambios según McKinsey?
4. ¿Qué es una organización **AI-enabled** y por qué solo el 14% logra escalarla bien?
5. ¿Qué es una organización **P&P (People + Performance)** y qué resultados sostenidos muestran?
6. ¿Cuánto más probable es que una org P&P se mantenga top performer 9/10 años?
7. ¿Cuáles son las **2 dimensiones de impacto** de la IA en el proceso creativo (estratégica / operativa)?
8. ¿Cuáles son los **6 usos posibles** de IA frente a la competencia?
9. ¿Qué datos del WEF dan urgencia: cuántos empleos se pierden y cuántos se crean al 2025/2026?
10. ¿Qué proyecciones de PBI argentino plantea el material si se adopta IA seriamente?
11. ¿Qué es el **"ES HORA / PENSAR"** del cierre del Módulo 3? Explicá los puntos clave.
12. **Trampa**: "Pero la IA va a destruir empleo." ¿Cómo se responde con evidencia y matiz?
13. ¿Qué dice Allianz / Hitachi sobre las **skills que cambiarán** en 5 años?
14. **Trampa final**: ¿Cuál es el mayor predictor de éxito en transformación con IA según los 3 reportes (Thomson Reuters, Deloitte, McKinsey)?

---

## Mini-set transversal (mezcla todo, defensa TPI)

Estas son las preguntas que te puede hacer un tribunal mezclando capítulos. Si las podés responder sin trabarte, estás a punto caramelo.

1. Tu cliente quiere **automatizar atención al cliente con IA**. ¿Cómo lo encarás aplicando: (a) AS IS / TO BE, (b) BUILD/BUY/PARTNER, (c) 3 capas Agente Profesional, (d) Semáforo de Decisiones?
2. Te traen un dataset con problemas en 4 de los 7 criterios de calidad. ¿Bajo qué condiciones igual seguís adelante, y bajo cuáles parás?
3. Defendé por qué **no** automatizarías un proceso particular, aun habiendo presupuesto. ¿Qué red flags activarías (3 anti-patrones, ROI dudoso, datos malos)?
4. Tu cliente quiere subir información de empleados a ChatGPT público. Construí la respuesta de 2 minutos que combina: Ley 25.326 + Resolución 161/2023 + Semáforo + alternativa concreta.
5. Te piden un agente IA para decidir aprobaciones crediticias. ¿Bajo qué nivel del EU AI Act cae y qué requisitos te impone (aun sin ley argentina equivalente)?
6. ¿Cómo justificás ante un CFO que "ROI 137% en 6 meses" no es una promesa sino una hipótesis? ¿Qué supuestos hace falta explicitar?
7. Defendé la elección de **RAG sobre fine-tuning** para un chatbot interno de soporte técnico de una PyME.
8. Tu equipo discute entre **n8n self-hosted** y **Zapier**. ¿Qué 4 criterios mueven la decisión?
9. Un cliente dice "yo ya tengo IA, uso ChatGPT". ¿Cómo lo llevás conversacionalmente desde IA tactical a una **estrategia tecnológica** real (usá el Modelo 4E + capacidad de absorción)?
10. ¿Cuál es **una sola** decisión irreversible (one-way door) que recomendarías evitar a una PyME que recién arranca con IA, y por qué?

---

## Notas para el redactor / estudiante

- Si te trabaste en 10+ preguntas seguidas, volvé al capítulo, no insistas con más preguntas.
- Si una pregunta te parece mal formulada — felicitaciones, eso significa que ya pasaste el umbral del básico. Re-escribila mejor y mandala al grupo.
- Las **trampas conceptuales** son las preguntas más valiosas: si las resolvés rápido, podés defender el TPI ante cualquier tribunal.
- Para el día previo al TPI: respondé el **mini-set transversal** completo en voz alta, cronometrando. Eso te entrena el músculo de defensa.

---

➡️ Siguiente: [18-bibliografia-recursos.md](18-bibliografia-recursos.md)
