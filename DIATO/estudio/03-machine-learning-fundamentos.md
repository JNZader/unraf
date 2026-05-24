# 03 — Machine Learning: Fundamentos

> Si la IA es el paraguas y el Big Data es el combustible, el **Machine Learning** es el motor. Acá la máquina **aprende patrones de los datos** en lugar de seguir reglas escritas a mano. Este capítulo te enseña los 4 tipos de aprendizaje y los algoritmos que tenés que poder nombrar, **sin una sola fórmula matemática**.

---

## 1. Concepto

### Definición de la cátedra — Alvear

> "El Machine Learning es una rama dentro del campo de la Inteligencia Artificial que proporciona a los sistemas la **capacidad de aprender y mejorar de manera automática, a partir de la experiencia**. Estos sistemas transforman los datos en información, y con esta información pueden tomar decisiones."

### Definición de la cátedra — Moscardo

> "El Machine Learning o Aprendizaje Automático es una rama de la IA que estudia cómo dotar a las máquinas de capacidad de aprendizaje, basándose en **algoritmos capaces de identificar patrones en grandes bases de datos y aprender de ellos**."

### Definición clásica (académica) — Tom Mitchell, Carnegie Mellon, 1997

> "Se dice que un programa computacional aprende de la experiencia E con respecto a alguna clase de tareas T y una medida de rendimiento P, si su rendimiento en las tareas en T, medido por P, **mejora con la experiencia E**."

Tres palabras clave: **Experiencia (E) — Tareas (T) — Performance (P)**. Si no podés definir las tres para tu caso, no es un proyecto de ML, es un proyecto de "queremos hacer ML porque está de moda".

### Definición business (la que vas a usar en el TPI)

> Machine Learning es **dejar de programar cada decisión a mano** y dejar que el sistema **descubra las reglas a partir de los datos**.

La diferencia con la programación clásica:

| Programación tradicional | Machine Learning |
|---|---|
| Vos escribís las reglas | El algoritmo **descubre** las reglas |
| Datos + Reglas → Resultados | Datos + Resultados → **Reglas (modelo)** |
| Si cambia el problema, reescribís las reglas | Si cambian los datos, el modelo se reentrena |
| Determinista y predecible | Estadístico y probabilístico |

---

## 2. Intuición

Imaginate que tenés que **enseñarle a un chico a distinguir un perro de un gato**.

**Opción A (programación clásica)**: le das reglas. "Si tiene orejas paradas y bigotes largos, es gato. Si tiene cola que se mueve mucho y ladra, es perro." Funciona hasta que aparece un Husky con orejas paradas o un Sphinx sin pelo. Las reglas se rompen.

**Opción B (Machine Learning)**: le mostrás **10.000 fotos** etiquetadas como "perro" o "gato". El chico, sin reglas explícitas, **aprende los patrones** que distinguen unos de otros. Cuando le mostrás una foto nueva, puede clasificarla aunque sea de una raza que nunca vio.

Eso es ML: **mostrarle ejemplos y dejar que descubra el patrón**, en lugar de escribir reglas.

### Pipeline conceptual (Moscardo)

```
DATOS HISTÓRICOS  →  APRENDE  →  MODELO DE PREDICCIÓN  →  PREDICE NUEVOS RESULTADOS
   (insumo)         (proceso)        (artefacto)            (con datos nuevos)
```

> "Los datos tienen que ser fidedignos. La precisión de la salida prevista depende, en general, de la cantidad de datos, ya que una gran cantidad ayuda a construir un mejor modelo que presagia la salida con una mayor precisión." — Moscardo

---

## 3. Cuerpo desarrollado

### 3.1. Los 4 tipos de aprendizaje (framework central de Alvear)

| # | Tipo | Pregunta clave | Datos que necesitás | Cuándo usarlo |
|---|---|---|---|---|
| **1** | **Supervisado** | "Te enseño con ejemplos etiquetados" | Datos **con etiqueta** (sabés la respuesta correcta) | Cuando tenés histórico con resultado conocido |
| **2** | **No supervisado** | "Descubrí vos solo patrones" | Datos **sin etiquetas** | Cuando no sabés qué buscar, querés agrupar/segmentar |
| **3** | **Semi-supervisado** | "Te enseño con poquitos ejemplos y mucho dato sin etiquetar" | Mezcla: poco etiquetado + mucho sin etiquetar | Cuando etiquetar es caro pero generar datos no |
| **4** | **Por refuerzo** | "Probá, premio si acertás, castigo si fallás" | Un **entorno** donde el agente actúa y recibe feedback | Cuando hay decisiones secuenciales y el resultado se ve después |

