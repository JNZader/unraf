# 11. Ética, privacidad y marco legal argentino para IA

> Tema 1 del material complementario — Dras. Baima y Cáceres. **El capítulo más denso del programa**: cubre marco legal vigente, organismos reguladores, comparación con GDPR/RGPD, EU AI Act, dilemas éticos, sesgos algorítmicos y los frameworks operativos que tu organización necesita para implementar IA sin terminar en un juicio. Lectura obligatoria para cualquier profesional que vaya a tocar IA en una organización argentina.

## 1. Concepto

**Ética y privacidad aplicadas a IA** es la disciplina que define cómo una organización **diseña, implementa y opera** sistemas de IA respetando:

1. Los **derechos fundamentales** de las personas (privacidad, no discriminación, intervención humana en decisiones automatizadas).
2. El **marco normativo vigente** de la jurisdicción donde opera.
3. **Principios éticos** que van más allá de la ley (transparencia, equidad, responsabilidad).

En Argentina, esto significa moverte simultáneamente en cuatro planos:

- **Constitucional**: arts. 14 bis, 16 y 43 de la Constitución Nacional.
- **Legal nacional**: Ley 25.326 de Protección de Datos Personales (2000), Ley 23.592 Antidiscriminación, Ley 27.275 de Acceso a la Información Pública, entre otras.
- **Regulatorio**: AAIP (Agencia de Acceso a la Información Pública) y sus resoluciones, especialmente la **161/2023**.
- **Internacional**: Convenio 108+ del Consejo de Europa (ratificado por Ley 27.699/2022), Recomendación UNESCO 2021, Principios IA OCDE, y como referencia técnica de exportación: **EU AI Act** (Reglamento UE 2024/1689).

> **Cita ancla de la cátedra**: *"La IA no está fuera del derecho. Todo depende de cómo, para qué y en qué contexto se use."*

## 2. Intuición

Imaginate que sos dueño de una PyME santafesina que vende productos de cuidado personal online. Querés implementar un chatbot con IA para atender consultas, y un modelo que te recomiende a qué clientes ofrecerles un nuevo producto premium.

Aparentemente, dos features inofensivas. Pero pensá:

- El chatbot **conversa con menores de edad** que entran al sitio sin que la empresa lo sepa.
- El modelo de recomendación **deduce** quién tiene "mayor poder adquisitivo" y por lo tanto está **discriminando** según un atributo no declarado.
- Para entrenar al modelo usaste el historial completo de chats, **sin consentimiento explícito** de los clientes.
- Cuando alguien te pregunta "¿por qué la IA me recomendó eso?", **no podés explicarlo** porque el modelo es una caja negra.

Cada uno de estos puntos puede caerte encima como:

- Una sanción de AAIP por Ley 25.326.
- Una denuncia por discriminación (Ley 23.592, Art. 16 CN).
- Una multa de Defensa del Consumidor (Ley 24.240).
- Y si vendés a Europa, una multa GDPR que puede llegar al **4% de tu facturación global anual**.

**La diferencia entre una empresa que usa IA con cabeza y una que se va a comer un juicio** no es la tecnología. Es la arquitectura de protección (perímetro + muro + botón rojo, que vas a ver más abajo) y el conocimiento del marco normativo.

> Otra cita de la cátedra que conviene tatuarte: *"Ni robots sin reglas, ni algoritmos sin alma."*

## 3. Cuerpo desarrollado

### 3.1 Tecnología vs IA: la distinción que define todo

La cátedra arranca con una distinción simple pero crítica:

| Tecnología | IA |
|------------|-----|
| Reglas fijas, programación explícita. | Capacidad de **aprender, adaptar y decidir** a partir de datos. |
| El humano define cada regla. | El sistema infiere reglas del entrenamiento. |
| CRM clásico, ERP, calculadora. | Motor de recomendación de Netflix, ChatGPT, scoring crediticio adaptativo. |
| Sujeta al marco legal **general** del software. | Sujeta a marco legal general **+ régimen específico de datos personales + (próximamente) regulación específica de IA**. |

Esta distinción importa porque la **responsabilidad legal** sobre una decisión de IA no se diluye con la frase "lo decidió el algoritmo". El responsable sigue siendo la **organización** que lo desplegó.

### 3.2 Los 3 pilares para PyMEs (framework cátedra)

La cátedra ofrece una manera memorable de venderle la ética y privacidad al directorio de una PyME (porque seamos honestos: si no le mostrás retorno, no aprueban el presupuesto):

1. **Privacidad = Blindaje Industrial**. Protegemos datos porque son el secreto del éxito. Si se filtran, la competencia sabe cómo fabricás o a quién le vendés. La privacidad no es un gasto regulatorio; **es una defensa competitiva**.

