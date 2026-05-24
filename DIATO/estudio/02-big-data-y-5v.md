# 02 — Big Data y las 5 V

> Si una IA es un cerebro, los datos son la sangre. Big Data **no es "tener muchos datos"**: es un fenómeno con cinco dimensiones que definen si los datos sirven o no para tomar decisiones. Este capítulo te enseña a leer el dato como activo organizacional, no como ruido.

---

## 1. Concepto

### Definición de la cátedra (Alvear)

> "Big Data es un fenómeno científico-tecnológico que, gracias a la integración de la ciencia y la tecnología, nos permite **transformar la complejidad en simplicidad** con ayuda de las tecnologías de la información."
>
> — Prof. Alexis Alvear, Unidad de Big Data y Data Science

Tres cosas importantes en esta definición:

1. **Fenómeno, no tecnología**. Big Data no es "comprar Hadoop". Es un cambio cualitativo en cómo generamos, almacenamos y analizamos datos.
2. **Complejidad → simplicidad**. La promesa es que **datos masivos bien procesados producen mejores decisiones**, no más confusión.
3. **Integración ciencia + tecnología**. No alcanza con servidores potentes (tecnología) si no tenés método científico para interpretar los datos.

### Definición externa — Doug Laney, Gartner (2001)

El origen formal del concepto. En **febrero de 2001**, el analista **Doug Laney** publicó para Gartner (entonces META Group) el reporte:

> **"3D Data Management: Controlling Data Volume, Velocity, and Variety"** (Application Delivery Strategies, File 949).

Laney definió las **3 dimensiones originales** que después se ampliarían a 5. **No usó la palabra "Big Data"** en su reporte original; el término se popularizaría después, pero las 3 V son su contribución fundacional.

> "La definición original de Big Data nació en un reporte interno de Gartner, no en un paper académico. Eso debería decirte algo sobre dónde se cocinó la conversación: en consultoras, no en universidades. El sesgo business viene de fábrica."

### ¿Big Data vs Business Intelligence (BI) tradicional?

La cátedra no lo desarrolla explícitamente, pero la distinción es crítica:

| Dimensión | **BI tradicional** | **Big Data** |
|---|---|---|
| Volumen | GB, máximo TB | TB, PB, ZB |
| Tipo de dato | **Estructurado** (tablas SQL) | Estructurado + semi + no estructurado (texto, imagen, audio, video) |
| Procesamiento | **Batch** (informes semanales/mensuales) | **Streaming + batch** (tiempo real) |
| Preguntas que responde | Mayormente ¿qué pasó? | ¿Qué pasó, por qué, qué va a pasar y qué debería hacer? |
| Stack | SQL, Excel, Tableau, Power BI | Hadoop, Spark, Kafka, NoSQL, lakehouses |
| Esquema | **Schema-on-write** (definido antes de cargar) | **Schema-on-read** (definido al consultar) |

> No te confundas: **Big Data no reemplazó a BI**, lo **expandió**. Una organización madura usa ambos. BI para reporting de gestión, Big Data para análisis avanzado y predicciones.

---

## 2. Intuición

Pensá en tu empresa como **un edificio inteligente** lleno de sensores:

- Cada vez que un cliente entra a la web → **sensor que captura** clic, tiempo, scroll.
- Cada vez que un empleado abre un mail → **sensor que captura** apertura, hora, dispositivo.
- Cada vez que el camión cruza el portón → **sensor que captura** patente, peso, tiempo.
- Cada vez que un sensor IoT mide temperatura → **dato cada 30 segundos**.

Hace 20 años, vos guardabas en una planilla la **facturación mensual**. Hoy generás **millones de eventos por día** sin darte cuenta. Esa avalancha es Big Data.

El desafío no es **capturar** todo eso (las herramientas lo hacen). El desafío es **transformar esa avalancha en decisiones**. Las 5 V te dan el marco para evaluar si tu organización está lista para hacerlo.

---

## 3. Cuerpo desarrollado

### 3.1. Las 5 V del Big Data (el framework central)

