# 10. Gestión estratégica de datos

> Módulo 7 — Mg. Luis Ferrario y Lic. Carina Barbero. **Base de "data thinking" para todo profesional que vaya a trabajar con IA**: qué son los datos, cómo se diferencian de la información y el conocimiento, qué los hace de calidad, y por qué se convirtieron en el activo estratégico más codiciado del siglo XXI.

## 1. Concepto

**Gestión estratégica de datos** es el conjunto de políticas, procesos, roles y tecnologías que una organización pone en juego para tratar los datos **como un activo** —comparable al capital, a la marca o al talento humano— y no como un subproducto técnico de los sistemas.

Comprende tres movimientos:

1. **Reconocer el dato como activo** (no como ruido administrativo).
2. **Convertirlo en información, conocimiento y eventualmente en sabiduría** (la pirámide DIKW que vas a ver enseguida).
3. **Garantizar su calidad** mediante criterios verificables (los 7 criterios que la cátedra te exige conocer).

La frase de cabecera del Foro Económico Mundial (2011) lo dice sin vueltas: *"Los datos son el nuevo petróleo"*. Pero hay una diferencia importante: el petróleo se consume al usarlo; los datos, bien gestionados, **se multiplican**. La gestión estratégica es lo que hace posible esa multiplicación.

## 2. Intuición

Pensá en una panadería de barrio. Todos los días el dueño anota en un cuaderno:

- Cuántos kilos de harina compró.
- Cuántos panes vendió.
- Quién le pidió fiado.

Eso son **datos**. Sueltos, crudos, sin contexto.

Cuando al final del mes el dueño cruza esos datos y descubre que *"los lunes de lluvia vende un 30% menos"*, eso es **información**.

Cuando entiende *"si el pronóstico marca lluvia para el lunes, conviene amasar 30% menos para no tirar"*, eso es **conocimiento** —porque ya guía la acción.

Y si además decide *"voy a comprar un sensor de humedad y conectarlo a mi sistema de pedidos para automatizar el ajuste"*, ahí está la **sabiduría**: la decisión estratégica que combina datos, contexto, experiencia y propósito.

Ese cuaderno de tapa dura, en una organización mediana o grande, se convierte en un data warehouse, un data lake, un dashboard de Tableau o una conversación en lenguaje natural con Excelmatic. Pero el principio es el mismo: **sin datos buenos, no hay decisión buena**.

## 3. Cuerpo desarrollado

### 3.1 La pirámide DIKW: del dato a la sabiduría

La jerarquía **DIKW** (Data → Information → Knowledge → Wisdom) fue popularizada por **Russell Ackoff** en su artículo *"From Data to Wisdom"* (Journal of Applied Systems Analysis, 1989). Ackoff, profesor de la Wharton School y referente de la Operations Research, propuso esta pirámide para explicar cómo agregamos valor a medida que procesamos el mundo.

```
            ▲
           / \
          / S \      Sabiduría: ¿por qué hacerlo? (juicio, propósito)
         /-----\
        /   K   \    Conocimiento: ¿cómo hacerlo? (acción)
       /---------\
      /     I     \  Información: ¿qué, quién, cuándo? (contexto)
     /-------------\
    /       D       \ Dato: hechos crudos, sin interpretación
   /─────────────────\
```

| Nivel | Qué es | Ejemplo de la cátedra | Ejemplo organizacional |
|-------|--------|----------------------|-------------------------|
| **Dato** | Conjunto discreto de factores objetivos sobre un hecho real. Sin procesar, sin interpretación. | El número `42`. "Corrió 5 km". | `cliente_id=4837`, `monto=12500`, `fecha=2026-03-15` |
| **Información** | Datos con significado, procesados, en contexto. | "El paciente tiene 42° de temperatura". "Corrió 5 km tres veces por semana en agosto". | "El cliente 4837 compró $12.500 el 15-mar; es la tercera compra en 30 días". |
| **Conocimiento** | Experiencias, valores e información que sirven como marco para la **acción**. Está destinado a resolver un problema. | "Si la temperatura llega a 42° pueden producirse lesiones cerebrales irreversibles". | "Clientes que compran 3+ veces en 30 días tienen 4x más probabilidad de churn si no reciben contacto personalizado". |
| **Sabiduría** | Juicio sobre cuándo y por qué aplicar el conocimiento. Incluye ética, propósito, contexto a largo plazo. | "El médico decide priorizar a este paciente sobre otros con base en triage". | "Vamos a abandonar el segmento aunque sea rentable porque entra en conflicto con nuestros valores y dañaría la marca a 5 años". |