### 3.2. Aprendizaje Supervisado en profundidad

> "El aprendizaje supervisado necesita conjuntos de datos etiquetados, es decir, **le decimos al modelo qué es lo que queremos que aprenda**." — Alvear

Dentro de supervisado hay dos grandes familias:

| Familia | Qué predice | Ejemplo de pregunta |
|---|---|---|
| **Clasificación** | Una **categoría** (etiqueta) | ¿Este mail es spam o no? ¿Este tumor es maligno o benigno? ¿Este cliente va a pagar la cuota? |
| **Regresión** | Un **número** (valor cuantitativo) | ¿Cuántos helados venderé mañana? ¿Cuánto vale esta casa? ¿En cuántos días llegará el envío? |

#### Algoritmos de Clasificación (lo que tenés que poder nombrar)

| Algoritmo | Cómo se entiende (sin matemáticas) | Cuándo usarlo | Caso ejemplo (cátedra) |
|---|---|---|---|
| **Naive Bayes** | "Algoritmo inocente" porque asume que las variables son independientes entre sí. Calcula probabilidades de pertenencia a cada clase | Clasificación rápida de texto, filtros de spam, scoring inicial | Clasificación de cliente riesgoso |
| **KNN (K-Nearest Neighbors)** | "Vecinos más cercanos": clasifica un caso nuevo según las etiquetas de los **K casos más parecidos** ya conocidos | Cuando los datos tienen estructura local clara | Identificar resultados relevantes en búsquedas (NLP) |
| **Árboles de Decisión** | Una serie de preguntas tipo "¿X >5?" que va dividiendo los datos hasta llegar a una decisión | Cuando necesitás **explicabilidad** (mostrar el "por qué" al cliente o al regulador) | "¿Debería salir si está lloviendo? → ¿durará mucho? → ¿cuántos mm caerán?" |
| **Random Forest** | "Bosque de árboles": entrena **muchos árboles** sobre subconjuntos aleatorios de datos y los hace votar. Más robusto que un solo árbol | Cuando querés performance + cierta explicabilidad | Marketing telefónico (predecir comportamiento de clientes), pronóstico de ventas, predecir probabilidad de compra de visitantes web |
| **Support Vector Machine (SVM)** | Traza un **hiperplano óptimo** que separa las clases. Usa **kernels** para manejar datos complejos | Imágenes médicas, texto, datos de alta dimensionalidad | Predicción de cáncer por imágenes de diagnóstico |

#### Algoritmos de Regresión

| Algoritmo | Cómo se entiende | Cuándo usarlo | Caso ejemplo (cátedra) |
|---|---|---|---|
| **Regresión Lineal** | Encuentra la **recta** (o plano, en más dimensiones) que mejor pasa por los datos | Predicciones simples con relación lineal clara | Predecir ventas según temperatura y día (heladería); horas de estudio vs nota del examen |
| **Regresión Logística** | A pesar del nombre, **clasifica** (binario). Predice la probabilidad de pertenecer a una clase | Scoring crediticio, churn, conversión | Predecir si un cliente pagará una deuda |
| **Regresión Polinomial** | Como la lineal pero con curvas | Cuando la relación no es lineal | Demanda no lineal de un producto |
| **Árboles / Random Forest / SVM (en versión regresión)** | Los mismos algoritmos de clasificación, adaptados a predecir números | Casi cualquier predicción cuantitativa | Tiempo de viaje, demanda futura, precio óptimo |

#### Casos típicos de aprendizaje supervisado en negocio

(De Moscardo + Alvear):
- Estimar cuántos productos A se venderán en un tiempo específico.
- Predecir cuánto tiempo permanecerá un empleado en la empresa.
- Estimar cuánto tardará un vehículo en llegar a destino.
- Predecir la probabilidad de que un cliente pague una deuda.
- Predecir si un tumor es maligno o benigno.
- Predecir cuántos clientes vendrán el fin de semana a la cafetería (para definir compras de materia prima).

### 3.3. Aprendizaje No Supervisado