> ⚠️ **Cuidado con la confusión histórica**: la formulación **original de Laney en 2001 fueron 3 V** (Volumen, Velocidad, Variedad). Las **otras 2 V (Veracidad y Valor)** se agregaron después por la comunidad y por IBM hacia 2014, sobre todo para responder a críticas de que "tener muchos datos rápido y variados" no garantizaba ningún beneficio. Hoy el modelo **estándar de la cátedra y la industria son las 5 V**.

| V | Definición (cátedra) | Pregunta clave | Desafío organizacional |
|---|---|---|---|
| **1. Volumen** | Grandes volúmenes de información. Los dispositivos tecnológicos permiten capturar miles de datos minuto a minuto | ¿Cuánto dato manejamos? | Desarrollar **capacidades técnicas** de almacenamiento y procesamiento |
| **2. Velocidad** | Rapidez de generación y procesamiento. Muchos datos tienen **corta vida útil** | ¿Qué tan rápido podemos analizar? | Capturar y analizar **en el momento oportuno** antes de que pierdan valor |
| **3. Variedad** | Datos de **diferentes fuentes y formatos**: estructurados, semi-estructurados, no estructurados | ¿Qué tipos de dato tenemos? | Configurar procesos de análisis que **integren la diversidad** |
| **4. Veracidad** | **Calidad** de los datos. Registros incompletos, erróneos, faltantes, fuentes discrepantes | ¿Confiamos en los datos? | Detectar **errores, duplicados, inconsistencias** antes de tomar decisiones |
| **5. Valor** | Capacidad de **extraer utilidad de negocio** del dato | ¿Para qué nos sirve? | Tener **capacidad analítica** y **objetivos claros** para que el dato aporte ROI |

> Una regla de oro: **si te falla una sola V, fallan todas**. De nada sirve tener petabytes (Volumen) si los datos son falsos (Veracidad). De nada sirven datos confiables (Veracidad) si tardan 3 meses en llegar al decisor (Velocidad).

### 3.2. Variedad — los 3 subtipos de datos

Acá hay que ser quirúrgico, porque el TPI puede pedirte clasificar qué datos vas a usar.

| Tipo | Definición (cátedra) | Ejemplos | % del Big Data total* |
|---|---|---|---|
| **Estructurados** | Datos con modelo definido o provenientes de un campo determinado en un registro | Fichas de clientes, transacciones comerciales, tablas SQL, Excel | ~20% |
| **Semi-estructurados** | Datos **sin formato fijo pero con atributos o etiquetas** | Correos electrónicos, JSON, XML, logs, fichas médicas con imágenes embebidas | ~10% |
| **No estructurados** | Datos sin modelo predefinido ni organización | Videos, fotografías, audios, texto libre, redes sociales | **~80%** (y creciendo) |

\* *Estimación de la industria. El gran salto que produjo el Big Data fue justamente poder procesar el ~80% de datos no estructurados, que el BI tradicional dejaba afuera.*

### 3.3. Veracidad — los 3 problemas típicos de calidad

La cátedra los identifica explícitamente:

1. **Datos erróneos** — campos mal consignados por errores de lectura/tipeo. *Ejemplo (cátedra chilena): "RUTs de 3 dígitos", direcciones inexistentes. **Adaptado a Argentina**: CUITs mal cargados, DNIs con formato inválido, números de teléfono sin código de área.*
2. **Datos faltantes** — información incompleta de dimensiones considerables. Ejemplo: campo "ingresos" del cliente vacío en el 40% de los registros.
3. **Fuentes discrepantes** — información del mismo cliente en distintos sistemas con valores contradictorios. Ejemplo: el CRM dice "Juan García, Rosario" y el ERP dice "J. García, Santa Fe".

### 3.4. Los 7 criterios de calidad de datos (Módulo 7 — Ferrario/Barbero)

El Módulo 7 sistematiza los criterios que definen un dato "veraz":