> **Atención**: muchos autores omiten la W (Wisdom) o la dejan como aspiracional. La cátedra DIATO menciona los tres primeros niveles (Dato/Información/Conocimiento) y deja la sabiduría como horizonte ético —que vas a profundizar en el capítulo 11.

**Por qué importa la pirámide para vos como profesional de IA en transformación organizacional:**

- La mayoría de las organizaciones tiene **océanos de datos** y **gotas de conocimiento**.
- La IA generativa promete acelerar la subida de la pirámide, pero **si el dato de base está sucio, la información será errónea, el conocimiento estará viciado, y la "sabiduría" será directamente peligrosa**. GIGO clásico: *Garbage In, Garbage Out*.
- Tu trabajo va a ser, muchas veces, **bajar a la base de la pirámide** antes de subir: revisar la calidad del dato antes de prometer dashboards o agentes inteligentes.

### 3.2 Tipos de datos según su estructura

| Tipo | Descripción | Ejemplos | Quién los procesa bien |
|------|-------------|----------|------------------------|
| **Estructurados** | Organizados en filas y columnas, esquema fijo. Caben en una tabla relacional. | Tablas SQL, planillas Excel, formularios validados. | Bases SQL (PostgreSQL, MySQL), data warehouses. |
| **Semi-estructurados** | Tienen estructura pero flexible, con etiquetas o tokens auto-descriptivos. | JSON, XML, YAML, logs estructurados. | Bases NoSQL documentales (MongoDB), motores de búsqueda (Elasticsearch). |
| **No estructurados** | Sin esquema predefinido. La estructura emerge del procesamiento posterior. | Texto libre, PDF, imágenes, audio, video, mails. | Modelos de embeddings, LLMs, computer vision, bases vectoriales (Pinecone, Qdrant). |

Dato útil para la realidad organizacional: **se estima que el 80% de los datos de una empresa moderna son no estructurados** (mails internos, contratos PDF, grabaciones de reuniones, fotos de planta). La IA generativa es revolucionaria justamente porque por primera vez podemos extraer valor de ese 80% sin convertirlo manualmente a tabla.

### 3.3 Los 7 criterios de calidad de datos

Sin estos criterios, cualquier proyecto de IA en tu organización va a fracasar. La cátedra los enumera así (en inglés son el estándar **DAMA-DMBOK** —Data Management Body of Knowledge, mantenido por la asociación internacional DAMA—, que es **la** referencia profesional en data management):

1. **Exactitud (Accuracy)**: los datos reflejan la realidad con precisión. Si el sistema dice que un cliente tiene 35 años y en realidad tiene 53, hay un problema de exactitud.

2. **Completitud (Completeness)**: no faltan campos esenciales. Si el 40% de las filas no tiene email, no podés correr una campaña de email marketing.

3. **Consistencia (Consistency)**: los datos coinciden entre sistemas. Si el CRM dice "Buenos Aires" y el ERP dice "CABA" para el mismo cliente, ningún reporte cruzado va a cerrar.

4. **Validez (Validity)**: los datos cumplen reglas de negocio y restricciones técnicas (tipos correctos, rangos válidos, formatos esperados). Un DNI de 8 dígitos no puede tener 12; una fecha de nacimiento no puede ser del año 2050.

5. **Actualización (Timeliness)**: los datos reflejan la situación más reciente. Un stock actualizado hace 6 meses no sirve para decidir si reponer hoy.

