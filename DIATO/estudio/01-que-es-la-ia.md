# 01 — ¿Qué es la Inteligencia Artificial?

> Si arrancás un proyecto de IA sin haberte sentado a definir qué es IA, vas a confundir Excel con un modelo, una macro con un agente y un chatbot de reglas con ChatGPT. Este capítulo te da las definiciones, la historia y los tipos. Sin esto, el resto del curso es ruido.

---

## 1. Concepto

No hay **una** definición de Inteligencia Artificial. Hay varias, y cada una tiene sesgo. La cátedra te propone tres definiciones canónicas; te las dejo, y le sumo dos más que vas a ver en cualquier paper o discusión seria.

### Definición 1 — John McCarthy (el padre fundador)

> "Es la ciencia y la ingeniería para fabricar máquinas inteligentes, especialmente programas informáticos inteligentes. Está relacionada con la tarea similar de usar computadoras para comprender la inteligencia humana."
>
> — **John McCarthy**, matemático estadounidense, **acuñó el término "Artificial Intelligence" en 1955** y co-organizó la histórica **Conferencia de Dartmouth de 1956**, considerada el "Big Bang" de la IA como disciplina.

### Definición 2 — Real Academia Española (RAE)

> "Disciplina científica que se ocupa de crear programas informáticos que ejecutan operaciones comparables a las que realiza la mente humana, como el aprendizaje o el razonamiento."

### Definición 3 — UNESCO / COMEST 2019 (la más completa)

> "La inteligencia artificial es un campo que implica máquinas (con algoritmos) capaces de imitar determinadas funcionalidades de la inteligencia humana, incluidas características como la percepción, el aprendizaje, el razonamiento, la resolución de problemas, la interacción lingüística e incluso la producción de trabajos creativos."

### Definición 4 (bonus) — Russell & Norvig, libro de referencia académica

Stuart Russell y Peter Norvig, en su libro **"Artificial Intelligence: A Modern Approach"** (referencia académica desde 1995, 4ª edición vigente), proponen un **mapa de 2x2** que cruza dos ejes:

|  | **Pensar** (cognición interna) | **Actuar** (comportamiento observable) |
|---|---|---|
| **Como humano** | Sistemas que **piensan como humanos** (ciencia cognitiva) | Sistemas que **actúan como humanos** (Test de Turing) |
| **Racionalmente** | Sistemas que **piensan racionalmente** (lógica formal) | Sistemas que **actúan racionalmente** (agentes racionales) |

Russell & Norvig **prefieren la cuarta** ("actuar racionalmente"): un agente racional es aquel que actúa para alcanzar el mejor resultado esperado, dadas las creencias que tiene. Esta definición es la que mejor encaja con la IA business: **no nos importa si la máquina "piensa de verdad", nos importa si toma buenas decisiones**.

---

## 2. Intuición

Pensá en la IA como **un colega contratado con un perfil muy raro**:

- Tiene la **memoria de Internet entera** (lee millones de documentos en segundos).
- No se cansa, no duerme, no se enoja.
- **No tiene sentido común**: si le pedís algo absurdo, lo intenta sin chistar.
- Aprende de patrones, no de comprensión profunda. Si los patrones son malos, sus respuestas son malas.
- Necesita un **director** (vos) que le diga **qué hacer y con qué límites**.

Tony Stark y Jarvis. Vos dirigís, ella ejecuta. La IA **no es magia ni va a "reemplazarte"**: te multiplica si la sabés dirigir, te avergüenza si la usás sin entender.

---

## 3. Cuerpo desarrollado

### 3.1. Breve historia: del Test de Turing a ChatGPT

Una línea de tiempo mínima que tenés que poder contar de memoria:

| Año | Hito | Por qué importa |
|---|---|---|
| **1939** | Alan Turing diseña la máquina **Bombe** para descifrar Enigma | Precursora de la computadora programable digital |
| **1950** | Turing publica **"Computing Machinery and Intelligence"** en la revista *Mind* | Plantea la pregunta fundacional: "¿Pueden pensar las máquinas?" |
| **1955-56** | McCarthy acuña **"Artificial Intelligence"** y organiza la **Conferencia de Dartmouth** con Minsky, Rochester y Shannon | Nace la IA como disciplina formal |
| **1960s-70s** | Sistemas expertos, IA simbólica | Auge inicial, "Primavera de la IA" |
| **1970s-80s** | "Inviernos de la IA" | Las promesas no se cumplen, el financiamiento se corta |
| **1997** | Deep Blue (IBM) vence a Kasparov en ajedrez | IA gana a campeón mundial en juego complejo |
| **2012** | AlexNet revoluciona la visión por computadora | Inicio del boom del **Deep Learning** (gracias a las GPUs) |
| **2016** | AlphaGo vence a Lee Sedol en Go | El "santo grial" de los juegos cae |
| **2018** | Google Duplex llama por teléfono para reservar peluquería frente a 7.000 personas | Demostración pública del Test de Turing moderno |
| **2022** | **ChatGPT** se lanza al público | La IA generativa entra al consumo masivo. Cambia todo. |
| **2024-26** | Auge de la **IA agéntica** | De "chatbots que responden" a "agentes que actúan" |

### 3.2. El Test de Turing — la pregunta que abrió todo

En **1950**, Alan Turing publicó en *Mind* el artículo "**Computing Machinery and Intelligence**" donde planteó:

> "Propongo que se considere la siguiente pregunta: ¿Pueden pensar las máquinas?"

Como la pregunta es filosóficamente intratable, Turing propuso reemplazarla por un **juego de imitación**: si un juez humano, conversando a través de un teclado, **no puede distinguir** si está hablando con otra persona o con una máquina, entonces a efectos prácticos esa máquina **es inteligente**.

**Definición operacional del Test de Turing** (versión cátedra):
> Se considera que el proyecto de IA es exitoso siempre y cuando **más del 30% de los jueces**, luego de 5 minutos de conversación, concluyan que la computadora es humana.

#### El Premio Loebner
Competencia anual de chatbots vs jueces humanos basada en el Test de Turing. Premio dorado para la primera máquina que pase el test "perfectamente". Nunca se otorgó.

#### Google Duplex (2018)
En la conferencia Google I/O 2018, Sundar Pichai mostró en vivo cómo Google Duplex llamó por teléfono a una peluquería para reservar un turno. La recepcionista **nunca se dio cuenta** de que estaba hablando con una IA. Aplausos y, también, polémica ética enorme.

#### El CAPTCHA — Turing invertido
> "Completely Automated Public Turing test to tell Computers and Humans Apart"

Cuando seleccionás todos los semáforos antes de entrar a una página web, sos **vos quien le tiene que demostrar a la máquina que sos humano**. El test de Turing dado vuelta.

### 3.3. Los Agentes: el corazón conceptual de la IA

Un **agente** es la unidad básica de análisis de cualquier sistema de IA.

> **Definición de la cátedra (Moscardo):** "Un agente de IA se define como una ENTIDAD (software o hardware) que percibe su entorno mediante sensores, procesa esa información y actúa en consecuencia a través de actuadores o salidas, con el objetivo de cumplir una meta o resolver un problema de manera autónoma o semiautónoma."

#### Los 6 componentes de cualquier agente

| Componente | Qué hace | Ejemplo físico (robot) | Ejemplo software (chatbot) |
|---|---|---|---|
| **Entorno (Environment)** | Contexto donde opera | Fábrica | Sistema empresarial |
| **Percepción (Sensors)** | Capta información | Cámaras, sensores de temperatura | Lectura de base de datos, mensajes de WhatsApp |
| **Acción (Actuators)** | Influye sobre el entorno | Brazo mecánico | Envío de respuesta, ejecución de comando |
| **Objetivos (Goals)** | Define qué quiere lograr | Ensamblar pieza X | Responder consulta del cliente |
| **Algoritmo de decisión** | Cómo elige qué hacer | Reglas de control + ML | Modelo de lenguaje + reglas de negocio |
| **Adaptación** (transversal) | Aprende y mejora con la experiencia | Optimización del movimiento | Refinamiento de respuestas según feedback |

#### Los 5 tipos de agentes (la clasificación de Moscardo)

Esta tabla es **la columna vertebral del módulo**. Tenela siempre a mano.