2. **Ética = Calidad de Marca**. Un agente sin sesgos no discrimina clientes valiosos. La justicia es rentable: si tu IA discrimina a un segmento, perdés ese segmento + la reputación + posibles juicios.

3. **Transparencia = Confianza del Cliente**. Poder explicar cómo funciona tu IA es lo que va a hacer que te elijan. En un mundo donde el 65%+ de los consumidores desconfía de las decisiones automatizadas, la **explicabilidad** se vuelve un diferenciador comercial.

> Cita cátedra: *"La ética no es un gasto; es una forma de proteger y multiplicar el valor de tu empresa a largo plazo."*

### 3.3 Marco legal argentino — Inventario completo

**Constitución Nacional**:

- **Art. 14 bis**: derecho al trabajo digno. Base para impugnar decisiones laborales 100% automatizadas (despidos, evaluaciones de desempeño exclusivamente por IA).
- **Art. 16**: igualdad ante la ley. Base contra la discriminación algorítmica, incluso sin intencionalidad.
- **Art. 43**: acción de **habeas data**. Toda persona tiene derecho a conocer qué datos suyos están en bases públicas o privadas, y a exigir su rectificación, actualización o supresión.

**Leyes nacionales clave**:

- **Ley 25.326 — Protección de Datos Personales (2000)**. La columna vertebral del régimen. Vigente, pero **desactualizada** para la era de IA (no menciona perfilado, decisiones automatizadas ni transparencia algorítmica). Hay proyectos de reforma en debate (Proyecto 4243-D-2025).
- **Ley 27.275 — Acceso a la Información Pública (2016)**. Crea la **AAIP** y garantiza transparencia del Estado.
- **Ley 23.592 — Actos Discriminatorios (1988)**. Prohíbe discriminación arbitraria. **Crítico**: aplica a sesgo algorítmico aun sin intencionalidad.
- **Ley 27.699 (2022)** — ratifica el **Convenio 108+** del Consejo de Europa.
- **Ley 27.555 — Teletrabajo (2020)**. Derecho a la desconexión digital.
- **Ley 20.744 — Ley de Contrato de Trabajo (LCT)**. Principio protectorio (art. 17 bis), buena fe (art. 63 modif.), prohibición de trato discriminatorio (art. 81).
- **Ley 24.240 — Defensa del Consumidor (1993)**. Información clara, veraz y suficiente. Aplica a recomendaciones automatizadas y publicidad personalizada.

**Resoluciones de AAIP** (la regulación operativa):

- **Resolución AAIP 161/2023**: crea el **Programa de Transparencia y Protección de Datos Personales en el uso de IA**. Da origen a la **"Guía AAIP para una IA responsable"** publicada en junio 2024.
- **Resolución AAIP 4/2019**: criterios orientadores para aplicación de Ley 25.326.
- **Resolución AAIP 47/2018**: medidas de seguridad recomendadas para el tratamiento de datos personales.
- **Resolución AAIP 40/2018**: política modelo de protección de datos para el sector público.

**Proyectos en debate (atento a estos):**

- **Proyecto 3003-D-2024** — Marco general de IA basado en EU AI Act (enfoque por riesgo).
- **Proyecto 4243-D-2025** — Reforma específica de Protección de Datos Personales para Sistemas de IA.

**Adhesiones internacionales:**

- Principios IA de la **OCDE** (2019).
- Recomendación **UNESCO** sobre la Ética de la IA (2021).
- **Convenio 108 modernizado (108+)** del Consejo de Europa — Argentina lo ratificó en 2021.
- Dato político relevante: **Argentina fue la única nación del G20 que NO firmó** la Declaración sobre Regulación de IA. Esto no anula la normativa interna, pero marca la posición del país en la mesa internacional.

### 3.4 La AAIP — Agencia de Acceso a la Información Pública

**Qué es**: ente autárquico creado por la Ley 27.275 (2016) en el ámbito de la Jefatura de Gabinete de Ministros.

**Doble rol**:

1. **Autoridad de aplicación de Ley 25.326** (protección de datos personales).
2. **Autoridad de aplicación de Ley 27.275** (acceso a información pública).

**Competencias en materia de IA** (vía Resolución 161/2023):

- Promover la **transparencia algorítmica** en el uso de IA por parte del Estado y entidades privadas.
- Publicar **guías y recomendaciones** (la Guía 2024 es la más importante).
- Recibir **denuncias** por mal uso de datos personales en sistemas automatizados.
- Imponer **sanciones** por infracción a Ley 25.326 (que pueden llegar a 5 millones de pesos por infracción, montos en revisión).

**Sitio oficial**: argentina.gob.ar/aaip

> Si vas a implementar IA con datos personales en Argentina, **leé la Guía AAIP 2024 completa**. No es opcional. Es la referencia regulatoria que va a usar cualquier auditor o juez.