6. **Accesibilidad (Accessibility)**: los datos están disponibles para quienes los necesitan, en el momento que los necesitan, en el formato adecuado. De nada sirve tener datos perfectos si están en un servidor al que solo accede un técnico.

7. **Integridad (Integrity)**: las relaciones entre conjuntos de datos son precisas. Si un pedido en una tabla apunta a un cliente que no existe en la tabla de clientes, hay un problema de integridad referencial.

**Desafíos comunes (los enemigos de la calidad):**

- **Duplicados**: el mismo cliente con tres filas distintas porque cargó su mail tres veces.
- **Valores faltantes**: nulls donde no deberían existir.
- **Errores de entrada**: tipeo humano sin validación.
- **Inconsistencia entre sistemas**: el problema arquetípico cuando hay CRM + ERP + planillas paralelas.
- **Datos desactualizados**: lo que estaba bien hace dos años hoy es ruido.

### 3.4 Big Data: las 3V → 5V

El término "Big Data" se popularizó después del paper seminal **"3D Data Management: Controlling Data Volume, Velocity, and Variety"** publicado por **Doug Laney** en META Group (luego absorbido por Gartner) en febrero de 2001. Laney describió tres dimensiones del problema:

- **Volumen**: la cantidad de datos crece exponencialmente (terabytes → petabytes → zettabytes).
- **Variedad**: ya no son solo tablas, son texto, imagen, video, IoT, social, geo, biométrico.
- **Velocidad**: los datos llegan en streaming, no en lotes mensuales como antes.

Con el tiempo (y a medida que el hype industrial necesitaba diferenciar), se agregaron dos V más para llegar a las **5V actuales**:

- **Veracidad**: ¿qué confianza tengo en estos datos? ¿Vienen de una fuente confiable? ¿Están limpios?
- **Valor**: ¿qué retorno de negocio puedo extraer? Esta es la V que más le importa al directorio, y la que la cátedra DIATO enfatiza como diferencial.

> Cruce con el capítulo 02 (Fundamentos de IA): allí ya vimos las 5V como input al pipeline de Machine Learning. Acá las miramos desde el lado **gestional**: cómo organizar la captura, el almacenamiento, la calidad y el aprovechamiento.

### 3.5 Datos cuantitativos vs cualitativos

| Cuantitativos | Cualitativos |
|---------------|--------------|
| Numéricos, medibles. | Descripción, atributos, percepciones. |
| Se prestan a estadística. | Se prestan a interpretación. |
| Ejemplo: encuesta NPS con escala 1-10. | Ejemplo: respuestas abiertas a "¿qué mejorarías?". |
| Herramienta clásica: Excel, SPSS, Power BI. | Herramienta clásica: NVivo, Atlas.ti, hoy también NotebookLM. |

Lo más rico —y lo que la cátedra subraya— es la **combinación**. Una encuesta de satisfacción que solo te da un NPS de 7 te dice menos que una que también incluye dos preguntas abiertas y te permite hacer análisis de sentimiento sobre las respuestas.

### 3.6 Métodos de recolección

**Cuantitativos:**

- **Encuestas y cuestionarios**: abiertas, cerradas, escala Likert (1-5 o 1-7).
- **Experimentos**: diseño experimental u observacional, ensayos controlados, A/B testing.
- **Observación estructurada**: definición de variables, muestreo, codificación.

**Cualitativos:**

- **Entrevistas**: estructuradas (cuestionario rígido), semiestructuradas (guía flexible), no estructuradas (conversación abierta).
- **Grupos focales**: 6-10 participantes, moderador, foco en dinámica grupal.
- **Observación participante**: etnografía, trabajo de campo, inmersión en el contexto.
- **Revisión documental**: documentos institucionales, fuentes históricas, archivos.

**Mixtos:**

- Combinan ambos enfoques.
- **Triangulación**: cruzar múltiples fuentes y métodos para validar una conclusión. Si la encuesta dice una cosa, las entrevistas otra y las ventas otra, sabés que el dato es inestable.

