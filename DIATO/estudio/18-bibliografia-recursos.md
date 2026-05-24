# 18 — Bibliografía y recursos: guía de USO

> Esto NO es una lista alfabética. Es una **guía de uso**: para cada referencia te digo **qué cubre**, **a qué capítulo del estudio (`01`-`14`) le sirve**, **nivel** (intro / intermedio / avanzado) y **dónde y cómo conseguirla** (en particular, si hay versión gratis online).
>
> URLs verificadas en mayo de 2026. Si una se cae, buscá por título — los recursos institucionales suelen mantener URLs estables aunque cambien dominio.

> **Cómo navegar este archivo**:
> 1. Si necesitás un libro de cabecera, mirá las **categorías 1–3** (fundamentos técnicos).
> 2. Si querés profundizar marcos organizacionales, **categorías 4–7**.
> 3. Si tu TPI pide compliance/normativa, **categorías 8–9**.
> 4. Para herramientas operativas, **categoría 10**.
> 5. Si querés contenido **en español**, **categoría 11**.
> 6. URLs sueltas y autodiagnósticos al final, **categoría 12**.

---

# 1. Fundamentos técnicos de IA

## 1.1 Russell, S. & Norvig, P. — *Artificial Intelligence: A Modern Approach* (4th ed., 2020)

- **Qué cubre**: el libro de cabecera mundial sobre IA. Cubre agentes, búsqueda, lógica, planeamiento, conocimiento, razonamiento bajo incertidumbre, ML, percepción, robótica, ética. Es **EL** estándar académico.
- **Capítulos DIATO**: `01` (definición de IA, agentes, tipos), `02` (ML), `03` (DL), `12` (ética).
- **Nivel**: avanzado. Es técnico, denso, matemático. No es lectura de café.
- **Disponibilidad**: el libro completo es **pago** (Pearson/Amazon). El sitio oficial Berkeley (`aima.cs.berkeley.edu`) ofrece **gratis**: tabla de contenidos completa, índice, capítulo 0 (introducción), recursos pedagógicos, código de ejemplo en Python/Java/JavaScript, ejercicios interactivos, traducciones.
- **URL oficial**: <https://aima.cs.berkeley.edu/>
- **Cuándo usarlo**: cuando una idea de la cátedra te quede floja o ambigua y necesites la definición canónica de referencia (especialmente "agente racional", taxonomías de aprendizaje, conceptos de búsqueda).

## 1.2 Géron, A. — *Hands-On Machine Learning with Scikit-Learn, Keras & TensorFlow* (3rd ed., O'Reilly, 2022)