### 3.5 Resolución AAIP 161/2023 y Guía AAIP 2024 — Tu compliance baseline

La Resolución 161/2023 crea el Programa con **tres líneas de acción**:

1. **Observatorio sobre IA** — monitoreo del uso de IA en sector público y privado.
2. **Gobernanza y participación social** — espacios de consulta.
3. **Fortalecimiento de capacidades** — capacitación.

La **Guía AAIP 2024** (94 páginas) establece principios y recomendaciones organizadas en **el ciclo de vida del sistema de IA en 4 etapas**:

| Etapa | Qué hacer |
|-------|-----------|
| **1. Diseño** | Aplicar **responsabilidad proactiva**, hacer **Evaluación de Impacto en Protección de Datos (EIPD)**, aplicar **privacidad por diseño y por defecto**, definir licitud y minimización, ensamblar **equipos diversos y multidisciplinarios**. |
| **2. Verificación y validación** | Monitorear el testeo, definir métricas de rendimiento, **revisar sesgos**, firmar **Acta de compromiso ético del proyecto**, validar con datos sintéticos antes que reales. |
| **3. Implementación** | Definir infraestructura, publicar **Política de Privacidad**, monitoreo continuo, **etiquetar productos generados por IA** ("marca de agua"). |
| **4. Operación y mantenimiento** | Comunicar incidentes éticos y de seguridad, **publicar la Ficha de Transparencia del sistema**, mantener canales de comunicación y reclamo. |

**Principios legales que la IA debe cumplir** (síntesis de la Guía AAIP):

1. **Consentimiento informado** (libre, expreso e informado).
2. **Finalidad específica** (solo para el propósito autorizado).
3. **Calidad del dato** (exacto y actualizado — los 7 criterios del capítulo 10).
4. **Seguridad y confidencialidad**.
5. **Licitud**.
6. **Minimización** (no recolectar más de lo necesario).
7. **Transparencia** (proceso y resultado).

**Derechos garantizados al titular del dato:**

- Acceso.
- Rectificación / actualización / supresión.
- Oposición.
- Revocación del consentimiento.

### 3.6 Comparativa Ley 25.326 vs GDPR/RGPD — Las 8 dimensiones críticas

Esta tabla la pidió la cátedra y es central para entender por qué Argentina está retrasada y qué te espera si vendés en Europa:

| Dimensión | Ley 25.326 (Argentina, 2000) | RGPD/GDPR (UE, 2016/2018) |
|-----------|------------------------------|----------------------------|
| **Tratamiento automatizado** | No lo regula específicamente. | Regulado expresamente (Art. 22 GDPR). |
| **Perfilado algorítmico** | No se menciona. | Regulación específica (Art. 22 GDPR + Considerando 71). |
| **Decisiones automatizadas** | No exige transparencia ni justificación. | Derecho a no ser sometido a decisión 100% automatizada sin justificación (Art. 22 GDPR). |
| **Evaluación de impacto** | No obligatoria. | **Obligatoria** en alto riesgo (Art. 35 GDPR — DPIA). |
| **Consentimiento** | Requerido, pero más laxo. | Estricto: **libre, informado, específico, inequívoco** y demostrable (Art. 7 GDPR). |
| **Transparencia algorítmica** | No contemplada. | Derecho a información sobre la lógica del algoritmo (Arts. 13, 14, 15 GDPR). |
| **Derecho al olvido** | No explícito (aunque la jurisprudencia lo reconoce). | Reconocido y regulado expresamente (Art. 17 GDPR). |
| **Estado actual** | En revisión para reforma (Proyecto 4243-D-2025). | Totalmente vigente; ya hubo cientos de millones de euros en multas. |

**Lo importante**: aunque la Ley 25.326 no exige expresamente todo lo que GDPR exige, la **Guía AAIP 2024** y el **Convenio 108+** (vinculante para Argentina vía Ley 27.699) **cierran muchas de esas brechas en la práctica**. Si tu organización piensa en escalar internacionalmente, **conviene apuntar a estándar GDPR desde el día uno**: cumplís en Argentina y quedás listo para Europa.

### 3.7 Convenio 108+ del Consejo de Europa — Qué aporta

El **Convenio 108** original es de 1981, fue el primer tratado internacional vinculante en materia de protección de datos. La versión **modernizada (108+)** se aprobó en 2018 y Argentina la ratificó por Ley 27.699 en 2022.

**Qué agrega a la Ley 25.326**:

- Regulación del tratamiento automatizado de datos.
- Perfilado y decisiones automatizadas.
- Transparencia y rendición de cuentas (accountability).
- Evaluación de impacto.
- Derechos reforzados: acceso, rectificación, oposición a decisiones automatizadas.