> "Se utiliza cuando los datos **no presentan una estructura clara** y no contamos con información suficiente para clasificarlos. Esta técnica permite que el algoritmo identifique de manera autónoma la estructura de un conjunto de datos." — Alvear

Tres grandes familias:

| Familia | Qué hace | Algoritmos típicos |
|---|---|---|
| **Clustering (agrupamiento)** | Junta casos parecidos en grupos | **K-Means**, DBSCAN, jerárquico |
| **Reducción de dimensionalidad** | Resume muchas variables en pocas, manteniendo la información clave | **ACP (PCA)** |
| **Asociación** | Descubre reglas tipo "quien compra X también compra Y" | **Apriori**, FP-Growth |
| **Detección de anomalías** | Identifica datos raros / outliers | **Z-Score**, **Isolation Forest** |

#### Algoritmos no supervisados clave

| Algoritmo | Cómo se entiende | Casos de uso (cátedra) |
|---|---|---|
| **K-Means** | Agrupa los datos en **K grupos** según similitud | Identificar células cancerosas; agrupar palabras con definiciones similares en motores de búsqueda; detectar valores atípicos en rendimiento académico; localizar minas terrestres en un campo |
| **ACP (Análisis de Componentes Principales)** | Resume un conjunto de **muchas variables** en pocas **"componentes principales"** que conservan la mayor información posible | Cuando tenés 200 variables y necesitás reducirlas a 5 para visualizar / modelar más simple |
| **Apriori** | Busca **patrones de co-ocurrencia** (regla "quien compra pañales también compra cerveza", el famoso *market basket analysis*) | Carrito de compras: ofertas cruzadas, cross-selling |
| **Z-Score** | Mide qué tan "alejado" está un dato del promedio | Detección de outliers en métricas de negocio |
| **Isolation Forest** | "Aísla" los datos raros con menos divisiones de árbol que los normales | Detección de fraude, intrusión en redes, fallas en sensores |

#### Casos típicos de aprendizaje no supervisado en negocio

(De Moscardo + Alvear):
- Supermercado que **segmenta clientes** (grupo de naturales vs grupo de golosinas) para campañas dirigidas.
- **Spotify / YouTube**: observan qué escuchás/mirás y agrupan tu perfil para recomendar similar.
- Agricultor con drones+sensores: **clusters de tipos de suelo** (fértil húmedo → arroz/maíz; seco poco nutritivo → soja; alta acidez → fertilizar).
- **Cesta de compras** del minimarket.
- **Detección de fraude** en transacciones bancarias.
- **Detección de intrusiones** en redes corporativas.

### 3.4. Aprendizaje Semi-Supervisado

> "Enfoque que combina elementos del aprendizaje supervisado y no supervisado. Se utiliza en situaciones donde se dispone de una **pequeña cantidad de datos etiquetados** y una **gran cantidad de datos no etiquetados**." — Alvear

**Cuándo usarlo**: en la práctica, **casi siempre**. Etiquetar datos es caro y lento (alguien tiene que mirar fotos, oír audios, leer textos uno por uno). Tener 1% del dataset etiquetado + 99% sin etiquetar es la realidad de la mayoría de las empresas.

**Ejemplo**: clasificación de fotos de Google Photos. Vos etiquetás 5 caras manualmente; el sistema agrupa miles de fotos con caras similares automáticamente.

### 3.5. Aprendizaje por Refuerzo

> "Método de aprendizaje basado en la retroalimentación, en el que un agente recibe una **recompensa** por cada acción correcta y una **penalización** por cada acción incorrecta." — Moscardo

**Ejemplo cuantitativo de la cátedra — Brazo robótico en línea de ensamblaje**:

| Acción | Resultado |
|---|---|
| Pieza colocada en lugar correcto | **+1 punto** |
| Ensamble más rápido | **+1 punto** |
| Sin errores | **+1 punto** |
| Mala colocación | **-1 punto** |
| Retraso | **-1 punto** |
| Atasco en línea de producción | **-1 punto** |

**KPIs de impacto organizacional**:
- Menos errores → menos desperdicio de materiales.
- Mayor eficiencia → más producción por unidad de tiempo.
- Menos intervención humana → reducción de costos laborales y de supervisión.

