# 04 — Ingeniería de prompts: cómo se le habla a un LLM para que entregue valor

> **Módulo DIATO**: Módulo 2 — Herramientas de IA generativa para el trabajo
> **Docente**: Mg. María Della Torre
> **Cohorte**: 5 (2026)

---

## 1. Concepto

Un **prompt** es la instrucción —escrita en lenguaje natural— con la que un humano le encarga una tarea a un modelo de lenguaje grande (LLM). La cátedra lo define en su versión más operativa: **"prompt = instrucción"**. La **ingeniería de prompts** es, entonces, el **proceso de diseño de pautas de alta calidad que guíen a los LLM a producir resultados** útiles, reproducibles y alineados a un objetivo organizacional.

Dicho de manera business: si la IA generativa es una nueva interfaz de trabajo, el prompt es la manera en que vos —como profesional, mando medio o líder— le dictás el trabajo a esa interfaz. Y como toda interfaz nueva, **se aprende, se entrena y se mejora**. No es magia ni adivinanza.

Dos quotes de la cátedra resumen el espíritu del capítulo:

> **"SABER CONSTRUIR UN BUEN PROMPT ES LA CLAVE."**

> **"LA ÚLTIMA PALABRA LA TENEMOS QUIENES PREGUNTAMOS."**

La segunda frase es política, no técnica: reafirma que **la agencia, la responsabilidad y la dirección siguen siendo humanas**. La IA ejecuta; vos decidís qué se le pide, qué se acepta como respuesta y qué se descarta.

---

## 2. Intuición

Pensalo así: imaginá que entra a tu oficina un practicante recién recibido, brillante, que leyó toda la biblioteca del mundo pero **nunca trabajó en tu organización**. No conoce a tus clientes, no conoce el tono de tu marca, no sabe a quién le tiene que contestar el mail ni cuáles son las restricciones de la normativa interna. ¿Qué hacés? Le explicás **quién es** dentro del equipo (rol), **qué tiene que hacer** (tarea), **qué tiene que saber del contexto** (background) y **en qué formato querés el entregable**.

Si le decís *"redactame algo sobre RRHH"*, te va a tirar un genérico. Si le decís *"Sos analista senior de RRHH de una pyme metalúrgica de 80 personas en Rosario; tenemos rotación alta en el sector operario; redactame en formato tabla 5 hipótesis de causa y 5 acciones de retención de bajo costo, en tono interno para mandar a Gerencia"*, vas a obtener algo accionable.

La analogía es la que la propia cátedra propone en la Clase 1 (p. 21): **escribir un prompt es como explicarle algo a una persona que no sabe de lo que le estás hablando**. Si no lo entendería un humano nuevo en el tema, tampoco lo va a resolver bien un modelo.

---

## 3. Cuerpo desarrollado

### 3.1 Por qué importa la habilidad de promptear

La cátedra es enfática: **promptear es una habilidad a desarrollar, no una técnica trivial**. Lo plantea de entrada en la Clase 1 (p. 8) con la pregunta *"¿Por qué es importante desarrollar la habilidad de promptear?"*. La respuesta corta: porque la diferencia entre obtener un texto de 200 palabras inservible y un entregable que reemplaza dos horas de trabajo está **íntegramente en cómo formulaste el pedido**.

Esto importa para una transformación organizacional por tres razones:

1. **Velocidad de adopción**: el cuello de botella ya no es el modelo, es la habilidad del usuario. Hoy ChatGPT, Gemini, Claude y Copilot tienen capacidades muy similares para la mayoría de las tareas; lo que separa al equipo productivo del equipo que abandona la herramienta es la calidad de los prompts.
2. **Estandarización**: si en tu organización 30 personas usan IA generativa y cada una arma sus prompts a ojo, vas a tener 30 niveles de calidad y cero trazabilidad. Promptear con método permite **bibliotecar prompts** y reutilizarlos.
3. **Reducción de riesgo**: un prompt mal formulado aumenta la probabilidad de alucinaciones, fugas de información sensible y outputs sesgados. Un prompt bien diseñado contiene gran parte del control de calidad.