**Limitación**: el Convenio NO reemplaza la necesidad de una ley nacional actualizada. Es complementario.

### 3.8 EU AI Act — Reglamento UE 2024/1689

Aunque no es ley argentina, **te va a impactar** si:

- Tu organización tiene clientes europeos.
- Tu organización vende software/SaaS a empresas que operan en Europa.
- Argentina copia el modelo (Proyecto 3003-D-2024 ya lo toma como base).

El EU AI Act —aprobado en marzo 2024, vigente progresivamente entre 2024 y 2027— clasifica los sistemas de IA en **4 niveles de riesgo**:

| Nivel | Qué incluye | Obligaciones |
|-------|-------------|--------------|
| **1. Riesgo inaceptable** | Manipulación cognitiva, social scoring estatal, **inferencia de emociones en ámbito laboral/educativo**, reconocimiento biométrico masivo en espacios públicos. | **Prohibidos**. |
| **2. Riesgo alto** | Equipamiento médico, vehículos autónomos, infraestructura crítica, credit scoring, sistemas de RRHH (selección, evaluación, despido), educación, justicia. | Requisitos estrictos: EIPD, registro en BBDD UE, supervisión humana, documentación técnica, transparencia, ciberseguridad. |
| **3. Riesgo limitado** | Chatbots, asistentes virtuales, sistemas de recomendación, generación de contenido. | **Transparencia obligatoria**: avisar al usuario que está interactuando con IA / que el contenido fue generado por IA. |
| **4. Riesgo mínimo** | Filtros de spam, IA en videojuegos. | Sin requisitos específicos (se rigen por marco general). |

**Multas**: hasta **35 millones de euros o 7% de la facturación global anual** (lo que sea mayor) para infracciones graves.

> Si tu organización usa IA para RRHH, scoring crediticio, educación, salud o seguridad, **estás en alto riesgo** según EU AI Act. Aunque hoy no te aplique en Argentina, **es la dirección regulatoria global**. Más vale empezar a documentar bien desde ahora.

### 3.9 Los 4 tipos de sesgos (según Guía AAIP)

La discriminación algorítmica es **ilegal en Argentina aun sin intencionalidad** (combinación de Art. 16 CN + Ley 23.592). Las organizaciones son responsables de **auditar y mitigar sesgos**. La Guía AAIP identifica 4 tipos según su origen:

1. **Sesgo de percepción**: la realidad capturada no representa al universo total. Sub-representación o sobre-representación. *Ejemplo*: dataset de reconocimiento facial entrenado mayoritariamente con rostros blancos masculinos → falla en mujeres de piel oscura (estudio Buolamwini & Gebru, MIT, 2018).

2. **Sesgo técnico**: surge de la tecnología en sí (limitaciones del sensor, del algoritmo, de la métrica). *Ejemplo*: una cámara que captura peor a personas con poca iluminación.

3. **Sesgo de modelado**: diseño manual con omisiones o supuestos erróneos. *Ejemplo*: un modelo de scoring que usa código postal como variable, lo que termina actuando como proxy de etnia o nivel socioeconómico.

4. **Sesgo de activación**: el uso del sistema en un entorno distinto al previsto introduce sesgo nuevo. *Ejemplo*: un modelo entrenado para Buenos Aires CABA aplicado en interior del país sin recalibración.

**Categorías particularmente sensibles** que la Guía destaca:

- **Sesgos étnicos y de género**: las mujeres de piel oscura tienen significativamente mayor tasa de error en reconocimiento facial.
- **Neurodatos**: datos cerebrales captados por wearables —debate abierto sobre si requieren régimen específico.
- **NNyA en entornos digitales** (niños, niñas y adolescentes): la ONU 2024 emitió 6 puntos específicos de gobernanza de IA para esta población vulnerable.

### 3.10 Riesgos centrales (síntesis cátedra)

- **Discriminación algorítmica**: ILEGAL en Argentina aun sin intencionalidad (Art. 16 CN + Ley 23.592). Las organizaciones son responsables de auditar.
- **"Caja Negra" inaceptable**: el derecho a la información y la defensa exige transparencia algorítmica. Si tu IA decide algo importante sobre una persona y no podés explicar **cómo** llegó a esa decisión, estás en problemas.
- **Decisiones 100% automatizadas**: NO pueden ser definitivas si afectan derechos. **Derecho a intervención humana** (HITL — Human In The Loop).

### 3.11 Arquitectura de Agente Profesional (framework cátedra — 3 capas)

Este es uno de los modelos operativos más memorables del programa. Pensá en tu agente de IA como un edificio con tres capas de protección:

```
┌─────────────────────────────────────────────────┐
│  CAPA 3: BOTÓN ROJO — Supervisión Humana (HITL)│
│  Umbrales críticos requieren validación humana  │
├─────────────────────────────────────────────────┤
│  CAPA 2: MURO DE CONTENCIÓN — Privacidad        │
│  por Diseño. Anonimización, no "ver" sensibles  │
├─────────────────────────────────────────────────┤
│  CAPA 1: PERÍMETRO DE ACCIÓN — Manual de        │
│  Conducta (System Prompt) misión y límites      │
│  éticos del agente                              │
└─────────────────────────────────────────────────┘
```

1. **Perímetro de Acción (Manual de Conducta)**: el **system prompt** que define misión, alcance, tono, y especialmente los **límites éticos** del agente. *Ejemplo*: "Sos un asistente de cobranzas. NO podés amenazar, insultar, ni contactar fuera de horario hábil. NO podés tomar decisiones que afecten el score crediticio sin escalado humano."

2. **Muro de Contención (Privacidad por Diseño)**: el agente **no debería poder ver** datos sensibles que no necesita. *Ejemplo*: anonimización antes del procesamiento, separación de datos personales en otra capa, hashing de identificadores.

3. **El Botón Rojo (Supervisión Humana — HITL)**: umbrales críticos disparan validación humana obligatoria. *Ejemplo*: cualquier decisión que afecte > X pesos, o que recaiga sobre un menor, o que implique cancelar un servicio, pasa por revisión humana antes de ejecutarse.

### 3.12 Semáforo de Decisiones (framework cátedra)

Herramienta de bolsillo para evaluar rápido si una acción de IA en una PyME es prudente:

| Situación | Nivel | Por qué | Acción correcta |
|-----------|-------|---------|-----------------|
| Subir balance contable a ChatGPT público | **ROJO** | Fuga de secreto industrial. Los datos podrían usarse para entrenamiento. | Copilot Pro/Enterprise (con acuerdo de no entrenamiento) o **NotebookLM privado**. |
| Control de asistencia con reconocimiento facial | **ROJO** | Invasión de privacidad. Dato biométrico = **dato sensible** según AAIP. | Reloj biométrico tradicional con consentimiento, o si IA: **consentimiento escrito + auditoría**. |
| IA que descarta CVs autónomamente | **AMARILLO** | Riesgo de sesgo (descarte por barrio, edad, género). | IA solo **clasifica/ordena**, **humano siempre revisa descartados** (HITL). |
| Chatbot de consulta de productos | **VERDE** | Bajo riesgo, transparencia simple. | Avisar que es IA (transparencia Art. 50 EU AI Act preventivo). |

### 3.13 Matriz por área de aplicación (la cátedra te pide aplicarla a tu organización)

| Área | ¿Qué optimiza? | Riesgos éticos | Marco normativo | Buenas prácticas |
|------|----------------|----------------|-----------------|------------------|
| **Cadena de suministro** | Rutas, inventarios, logística | Discriminación geográfica (zonas no atendidas) | Comercio digital, GDPR (localización) | Transparencia en criterios de zonificación |
| **Atención al cliente** | Respuesta inmediata, automatización | Falta de empatía, manejo de datos sensibles | Ley 25.326, EU AI Act | Diseño centrado en usuario, supervisión humana en casos complejos |
| **Evaluación de desempeño** | Medición objetiva | Vigilancia excesiva, sesgos en métricas | LCT, derecho a privacidad | Transparencia, opción de revisión humana del resultado |
| **Desarrollo profesional** | Detección de áreas de mejora | Sesgos en recomendaciones, perfilamiento implícito | GDPR (decisiones automatizadas) | Feedback humano, explicabilidad de la recomendación |
| **Marketing personalizado** | Segmentación, targeting | Manipulación conductual, datos sin consentimiento | Ley 24.240, GDPR, CCPA | Consentimiento activo, trazabilidad de uso |
| **Selección de personal** | Filtrado de CVs, matching | Discriminación por género/edad/etnia (proxies) | Ley 23.592, EU AI Act (alto riesgo) | **Auditoría algorítmica**, intervención humana obligatoria |

## 4. Casos reales

### 4.1 Caso Mercado Libre — IA con filtros éticos

Mercado Libre desplegó modelos de recomendación con filtros éticos explícitos para **no mostrar productos sensibles** (armas, productos para adultos, contenido riesgoso) a usuarios identificados como **menores de edad** o cuando hay señales contextuales de menor. El filtro opera **antes** de la salida del modelo, no como auditoría posterior. Es un ejemplo claro de **Muro de Contención** (capa 2 del agente profesional).

### 4.2 Caso Unilever — IA en entrevistas

Unilever (y luego Accenture) usó la plataforma **HireVue** (luego **Harver/Pymetrics**) para analizar videos de entrevistas: lenguaje corporal, tono de voz, contenido verbal. El modelo entrega un score que filtra candidatos.