**Recolección automatizada:**

- **Apps y software**: Google Forms, SurveyMonkey, Typeform.
- **Sensores e IoT**: temperatura, geolocalización, presencia, vibración.
- **Web scraping y APIs**: para datos públicos, reseñas, precios de competencia, redes sociales.

**Consideraciones éticas (que vas a profundizar en el capítulo 11):**

- Privacidad y protección de datos personales (Ley 25.326 en Argentina).
- Consentimiento informado.
- Manejo de información sensible (salud, biométrica, ideología).
- Regulaciones locales e internacionales.

### 3.7 Evolución del tratamiento de datos (4 etapas)

La cátedra ofrece esta línea histórica útil para situarte:

1. **Búsquedas por "fuerza bruta"** (años 50-70): índices manuales, mainframes, lectura secuencial.
2. **Modelo relacional / SQL** (años 70-2000): Codd y la revolución de las bases relacionales.
3. **Universo heterogéneo de la web** (2000-2010): documentos, metadatos, buscadores, NoSQL.
4. **Big Data** (2010-hoy): volumen masivo, streaming, IA. Y ahora **IA generativa + bases vectoriales** como nuevo paradigma.

### 3.8 Herramientas mencionadas en la cátedra (con su lugar en el flujo)

| Herramienta | Para qué sirve | Dónde se usa |
|-------------|---------------|--------------|
| **Excelmatic** (excelmatic.ai) | Subís una planilla y le preguntás en lenguaje natural ("¿cuál fue el mes con más ventas en Patagonia?"). | Análisis exploratorio rápido sin saber SQL ni fórmulas. |
| **NotebookLM** (Google) | Cargás documentos (PDFs, notas, mails) y la IA los toma como **base de conocimiento cerrada** para responder con citas. | Análisis cualitativo, síntesis de reportes propios, análisis competitivo (capítulo 12). |
| **Sharly.ai** | Análisis de documentos largos con IA. | Compliance, due diligence, revisión de contratos. |
| **Tableau Public** | Visualización avanzada e interactiva. | Dashboards para decisión gerencial. |
| **ChatGPT / Gemini / Copilot** | Asistentes generales para procesamiento de texto. | Combinación con datos propios vía prompt o RAG. |
| **Flourish** | Visualizaciones embebibles para reportes y storytelling. | Comunicación de datos a audiencias no técnicas. |
| **Azure Vision** | Detección de objetos en imágenes. | Procesamiento de datos no estructurados visuales. |

## 4. Caso real organizacional

**Mercado Libre y su evolución hacia data-driven culture** (información pública, reportes anuales 2022-2025).

Mercado Libre genera más de **2 mil millones de eventos diarios** entre clicks, búsquedas, compras, mensajes, valoraciones y movimientos logísticos. Para convertir ese tsunami de datos en decisiones operó tres movimientos clásicos de **gestión estratégica de datos**:

1. **Data governance formalizado**: equipo central de "Data Council" con representantes de cada vertical (Marketplace, Mercado Pago, Mercado Envíos, Mercado Crédito). Reglas claras sobre quién es **dueño** de cada dataset, quién puede acceder, y quién garantiza la calidad.

2. **Data lake unificado**: en lugar de tener un silo de datos por país (Argentina, Brasil, México, Colombia, Chile), construyeron un único lake en la nube con los 7 criterios de calidad auditados continuamente.

3. **Democratización del acceso**: cualquier analista certificado puede consultar el lake con SQL o herramientas no-code. Esto redujo el tiempo de respuesta para preguntas de negocio de semanas (esperar al equipo de BI) a horas.

**Resultado medible**: la velocidad de iteración en pricing dinámico, segmentación de campañas y detección de fraude se aceleró drásticamente. Los modelos de Machine Learning de fraude, que antes se reentrenaban trimestralmente, hoy se reentrenan **diariamente** porque el pipeline de datos lo permite.