### 3.2 Estructura base: PERSONA + TAREA + CONTEXTO + FORMATO

Es la estructura mínima que la cátedra introduce en la Clase 1 (pp. 9–13). Cuatro componentes obligatorios para todo prompt no trivial:

| Componente | Qué define | Verbos / fórmulas disparadoras |
|---|---|---|
| **PERSONA / ROL** | Desde qué expertise/identidad debe responder el modelo | "Actuá como…", "Sos especialista en…", "Te comportás como…", "Ocupá el rol de…" |
| **TAREA / OBJETIVO** | Qué acción concreta tiene que ejecutar | "Hacé…", "Completá…", "Estructurá…", "Listá…", "Compará…", "Redactá…" |
| **CONTEXTO + EJEMPLO** | Información de fondo, restricciones, audiencia | "Tené presente que…", "Es una organización que…", "La respuesta está dirigida a…", "Considerá que ya hicimos…" |
| **FORMATO** | Cómo querés ver el entregable | "En tabla de 5 columnas", "En 3 párrafos", "En formato informe ejecutivo de 1 página", "En bullets numerados" |

**Ejemplo malo (prompt vago, todo lo que NO queremos):**

> *"Hacé un mail para clientes."*

**Ejemplo bueno (mismo objetivo, estructura completa):**

> *"Sos responsable de comunicación externa de una cooperativa de servicios de Santa Fe (PERSONA). Redactá un mail (TAREA) dirigido a clientes residenciales sobre el aumento tarifario del 8% que entra en vigencia el 1° de junio, sabiendo que ya recibieron una comunicación previa hace 30 días y que estamos en un contexto de reclamos por cortes de luz (CONTEXTO). Devolvelo en formato mail con asunto, cuerpo de máximo 180 palabras y firma corporativa, en tono empático pero firme (FORMATO)."*

El segundo prompt **no es un párrafo largo por capricho**: cada cláusula reduce ambigüedad y elimina una variante de respuesta inútil.

### 3.3 Evolución a ROCEF (modelo cátedra)

En la slide 16 de la Clase 1 aparece el modelo **ROCEF**, presentado como una evolución del esquema anterior. La sigla **no se desglosa letra por letra en las slides** (gap declarado en el extract); por el ejemplo de la slide 17 y por la composición previa P+T+C+F, la expansión razonable —y la que adopta este apunte— es:

| Letra | Componente | Diferencia respecto a la base |
|---|---|---|
| **R** | **Rol** | Equivalente a PERSONA |
| **O** | **Objetivo** | Equivalente a TAREA, pero pone el énfasis en *el resultado deseado*, no en *la acción* |
| **C** | **Contexto** | Equivalente, pero la versión avanzada (Clase 2 p. 23) incorpora **archivos adjuntos y referencias documentales** |
| **E** | **Ejemplo** | **Nuevo componente**: incluir un ejemplar del output deseado o de un caso análogo previo |
| **F** | **Formato** | Equivalente |

> **Nota honesta del autor**: la cátedra no documenta la sigla letra por letra en las slides. Si en la cursada la docente confirma una expansión distinta (por ejemplo "Estilo" o "Ejecución" en lugar de "Ejemplo"), corregir este capítulo. La interpretación "Ejemplo" es la que mejor encaja con el ejemplo de la slide 17, con la práctica del Few-Shot Prompting documentada por OpenAI y Anthropic, y con la versión avanzada de la Clase 2 que efectivamente trabaja con un **ejemplo de Reglamento adjunto**.

**Ejemplo cátedra del modelo ROCEF** (Clase 1, p. 17):

> *"Sos responsable de armar el sistema de créditos de una Universidad. Actualmente, te toca actualizar la normativa de la Institución con respecto a la nueva Normativa. Considerando que la situación actual es … y debés llegar a …, armá una lista de los pasos a seguir para iniciar el proceso."*