**Controversia ética**: estudios independientes encontraron sesgos por género y etnia. **Illinois (USA) prohibió en 2020** el uso de IA en entrevistas sin consentimiento explícito (AI Video Interview Act). HireVue terminó **retirando el análisis facial** del producto en 2021 por las críticas.

**Lección**: aun una multinacional con recursos legales gigantescos puede tropezar con sesgos sistémicos. La auditoría externa de sesgos no es opcional.

### 4.3 Caso Coca-Cola — Recreación con IA del comercial navideño 1995

En 2024, Coca-Cola lanzó una versión recreada con IA generativa del icónico comercial navideño "Holidays Are Coming" de 1995. Generó **debate global** sobre derechos de autor, autenticidad, calidad estética y uso ético de IA en publicidad.

**Lección**: el uso de IA generativa en contenido público requiere **etiquetado** (Content Credentials, Adobe Beta) y **política comunicacional clara**. Aun cuando es legal, el costo reputacional puede ser alto si no manejás la comunicación.

### 4.4 Caso Santa Fe — Poder Judicial pionero con HITL

El **Poder Judicial de Santa Fe** es pionero en Argentina en el uso de IA generativa para **redacción de sentencias de baja complejidad** (resoluciones de trámite, fallos modelo). Lo distintivo:

- **Supervisión Humana Obligatoria** explícita: *"la IA propone, el profesional valida"*.
- La Comisión Especial de IA en la Legislatura provincial adoptó postura de **"estudio previo a regulación"** (modelo sandbox).
- Es **el caso paradigmático argentino** de **HITL institucionalizado** en sector público.

**Lección**: si vas a implementar IA en una organización donde las decisiones afectan derechos, **inspirate en este modelo**: la IA acelera el trabajo profesional, pero **no firma**.

### 4.5 Caso ficcionado de la cátedra — VelozShop y LogiTrack

- **VelozShop** (tienda online): IA construye perfiles psicológicos de usuarios y envía ofertas hiperespecíficas. **Conversión +25%**, pero los usuarios reportan sentirse manipulados. Dilema: **beneficio comercial vs autonomía del consumidor**.

- **LogiTrack** (logística): cámaras con reconocimiento facial + monitoreo móvil de conductores. **Productividad +12%**, pero crecen rotación, estrés y desconfianza. Dilema: **eficiencia vs vigilancia laboral**.

Ambos casos son perfectos para discusión grupal en una organización antes de implementar IA: ¿Hasta dónde queremos ir? ¿Qué valores estamos dispuestos a comprometer?

## 5. Aplicación a la transformación organizacional

Cómo armar un **compliance básico de IA para una PyME argentina** (paso a paso):

### Paso 1 — Mapeo (semana 1)

- Listá **todos los sistemas que usan IA** o que vas a implementar (CRM con scoring, chatbot, recomendador, IA generativa interna).
- Para cada uno, clasificá según **niveles de riesgo EU AI Act** (inaceptable / alto / limitado / mínimo).
- Identificá si procesan **datos personales** (entonces aplica Ley 25.326).
- Identificá si procesan **datos sensibles** (salud, biométrico, ideología, religión — entonces responsabilidad reforzada).

### Paso 2 — Inventario legal (semana 2)

- Verificá que tengas **Política de Privacidad** publicada y actualizada (Art. 6 Ley 25.326).
- Verificá que las **bases de datos personales estén inscriptas** en el Registro Nacional de Bases de Datos de la AAIP (Art. 21 Ley 25.326).
- Documentá la **base legal** del tratamiento de datos para cada caso (consentimiento, contrato, obligación legal, interés legítimo).

### Paso 3 — Evaluación de Impacto (mes 1)

Para cada sistema de alto riesgo o que toque datos sensibles, hacé **EIPD (Evaluación de Impacto en Protección de Datos)**:

- Descripción del tratamiento.
- Necesidad y proporcionalidad.
- Riesgos para los derechos de los titulares.
- Medidas para mitigar esos riesgos.

### Paso 4 — Implementar Arquitectura del Agente Profesional (mes 2-3)

Para cada agente/sistema IA, definí explícitamente:

- **Perímetro**: system prompt con misión + límites éticos documentados.
- **Muro**: anonimización, control de acceso, separación de datos sensibles.
- **Botón Rojo**: umbrales de escalado humano + responsable identificado.

### Paso 5 — Acta de Compromiso Ético (mes 3)

Antes de poner en producción cualquier sistema de IA, firmar (literalmente) un **Acta de Compromiso Ético del Proyecto** con:

- Equipo responsable.
- Principios éticos asumidos.
- Compromisos de auditoría periódica.
- Plan de manejo de incidentes.

### Paso 6 — Publicar Ficha de Transparencia (mes 4)