| # | Criterio | Significado |
|---|---|---|
| 1 | **Exactitud (Accuracy)** | El dato refleja la realidad con precisión |
| 2 | **Completitud (Completeness)** | No faltan elementos esenciales |
| 3 | **Consistencia (Consistency)** | El dato es consistente entre sistemas y formatos |
| 4 | **Validez (Validity)** | Cumple reglas de negocio (tipos, rangos, formatos) |
| 5 | **Actualización (Timeliness)** | Refleja la información más reciente |
| 6 | **Accesibilidad (Accessibility)** | Disponible para usuarios autorizados en tiempo/formato adecuado |
| 7 | **Integridad (Integrity)** | Relaciones precisas entre conjuntos de datos |

> En un TPI, si decís "vamos a usar IA con los datos de la empresa", la pregunta inevitable es: **¿cómo evaluaron la calidad de esos datos?** Esta tabla es la respuesta estándar.

### 3.5. La Pirámide de Complejidad Analítica (los 4 niveles)

Otro framework central del módulo. **Memorizalo**.

> "La complejidad analítica presenta una relación directa entre valor y la dificultad de los procesos de análisis." — Alvear

```
                          ╱ ╲
                         ╱   ╲      ┌───────────────┐
                        ╱  4  ╲     │ PRESCRIPTIVO   │  ¿Qué debería hacer?
                       ╱───────╲    └───────────────┘
                      ╱    3    ╲   ┌───────────────┐
                     ╱───────────╲  │ PREDICTIVO     │  ¿Qué va a pasar?
                    ╱      2      ╲ └───────────────┘
                   ╱───────────────╲┌───────────────┐
                  ╱        1        ╲│ DIAGNÓSTICO    │  ¿Por qué pasó?
                 ╱───────────────────╲└──────────────┘
                ╱                     ╲┌──────────────┐
               ╱──────────────────────╲│ DESCRIPTIVO   │  ¿Qué pasó?
                                       └──────────────┘
              ←     menor valor / facilidad           mayor valor / dificultad     →
```

| Nivel | Tipo de analítica | Pregunta | Herramientas típicas | Ejemplo retail (Mumbo) |
|---|---|---|---|---|
| **1** | **Descriptiva** | ¿Qué pasó? | Dashboards, reporting, BI | "Mumbo gastó $3.000 en agosto, compró 12 productos, vino 4 veces" |
| **2** | **Diagnóstica** | ¿Por qué pasó? | Drill-down, correlaciones, análisis exploratorio | "Mumbo compró esos productos porque estaban en oferta + ubicación en góndola + tradición familiar" |
| **3** | **Predictiva** | ¿Qué va a pasar? | ML supervisado, modelos de series temporales | "Mumbo probablemente volverá a comprar leche, galletas y café en septiembre" |
| **4** | **Prescriptiva** | ¿Qué debería hacer? | Optimización, sistemas de recomendación, simulación | "Enviarle a Mumbo cupón -20% en café + sugerirle producto sustituto Y porque su marca preferida X no estará stockeada" |

#### Caso ilustrativo de la cátedra: "Mumbo Minimarket"

La cátedra usa al personaje **Mumbo** (sistema de puntos "¡Puntos Mumbo!", "Mumbo give you more!", "Ofertas para ti!") como **hilo conductor** para mostrar cómo se aplican los 4 niveles al retail. Lo importante es que vos puedas trasladar esa lógica a tu propio TPI:

- **Caso turismo**: descriptivo = "¿cuántos turistas vinieron?"; diagnóstico = "¿por qué bajó la ocupación en julio?"; predictivo = "¿qué demanda tendremos para Bariloche en invierno?"; prescriptivo = "¿qué precio dinámico aplicar a cada habitación?".
- **Caso agro**: descriptivo = "¿cuánto rindió cada lote?"; diagnóstico = "¿por qué cayó el rinde en el lote 5?"; predictivo = "¿qué rinde esperamos la próxima campaña?"; prescriptivo = "¿qué semilla y dosis aplicar en cada zona del lote?".

### 3.6. Las 4 etapas históricas del tratamiento de datos (Módulo 7)

Para entender de dónde venimos:

| # | Etapa | Tecnología | Limitación |
|---|---|---|---|
| 1 | **Búsqueda por fuerza bruta** | Listas, fichas manuales | No escala |
| 2 | **Modelo relacional (SQL)** | Bases de datos relacionales (Oracle, MySQL, PostgreSQL) | Solo datos estructurados |
| 3 | **Universo heterogéneo de la web** | Metadatos, búsqueda en HTML | Sin estructura, ruidoso |
| 4 | **Big Data** | Hadoop, Spark, lakehouses, NoSQL | Complejo de gobernar |

### 3.7. Herramientas y ecosistema mencionados (Módulo 1 + 7)

| Herramienta | Categoría | Uso |
|---|---|---|
| **Apache Hadoop** | Procesamiento distribuido | El padre de Big Data. Permite procesar PB en clusters de commodity hardware |
| **Apache Spark** | Procesamiento in-memory | Sucesor "moderno" de Hadoop, hasta 100x más rápido para muchas cargas |
| **Tableau / Power BI** | Visualización / BI | Convertir datos en gráficos accionables |
| **Tableau Public / Flourish** | Visualización pública | Versiones gratuitas para storytelling con datos |
| **Excelmatic** (`excelmatic.ai`) | IA + Excel | Subir planilla y preguntar en lenguaje natural — democratiza el análisis |
| **NotebookLM** (Google) | Análisis de documentos con IA | Cargás PDFs y la IA los resume y responde preguntas |
| **Sharly.ai** (`sharly.ai`) | Análisis de documentos con IA | Alternativa a NotebookLM, foco en docs corporativos |
| **Azure Vision** | Visión por computadora | Detección de objetos en imágenes |
| **Google Forms / SurveyMonkey** | Recolección de datos cuantitativos | Encuestas digitales |

---

## 4. Caso real organizacional

### Mercado Libre — Big Data como ventaja competitiva (Argentina/LATAM)

Mercado Libre es **el caso emblemático argentino** de las 5 V en producción:

**Volumen**:
- +5.000 variables analizadas por transacción en su sistema antifraude.
- Millones de reseñas analizadas con NLP.
- Petabytes de imágenes de productos procesadas por visión artificial.

**Velocidad**:
- Detección de fraude en **menos de 1 segundo** por transacción.
- Recomendaciones personalizadas en tiempo real según contexto y horario.

**Variedad**:
- Datos estructurados: transacciones, fichas de productos, ubicación.
- Semi-estructurados: reseñas con metadata, logs de navegación.
- No estructurados: imágenes de productos, mensajes en Mercado Pago.

**Veracidad**:
- Modelos de detección de productos prohibidos con visión por computadora.
- Análisis de sentimiento para detectar fakes y reseñas falsas.

**Valor**:
- Más de **50 soluciones propias de IA en producción**.
- Pasaron de un equipo de **50 personas (2015) a más de 1.000 personas (2024)** generando valor desde IA + datos.

### Otros casos rápidos

| Empresa | Aplicación de Big Data |
|---|---|
| **YPF / Y-TEC** | Digital Twins + ML sobre datos de perforación en Vaca Muerta. Optimización de trayectoria de pozo en tiempo real con sensores a 3.000m de profundidad |
| **Banco Galicia** | Plataforma propia de NLP con Red Hat; procesa documentación corporativa con 90% de exactitud, reduciendo verificación de días a minutos |
| **AFIP** | Cruces masivos de datos para detección de evasión (declaraciones, consumos, propiedades, viajes) — caso pionero de Big Data en sector público argentino |
| **Globant** | Productiza Big Data y ML como servicio para clientes globales (Disney, Google, EA) |

---

## 5. Aplicación a la transformación organizacional

### Las 5 preguntas que tenés que hacerle a tu organización antes de proponer IA

1. **¿Tenemos los datos? (Volumen + Variedad)**
   Si tu organización genera 200 transacciones por mes en una planilla, **no tenés Big Data**. Tenés data clásico. Eso está bien — empezá con BI antes de saltar a ML.

2. **¿Los datos llegan a tiempo? (Velocidad)**
   Si el reporte mensual llega el día 25 del mes siguiente, **no podés tomar decisiones de gestión** en base a él. Antes de IA, resolvé la latencia.