| # | Tipo de agente | Cómo funciona | Ejemplo cotidiano | Ejemplo empresarial |
|---|---|---|---|---|
| **1** | **Reactivos simples** | Responden a estímulos sin memoria. "Si X, entonces Y" | Termostato, robot aspiradora básico | Macro de Excel, semáforo |
| **2** | **Basados en modelo (con memoria)** | Guardan info histórica, mantienen modelo interno del entorno | Google Maps con tráfico histórico | Sistema de inventario con stock predictivo |
| **3** | **Basados en objetivos** | Evalúan alternativas para alcanzar una meta | Vehículo autónomo, GPS que recalcula ruta | Robot de logística entregando paquete |
| **4** | **Basados en utilidad** | Comparan estados con función matemática de utilidad/preferencia | Sistema de inversión que optimiza rentabilidad/riesgo | Diagnóstico médico que elige tratamiento más seguro y eficiente |
| **5** | **Con aprendizaje** | Incorporan ML/DL para mejorar con la experiencia | **ChatGPT**, asistente conversacional | Sistemas de recomendación de Mercado Libre, motor de Netflix |

A medida que **subís en la lista, sube la autonomía** y baja la dependencia de programación explícita. Los reactivos simples necesitan reglas escritas a mano; los agentes con aprendizaje **construyen sus propias reglas** desde los datos.

### 3.4. IA Generativa vs IA Agéntica (la confusión del momento)

A partir de 2022 (ChatGPT) y 2024 (Claude, Gemini con tool-use), la conversación pública confunde estos dos términos. Sentate, respirá, y memorizá la diferencia:

| Dimensión | **IA Generativa** | **IA Agéntica** |
|---|---|---|
| Qué hace | **Genera contenido** (texto, imagen, código) | **Ejecuta acciones** en sistemas reales |
| Interacción | Pregunta → respuesta | Objetivo → planificación → acciones → resultado |
| Autonomía | Baja (necesita prompt) | Alta (toma decisiones intermedias) |
| Acceso a sistemas | No (solo conversa) | Sí (APIs, bases de datos, archivos, web) |
| Ejemplo | ChatGPT te explica cómo reservar un vuelo | El agente entra a la web de la aerolínea, compara precios, reserva, paga y te manda el confirmation por mail |
| Riesgo principal | Alucinaciones, sesgos | Acciones no deseadas, escalamiento de permisos |

> **Cita clave (Moscardo, PDF principal):**
> "La IA agéntica no solo 'piensa' o 'responde': también puede actuar, coordinar pasos y ejecutar trabajo real en sistemas digitales y físicos, pero necesita control humano y una implementación muy cuidada."

#### ¿Por qué importa la IA Agéntica en una empresa?

Aplicaciones que la cátedra destaca:

- **Banca / Finanzas**: detección de fraude en tiempo real, asesoramiento personalizado, automatización de aprobación de préstamos, compliance.
- **Retail**: compras personalizadas, atención al cliente 24/7, planificación comercial.
- **Logística**: monitoreo de depósito, detención de cintas ante problemas detectados por visión artificial.

Beneficios:
- Disponibilidad **24/7** sin fatiga humana.
- Reducción de **costos de transacción** (tiempo de buscar, comparar, comunicar, cerrar acuerdos).
- Mejores decisiones en contextos con **asimetrías informativas** (seguros, autos usados, inversiones, admisiones universitarias).

Riesgos:
- **Confiabilidad irregular**: el agente puede actuar con info errónea.
- **Ciberseguridad**: necesita permisos sobre múltiples sistemas → superficie de ataque enorme.
- **Responsabilidad legal**: ¿quién responde si el agente comete un error?

### 3.5. IA Débil vs IA General vs Singularidad

| Tipo | Estado actual | Qué es | Ejemplos |
|---|---|---|---|
| **IA Débil (Narrow AI)** | **La única que existe hoy (2026)** | Resuelve tareas específicas, por más impresionantes que sean | ChatGPT, AlphaGo, Mercado Libre fraude, Tesla Autopilot |
| **IA General (AGI)** | **Hipotética** | Igualaría o excedería las capacidades humanas en TODAS las tareas | No existe. Se debate si llegará en 5, 50 o 500 años |
| **Superinteligencia / Singularidad** | **Especulación** | IA que se auto-mejora indefinidamente, quedando fuera del control humano | Propuesta por **Ray Kurzweil**. Tema de Black Mirror y debate filosófico |