La Guía AAIP define la **Ficha de Transparencia** del sistema con **3 secciones** (~20 ítems):

1. **Caracterización general**: denominación, organismo, objetivo, funcionalidades, medios de impugnación, supervisión humana, responsable, proveedor.
2. **Caracterización tecnológica**: tecnología IA usada, nivel de riesgo, datos de entrada/salida, fuente de datos, tipo de servidor.
3. **Transparencia en interacción ciudadana**: canales de comunicación, etiquetado de IA, alternativa humana disponible.

### Paso 7 — Capacitación interna (continuo)

- Capacitá al **equipo de RRHH** en sesgos de selección.
- Capacitá al **equipo de atención al cliente** en cuándo escalar a humano.
- Capacitá al **directorio** en los 3 pilares (blindaje/marca/confianza) para que apruebe presupuesto.
- Trabajá la **alfabetización digital generacional** (6 generaciones digitales conviviendo en organizaciones: Silenciosa, Boomers, X, Millennials, Z/Centennials, Alpha).

### Paso 8 — Auditoría externa (anual)

- Auditoría externa de sesgos por una consultora independiente (al menos anual).
- Revisión de la política de privacidad.
- Test de penetración / seguridad del modelo.
- Si exportás a UE: evaluación de conformidad EU AI Act.

## 6. Errores comunes / mitos

- **"La Ley 25.326 cubre todo lo que necesito"**. Falso. La Ley es de 2000 y NO contempla tratamiento automatizado, perfilado ni decisiones automatizadas. Tenés que complementarla con la **Guía AAIP 2024**, el **Convenio 108+** (vinculante), y mirar EU AI Act como referencia.
- **"Como vendo solo en Argentina, no me importa GDPR"**. Falso si tenés un cliente europeo, un proveedor europeo, una visita europea a tu web con tracking, o usás herramientas cloud que procesan datos en Europa. GDPR tiene alcance extraterritorial.
- **"El algoritmo decidió, yo no soy responsable"**. **MUY** falso. La organización es **responsable de los daños** causados por sistemas que despliega. Es responsabilidad objetiva en muchos casos.
- **"Como no hay intencionalidad de discriminar, no hay discriminación"**. Falso. La Ley 23.592 + Art. 16 CN aplican **incluso sin intencionalidad**. El sesgo algorítmico no intencional es igualmente sancionable.
- **"La transparencia algorítmica revela secretos comerciales"**. Mito. La transparencia no exige publicar el código fuente: exige poder **explicar la lógica de decisión** en términos comprensibles, los datos de entrada usados, y el rango de salida.
- **"Pedir consentimiento traba el negocio"**. Falso. Pedirlo MAL traba el negocio. Pedirlo bien (claro, granular, en el momento adecuado, con beneficio explícito) **mejora la conversión y la confianza**.
- **"La IA generativa pública (ChatGPT, Gemini) es segura para datos de mi empresa"**. ROJO en el semáforo. Por defecto, las versiones gratuitas/básicas pueden usar tus datos para reentrenamiento. Usá versiones Enterprise con acuerdo de no entrenamiento, o herramientas privadas como NotebookLM con tu cuenta corporativa.
- **"Si no soy un Mercado Libre, no me van a auditar"**. Riesgoso. La AAIP recibe denuncias de particulares y puede iniciar inspecciones a PyMEs. Una sola denuncia puede disparar una investigación completa.

## 7. Checklist

Para llevar a tu organización un **compliance básico de IA**:

- [ ] Mapeé todos los sistemas con IA (actuales y previstos).
- [ ] Clasifiqué cada uno según los **4 niveles de riesgo EU AI Act**.
- [ ] Identifiqué cuáles procesan datos personales (Ley 25.326) y cuáles datos sensibles.
- [ ] Tengo **Política de Privacidad** publicada, actualizada y comprensible.
- [ ] Tengo las **bases de datos inscriptas** en el Registro Nacional de la AAIP.
- [ ] Documenté la **base legal** del tratamiento para cada caso.
- [ ] Hice **EIPD (Evaluación de Impacto)** para los sistemas de alto riesgo o datos sensibles.
- [ ] Definí explícitamente el **Perímetro** (system prompt + límites éticos) de cada agente.
- [ ] Implementé el **Muro** (anonimización + control de acceso + separación de sensibles).
- [ ] Definí el **Botón Rojo** (umbrales HITL + responsable identificado).
- [ ] Firmé **Acta de Compromiso Ético** por cada proyecto IA en producción.
- [ ] Publiqué **Ficha de Transparencia** con las 3 secciones de la Guía AAIP.
- [ ] Implementé **canales de reclamo** claros y visibles para los titulares de datos.
- [ ] Identifiqué los **4 tipos de sesgos** posibles en cada modelo y tengo plan de mitigación.
- [ ] Audito **anualmente** los sistemas con consultora externa independiente.
- [ ] Capacité al equipo (RRHH, atención, dirección) en ética IA.
- [ ] Tengo un **plan de gestión de incidentes** documentado (qué hacer si se filtran datos o el modelo discrimina).
- [ ] Etiqueto el contenido generado por IA (transparencia EU AI Act Art. 50 / Adobe Content Credentials).
- [ ] Tengo cláusulas contractuales con proveedores de IA que cubran responsabilidad por sesgo y filtración.
- [ ] Si vendo a UE: tengo evaluación preliminar de conformidad EU AI Act.