**Casos famosos de RL**:
- **AlphaGo / AlphaZero** (DeepMind): aprendió Go, ajedrez y shogi jugando millones de partidas contra sí mismo.
- **Vehículos autónomos**: aprenden a manejar en simulación antes de salir a la calle.
- **Trading algorítmico**: agentes que aprenden estrategias de inversión.
- **Recomendaciones dinámicas**: Netflix/Spotify ajustan en tiempo real según interacción.

### 3.6. Deep Learning — la rama estrella

> "Subcampo del aprendizaje automático que se ocupa de los algoritmos inspirados en la **estructura y función del cerebro** llamados **redes neuronales artificiales**." — Moscardo

#### ¿Por qué Deep Learning explotó recién en los 2010s?

Las redes neuronales se conocían desde los **80s**, pero requerían dos cosas que no existían:

1. **Volúmenes enormes de datos etiquetados** (los vehículos autónomos necesitan **millones de imágenes y miles de horas de video**).
2. **Potencia de cómputo masiva**: las **GPU (Graphics Processing Unit)** con arquitectura paralela hicieron posible entrenar modelos que antes tomaban años en semanas.

#### Arquitectura básica de una red neuronal

```
[ENTRADA]      →     [CAPAS OCULTAS]      →     [SALIDA]
  Datos             (Una o muchas)              Predicción
                  Cada neurona conecta
                con todas las de la
                  capa siguiente
```

> "La red aprende examinando los registros individuales, generando una predicción para cada registro y realizando ajustes a las ponderaciones cuando realiza una predicción incorrecta. Este proceso se repite muchas veces hasta haber alcanzado uno o varios criterios de parada." — Moscardo

#### Variantes famosas

| Tipo | Para qué sirve | Ejemplo |
|---|---|---|
| **CNN (Convolutional Neural Network)** | Imágenes, audio, señales, series temporales | Reconocimiento facial, diagnóstico por imágenes |
| **RNN / LSTM** | Secuencias (texto, audio) | Traducción, autocompletado |
| **Transformer** | Texto y multimodal | **ChatGPT, Claude, Gemini**, traducción moderna |
| **GAN (Generative Adversarial Network)** | Generar imágenes/video | Deepfakes, generación creativa |
| **Diffusion Models** | Generación de imágenes | DALL·E, Midjourney, Stable Diffusion |

### 3.7. ML vs IA Generativa vs IA Agéntica (recordatorio)

Reaparece la confusión que ya viste en el Cap. 01, pero ahora con la lente del ML:

| Dimensión | **ML clásico** | **IA Generativa** | **IA Agéntica** |
|---|---|---|---|
| Qué hace | **Predice / clasifica** | **Genera contenido nuevo** | **Ejecuta acciones autónomas** |
| Datos típicos | Estructurados (CSV, SQL) | No estructurados (texto, imagen) | Cualquiera + acceso a sistemas |
| Algoritmo típico | Random Forest, XGBoost, regresión | Transformers, difusión | LLM + tools + planning |
| Output | Número o categoría | Texto/imagen/audio/video nuevo | Acciones en sistemas reales |
| Ejemplo | Mercado Libre fraude | ChatGPT redactando un mail | Agente que reserva vuelo y paga |

---

## 4. Caso real organizacional

### Caso 1 — Banco Galicia (Argentina): NLP + ML para onboarding y fraude

**Sector**: banca.
**Problema**: verificación de documentación corporativa era manual, tardaba **días**, con errores.
**Solución**: plataforma propia de NLP construida con Red Hat Consulting, usando código abierto.
**Resultados**:
- **90% de exactitud** en verificación automatizada.
- Tiempos reducidos **de días a minutos**.
- **40% menos downtime** de la aplicación.
- Chatbot **Gala** integrado: +5M de consultas atendidas por WhatsApp.
- Participación en la red **BioCatch Trust Argentina** para intercambio de inteligencia de fraude entre bancos y fintechs en tiempo real.

**Tipos de ML aplicados**: NLP (no supervisado para clustering + supervisado para clasificación), detección de anomalías (no supervisado).

### Caso 2 — Plantium (Argentina, agro): caso de estudio del propio TPI del usuario

**Sector**: agricultura de precisión.
**Tamaño**: 250 empleados (Villa Constitución + Rosario).
**Problema**: sobrecarga de atención al cliente en canales digitales (WhatsApp, redes), modelo manual no escalable.
**Solución propuesta**:
- IA conversacional (chatbot por WhatsApp).
- Arquitectura **RAG** (Retrieval Augmented Generation) sobre base de conocimiento técnica.
- Clasificación automática de consultas.
- Copiloto interno para agentes humanos.
- Analítica de demanda.