> "La singularidad tecnológica implica que un conjunto de algoritmos, redes informáticas o robots, puedan ser capaces de diseñar o producir computadoras o robots mejores que los ya existentes." — Moscardo

Aviso: la palabra **AGI** (Artificial General Intelligence) se usa muy ligeramente en marketing de empresas como OpenAI, Anthropic y Google. **Hoy NO existe AGI** y nadie sabe cuándo va a existir, si es que llega.

### 3.6. Relación IA / ML / DL / IAG / Agéntica (el diagrama mental)

```
┌─────────────────────────────────────────────────────────┐
│  INTELIGENCIA ARTIFICIAL (IA) — el paraguas              │
│                                                          │
│   ┌──────────────────────────────────────────────┐      │
│   │  MACHINE LEARNING (ML) — aprende de datos    │      │
│   │                                              │      │
│   │    ┌──────────────────────────────────┐     │      │
│   │    │  DEEP LEARNING (DL) — redes      │     │      │
│   │    │  neuronales profundas             │     │      │
│   │    │                                   │     │      │
│   │    │   ┌─────────────────────────┐    │     │      │
│   │    │   │  IA GENERATIVA (IAG)    │    │     │      │
│   │    │   │  LLMs, difusión, etc.   │    │     │      │
│   │    │   └─────────────────────────┘    │     │      │
│   │    └──────────────────────────────────┘     │      │
│   └──────────────────────────────────────────────┘      │
│                                                          │
│   IA AGÉNTICA = IAG + tool use + planificación +        │
│                  acción autónoma en sistemas reales      │
└─────────────────────────────────────────────────────────┘
```

- **IA** = paraguas que incluye sistemas expertos, búsqueda heurística, ML, etc.
- **ML** = subconjunto que **aprende de datos** en lugar de seguir reglas escritas.
- **DL** = subconjunto de ML que usa **redes neuronales con muchas capas**.
- **IAG** = aplicación de DL para **generar contenido nuevo**.
- **Agéntica** = capa **encima** de la IAG que le suma capacidad de **actuar**.

---

## 4. Caso real organizacional

### Mercado Libre — IA aplicada en todas las capas (Argentina/LATAM)

**Sector**: e-commerce / fintech / logística.
**Tamaño**: empresa más valiosa de Latinoamérica.
**Inicio del uso intensivo de IA**: **2015**.

**Aplicaciones concretas**:

| Aplicación | Tipo de IA | Métrica/impacto |
|---|---|---|
| **Recomendaciones personalizadas** | ML clásico (sistemas de recomendación) basado en consumo, contexto y horario | Mayor conversión, mejor experiencia |
| **Prevención de fraude** | ML (detección de anomalías) | Analiza **+5.000 variables en menos de 1 segundo** por transacción |
| **Análisis de sentimiento** | NLP + ML | Detecta productos problemáticos analizando millones de reseñas antes de que escalen |
| **Mercado Crédito** | ML + análisis predictivo | Otorga crédito a personas que no acceden al sistema bancario tradicional |
| **Visión por computadora** | Deep Learning (CNN) | Procesamiento de imágenes de publicaciones, detección de productos prohibidos |

**Equipos**: pasaron de **50 personas en 2015 a más de 1.000 personas usando IA** en la empresa. Más de **50 soluciones propias de IA** en desarrollo.

> Mercado Libre es el ejemplo más claro de que la IA **no es un proyecto**: es una **capacidad organizacional transversal**. Permea producto, riesgo, logística, marketing, finanzas y atención al cliente.

### Otros casos argentinos rápidos

| Empresa | Sector | Uso destacado |
|---|---|---|
| **YPF / Y-TEC** | Energía / Oil & Gas | IA + Starlink para perforación remota desde Buenos Aires en Vaca Muerta. Reducción de tiempos del 15-30% |
| **Banco Galicia** | Banca | Chatbot **Gala** (más de 5M de consultas por WhatsApp). Red BioCatch Trust Argentina para detección de fraude en tiempo real entre bancos y fintech |
| **Globant** | Servicios IT | "GeneXus + Stark Studio" para integración de IA en software empresarial |
| **Poder Judicial de Santa Fe** | Sector público | Uso pionero de IAG para redacción de sentencias de baja complejidad, con **Supervisión Humana Obligatoria** |