Lección para una PyME argentina: no necesitás el data lake de Mercado Libre. Pero sí necesitás **definir quién es dueño de cada dataset crítico**, **medir calidad de manera regular**, y **dar acceso a quienes lo necesitan para decidir**. Eso es gestión estratégica de datos, sin importar el tamaño de la empresa.

## 5. Aplicación a la transformación organizacional

Cuando una organización quiere "transformarse digitalmente" pero todavía no tiene gestión de datos, está construyendo sobre arena. Estos son los pasos para armar un **programa de gestión estratégica de datos** en tu organización:

### Paso 1 — Inventario y diagnóstico (semana 1 a 4)

- **Mapeá los datasets críticos**: ¿qué datos sostienen las decisiones diarias? (clientes, productos, transacciones, inventario, empleados).
- **Identificá los dueños actuales**: ¿quién los crea, los actualiza, los consume?
- **Medí calidad inicial**: para cada dataset, evaluá los 7 criterios con un score 1-5.
- **Detectá silos**: ¿hay versiones distintas del mismo dato en sistemas distintos?

### Paso 2 — Gobernanza mínima viable (mes 2 a 3)

- Nombrá **Data Owners** (responsables de negocio) y **Data Stewards** (responsables operativos) por dataset.
- Definí un **glosario de datos** con definiciones únicas: ¿qué quiere decir "cliente activo"? ¿qué quiere decir "venta cerrada"?
- Aprobá políticas básicas de **clasificación** (público / interno / confidencial / sensible).
- Conectá esto con el marco legal (capítulo 11): qué datos son personales según Ley 25.326.

### Paso 3 — Calidad como proceso (mes 3 en adelante)

- Implementá controles automáticos de validación al **momento de ingreso** (no después).
- Establecé un **dashboard de calidad** con los 7 criterios y un score por dataset, revisado mensualmente.
- Definí un proceso de **remediación**: cuando se detecta un problema, ¿quién lo arregla, en qué plazo?

### Paso 4 — Democratización con guardrails (mes 4 a 6)

- Habilitá acceso a herramientas como Excelmatic, NotebookLM o un BI con catálogo de datos.
- Capacitá a los usuarios de negocio en "data literacy" mínima: qué es un join, qué es un null, qué es un sesgo de muestreo.
- Mantené **logs de auditoría** sobre quién accede a qué (esto te va a servir para compliance, capítulo 11).

### Paso 5 — De información a conocimiento (mes 6 en adelante)

- Acá entra la IA: modelos de predicción, segmentación, recomendación.
- **Recién ahora** tiene sentido escalar IA, porque ya tenés datos de calidad sobre los cuales entrenar.
- Recordá: cualquier proyecto de IA arrancado **antes** de esta etapa tiene 80% de probabilidad de fracasar por mala calidad de datos (es la "paradoja de la generación IA" que vimos en el capítulo previo).

## 6. Errores comunes / mitos

- **"Más datos = mejor decisión"**. Falso. Datos de mala calidad amplifican el error. Mejor 10 mil registros limpios que 10 millones sucios.
- **"Los datos hablan solos"**. Falso. Sin un marco de interpretación (que es lo que aporta el conocimiento del negocio), los datos son ruido.
- **"Esto es problema del área de IT/Sistemas"**. Falso. La gestión de datos es **responsabilidad del negocio**. IT provee la infraestructura; el negocio define qué importa, qué es confiable y para qué se usa.
- **"Con un dashboard ya está"**. Falso. El dashboard es la punta del iceberg. Sin gobernanza, sin calidad y sin proceso de actualización, el dashboard se vuelve obsoleto en 3 meses.
- **"La IA va a resolver mi problema de datos"**. Mito peligroso. La IA **amplifica** lo que tenés. Si tenés caos, te va a dar caos a escala industrial. La gestión de datos viene primero, la IA viene después.
- **"Big Data es solo para Google y Amazon"**. Falso. Las **5V** aplican a cualquier organización que tenga ventas online, sensores IoT, redes sociales o múltiples sistemas. Una PyME santafesina con e-commerce ya enfrenta volumen, velocidad y variedad.
- **"Los datos no estructurados no se pueden usar"**. Falso. Era cierto hace 10 años. Hoy con LLMs y embeddings podés extraer información de mails, PDFs, audios y videos. De hecho, ahí está el 80% del valor sin explotar.