La **versión avanzada** del mismo caso (Clase 2, p. 23) suma documentos adjuntos:

> *"Sos responsable de armar el sistema de créditos de una Universidad. Actualmente, te toca actualizar la normativa de la Institución con respecto a la nueva Normativa. **Contás con el Reglamento anterior, la Normativa anterior y la vigente.** Adaptá la normativa actual a la vigente y hacelo considerando: -el ejemplo de Reglamento que te comparto -en formato texto. Al finalizar, armá una **tabla comparativa con los principales cambios** de una versión a la otra del documento."*

Acá ya no estamos preguntando: estamos **orquestando un mini-flujo de trabajo** sobre tres documentos con un output estructurado. Eso es ROCEF en producción.

### 3.4 Diagnóstico de fallas frecuentes (autodiagnóstico cátedra)

La Clase 1 (pp. 19–22) dedica un bloque entero a "situaciones frecuentes" con autopreguntas en lugar de prescribir soluciones. Es el bloque más maduro pedagógicamente del módulo, porque te entrena a **detectar tus propios errores** antes de culpar al modelo:

| Queja típica del usuario | Pregunta diagnóstica a hacerse antes de quejarse |
|---|---|
| *"No me respondió lo que necesitaba"* | ¿Tenía claro **yo** qué necesitaba? ¿Pregunté correctamente? ¿Di suficiente información? Si le planteara la misma situación a alguien que no sabe del tema, ¿podría resolverlo (mejor)? |
| *"Di muchas vueltas y lo terminé cerrando"* | ¿Pregunté correctamente? ¿Era una situación que podía resolverla **sin** usar IAG? |
| *"No me entiende"* | (Mismo bloque que la anterior + revisar si el modelo tenía acceso al contexto necesario) |

La regla detrás del diagnóstico es brutal pero útil: **el 80% de los prompts malos son problemas del humano, no del modelo**. Saberlo cambia la manera de iterar.

### 3.5 Buenas prácticas explícitas de la cátedra (Clase 1, p. 23)

1. **Lenguaje natural**: como si le hablases a otra persona. Oraciones completas.
2. **Sé específico/a**: explicá lo que **sí** necesitás y las restricciones.
3. **Sé conciso/a** y evitá la jerga.
4. **Mantené un proceso iterativo** para mejorar el resultado.

A esto suman las guías oficiales de OpenAI y Anthropic dos principios fuertes que conviene incorporar:

5. **Ubicación de los documentos largos** (Anthropic): si vas a pegar un documento extenso como contexto, **ponelo arriba**, antes de la consigna. Mejora la calidad de la respuesta hasta un 30% en tareas de comprensión.
6. **Pinear el modelo en producción** (OpenAI): si vas a estandarizar un prompt en una organización, fijá la versión del modelo (por ejemplo `gpt-4.1-2025-04-14`) para que la respuesta sea reproducible en el tiempo. Una actualización silenciosa del modelo te puede romper la calidad sin que nadie se entere.

### 3.6 Otros frameworks reconocidos (sin fanatismo)

ROCEF no es el único. La industria viene generando variantes hace tres años con la misma columna vertebral. **Conocerlas sirve para detectar que muchas "novedades" son rebrands.**

| Framework | Componentes | Diferencial |
|---|---|---|
| **P+T+C+F** (cátedra base) | Persona, Tarea, Contexto, Formato | Mínimo común |
| **ROCEF** (cátedra avanzada) | Rol, Objetivo, Contexto, Ejemplo, Formato | Suma **Ejemplo** (few-shot) |
| **RTF** | Role, Task, Format | Versión express |
| **CRISPE** | Capacity & Role, Insight, Statement, Personality, Experiment | Suma "Experiment" → pedir variantes del output |
| **CO-STAR** | Context, Objective, Style, Tone, Audience, Response | Separa estilo, tono y audiencia |
| **TAG** | Task, Action, Goal | Ultra-minimalista para developers |
| **RISEN / RACE** | Role-Instruction-Steps-End-Narrowing / Role-Action-Context-Expectation | Énfasis en pasos secuenciales |