**Tipos de ML aplicados**: clasificación supervisada (categorización de consultas), embeddings (NLP), recuperación semántica (RAG), generación con LLM.

**ROI proyectado**: 137,6% (cálculos del propio TPI), payback 5-6 meses.

### Caso 3 — Mercado Libre (LATAM): ML en escala

| Aplicación | Tipo ML | Algoritmo probable |
|---|---|---|
| Recomendaciones | Supervisado + colaborativo | Matrix factorization, deep learning, gradient boosting |
| Fraude (+5.000 variables, <1 segundo) | Supervisado + detección anomalías | XGBoost, Isolation Forest, autoencoders |
| Análisis de sentimiento de reseñas | NLP (supervisado) | Transformers, fine-tuned BERT |
| Mercado Crédito (scoring) | Supervisado clasificación | Regresión logística, Random Forest |
| Visión por computadora (productos prohibidos) | Deep Learning | CNN |

---

## 5. Aplicación a la transformación organizacional

### Cómo elegir el tipo de ML correcto para tu problema

Diagrama de decisión rápido:

```
¿Tenés datos con la respuesta correcta (etiqueta)?
    │
    ├── SÍ → SUPERVISADO
    │       │
    │       ├── ¿Predecís número?     → REGRESIÓN (ventas, demanda, precio)
    │       └── ¿Predecís categoría?  → CLASIFICACIÓN (spam/no-spam, riesgo, churn)
    │
    └── NO → ¿Querés descubrir grupos / patrones?
              │
              ├── Agrupar similares → CLUSTERING (segmentación de clientes)
              ├── Reducir variables → ACP (visualización, simplificar)
              ├── Co-ocurrencia    → ASOCIACIÓN (cesta de compras)
              └── Detectar raros   → ANOMALÍAS (fraude, intrusión)

¿Hay decisiones secuenciales con feedback? → REFUERZO (robótica, trading)
¿Tenés muy poco etiquetado y mucho sin etiquetar? → SEMI-SUPERVISADO
```

### Métricas business (no técnicas)

> El material de la cátedra **no profundiza en métricas técnicas** (accuracy, precision, recall, F1, RMSE, AUC). Para vos como decisor business, lo que importa son las **métricas de impacto**:

| Métrica | Cómo se calcula (idea) | Ejemplo |
|---|---|---|
| **ROI** | (Beneficio - Inversión) / Inversión × 100 | Plantium TPI: USD 118,8k ahorro/año vs USD 50k inversión = **137,6%** |
| **Payback period** | Inversión / Ahorro mensual | Plantium TPI: 5-6 meses |
| **Reducción de errores** | (Errores antes - Errores después) / Errores antes | Galicia: 90% accuracy en docs → menos rework |
| **Tiempo ahorrado** | Tiempo manual - Tiempo automatizado | Galicia: de **días a minutos** |
| **Capacidad escalada** | Volumen atendido con misma plantilla | Mercado Libre: +5.000 variables/transacción < 1 seg |
| **Disponibilidad** | Horas/año en servicio | Agente IA 24/7/365 vs 9h/día humano |
| **Costos de transacción** | Tiempo de buscar, comparar, cerrar | IA agéntica los reduce drásticamente |

> Para el TPI: **siempre cerrá tu sección 8 con ROI y KPIs business**. Los técnicos van al anexo.

### Pipeline ML conceptual (lo que no te enseñan pero tenés que saber)

Aunque la cátedra no lo desarrolla, todo proyecto serio de ML pasa por estas **6 etapas** (variantes: CRISP-DM, KDD, MLOps):

| Etapa | Qué pasa | Quién participa |
|---|---|---|
| **1. Entendimiento del negocio** | ¿Qué problema resolvemos? ¿Cómo se mide éxito? | Business + Data Lead |
| **2. Recolección y preparación de datos** | Extracción, limpieza, feature engineering | Data Engineer |
| **3. Modelado (entrenamiento)** | Probar algoritmos, validar, ajustar | Data Scientist |
| **4. Evaluación** | ¿El modelo cumple métricas de negocio? ¿Es ético? | Data Scientist + Business + Compliance |
| **5. Despliegue (producción)** | Integración con sistemas, APIs, monitoreo | ML Engineer / DevOps |
| **6. Monitoreo y mantenimiento** | Detectar drift, reentrenar, gobernar | MLOps |