## 7. Checklist

Para empezar tu programa de gestión estratégica de datos, andá tachando:

- [ ] Identifiqué los 5 datasets más críticos de la organización.
- [ ] Cada uno tiene un **Data Owner** y un **Data Steward** asignados con nombre y apellido.
- [ ] Existe un glosario único de términos de negocio aprobado.
- [ ] Tengo un score inicial de los 7 criterios de calidad para cada dataset.
- [ ] Existen controles de validación en el momento de ingreso de datos.
- [ ] Hay un dashboard de calidad revisado al menos mensualmente.
- [ ] Existe un proceso documentado para remediar problemas de calidad.
- [ ] Los datos personales están clasificados y cumplen Ley 25.326 (ver capítulo 11).
- [ ] El acceso a datos sensibles está auditado y log-trazado.
- [ ] Los usuarios de negocio tienen capacitación básica en data literacy.
- [ ] Hay un canal claro para reportar problemas de calidad de datos.
- [ ] Ningún proyecto de IA se lanza sin auditoría previa de la calidad de los datos que va a consumir.

## 8. Para profundizar

- **Ackoff, R. (1989). *"From Data to Wisdom"*. Journal of Applied Systems Analysis**. Paper fundacional de la pirámide DIKW.
- **Laney, D. (2001). *"3D Data Management: Controlling Data Volume, Velocity, and Variety"*. META Group / Gartner**. El paper que parió el término "Big Data" tal como lo usamos hoy.
- **DAMA International. *DAMA-DMBOK: Data Management Body of Knowledge (2nd Edition)*. Technics Publications**. La biblia profesional del data management. Si vas en serio, conseguila.
- **Sitio oficial DAMA International**: dama.org —incluye certificaciones (CDMP) y comunidades locales.
- **Wang, R. & Strong, D. (1996). *"Beyond Accuracy: What Data Quality Means to Data Consumers"*. Journal of Management Information Systems**. El paper clásico que sistematizó las dimensiones de calidad de datos.
- **NotebookLM** (notebooklm.google.com) — probalo con tus propios PDFs antes del capítulo 12.
- **Excelmatic** (excelmatic.ai) — para practicar el "consultá tu Excel en lenguaje natural".
- **DataGovernance.com** — comunidad y artículos sobre gobierno de datos.

## Próximo paso

En el [capítulo 11](./11-etica-privacidad-marco-legal-ar.md) vamos a tomar el dato como activo —que ya conocés— y meterlo en el laberinto normativo más denso del programa: **Ley 25.326**, AAIP, EU AI Act, Convenio 108+, y los frameworks operativos que la cátedra te exige (Semáforo de decisiones, Arquitectura del Agente Profesional, 4 tipos de sesgos). Si gestionar datos sin ética es construir sobre arena, gestionar datos sin marco legal es construir sobre arenas movedizas.

## Referencias

- Ackoff, R. L. (1989). *From Data to Wisdom*. Journal of Applied Systems Analysis, 16, 3-9.
- Laney, D. (2001). *3D Data Management: Controlling Data Volume, Velocity, and Variety*. META Group Research Note, 6.
- DAMA International (2017). *DAMA-DMBOK: Data Management Body of Knowledge* (2nd ed.). Technics Publications.
- Material de cátedra DIATO — Módulo 7, Pres 1 y Pres 2 (Mg. Luis Ferrario y Lic. Carina Barbero, UNRaf 2026).
- World Economic Forum (2011). *Personal Data: The Emergence of a New Asset Class*.
- Wang, R. Y., & Strong, D. M. (1996). *Beyond Accuracy: What Data Quality Means to Data Consumers*. Journal of Management Information Systems, 12(4), 5-33.