3. **¿Confiamos en los datos? (Veracidad)**
   Los 7 criterios del Módulo 7 (exactitud, completitud, consistencia, validez, actualización, accesibilidad, integridad). Si fallan, cualquier modelo de IA va a aprender basura y a entregar basura ("garbage in, garbage out").

4. **¿Qué nivel de la pirámide analítica somos hoy? (Valor)**
   - Solo dashboards = nivel 1 (descriptivo). Estás en BI.
   - Análisis ad-hoc, drill-down = nivel 2 (diagnóstico).
   - Forecasting, modelos predictivos = nivel 3 (predictivo). Acá empieza ML.
   - Sistemas que recomiendan acciones = nivel 4 (prescriptivo). Acá entra IA agéntica.

5. **¿Cumplimos con la normativa argentina?**
   - **Ley 25.326** (Protección de Datos Personales).
   - **Resolución AAIP 161/2023** (transparencia en uso de IA).
   - **Constitución Nacional Art. 43** (habeas data).

   *El Módulo 5 te lo va a desarrollar a fondo. Pero ya desde Big Data tenés que tener consentimiento y finalidad explícita para usar datos personales.*

### Roadmap típico de madurez analítica organizacional

| Etapa | Capacidad | Inversión típica | Tiempo |
|---|---|---|---|
| **0. Pre-data** | Decisiones por intuición | $0 | — |
| **1. BI descriptivo** | Dashboards y reportes | USD 5k-30k/año (Power BI, Tableau) | 3-6 meses |
| **2. Diagnóstico avanzado** | Self-service analytics, drill-down | USD 30k-100k/año | 6-12 meses |
| **3. Predictivo (ML)** | Modelos de forecasting, clasificación | USD 100k-500k/año + equipo data science | 12-24 meses |
| **4. Prescriptivo / IA agéntica** | Sistemas que optimizan y actúan | USD 500k+/año + governance | 24+ meses |

> No te saltes etapas. Una PyME santafesina que arranca con un proyecto de "IA generativa con RAG sobre sus documentos" probablemente debería primero **resolver que sus documentos estén digitalizados y bien indexados** (etapa 1-2). Sin eso, ningún modelo va a funcionar.

---

## 6. Errores comunes / mitos

| Mito | Realidad |
|---|---|
| "Big Data es tener muchos datos" | **Falso**. Big Data es un fenómeno con 5 dimensiones. El volumen es solo una. Tener 5 TB de basura no es Big Data, es un problema |
| "Big Data reemplaza al BI" | **Falso**. Lo complementa. Las organizaciones maduras usan ambos: BI para reporting de gestión, Big Data para análisis avanzado |
| "Necesito Hadoop para hacer Big Data" | **Cada vez menos cierto**. Hoy hay opciones cloud (BigQuery, Snowflake, Databricks) que no requieren administrar clusters |
| "Las 5 V son inmutables" | **Matiz**. Empezaron como 3 V (Laney 2001), pasaron a 5 V (~2014), algunos hablan de 7 V o 10 V (sumando Variabilidad, Visualización, Validez, etc.). El estándar más usado son las 5 V |
| "Si tengo Big Data, ya tengo IA" | **Falso**. Big Data es **insumo**, no producto. La IA necesita Big Data pero también modelos, equipos, gobernanza y casos de uso |
| "Cuanto más dato, mejor modelo" | **Falso**. "MÁS no significa MEJOR" (Moscardo). La **calidad** y **relevancia** importan más que la cantidad. Un dataset chico bien etiquetado puede vencer a uno enorme y sucio |
| "Cualquier dato sirve si lo limpio" | **Cuidado**. Si tu dataset histórico está sesgado (ej: solo aprobaste préstamos a hombres durante 30 años), el modelo va a aprender el sesgo. Limpiar formato no arregla sesgo histórico |

---

## 7. Checklist de comprensión