- **Qué cubre**: el manual práctico más usado del mundo para construir modelos de ML y DL en Python. Cubre regresión, clasificación, árboles, random forest, SVM, redes neuronales, CNN, RNN, transformers, autoencoders, GANs, diffusion models, RL.
- **Capítulos DIATO**: `02` (ML completo), `03` (DL: CNN, transformers), `07` (preprocesamiento de datos).
- **Nivel**: intermedio-práctico. Asume Python básico y matemática de secundaria avanzada. Es de los pocos libros que te lleva de cero a producción.
- **Disponibilidad**: el libro es **pago** (O'Reilly). El **código completo** y los **notebooks Jupyter** del autor son gratis y abiertos.
- **URL código (gratis)**: <https://github.com/ageron/handson-ml3>
- **URL libro (pago)**: <https://www.oreilly.com/library/view/hands-on-machine-learning/9781098125967/>
- **Cuándo usarlo**: si en algún momento querés pasar de hablar de ML a *construir* un modelo, este es el atajo.

## 1.3 Andrew Ng — *Machine Learning Specialization* (Coursera, Stanford + DeepLearning.AI)

- **Qué cubre**: 3 cursos: (1) ML supervisado: regresión y clasificación; (2) algoritmos avanzados de aprendizaje (redes neuronales, árboles); (3) ML no supervisado, recomendadores y RL. Es la versión actualizada del legendario curso original de Ng (2012, 4.8M alumnos).
- **Capítulos DIATO**: `02`, `03`.
- **Nivel**: intermedio. Requiere matemática básica y Python.
- **Disponibilidad**: **gratis en modo audit** (videos + lecturas; sin quizzes graded ni certificado). Certificado: pago, ~USD 49/mes con suscripción Coursera.
- **URL**: <https://www.coursera.org/specializations/machine-learning-introduction>

## 1.4 Andrew Ng — *Generative AI for Everyone* (Coursera, DeepLearning.AI)

- **Qué cubre**: curso introductorio NO técnico sobre IA generativa: qué es, cómo funcionan los LLM, dónde aplicarlos, limitaciones, ética, casos de negocio. Sin código.
- **Capítulos DIATO**: `04` (prompt engineering, IAG), `12` (ética IA), `14` (futuro del trabajo).
- **Nivel**: intro. Ideal para mandos medios o no-técnicos.
- **Disponibilidad**: **gratis en modo audit**.
- **URL**: <https://www.coursera.org/learn/generative-ai-for-everyone>
- **Cuándo usarlo**: si tenés que explicarle IAG a un directorio, este curso te da el guion y los argumentos.

---

# 2. Big Data y gestión estratégica de datos

## 2.1 Marr, B. — Serie *Big Data* / *Data Strategy*

- **Qué cubre**: Bernard Marr es uno de los autores más prolíficos sobre Big Data aplicado a negocio. Sus libros más relevantes: *Big Data: Using SMART big data, analytics and metrics to make better decisions and improve performance* (2015), *Big Data in Practice* (2016) y *Data Strategy: How to Profit from a World of Big Data, Analytics and AI* (2nd/3rd ed., 2022/2024). Foco: cómo armar una estrategia de datos práctica para tu organización.
- **Capítulos DIATO**: `01` (Big Data), `07` (datos), `14` (estrategia organizacional).
- **Nivel**: intermedio, orientado a managers/decisores. Lectura ágil, sin ecuaciones.
- **Disponibilidad**: libros **pagos** (Amazon, Wiley). El sitio del autor publica **capítulos sampler gratuitos** en PDF.
- **URL sampler gratis**: <https://bernardmarr.com/big-data/>
- **Sitio autor**: <https://bernardmarr.com/>

## 2.2 DAMA International — *DAMA-DMBOK: Data Management Body of Knowledge* (2nd ed., 2017)

- **Qué cubre**: la "biblia" del data management. Cubre gobernanza, calidad, arquitectura de datos, modelado, integración, metadatos, master data, ciclo de vida. Es **el** marco operativo de la disciplina.
- **Capítulos DIATO**: `07` (datos completo), `08` (arquitectura), `10` (control de gestión).
- **Nivel**: avanzado-operativo. Es referencia, no lectura corrida.
- **Disponibilidad**: libro **pago** (DAMA International / Technics Publications). ISBN 1634622340.
- **Cuándo usarlo**: si tu TPI o trabajo profesional toca **gobierno de datos** y necesitás vocabulario formal y reconocido internacionalmente.

---

# 3. IA Generativa — guías oficiales (gratis)

## 3.1 Anthropic — *Prompt Engineering Guide* (oficial Claude)

- **Qué cubre**: técnicas de prompting específicas para Claude: uso de XML tags, role prompting, chain-of-thought, few-shot, evidencia antes de conclusión, etc. Es **gratis y muy práctico**.
- **Capítulos DIATO**: `04` (prompt engineering, ROCEF).
- **Nivel**: intermedio. Requiere haber usado un LLM.
- **Disponibilidad**: **gratis online**, sin login.
- **URLs**:
  - Guía oficial: <https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview>
  - Tutorial interactivo en GitHub: <https://github.com/anthropics/prompt-eng-interactive-tutorial>
- **Cuándo usarlo**: cuando tus prompts en ROCEF no dan resultado y querés llevarlos al siguiente nivel con técnicas avanzadas.

## 3.2 OpenAI — *Prompt Engineering Guide* y *Best Practices*

- **Qué cubre**: estrategias oficiales OpenAI: escribir instrucciones claras, dar referencias, dividir tareas complejas, dar tiempo de pensar al modelo (CoT), testing sistemático.
- **Capítulos DIATO**: `04`.
- **Nivel**: intro-intermedio.
- **Disponibilidad**: **gratis online**.
- **URLs**:
  - Best Practices: <https://help.openai.com/en/articles/6654000-best-practices-for-prompt-engineering-with-the-openai-api>
  - Guía API: <https://platform.openai.com/docs/guides/prompt-engineering>
  - GPT-4.1 prompting (avanzado): <https://cookbook.openai.com/examples/gpt4-1_prompting_guide>
- **Cuándo usarlo**: comparalo con la guía de Anthropic — vas a notar diferencias de estilo que te ayudan a entender qué es universal y qué es específico de cada modelo.

---

# 4. Reingeniería y procesos (clásicos imprescindibles)

## 4.1 Hammer, M. & Champy, J. — *Reengineering the Corporation: A Manifesto for Business Revolution* (HarperBusiness, 1993)

- **Qué cubre**: el libro que fundó el movimiento de **BPR (Business Process Reengineering)**. Tesis central: no basta con automatizar procesos existentes, hay que **rediseñarlos radicalmente** aprovechando la tecnología.
- **Capítulos DIATO**: `06` (procesos), `09` (automatización), `14` (transformación organizacional).
- **Nivel**: intermedio. Lectura clásica, en estilo manifiesto. Es la fuente conceptual del "**no automatices ineficiencias**" que repite la cátedra.
- **Disponibilidad**: libro **pago**. Ediciones revisadas posteriores con prefacios actualizados.
- **Cuándo usarlo**: para defender por qué *primero rediseñás, después automatizás* — Hammer ya lo dijo en 1993.

## 4.2 Davenport, T. — *Process Innovation: Reengineering Work through Information Technology* (Harvard Business School Press, 1993)

- **Qué cubre**: junto con Hammer & Champy, el otro pilar del BPR. Davenport pone más énfasis en la **innovación con IT** (no solo radicalismo). Cubre cómo identificar procesos clave, rediseñarlos y gestionar el cambio.
- **Capítulos DIATO**: `06`, `08`, `09`.
- **Nivel**: intermedio.
- **Disponibilidad**: libro **pago**. Es la referencia más citada después de Hammer.
- **Cuándo usarlo**: si tu TPI propone un rediseño de proceso, citarlo te da peso académico.

---

# 5. Estrategia y ambidestreza organizacional

## 5.1 O'Reilly, C.A. & Tushman, M.L. — *Lead and Disrupt: How to Solve the Innovator's Dilemma* (Stanford Business Books, 2016; 2nd ed. 2021)

- **Qué cubre**: la fuente canónica del concepto de **ambidestreza organizacional**. Explica cómo las empresas exitosas equilibran **explotar** capacidades actuales y **explorar** nuevas. Casos: IBM, Ciba Vision, USA Today, etc.
- **Capítulos DIATO**: `05` (estrategia), `14` (transformación).
- **Nivel**: intermedio. Estilo Stanford Business: claro, basado en casos.
- **Disponibilidad**: libro **pago**. La 2nd ed. (2021) añade caso de transformación digital.
- **URL editorial**: <https://www.sup.org/books/business/lead-and-disrupt>
- **Cuándo usarlo**: para fundamentar académicamente el ejercicio cátedra "Universidad explota carreras actuales + explora carreras del futuro".

## 5.2 Cohen, W.M. & Levinthal, D.A. — *Absorptive Capacity: A New Perspective on Learning and Innovation* (Administrative Science Quarterly, 1990, 35(1), pp. 128-152)

- **Qué cubre**: el paper seminal que introdujo el concepto de **capacidad de absorción**: la habilidad de una firma para reconocer el valor de nueva información externa, asimilarla y aplicarla con fines comerciales. Mostró que esta capacidad depende del conocimiento previo y predice innovación mejor que el simple presupuesto de I+D.
- **Capítulos DIATO**: `05` (núcleo conceptual de Costamagna/Berra).
- **Nivel**: avanzado. Es paper académico denso, ~24 páginas.
- **Disponibilidad**: paper **pago** vía JSTOR. PDF públicos académicos disponibles en repos universitarios.
- **URL PDF académico**: <https://josephmahoney.web.illinois.edu/BA545_Fall%202022/Cohen%20and%20Levinthal%20(1990).pdf>
- **Cuándo usarlo**: para citar la base académica detrás de "capacidad de absorción" en defensa de TPI.

---

# 6. McKinsey, Deloitte, Gartner — los grandes reportes

## 6.1 McKinsey — *The State of Organizations 2026* (2nd edition, McKinsey & Company)

- **Qué cubre**: encuesta a 10.000+ ejecutivos en 15 países, 16 industrias. Marco: **3 fuerzas tectónicas + 9 shifts** que están remodelando las organizaciones. Casos: Allianz, Hitachi, Moderna, Walmart, Tonies, Rolls-Royce. Es el reporte organizacional más comprensivo del año.
- **Capítulos DIATO**: `05` (estrategia), `09` (operating model), `14` (transformación, futuro del trabajo).
- **Nivel**: intermedio. Lectura ejecutiva, 74 páginas.
- **Disponibilidad**: **gratis** descarga directa.
- **URL PDF oficial**: <https://www.mckinsey.com/~/media/mckinsey/business%20functions/people%20and%20organizational%20performance/our%20insights/the%20state%20of%20organizations/2026/the-state-of-organizations-2026.pdf>
- **URL página resumen**: <https://www.mckinsey.com/capabilities/people-and-organizational-performance/our-insights/the-state-of-organizations>
- **Cuándo usarlo**: como marco general en la sección "Contexto" del TPI y para sustentar predicciones sobre tu sector.

## 6.2 Deloitte — *Tech Trends 2026* (17th annual edition)

- **Qué cubre**: 5 tendencias tecnológicas + capítulo de señales débiles. Foco: pasar de la experimentación al impacto medible. Datos estadísticos densos (800M usuarios IA, 280x reducción costo inferencia, etc.).
- **Capítulos DIATO**: `08` (arquitectura), `09` (automatización), `11` (tendencias), `12` (seguridad).
- **Nivel**: intermedio.
- **Disponibilidad**: **gratis** descarga directa.
- **URL PDF oficial**: <https://mkto.deloitte.com/rs/712-CNF-326/images/DI_Tech-trends-2026.pdf>
- **URL página oficial**: <https://www.deloitte.com/us/en/insights/topics/technology-management/tech-trends.html>
- **Cuándo usarlo**: para la sección "Estado del arte" del TPI; las **quotes de CIOs** son oro para citar.

## 6.3 Gartner — *Hype Cycle for Artificial Intelligence* / *Hype Cycle for Agentic AI*

- **Qué cubre**: visualización de la madurez de tecnologías IA en el ciclo (Innovation Trigger → Peak of Inflated Expectations → Trough of Disillusionment → Slope of Enlightenment → Plateau of Productivity). Útil para evitar comprar el hype.
- **Capítulos DIATO**: `11` (tendencias), `05` (estrategia tecnológica).
- **Nivel**: intermedio-decisor.
- **Disponibilidad**: el reporte completo es **pago** (Gartner subscription). El **gráfico anual y los artículos resumen** son gratis en el sitio.
- **URLs**:
  - Hype Cycle AI: <https://www.gartner.com/en/articles/hype-cycle-for-artificial-intelligence>
  - Hype Cycle Agentic AI: <https://www.gartner.com/en/articles/hype-cycle-for-agentic-ai>
- **Cuándo usarlo**: cuando un proveedor o partner te venda "la última tecnología de IA" — chequeá dónde está en el Hype Cycle.

## 6.4 World Economic Forum — *Organizational Transformation in the Age of AI* (2026)

- **Qué cubre**: marco para que las organizaciones maximicen el potencial de IA. 5 ejes: experiencia del cliente, operaciones, R&D, planeamiento estratégico, talento. Colaboración WEF + Accenture, 43 páginas.
- **Capítulos DIATO**: `05`, `09`, `14`.
- **Nivel**: intermedio.
- **Disponibilidad**: **gratis** descarga directa.
- **URL PDF oficial**: <https://reports.weforum.org/docs/WEF_Organizational_Transformation_in_the_Age_of_AI_How_Organizations_Maximize_AI's_Potential_2026.pdf>
- **URL página**: <https://www.weforum.org/publications/organizational-transformation-in-the-age-of-ai-how-organizations-maximize-ais-potential/>
- **Cuándo usarlo**: como segundo marco (junto con McKinsey) para diagnosticar madurez organizacional.

## 6.5 McKinsey — *Seizing the Agentic AI Advantage* / *Un año de IA agéntica*

- **Qué cubre**: estado del arte de la **IA agéntica** en organizaciones. "Seis lecciones de quienes están haciendo el trabajo". Datos: solo 11% en producción, 38% pilotando, 42% definiendo estrategia.
- **Capítulos DIATO**: `01` (agentes), `09` (automatización agéntica), `11` (tendencias).
- **Nivel**: intermedio-decisor.
- **Disponibilidad**: **gratis** vía McKinsey (la versión en español está en campus DIATO).
- **URL público**: <https://www.mckinsey.com/capabilities/quantumblack/our-insights/seizing-the-agentic-ai-advantage>
- **Cuándo usarlo**: si tu TPI propone agentes IA, citá este reporte para mostrar conciencia del estado del arte.

---

# 7. Tendencias y futuro del trabajo (complementarios)

## 7.1 *The AI Labor Playbook* (2025)

- **Qué cubre**: playbook breve sobre impacto de IA en el trabajo: roles afectados, skills emergentes, recomendaciones para empleadores y empleados.
- **Capítulos DIATO**: `14`.
- **Nivel**: intro.
- **Disponibilidad**: PDF distribuido en aula virtual DIATO; original abril 2025.

## 7.2 BID — *Tech Report: IA Generativa* (LATAM)

- **Qué cubre**: visión institucional del Banco Interamericano de Desarrollo sobre IAG en América Latina. Útil para casos regionales y políticas públicas.
- **Capítulos DIATO**: `04`, `12`, `14`.
- **Nivel**: intermedio.
- **Disponibilidad**: PDF en campus DIATO; reportes BID disponibles en su biblioteca digital.
- **URL biblioteca BID**: <https://publications.iadb.org/>
- **Cuándo usarlo**: si tu TPI tiene foco LATAM o políticas públicas, este reporte te da el ángulo regional.

---

# 8. Normativa y compliance — Argentina

## 8.1 Resolución AAIP 161/2023 + *Guía AAIP para una IA Responsable* (junio 2024)

- **Qué cubre**: la resolución crea el **Programa Nacional de Transparencia y Protección de Datos Personales en el uso de la IA**. La Guía (junio 2024) operacionaliza el ciclo de vida del sistema IA en 4 etapas + **Ficha de transparencia** (3 secciones).
- **Capítulos DIATO**: `12` (núcleo absoluto).
- **Nivel**: intermedio-jurídico, lectura accesible para no-abogados.
- **Disponibilidad**: **gratis y oficial**.
- **URLs**:
  - Resolución 161/2023 (texto oficial): <https://www.argentina.gob.ar/normativa/nacional/resoluci%C3%B3n-161-2023-389231/texto>
  - Boletín Oficial: <https://www.boletinoficial.gob.ar/detalleAviso/primera/293363/20230904>
  - Programa Nacional: <https://www.argentina.gob.ar/programa-nacional-de-transparencia-y-proteccion-de-datos-personales-en-el-uso-de-la-inteligencia>
  - Noticia oficial Guía: <https://www.argentina.gob.ar/noticias/guia-de-la-aaip-para-usar-la-inteligencia-artificial-de-manera-responsable>
- **Cuándo usarlo**: si tu TPI toca datos personales (clientes, empleados, leads), citarlo es **obligatorio** para mostrar compliance.

## 8.2 Ley 25.326 — *Protección de Datos Personales* (Argentina, 2000)

- **Qué cubre**: marco general de protección de datos en Argentina. 7 principios (licitud, consentimiento, finalidad, calidad, seguridad, confidencialidad, minimización). Derechos: acceso, rectificación, oposición.
- **Capítulos DIATO**: `12`.
- **Nivel**: jurídico básico.
- **Disponibilidad**: **gratis y oficial**.
- **URL InfoLeg**: <http://servicios.infoleg.gob.ar/infolegInternet/anexos/60000-64999/64790/norma.htm>
- **Sitio AAIP**: <https://www.argentina.gob.ar/aaip>
- **Cuándo usarlo**: junto con Resolución 161/2023, son tu base normativa argentina.

## 8.3 Constitución Nacional Argentina (arts. 14 bis, 16, 43) + Ley 23.592 (Actos Discriminatorios)

- **Qué cubre**: Art. 14 bis (derecho al trabajo digno), 16 (igualdad ante la ley), 43 (habeas data). Ley 23.592 prohíbe discriminación arbitraria — aplica al sesgo algorítmico.
- **Capítulos DIATO**: `12`.
- **Disponibilidad**: **gratis y oficial** vía InfoLeg.
- **URL CN**: <https://www.argentina.gob.ar/normativa/nacional/constitucion-nacional-804>

---

# 9. Normativa y marcos internacionales

## 9.1 EU AI Act — Reglamento (UE) 2024/1689

- **Qué cubre**: primera regulación comprensiva mundial sobre IA. Enfoque basado en riesgo (4 niveles: inaceptable, alto, limitado, mínimo). Aplicación plena: 2-ago-2026.
- **Capítulos DIATO**: `12`.
- **Nivel**: jurídico denso. Para uso práctico mejor leer resúmenes o el AI Act Explorer.
- **Disponibilidad**: **gratis y oficial** en todos los idiomas UE.
- **URLs**:
  - EUR-Lex (texto oficial): <https://eur-lex.europa.eu/eli/reg/2024/1689/oj/eng>
  - PDF directo: <https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=OJ:L_202401689>
  - AI Act Explorer (navegable): <https://artificialintelligenceact.eu/ai-act-explorer/>
- **Cuándo usarlo**: si tu cliente vende a Europa o si querés establecer un estándar exportable, citarlo te posiciona.

## 9.2 Convenio 108+ del Consejo de Europa (modernizado 2018)

- **Qué cubre**: tratamiento automatizado de datos, perfilado, decisiones automatizadas, transparencia, evaluación de impacto. Argentina lo ratificó por Ley 27.699 (2022).
- **Capítulos DIATO**: `12`.
- **Disponibilidad**: **gratis y oficial**.
- **URL Council of Europe**: <https://www.coe.int/en/web/data-protection/convention108-and-protocol>
- **Cuándo usarlo**: para mostrar que Argentina está alineada con el estándar europeo aunque la ley local sea antigua.

## 9.3 GDPR / RGPD — Reglamento Europeo (2016/2018)

- **Qué cubre**: el reglamento europeo de protección de datos. Define derecho al olvido, consentimiento estricto, transparencia algorítmica, evaluación de impacto.
- **Capítulos DIATO**: `12`.
- **Disponibilidad**: **gratis y oficial**.
- **URL**: <https://gdpr-info.eu/>

## 9.4 UNESCO — *Recomendación sobre la Ética de la IA* (2021)

- **Qué cubre**: marco global de principios éticos para IA. Argentina adhirió.
- **Capítulos DIATO**: `12`.
- **Disponibilidad**: **gratis**.
- **URL**: <https://www.unesco.org/en/artificial-intelligence/recommendation-ethics>

## 9.5 OCDE — *Principios sobre IA* (2019)

- **Qué cubre**: 5 principios para IA confiable + 5 recomendaciones para gobiernos. Argentina adhirió.
- **Capítulos DIATO**: `12`.
- **Disponibilidad**: **gratis**.
- **URL**: <https://oecd.ai/en/ai-principles>

---

# 10. Herramientas operativas (con documentación oficial)

## 10.1 n8n — *Workflow automation platform*

- **Qué cubre**: documentación oficial de la plataforma de automatización fair-code, self-hosted, con 400+ integraciones e IA agéntica nativa (LangChain). Hay versión community gratis.
- **Capítulos DIATO**: `09` (automatización).
- **Nivel**: intermedio-técnico.
- **Disponibilidad**: **gratis** (docs + community edition).
- **URLs**:
  - Sitio: <https://n8n.io/>
  - Docs: <https://docs.n8n.io/>
  - GitHub: <https://github.com/n8n-io/n8n>
  - Comunidad: <https://community.n8n.io/>
- **Cuándo usarlo**: si tu TPI plantea automatización, n8n self-hosted es la opción de ROI más alto para PyMEs.

## 10.2 Disco Fluxicon — *Process Mining*

- **Qué cubre**: herramienta clásica de minería de procesos. Sube un log de eventos (XES/CSV), te muestra el proceso real con frecuencias, tiempos, variantes.
- **Capítulos DIATO**: `06` (procesos), `07` (datos).
- **Disponibilidad**: **gratis para uso académico** (licencia para estudiantes y profesores de universidades partner, incluido UNRaf).
- **URLs**:
  - Sitio: <https://fluxicon.com/disco/>
  - Programa académico: <https://fluxicon.com/academic/>
- **Cómo conseguirlo**: descargás Disco, lo instalás, te registrás con email institucional UNRaf (`@unraf.edu.ar`) y pedís licencia académica.
- **Cuándo usarlo**: si tu TPI propone optimizar procesos, traer un log de eventos analizado con Disco te diferencia.

## 10.3 NotebookLM — Google

- **Qué cubre**: asistente IA que crea una "base de conocimiento" a partir de tus documentos (PDFs, links, Google Docs). Hace resúmenes, preguntas, briefings, podcasts. RAG visual sin código.
- **Capítulos DIATO**: `04`, `05` (ejercicios cátedra Costamagna), `07`.
- **Disponibilidad**: **gratis** con cuenta Google. Versión paga (NotebookLM Plus) para uso intensivo.
- **URL**: <https://notebooklm.google.com/>

## 10.4 Miro y Napkin.ai

- **Miro**: pizarra colaborativa para diagramas de flujo, BPMN, journey maps. Plan gratis con limitaciones. URL: <https://miro.com/>
- **Napkin.ai**: convierte texto en diagramas visuales automáticamente. Gratis. URL: <https://www.napkin.ai/>
- **Capítulos DIATO**: `06` (ejercicio cátedra Zinggerling — proceso de solicitud de personal).

## 10.5 Excelmatic, Tableau Public, Flourish, Google AI Studio

- **Excelmatic**: subís una planilla y le hacés preguntas en lenguaje natural. Gratis con limitaciones. URL: <https://excelmatic.ai/es/>
- **Tableau Public**: BI gratis, requiere publicar dashboards en público. URL: <https://public.tableau.com/>
- **Flourish**: visualizaciones para storytelling de datos. Plan gratis. URL: <https://flourish.studio/>
- **Google AI Studio**: para experimentar con la API de Gemini, prompting y agentes. Gratis con cuenta Google. URL: <https://aistudio.google.com/>
- **Capítulos DIATO**: `07`, `10` (control de gestión).

## 10.6 Azure AI Vision Demo

- **Qué cubre**: demo gratuito de visión por computador (detección de objetos genéricos) de Microsoft Azure.
- **URL**: <https://portal.vision.cognitive.azure.com/demo/generic-object-detection>
- **Capítulos DIATO**: `03` (DL aplicado).

---

# 11. Recursos en español (Argentina y región)

## 11.1 UTN BA — *Diplomatura en Inteligencia Artificial* y cursos relacionados

- **Qué cubre**: UTN Buenos Aires ofrece una diplomatura completa + varios cursos sueltos (IA Aplicada, Transformación Digital con IA, IA para Programadores, IA para Empresas y Negocios). En **español**, modalidad **e-learning** con clases en vivo + asincrónico, tutorías y certificación oficial UTN.
- **Capítulos DIATO**: `02`, `03`, `04`, `09`, `14`.
- **Nivel**: intro a intermedio.
- **Disponibilidad**: **paga** (con cuotas). Algunos cursos sueltos accesibles para PyMEs.
- **URLs**:
  - Diplomatura: <https://sceu.frba.utn.edu.ar/e-learning/detalle/diplomatura/4333/diplomatura-en-inteligencia-artificial>
  - IA Aplicada: <https://sceu.frba.utn.edu.ar/e-learning/detalle/curso/35141/curso-de-inteligencia-artificial-aplicada>
  - Listado completo: <https://sceu.frba.utn.edu.ar/e-learning/listado>
- **Cuándo usarlo**: si querés seguir formándote en español tras DIATO, son los más alineados con perfil business.

## 11.2 UBA — Cursos de IA (Secretaría de Ciencia y Técnica, UBA IA LAB)

- **Qué cubre**: la UBA ofrece cursos cortos sobre IA, incluyendo **Programación en IA** (50 hs, 2 meses) que cubre redes neuronales, ML, data science y ética. También cursos institucionales más amplios.
- **Capítulos DIATO**: `02`, `03`, `12`.
- **Disponibilidad**: **gratis o muy bajo costo** según convocatoria.
- **URLs**:
  - Curso UBA IA LAB: <https://cyt.rec.uba.ar/curso-ia/>
- **Cuándo usarlo**: opción gratuita o muy accesible para complementar formación técnica.

## 11.3 Pedreño, A. & Moreno, L. — *Europa frente a EE.UU. y China: Prevenir el declive en la era de la Inteligencia Artificial* (2019/2020)

- **Qué cubre**: visión geopolítica de la carrera de IA desde España. Útil para entender por qué LATAM debe armar estrategia propia.
- **Capítulos DIATO**: `05`, `14`.
- **Nivel**: ensayo, accesible.
- **Disponibilidad**: **pago** (Amazon, librerías españolas). Hay edición Kindle más barata.

## 11.4 *Libro Blanco de la Inteligencia Artificial Generativa* (COIT, España)

- **Qué cubre**: marco español sobre IA generativa, redactado por el Colegio Oficial de Ingenieros de Telecomunicación. Cubre arquitectura, casos de uso, ética, regulación. En español, accesible.
- **Capítulos DIATO**: `04`, `12`.
- **Disponibilidad**: **gratis online**, PDF oficial.
- **URL**: <https://www.coit.es/sites/default/files/digitales_libro_blanco_ia_generativa.pdf>

## 11.5 Enrique Dans — Blog y libros

- **Qué cubre**: profesor de IE Business School, autor prolífico en español sobre transformación digital, IA y negocio. Blog actualizado casi diariamente.
- **Capítulos DIATO**: `05`, `09`, `14`.
- **Disponibilidad**: **blog gratis online**; libros pagos.
- **URL blog**: <https://www.enriquedans.com/>
- **Cuándo usarlo**: para mantenerte al día en español con análisis de coyuntura sobre IA y negocio.

## 11.6 BID — Publicaciones IA y transformación digital (en español)

- **Qué cubre**: el Banco Interamericano de Desarrollo publica regularmente reportes en español sobre IA, datos y transformación digital en LATAM.
- **URL biblioteca**: <https://publications.iadb.org/es>

---

# 12. URLs útiles del file `links` (campus DIATO) + autodiagnósticos

## 12.1 Artículos

- **¿Qué es la transformación digital? — SAP**: <https://www.sap.com/spain/insights/what-is-digital-transformation.html>
  - Capítulos DIATO: `06`. Nivel: intro. Gratis.
- **WEF — Organizational Transformation in the Age of AI 2026**: <https://reports.weforum.org/docs/WEF_Organizational_Transformation_in_the_Age_of_AI_How_Organizations_Maximize_AI's_Potential_2026.pdf>
- **McKinsey — Un año de IA agéntica (en español)**: distribuido en aula virtual DIATO. URL inglés: <https://www.mckinsey.com/capabilities/quantumblack/our-insights/seizing-the-agentic-ai-advantage>

## 12.2 Autodiagnósticos de Madurez Digital (Argentina)

Útiles para la sección opcional "evaluación inicial de madurez digital" del TPI.

- **AMD IndTech Argentina** — autodiagnóstico nacional industria 4.0: <https://amdindtech.ar/>
- **Programa Industria Digital Santa Fe**: <https://www.santafe.gob.ar/ind-digital/>
- **UNL Chequeo Digital**: <https://servicios.unl.edu.ar/chequeo>
- **Cuándo usarlos**: corré el cuestionario con tu cliente del TPI antes de la sección "Contexto" — el resultado te da el baseline cuantitativo gratis.

## 12.3 Repositorio UNRaf — Gestión de procesos

- **Repositorio UNRaf**: <https://repositorio.unraf.edu.ar/items/e19497c4-f61c-4461-b1c1-4cdc83717731>
- Cuándo usarlo: para encontrar materiales académicos UNRaf que complementen el módulo 4.

---

# 13. Recursos extra mencionados en el corpus DIATO

## 13.1 fAIr LAC (BID) — *Hub de IA ética para LATAM*

- **Qué cubre**: tiene autoevaluación ética para PyMEs y materiales sobre IA responsable en la región.
- **URL**: <https://fairlac.iadb.org/>

## 13.2 Stanford HAI — *AI Index Report*

- **Qué cubre**: el reporte anual más completo sobre el estado mundial de IA (inversión, papers, talento, regulación, sentimiento público).
- **Capítulos DIATO**: `11`, `14`.
- **Disponibilidad**: **gratis**.
- **URL**: <https://aiindex.stanford.edu/>

## 13.3 IAPP — *Global AI Legislation Tracker*

- **Qué cubre**: mapa de regulación IA por país, actualizado continuamente. International Association of Privacy Professionals.
- **Capítulos DIATO**: `12`.
- **URL**: <https://iapp.org/resources/article/global-ai-legislation-tracker/>

## 13.4 Tortoise Media — *Global AI Index*

- **Qué cubre**: ranking de países por capacidad y estrategia IA. Útil para evaluar proveedores por país.
- **URL**: <https://www.tortoisemedia.com/intelligence/global-ai/>

## 13.5 DataGuidance (OneTrust)

- **Qué cubre**: base de datos jurisdiccional de regulación de datos por país. Útil si tu cliente vende afuera de Argentina.
- **URL**: <https://www.dataguidance.com/jurisdictions>

## 13.6 Content Credentials (Adobe + C2PA)

- **Qué cubre**: estándar de metadatos de credibilidad para contenido generado por IA (marca de agua firmada).
- **Capítulos DIATO**: `04`, `12`.
- **URL**: <https://contentauthenticity.org/>

---

# 14. Cómo combinar las referencias (mapa de uso)

| Si tu TPI necesita... | Usá primero | Luego complementá con |
|---|---|---|
| Marco general organizacional | McKinsey *State of Organizations 2026* (6.1) | WEF *Organizational Transformation* (6.4) |
| Tendencias tecnológicas | Deloitte *Tech Trends 2026* (6.2) | Gartner Hype Cycle (6.3) |
| Caso de procesos / BPM | Hammer & Champy (4.1) + cátedra | Davenport (4.2) + Disco Fluxicon (10.2) |
| Estrategia de IA | O'Reilly & Tushman *Lead and Disrupt* (5.1) | Cohen & Levinthal paper (5.2) |
| Prompt engineering | Della Torre (cap 04) | Anthropic (3.1) + OpenAI (3.2) |
| Compliance argentino | Resolución AAIP 161/2023 + Guía (8.1) | Ley 25.326 (8.2) + CN (8.3) |
| Compliance internacional | EU AI Act (9.1) | Convenio 108+ (9.2) + GDPR (9.3) |
| Datos y calidad | DAMA-DMBOK (2.2) | Marr *Data Strategy* (2.1) |
| ML práctico | Géron (1.2) | Andrew Ng Coursera (1.3) |
| IA agéntica | McKinsey *Seizing Agentic AI* (6.5) | Deloitte (6.2) shifts 1-2 |

---

# 15. Notas para el estudiante

- **NO comprés libros que no vas a usar.** Empezá por lo gratis (todos los reportes McKinsey/Deloitte/WEF/AAIP/EU AI Act). Si necesitás algo técnico profundo, Géron o Russell & Norvig son las inversiones que más rinden.
- **Las URLs cambian.** Si una se cae, googlear el título suele resolverlo en 30 segundos.
- **Para el TPI**: citar 2-3 fuentes oficiales (McKinsey + Deloitte + AAIP, por ejemplo) te da más peso académico que citar 15 blogs.
- **Para defensa oral**: leé al menos los **executive summaries** de McKinsey, Deloitte y WEF. Son ~5 páginas cada uno, te dan munición para responder cualquier pregunta de contexto.
- **Si encontrás material mejor**: agregalo a tu propio archivo y pasalo al grupo. Esta lista es punto de partida, no de llegada.

---

➡️ Siguiente: [19-guia-tpi.md](19-guia-tpi.md)