## 8. Para profundizar

**Marco legal argentino (oficial):**

- **Ley 25.326 — Protección de Datos Personales** (texto completo en argentina.gob.ar/normativa).
- **Ley 27.275 — Acceso a la Información Pública** (argentina.gob.ar/normativa).
- **Ley 27.699 — Convenio 108+** (argentina.gob.ar/normativa).
- **Resolución AAIP 161/2023** (boletinoficial.gob.ar).
- **AAIP — Guía para una IA responsable (junio 2024)** — argentina.gob.ar/aaip.
- Sitio oficial AAIP: argentina.gob.ar/aaip.

**Marco internacional:**

- **EU AI Act — Reglamento UE 2024/1689** (texto oficial en eur-lex.europa.eu).
- **Convenio 108+ — Consejo de Europa** (coe.int/data-protection).
- **GDPR — Reglamento UE 2016/679** (gdpr-info.eu).
- **OCDE — Principios de IA** (oecd.org/going-digital/ai/principles).
- **UNESCO — Recomendación sobre la Ética de la IA (2021)** (unesco.org).

**Frameworks y recursos prácticos:**

- **fAIr LAC (BID)**: hub de IA ética para LATAM, con **Autoevaluación Ética para PyMEs** (fairlac.iadb.org).
- **IAPP — Global AI Legislation Tracker**: mapa de regulación por país (iapp.org).
- **Stanford HAI — AI Index Report** anual (hai.stanford.edu/research/ai-index-report).
- **DataGuidance** (dataguidance.com/jurisdictions): para entender requisitos al vender a otros países.
- **Content Credentials (Adobe Beta)**: metadatos de credibilidad para contenido generado (contentauthenticity.adobe.com).
- **CONARP** (Consejo de Autorregulación Publicitaria, Argentina): conarp.org.ar.

**Lectura crítica recomendada:**

- Buolamwini, J. & Gebru, T. (2018). *Gender Shades: Intersectional Accuracy Disparities in Commercial Gender Classification*. MIT — el estudio que probó el sesgo racial/género en reconocimiento facial comercial.
- O'Neil, C. (2016). *Weapons of Math Destruction*. Crown Publishing — clásico sobre cómo los algoritmos pueden amplificar discriminación.
- Floridi, L. & Cowls, J. (2019). *A Unified Framework of Five Principles for AI in Society*. Harvard Data Science Review.

## Próximo paso

Con la base ética y normativa firme, en el [capítulo 12](./12-analisis-competitivo-con-ia.md) vamos a aplicar IA a un terreno donde se juegan ventajas competitivas reales: el **análisis competitivo**. Vas a ver cómo combinar frameworks clásicos (Porter, PESTEL, SWOT) con herramientas modernas (NotebookLM, análisis de patentes, monitoreo de competencia), y cómo evitar el error frecuente de "usar IA sin marco estratégico".

## Referencias

- Constitución Nacional Argentina, arts. 14 bis, 16 y 43.
- Ley 25.326 — Protección de Datos Personales (2000).
- Ley 23.592 — Actos Discriminatorios (1988).
- Ley 27.275 — Acceso a la Información Pública (2016).
- Ley 27.699 — Ratificación del Convenio 108+ (2022).
- Resolución AAIP 161/2023 — Programa de Transparencia y Protección de Datos en IA.
- AAIP (junio 2024). *Guía para entidades públicas y privadas en materia de Transparencia y Protección de Datos Personales para una Inteligencia Artificial responsable*.
- Reglamento (UE) 2024/1689 — Reglamento de Inteligencia Artificial (EU AI Act).
- Convenio 108+ del Consejo de Europa (versión modernizada 2018).
- Reglamento (UE) 2016/679 — Reglamento General de Protección de Datos (GDPR).
- Buolamwini, J. & Gebru, T. (2018). *Gender Shades*. Proceedings of Machine Learning Research, 81, 1-15.
- Material de cátedra DIATO — Material complementario Tema 1 (Dras. Baima y Cáceres) y Tema 5 (Guía AAIP), UNRaf 2026.
- Recomendación UNESCO sobre la Ética de la IA (2021).
- OECD AI Principles (2019).