> Si tu TPI dice "implementamos IA" y solo describe la 3, te falta el 80% del proyecto real. Las etapas 1, 5 y 6 son donde se cae la mayoría de los proyectos de IA según Gartner (**40% de los proyectos de IA agente serán cancelados antes de 2027**, no por fallas técnicas sino por automatizar procesos rotos).

### Sectores con alto potencial de ML aplicado (Argentina)

| Sector | Aplicación típica | Ejemplo |
|---|---|---|
| **Agro** | Optimización de siembra, riego, fitosanitarios | Plantium, Bioceres, INTA, drones + ML |
| **Salud** | Diagnóstico por imágenes, gestión de turnos, predicción de demanda | Hospital Italiano, Hospital Garrahan |
| **Finanzas** | Scoring crediticio, antifraude, asesoramiento | Mercado Crédito, Galicia, Naranja X |
| **Retail / e-commerce** | Recomendaciones, dynamic pricing, inventario | Mercado Libre, Fravega, Cencosud |
| **Energía** | Mantenimiento predictivo, optimización de pozos | YPF / Y-TEC, Vaca Muerta |
| **Logística** | Optimización de rutas, demanda de flota | Andreani, OCA, Mercado Envíos |
| **Educación** | Personalización del aprendizaje, detección de deserción | Plataformas EdTech |
| **Deporte** | Análisis táctico, biométrica, scouting | AFA, clubes de fútbol con análisis de video |

---

## 6. Errores comunes / mitos

| Mito | Realidad |
|---|---|
| "ML es magia que resuelve cualquier problema" | **Falso**. ML resuelve problemas con **patrones aprendibles desde datos históricos**. Si el problema es nuevo o el contexto cambia, ML falla |
| "Cualquier dataset sirve para entrenar" | **Falso**. "Garbage in, garbage out". Datos sesgados → modelos sesgados. Datos viejos → modelos obsoletos |
| "El mejor algoritmo es el más complejo" | **Falso**. Una regresión logística bien hecha puede vencer a una red neuronal mal entrenada. **Empezá simple** |
| "Deep Learning siempre es superior" | **Falso**. Para datos tabulares estructurados, **XGBoost y Random Forest siguen ganando** la mayoría de las competencias de Kaggle |
| "Una vez entrenado, el modelo dura para siempre" | **Falso**. Los modelos sufren **data drift** (los datos del mundo real cambian) y necesitan reentrenamiento periódico |
| "ML = Inteligencia Artificial" | **Falso**. ML es **un subconjunto** de IA. Hay IA sin ML (sistemas expertos, búsqueda heurística, lógica simbólica) |
| "Si tengo ChatGPT, no necesito ML clásico" | **Falso**. ChatGPT no predice demanda con un dataset histórico de tu empresa. Para muchas tareas business, ML clásico sigue siendo el camino correcto y más barato |
| "El modelo se equivoca = está mal hecho" | **Matiz**. "Los modelos no son perfectos. Requieren tiempo, ensayos, y fundamentalmente algunos requieren cierto entrenamiento para que funcionen de manera correcta" — Moscardo. **Toda predicción tiene error**: lo que importa es controlarlo |

---

## 7. Checklist de comprensión

- [ ] Puedo definir ML en una frase y diferenciarlo de "programación tradicional".
- [ ] Conozco los **4 tipos de aprendizaje** y sé cuándo aplicar cada uno.
- [ ] Distingo **clasificación** (categorías) de **regresión** (números).
- [ ] Puedo nombrar y describir en una línea: **Naive Bayes, KNN, Árboles, Random Forest, SVM, Regresión Lineal/Logística**.
- [ ] Puedo nombrar y describir en una línea: **K-Means, ACP, Apriori, Isolation Forest, Z-Score**.
- [ ] Entiendo qué es el **aprendizaje por refuerzo** y sé dar un ejemplo de KPI (caso brazo robótico).
- [ ] Sé qué es **Deep Learning** y por qué explotó en los 2010s (GPU + datos).
- [ ] Puedo dibujar el pipeline ML conceptual (Datos → Aprende → Modelo → Predice).
- [ ] Distingo **ML clásico**, **IA generativa** e **IA agéntica**.
- [ ] Conozco al menos 3 métricas business (no técnicas) para evaluar un proyecto de ML.
- [ ] Identifico al menos un caso argentino de ML aplicado en cada sector clave (agro, finanzas, e-commerce, energía).
- [ ] Identifico al menos 3 mitos sobre ML y sé refutarlos.