**Lectura honesta**: no hay framework superior. Lo dice la literatura reciente (Penlify, Encodedots, Promplify): *framework structure helps modestly, but execution matters more than framework selection*. Cualquier prompt que cubra **Rol + Tarea + Contexto + Formato (+ Ejemplo)** funciona bien.

**Recomendación**: adoptá UNO como estándar interno (por ejemplo ROCEF) para que la organización hable el mismo idioma y los prompts sean comparables y reutilizables.

### 3.7 Iteración: el prompt no se "termina", se versiona

OpenAI y Anthropic coinciden con la cátedra: **promptear es iterativo**. El ciclo: `prompt v1 → respuesta → evaluación → ajuste (rol/contexto/formato/ejemplo) → prompt v2 → …`

En entornos organizacionales esto se traduce en:
- **Versionado**: Anthropic lo dice literal: *treat your prompt like code — use version control or save copies of different attempts with notes on what changed*.
- **Evals**: si un prompt va a producción, medí su calidad sobre un set de casos de prueba (*building evals*, OpenAI).
- **Smallest effective prompt** (Anthropic): cada cláusula debe justificarse. Los prompts inflados gastan tokens y diluyen instrucciones críticas.

---

## 4. Caso real organizacional

### Caso recurrente cátedra: actualización de normativa universitaria

La cátedra usa este caso en Clase 1 y Clase 2 con creciente complejidad. Combina los tres factores típicos de una transformación organizacional: **documentación dispersa** (Reglamento anterior + Normativa anterior + Normativa vigente), **cambio normativo** que obliga a revisar todo, y **output accionable** (tabla comparativa + plan de pasos).

**Prompt cátedra (Clase 2, p. 23):**

> *"Sos responsable de armar el sistema de créditos de una Universidad. Te toca actualizar la normativa respecto a la nueva. Contás con el Reglamento anterior, la Normativa anterior y la vigente. Adaptá la normativa actual a la vigente considerando el ejemplo de Reglamento que te comparto. Al finalizar, armá una tabla comparativa con los principales cambios."*

**Lo que enseña**: adjuntar archivos cambia drásticamente la calidad (el modelo deja de inventar); pedir output estructurado obliga a respuestas concretas; arrancar acotado (5 páginas, no 800) y después escalar.

### Caso externo: Globant y los AI Pods

Globant construyó toda su narrativa 2025 alrededor de **AI Pods** (modelo de suscripción que combina agentes de IA con supervisión humana). En agosto 2025 sumó **Enterprise AI 2.0** con marketplace de +50 agentes certificados. Caso destacado: acuerdo con **YPF** (octubre 2025) para plataforma agéntica de cadena de suministro con 46 agentes.

**Lección**: lo que Globant llama "agentes" son **prompts estructurados y persistentes** sobre un modelo base con acceso a herramientas. Es ROCEF en producción: cada agente es un Rol + Objetivo + Contexto + Ejemplos + Formato versionado.

---

## 5. Aplicación a la transformación organizacional

Promptear bien no es un "skill blando" para mandos medios. Es **el primer cambio cultural concreto** que una organización puede mostrar cuando dice "adoptamos IA". A continuación, cinco workflows típicos donde ROCEF baja al piso:

### 5.1 Mails internos sensibles
**R**: Referente de Comunicación Interna · **O**: Redactá mail anunciando [cambio] · **C**: razón, comunicación previa, sensibilidad política · **E**: tono similar al mail adjunto · **F**: ≤200 palabras + asunto + llamado a Q&A.

### 5.2 Actas y resúmenes de reunión
**R**: Asistente ejecutivo en síntesis · **O**: Acta a partir de transcripción · **C**: tipo de reunión, participantes, objetivo · **F**: (1) Decisiones (2) Próximos pasos con responsable y fecha (3) Pendientes (4) Riesgos. Máx 1 página.