---

## 5. Aplicación a la transformación organizacional

Cuando llevás IA a una empresa, **no estás vendiendo tecnología**: estás vendiendo **una nueva forma de tomar decisiones y ejecutar procesos**. Por eso este capítulo te importa más como **business analyst** que como técnico.

### Las 4 preguntas que debés responder antes de proponer IA

1. **¿Qué tipo de agente necesitamos?** (reactivo, basado en modelo, en objetivos, en utilidad, con aprendizaje)
   - Si tu problema es "cuando llega un mail con X palabra, asignar a Sector Y" → **reactivo simple**, no necesitás IA cara.
   - Si tu problema es "predecir qué clientes van a abandonar el servicio" → **con aprendizaje**.

2. **¿IA generativa, IA agéntica o ML clásico?**
   - "Redactar informes desde plantillas" → **IAG**.
   - "Bot que reserva turnos y completa formularios en tu nombre" → **Agéntica**.
   - "Predecir demanda de inventario el próximo trimestre" → **ML clásico**.

3. **¿Qué riesgos asume la organización?**
   - Alucinaciones (IAG).
   - Acciones no deseadas (agéntica).
   - Sesgos (cualquier IA con datos históricos).
   - **Responsabilidad legal**: en Argentina, decisiones 100% automatizadas que afecten derechos NO son válidas (Constitución + Ley 25.326).

4. **¿Tenemos a las personas para dirigir esto?**
   - WEF (cita Moscardo): "Para 2025 se habrán perdido 75 millones de empleos por IA, pero se habrán creado 133 millones nuevos". El problema **no es el desempleo, es el reskilling**.

### Argumento de urgencia competitiva

> "La inteligencia artificial liderará el proceso de transformación tecnológica que se inicia con la cuarta revolución industrial. La experiencia de las revoluciones industriales previas sugiere que las firmas y los países que más rápido adoptaron las nuevas tecnologías fueron quienes mejor aprovecharon las oportunidades de crecimiento." — **Moscardo, PDF Módulo 1**

Argentina: el PBI podría pasar de 3% histórico a **4,4% anual** en la próxima década si se adopta IA a escala.

---

## 6. Errores comunes / mitos

| Mito | Realidad |
|---|---|
| "La IA es objetiva y justa" | **Falso**. Su imparcialidad depende de los datos con los que se entrenó. Si los datos están sesgados, la IA amplifica el sesgo |
| "La IA va a reemplazar todos los trabajos" | **Matiz**. Va a transformar tareas, eliminar algunas, crear otras. El verdadero impacto es la **redistribución**, no la desaparición |
| "Cuantos más datos, mejor" | **Falso**. "MÁS no significa MEJOR. La calidad, relevancia y diversidad de los datos son más relevantes que la cantidad." — Moscardo |
| "La IA es muy cara, solo para grandes empresas" | **Cada vez menos cierto**. Herramientas cloud + APIs (OpenAI, Claude, Gemini) democratizaron el acceso. Una PyME puede usar IA por USD 20/mes |
| "ChatGPT es IA" | **Es un subconjunto**. ChatGPT es IA generativa basada en LLMs, que es un subconjunto del Deep Learning, que es un subconjunto del ML, que es un subconjunto de la IA |
| "Si automatizo con IA, no necesito gente" | **Falso peligroso**. Necesitás gente que **dirija** la IA, que **audite** sus decisiones, que **explique** sus resultados al cliente y al regulador |
| "Los modelos están siempre bien" | **Falso**. "Los 'modelos' no son perfectos. Requieren tiempo, ensayos, y fundamentalmente algunos de ellos, requieren cierto entrenamiento para que funcionen de manera correcta." — Moscardo |

---

## 7. Checklist de comprensión

Marcalo antes de pasar al próximo capítulo:

- [ ] Puedo recitar de memoria las 3 definiciones de IA (McCarthy, RAE, UNESCO).
- [ ] Sé en qué año y dónde se acuñó el término "Artificial Intelligence" (1956, Dartmouth).
- [ ] Puedo explicar el Test de Turing en una frase y dar un ejemplo moderno (Google Duplex).
- [ ] Distingo CAPTCHA de Test de Turing y sé que uno es el inverso del otro.
- [ ] Puedo nombrar los **5 tipos de agentes** y dar un ejemplo de cada uno.
- [ ] Explico la diferencia entre **IA generativa** e **IA agéntica** sin googlear.
- [ ] Sé que **hoy solo existe IA débil** y que AGI / singularidad son hipotéticas.
- [ ] Puedo dibujar el diagrama IA ⊃ ML ⊃ DL ⊃ IAG.
- [ ] Tengo al menos un caso argentino concreto en la cabeza (Mercado Libre, YPF, Galicia).
- [ ] Identifico al menos 3 mitos comunes sobre IA y sé refutarlos.

---

## 8. Para profundizar

- **Russell, S. & Norvig, P. (2020)**. *Artificial Intelligence: A Modern Approach* (4ª ed.). Pearson. — El libro de texto académico de referencia. <https://aima.cs.berkeley.edu/>
- **Turing, A. M. (1950)**. *Computing Machinery and Intelligence*. Mind, 59, 433-460. — El paper fundacional, lectura obligatoria. Versión libre: <https://www.cs.ox.ac.uk/activities/ieg/e-library/sources/t_article.pdf>
- **Conferencia de Dartmouth (1956)** — propuesta original de McCarthy: <http://www-formal.stanford.edu/jmc/history/dartmouth/dartmouth.html>
- **UNESCO (2021)**. *Recomendación sobre la Ética de la Inteligencia Artificial*. — Marco internacional al que adhirió Argentina.
- **Kurzweil, R. (2005)**. *The Singularity Is Near*. — Para entender el debate sobre superinteligencia.
- **WEF — The Future of Jobs Report**. <https://www.weforum.org/publications/the-future-of-jobs-report-2025/> — Los números de empleo IA que cita Moscardo.

---

## Próximo paso

→ [02 — Big Data y las 5 V](02-big-data-y-5v.md)

Ya sabés qué es la IA. Pero la IA es **inútil sin datos**. En el próximo capítulo vamos al combustible: qué es Big Data, las 5 V que definen el fenómeno, y cómo se escalonan los niveles de análisis (de "qué pasó" a "qué deberías hacer").

---

## Referencias

- McCarthy, J. — *A Proposal for the Dartmouth Summer Research Project on Artificial Intelligence* (1955). <http://www-formal.stanford.edu/jmc/history/dartmouth/dartmouth.html>
- Dartmouth College — *Artificial Intelligence (AI) Coined at Dartmouth*. <https://home.dartmouth.edu/about/artificial-intelligence-ai-coined-dartmouth>
- Turing, A. M. (1950). *Computing Machinery and Intelligence*. **Mind** 59 (236): 433–460. <https://academic.oup.com/mind/article/LIX/236/433/986238>
- Russell, S. & Norvig, P. — *Artificial Intelligence: A Modern Approach* (4ª ed.). <https://aima.cs.berkeley.edu/>
- UNESCO / COMEST (2019). *Estudio preliminar sobre la ética de la IA*.
- Moscardo, E. — *Módulo 1: Introducción a la IA*, DIATO UNRaf Cohorte 5 (2026).
- Iproup — *Mercado Libre y su uso de IA*. <https://www.iproup.com/innovacion/57677-ia-en-banca-el-caso-galicia-y-como-mejora-experiencia-del-cliente-con-tecnologia-propia>
- Cronista InfoTechnology — *El arma secreta en la que está invirtiendo Mercado Libre*. <https://www.cronista.com/infotechnology/innovacion-it/el-arma-secreta-en-la-que-esta-invirtiendo-mercado-libre-y-pocos-conocen/>
- Ámbito — *YPF utiliza IA y Starlink en Vaca Muerta*. <https://www.ambito.com/energia/ypf-utiliza-inteligencia-artificial-y-starlink-mejorar-la-eficiencia-y-productividad-vaca-muerta-n6092997>
- BioCatch — *Argentinian banks and fintechs launch real-time fraud network*. <https://www.biocatch.com/press-release/argentinia-banks-fintechs-real-time-scams-intel-network>