- [ ] Puedo recitar las **5 V** y dar un ejemplo de negocio de cada una.
- [ ] Sé quién, cuándo y dónde se publicó la definición original (Laney, Gartner, **2001**, 3 V).
- [ ] Distingo datos **estructurados, semi-estructurados y no estructurados** con ejemplos.
- [ ] Conozco los **3 problemas típicos de veracidad** (errores, faltantes, discrepancias).
- [ ] Puedo nombrar los **7 criterios de calidad de datos** (al menos 5 de memoria).
- [ ] Sé dibujar la **Pirámide de Complejidad Analítica** (4 niveles) y explicar cada nivel con un ejemplo.
- [ ] Distingo **Big Data de BI tradicional** en al menos 3 dimensiones.
- [ ] Puedo evaluar en qué **nivel de madurez analítica** está mi propia organización.
- [ ] Conozco al menos **3 herramientas** del ecosistema (Hadoop, Spark, Tableau, NotebookLM, etc.).
- [ ] Identifico al menos **3 mitos** sobre Big Data y sé refutarlos.

---

## 8. Para profundizar

- **Laney, D. (2001)**. *3D Data Management: Controlling Data Volume, Velocity, and Variety*. META Group / Gartner Application Delivery Strategies, File 949. — **El reporte fundacional**.
- **McKinsey Global Institute (2011)**. *Big Data: The Next Frontier for Innovation, Competition, and Productivity*. — El paper que popularizó "Big Data" como término corporativo.
- **Mayer-Schönberger, V. & Cukier, K. (2013)**. *Big Data: A Revolution That Will Transform How We Live, Work, and Think*. Houghton Mifflin Harcourt.
- **Marr, B. (2016)**. *Big Data in Practice: How 45 Successful Companies Used Big Data Analytics to Deliver Extraordinary Results*. — Casos prácticos.
- **Guía AAIP (2024)** — *Guía para entidades públicas y privadas en materia de Transparencia y Protección de Datos Personales para una IA responsable*. Marco regulatorio argentino, lectura obligatoria si tu TPI toca datos personales.

---

## Próximo paso

→ [03 — Machine Learning: Fundamentos](03-machine-learning-fundamentos.md)

Ya tenés datos (Big Data) y entendés qué es la IA. Toca el puente: el **Machine Learning**. ¿Cómo "aprende" una máquina a partir de datos? ¿Qué tipos de aprendizaje existen y cuándo aplicar cada uno? ¿Qué algoritmos famosos conviene tener en el radar de un decisor business?

---

## Referencias

- Laney, D. (2001). *3D Data Management: Controlling Data Volume, Velocity, and Variety*. META Group/Gartner, File 949. <https://www.bibsonomy.org/bibtex/742811cb00b303261f79a98e9b80bf49>
- Alvear, A. — *Unidad 1: Big Data y Data Science*, DIATO UNRaf Cohorte 5 (2026).
- Ferrario, L. & Barbero, C. — *Módulo 7: Gestión Estratégica de Datos*, DIATO UNRaf Cohorte 5 (2026).
- AuraQuantic — *The 5 Vs of Big Data*. <https://www.auraquantic.com/blog/five-vs-big-data/>
- TDWI — *The 3 Vs and Unstructured Data Analytics*. <https://tdwi.org/articles/2022/10/20/data-all-3-vs-and-unstructured-data-analytics.aspx>
- Apache Hadoop. <https://hadoop.apache.org/>
- Apache Spark. <https://spark.apache.org/>
- AAIP — *Guía para una IA responsable* (junio 2024). <https://www.argentina.gob.ar/aaip>
- Cronista InfoTechnology — *Mercado Libre, IA y datos*. <https://www.cronista.com/infotechnology/innovacion-it/el-arma-secreta-en-la-que-esta-invirtiendo-mercado-libre-y-pocos-conocen/>
- Mejor Energía — *YPF: perforación autónoma desde RTIC con IA y Starlink*. <https://www.mejorenergia.com.ar/noticias/2025/08/25/4529-ypf-perfora-y-fractura-de-forma-autonoma-sin-intervencion-humana-desde-el-rtic-de-buenos-aires>