### 5.3 Comparación normativa/regulatoria
Es el caso cátedra. Reutilizable para versiones de contratos, cambios en regulación sectorial (ARCA, BCRA, ENRE, ENACOM) o adaptación de manuales internos a una norma corporativa nueva.

### 5.4 FAQ a partir de tickets
**R**: Analista de soporte/customer success · **O**: 20 FAQs a partir de tickets + documentación adjunta · **C**: audiencia pyme sin perfil técnico · **F**: tabla con pregunta (≤15 palabras), respuesta (≤80), categoría.

### 5.5 Ofertas comerciales / propuestas
**R**: Consultor comercial senior del vertical · **O**: Propuesta para [cliente] · **C**: fase de venta, dolores, competidores, presupuesto · **E**: propuesta análoga ganada · **F**: (1) Diagnóstico (2) Solución (3) Cronograma (4) Inversión (5) Próximos pasos. Máx 4 páginas.

---

## 6. Errores comunes / mitos

| Error / mito | Por qué es problemático | Corrección |
|---|---|---|
| **"Le pregunto y me responde, eso es promptear"** | Confunde uso casual con uso productivo. Sin método, no escala. | Adoptar un framework (ROCEF, CO-STAR, el que sea) y versionar prompts. |
| **"Cuanto más largo el prompt, mejor"** | Prompts inflados diluyen instrucciones críticas, gastan tokens y aumentan latencia. | *Smallest effective prompt* (Anthropic). Cada cláusula debe justificar su existencia. |
| **"Si no respondió bien, el modelo es malo"** | El 80% de las veces el problema es el prompt, no el modelo. | Usar el diagnóstico de la cátedra: ¿sabía yo qué necesitaba?, ¿di suficiente contexto?, ¿especifiqué formato? |
| **"No le doy ejemplos porque la IA debería poder sola"** | Ignora el few-shot, una de las técnicas más efectivas documentadas. | Incluir 1-3 ejemplos del output deseado dispara la calidad significativamente. |
| **"Pego el documento al final del prompt, total el modelo lee todo"** | Documentación de Anthropic: los documentos al final pierden hasta 30% de calidad de comprensión. | **Documentos largos al principio**, instrucciones al final. |
| **"Promptee una vez, lo guardo y listo"** | Los modelos se actualizan, los prompts se desactualizan. | Versionar, evaluar periódicamente, pinear modelo en producción. |
| **"Si pongo 'sé creativo' va a ser creativo"** | Instrucciones vagas → outputs vagos. | Reemplazar por restricciones concretas: "tono informal, máximo 3 párrafos, sin clichés corporativos". |
| **"El modelo me alucinó, es una basura"** | Las alucinaciones también se prompttean. Sin contexto ni grounding, el modelo rellena. | Adjuntar fuentes, pedir citas explícitas, instruir "si no sabés, decí 'no tengo información suficiente'". |
| **"Le mando datos sensibles porque total es privado"** | La mayoría de los planes gratuitos / personales reentrenan con tus inputs. | Revisar T&C, usar planes empresariales, anonimizar datos antes de promptear. |

---

## 7. Checklist

Antes de mandar un prompt a producción (o de adoptarlo como estándar interno), verificá:

- [ ] **Rol / Persona definida** explícitamente.
- [ ] **Objetivo accionable** (no "ayudame con", sino "hacé X").
- [ ] **Contexto suficiente**: organización, audiencia, restricciones, historial relevante.
- [ ] **Ejemplo** del output deseado o un caso análogo (cuando aplique).
- [ ] **Formato** especificado: tipo, extensión, estructura.
- [ ] **Tono** explícito (formal / informal / técnico / divulgativo).
- [ ] **Datos sensibles** revisados y/o anonimizados.
- [ ] **Modelo y versión** registrados.
- [ ] **Caso de prueba** definido para evaluar la calidad de la respuesta.
- [ ] **Versionado** del prompt (v1, v2…) con nota de qué cambió.
- [ ] **Documentos largos** al principio del prompt, instrucciones al final.
- [ ] **Iteración prevista**: ¿qué métrica me dice cuándo dejar de iterar?