---

## 8. Para profundizar

### Libros (los dos canónicos)

- **Géron, A. (2022)**. *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow* (3ª ed.). O'Reilly. — La biblia práctica de ML. Aunque vos no vas a programar, **leer los primeros capítulos te da una intuición que ningún video puede**. <https://www.oreilly.com/library/view/hands-on-machine-learning/9781098125967/>
- **Mitchell, T. (1997)**. *Machine Learning*. McGraw-Hill. — El clásico académico fundacional. Capítulos 1-2 son lectura obligatoria si querés sonar serio en una conversación de ML.

### Cursos online (los más recomendados)

- **Andrew Ng — Machine Learning Specialization (Coursera)**. Stanford + DeepLearning.AI. La actualización del curso original de 2012 que tuvo +4.8 millones de alumnos. Excelente balance intuición + práctica, **sin requisitos matemáticos previos**. <https://www.coursera.org/specializations/machine-learning-introduction>
- **DataCamp — Machine Learning Fundamentals**. Más práctico, sin matemáticas. <https://www.datacamp.com/>
- **fast.ai — Practical Deep Learning for Coders**. Si te animás al deep learning sin enterrarte en teoría. <https://www.fast.ai/>

### Documentación de herramientas

- **scikit-learn** (la librería estándar de ML en Python): <https://scikit-learn.org/stable/user_guide.html>
- **TensorFlow**: <https://www.tensorflow.org/learn>
- **PyTorch**: <https://pytorch.org/tutorials/>

### Reportes / informes para contexto business

- **Deloitte Tech Trends 2026** — incluye predicciones sobre adopción de ML y IA agéntica.
- **McKinsey — The State of AI in 2025** — encuesta global con datos de adopción por sector.
- **Stanford HAI — AI Index Report** — el barómetro anual de la academia. <https://aiindex.stanford.edu/>

---

## Próximo paso

→ [04 — Prompt Engineering](04-prompt-engineering.md)

Ya entendés qué es la IA, qué son los datos y cómo aprenden los modelos. Falta una habilidad transversal que **vas a usar todos los días** desde el momento en que abras ChatGPT o Claude: cómo **dirigir** a la IA con instrucciones que sí funcionen. Eso es prompt engineering.

---

## Referencias

- Alvear, A. — *Unidad 2: Machine Learning*, DIATO UNRaf Cohorte 5 (2026).
- Moscardo, E. — *Módulo 1: Introducción a la IA — Machine Learning y Deep Learning*, DIATO UNRaf Cohorte 5 (2026).
- Mitchell, T. (1997). *Machine Learning*. McGraw-Hill.
- Géron, A. (2022). *Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow* (3rd ed.). O'Reilly. <https://www.oreilly.com/library/view/hands-on-machine-learning/9781098125967/>
- Ng, A. — *Machine Learning Specialization*. Coursera / DeepLearning.AI + Stanford Online. <https://www.coursera.org/specializations/machine-learning-introduction>
- scikit-learn — *User Guide*. <https://scikit-learn.org/stable/user_guide.html>
- iProUp — *Banco Galicia: IA con tecnología propia*. <https://www.iproup.com/innovacion/57677-ia-en-banca-el-caso-galicia-y-como-mejora-experiencia-del-cliente-con-tecnologia-propia>
- Red Hat — *Banco Galicia builds first open source intelligent NLP platform*. <https://www.redhat.com/en/success-stories/banco-galicia-NLP>
- BioCatch — *Argentinian banks and fintechs launch real-time scams intel network*. <https://www.biocatch.com/press-release/argentinia-banks-fintechs-real-time-scams-intel-network>
- Cronista InfoTechnology — *Mercado Libre y su uso intensivo de IA*. <https://www.cronista.com/infotechnology/innovacion-it/el-arma-secreta-en-la-que-esta-invirtiendo-mercado-libre-y-pocos-conocen/>