---

## 8. Para profundizar

- **OpenAI — Prompt engineering** (guía oficial): patrones de prompts, *snapshots* de modelo para producción, principios de instrucciones claras. Buscar en *developers.openai.com/api/docs/guides/prompt-engineering* y en el Help Center *help.openai.com*.
- **Anthropic — Prompting best practices** (guía oficial de Claude): foco en estructura XML, posición de documentos en el prompt, *prompt improver*. *platform.claude.com/docs/en/build-with-claude/prompt-engineering/overview*.
- **Anthropic — Interactive Prompt Engineering Tutorial** (gratis, en GitHub): 9 capítulos con ejercicios prácticos. Repositorio público *anthropics/prompt-eng-interactive-tutorial*.
- **Phoenix, J. & Taylor, M. (2024). *Prompt Engineering for Generative AI: Future-Proof Inputs for Reliable AI Outputs*. O'Reilly Media.** 422 páginas. Cubre LLMs y modelos de difusión, técnicas de NLP aplicadas, generación de texto/imagen/código. ISBN 9781098153434. Es la referencia más completa publicada hasta hoy en formato libro.
- **GPT-5 / GPT-4.1 Prompting Guide** (OpenAI Cookbook): patrones específicos para los modelos más recientes. *cookbook.openai.com/examples/gpt-5/gpt-5_prompting_guide*.
- **Lakera — The Ultimate Guide to Prompt Engineering** (2026): compendio actualizado con foco también en seguridad de prompts (prompt injection).
- **Encodedots / Promplify — Comparativas de frameworks**: si querés ver lado a lado CRISPE, CO-STAR, RISEN, RACE, etc.

---

## Próximo paso

En el próximo capítulo (**05 — IA Generativa y modelo 4E**) vamos a poner el prompt en contexto: qué es exactamente la IAG, cuáles son sus alertas conocidas (fuente, sesgo, alucinación) y cómo se adopta una herramienta de IAG en una organización siguiendo el modelo **Explorar → Evaluar → Ejecutar → Escalar** de la cátedra.

---

## Referencias

### Cátedra
- Della Torre, M. (2026). *Módulo 2 — Herramientas de IA generativa para el trabajo*. Clase 1 (slides 1–36). DIATO, UNRaf, Cohorte 5.

### Externas (consultadas para este capítulo)
- **OpenAI** — *Prompt engineering* (guía oficial API) y *Prompt engineering best practices for ChatGPT* (Help Center).
- **OpenAI Cookbook** — *GPT-5 Prompting Guide* y *GPT-4.1 Prompting Guide*.
- **Anthropic** — *Prompting best practices* (Claude API Docs, platform.claude.com).
- **Anthropic** — *Interactive Prompt Engineering Tutorial* (repositorio público en GitHub).
- **Phoenix, J. & Taylor, M.** (2024). *Prompt Engineering for Generative AI*. O'Reilly Media. ISBN 9781098153434.
- **Lakera** — *The Ultimate Guide to Prompt Engineering* (2026).
- **Penlify** — *CRISPE and Other Prompt Frameworks: Which Actually Work With Claude and GPT-4o*.
- **Encodedots** — *Prompt Frameworks 2025 Explained: What Works and Why*.
- **Promplify** — *Prompt Engineering Frameworks Compared: CO-STAR, RISEN, RACE, CREATE, APE, and STOKE*.
- **Bloomberg Línea / Investing.com / La Nación** — Cobertura del caso **Globant AI Pods + Enterprise AI 2.0 + YPF** (2025).

> **Próximo capítulo**: [05-ia-generativa-y-modelo-4e.md](./05-ia-generativa-y-modelo-4e.md)
