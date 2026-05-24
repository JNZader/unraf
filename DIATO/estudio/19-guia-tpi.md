# 19 — Guía paso a paso del TPI (Trabajo Práctico Integrador)

> Fuente primaria: `TPI_5tacohorte-1.pdf` (consigna oficial, 4 páginas) + calendario DIATO + capítulos previos de este estudio.
> Esta guía te lleva de la mano desde "no arrancamos" hasta "subido al campus" sin que el grupo se pelee ni se duerma en el deadline.

---

## 0. TL;DR — Si tenés 3 minutos, leé esto

- **Tipo**: GRUPAL. Equipos de **4 a 6 personas**, **1 entrega por grupo**.
- **Entrega final**: **16/06/2026** en Campus Virtual UNRaf.
- **Definición de la organización**: **07/04/2026** (excel compartido por la cátedra).
- **Formato obligatorio**:
  - Resumen ejecutivo: **1 hoja**.
  - Desarrollo del proyecto: **máximo 12 hojas**.
  - Anexos: **sin límite** (acá metés todo lo que sobre).
- **8 bloques obligatorios** (a–h): contexto, problema, AS IS, mejora, solución (requisitos + arquitectura), proveedores y costos, cronograma, KPIs + ROI.
- **No hay rúbrica explícita publicada** — el PDF lista consignas pero no asigna puntaje por bloque. Estrategia segura: **cumplir 100% de lo obligatorio antes de invertir en lo optativo**.
- **El TPI NO obliga a usar IA generativa** específicamente — admite "herramientas y técnicas de IA y otras herramientas dictadas en la diplomatura". RPA, ML clásico, BI también cuentan.

---

## 1. Introducción — ¿Qué es el TPI?

### 1.1 Definición

El TPI (Trabajo Práctico Integrador) es el proyecto final grupal de la Diplomatura en IA aplicada a Transformación Organizacional. Es el momento donde **integrás todo lo visto en las 10 unidades** y lo aplicás a una organización real (o realista) para resolver un problema o aprovechar una oportunidad usando IA.

Cita textual de la consigna (p. 2):

> "Es necesario que utilicen los conceptos y herramientas de IA para diseñar y proponer una **solución innovadora**."

### 1.2 Objetivos pedagógicos (declarados)

1. Aplicar herramientas y técnicas de IA para diseñar una solución que mejore un proceso o resuelva un problema específico en un entorno organizacional.
2. Fomentar el trabajo en equipo y la colaboración interdisciplinaria.
3. Desarrollar habilidades prácticas en la implementación de tecnologías de IA.

### 1.3 Modalidad y entrega

| Aspecto | Detalle |
|---|---|
| **Modalidad** | Grupal |
| **Tamaño de equipo** | 4 a 6 personas |
| **Entregas por grupo** | 1 (consolidada) |
| **Canal** | Campus Virtual UNRaf |
| **Fecha final** | **16/06/2026** |
| **Definición de organización** | **07/04/2026** (excel compartido) |

> **Anomalía detectada en el calendario**: la fecha de "definición de la organización" (07/04) figura **después** del inicio del desarrollo del TP (31/03). Probablemente sea fecha límite blanda, no de arranque. **Verificá con la coordinación antes de asumir cualquiera de las dos como sagrada.**

### 1.4 Formato de entrega (no negociable)

| Sección | Extensión máxima |
|---|---|
| Resumen ejecutivo | **1 hoja** |
| Desarrollo del proyecto (a–h) | **12 hojas** |
| Anexos | Sin límite |

Esto significa que:

- **No podés bajarte del resumen ejecutivo** (es obligatorio aunque parezca redundante).
- **No podés pasarte de 12 hojas** en el desarrollo (acá viene el quilombo: muchos grupos lo hacen).
- **Sí podés meter todo lo voluminoso en anexos**: tablas extensas de proveedores, cálculos detallados de ROI, capturas de UI, transcripciones, código, encuestas, etc.

### 1.5 La "trampa" de no tener rúbrica explícita

El PDF de la consigna **no publica grilla de puntaje** por bloque. Solo enumera obligatorios y optativos. Esto deja ambigüedad sobre el peso relativo.

**Estrategia recomendada**:

1. Tratar los 8 bloques como **igual peso** (12,5% cada uno, mental).
2. Cumplir el 100% de lo obligatorio **antes** de invertir en optativos (madurez digital, benchmark industrial).
3. Si querés sumar, los optativos están claramente listados — son "puntos extra" implícitos.
4. **Coherencia narrativa entre bloques** vale más que profundidad desbalanceada (un bloque excelente y tres flojos baja la nota más que ocho bloques sólidos pero modestos).

---

## 2. Setup recomendado (semana 1 del grupo)

### 2.1 Cómo elegir la organización

Antes del 07/04, el grupo tiene que tener decidido sobre qué organización van a trabajar. Criterios para no clavarse:

#### Criterios de elegibilidad

| Criterio | Por qué importa |
|---|---|
| **Tenés acceso a información real (o pública robusta)** | Sin datos, todo es ficción. Si nadie del grupo trabaja ahí, asegurate de que haya: web institucional con info, casos públicos, memorias anuales, notas periodísticas. |
| **Tamaño que justifique IA** | Una PyME de 5 personas con 50 consultas/mes no justifica USD 50k de inversión. Buscá organizaciones medianas/grandes o áreas críticas dentro de una pyme grande. |
| **Tiene un proceso identificable** | "Mejorar el clima laboral" es demasiado vago. "Mejorar el tiempo de respuesta del soporte técnico" es procesable. |
| **El sector permite IA** | Sectores con datos digitalizados (banca, retail, telco, agro de precisión, salud) son más fáciles de defender. Sectores con datos opacos (construcción tradicional, gremios) requieren más esfuerzo. |
| **Hay un "dolor" claro** | Tiene que haber un problema medible: tiempos, costos, errores, satisfacción. Si tenés que inventar el dolor, mal arrancamos. |

#### Criterios de descarte (red flags)

- "Es la empresa de mi familia/conocido pero no me dan datos." → vas a inventar todo y se va a notar.
- "Es una multinacional gigante donde no podemos delimitar un área." → te quedás en abstracto.
- "Es una startup que hace IA." → meta. No tiene sentido proponer IA donde la IA ya es el producto.
- "Es un caso de estudio público famoso (Tesla, Netflix, Amazon)." → cero originalidad, los docentes lo vieron 200 veces.

#### Estructura sugerida para defender la elección

```markdown
**Organización elegida**: [Nombre]
**Sector**: [Industria]
**Tamaño**: [Empleados, facturación si pública]
**Ubicación**: [Argentina / región]
**Área de foco del TPI**: [Comercial / Servicio técnico / RRHH / etc.]
**Por qué este caso**:
1. Acceso a información: [fuentes que vamos a usar]
2. Problema identificado: [una oración]
3. Por qué la IA es relevante acá: [una oración]
**Integrantes del grupo y responsabilidades iniciales**: [tabla]
```

### 2.2 Cómo armar el equipo (4-6 personas)

Roles sugeridos (no rígidos, podés rotar):

| Rol | Responsabilidad |
|---|---|
| **Coordinador/a** | Agenda, deadlines internos, consolidación final. Idealmente alguien con experiencia de PM o que sea ordenado/a. |
| **Investigador/a de dominio** | Profundiza en el sector y la organización elegida. Lleva las entrevistas si hay. |
| **Arquitecto/a de solución** | Lidera el bloque (e): requisitos + arquitectura. Suele ser quien más conocimiento técnico tiene. |
| **Analista de procesos** | Lidera AS IS y mejora (bloques c y d). Hace los diagramas. |
| **Analista de costos / ROI** | Lidera bloques (f) y (h). Maneja las planillas y los supuestos. |
| **Editor/a** | Cuida coherencia narrativa, prosa, formato final. **Crítico** porque sin esto el documento parece Frankenstein. |

> Si el equipo es de 4, los roles se duplican. Si es de 6, alguien puede dedicarse solo a coherencia y otro a diagramas/visualización.

### 2.3 Cómo dividirse las 8 secciones

**Antipatrón**: "Cada uno hace una sección y al final juntamos." Resultado: documento Frankenstein con 8 tonos distintos, contradicciones internas y duplicaciones.

**Patrón recomendado**:

1. **Discutir TODO el caso juntos** en la primera sesión (2 horas). Que todos entiendan el problema y la propuesta de solución a alto nivel.
2. **Asignar responsables PRIMARIOS por sección**, pero todos tienen que poder leer y comentar todas las secciones.
3. **Definir convenciones globales temprano**:
   - Voseo o usted/vosotros? (recomiendo voseo o "se" impersonal).
   - Decimal: coma o punto?
   - Moneda: ARS o USD?
   - Nombre de la organización: como se escribe oficialmente.
   - Acrónimos: lista común al inicio.
4. **Editor/a pasa al final** y unifica tono.

#### Plantilla de asignación (ejemplo)

| Sección | Responsable primario | Revisor | Deadline interno |
|---|---|---|---|
| (a) Contexto | [Nombre] | [Otro] | [Fecha] |
| (b) Problema | [Nombre] | [Otro] | [Fecha] |
| (c) AS IS + diagrama | [Nombre] | [Otro] | [Fecha] |
| (d) Mejora | [Nombre] | [Otro] | [Fecha] |
| (e) Solución (req. + arquitectura) | [Nombre] | [Otro] | [Fecha] |
| (f) Proveedores y costos | [Nombre] | [Otro] | [Fecha] |
| (g) Cronograma | [Nombre] | [Otro] | [Fecha] |
| (h) KPIs + ROI | [Nombre] | [Otro] | [Fecha] |
| Resumen ejecutivo | **Editor/a** (al final) | Coordinador/a | [Fecha cercana al cierre] |
| Diagramas (AS IS, To-Be, arquitectura) | [Nombre — analista de procesos + arquitecto/a] | Todos | [Fecha intermedia] |

### 2.4 Herramientas sugeridas

| Necesidad | Herramientas |
|---|---|
| Documento colaborativo | **Google Docs** (mejor que Word compartido, para evitar quilombos de versiones). Notion también sirve si todos lo usan. |
| Diagramas (BPMN, flujos, arquitectura) | **bpmn.io** (gratis, sin login, exporta SVG/PNG), **draw.io / diagrams.net** (gratis, integra con Drive), **Miro** (colaborativo, freemium), **Lucidchart** (pago, muy bueno) |
| GANTT | **Excel/Google Sheets** (simple), **GanttProject** (gratis, desktop), **ClickUp / Notion** (si ya lo usan), **MS Project** (overkill para esto) |
| Investigación / referencias | **Zotero** (gestor de bibliografía gratis), **Google Scholar** |
| Reuniones | **Google Meet / Zoom** |
| Mensajería | **WhatsApp** o **Discord** (Discord es mejor para temas separados por canal) |
| PDF final | Exportar desde Google Docs a PDF |

> **Regla práctica**: una sola herramienta por necesidad. No te vayas a Notion + Google Docs + Word a la vez — terminás con tres versiones desincronizadas.

---

## 3. Los 8 bloques obligatorios (uno por uno)

Cada bloque referencia los capítulos del estudio donde está el marco teórico, así no escribís cosas sueltas.

---

### 3.a — Bloque (a) Contexto

**Consigna textual** (p. 2):

> "Presentar brevemente el contexto de la empresa y área seleccionada. Incluir descripción de la organización, tamaño y desafíos actuales.
> *Optativo*: Evaluación inicial del nivel de madurez digital de la organización."

#### Qué incluir (obligatorio)

1. **Identificación de la organización**: nombre, sector, ubicación, año de fundación, propiedad (privada/pública/familiar/cooperativa).
2. **Tamaño**: cantidad de empleados, facturación anual (si es pública), participación de mercado.
3. **Propuesta de valor / qué hace**: una o dos oraciones.
4. **Área seleccionada para el TPI**: dejar claro **desde el inicio** sobre qué área van a trabajar (comercial, servicio técnico, RRHH, supply chain, finanzas, etc.).
5. **Desafíos actuales**: dos o tres frases sobre presiones del entorno (regulación, competencia, crecimiento, digitalización).

#### Qué incluir (optativo, recomendado)

6. **Nivel de madurez digital**: usar uno de los autodiagnósticos públicos:
   - [AMDIA Industria 4.0](https://amdindtech.ar/)
   - [Gobierno Santa Fe — Industria Digital](https://www.santafe.gob.ar/ind-digital/)
   - [UNL Chequeo](https://servicios.unl.edu.ar/chequeo)

   O un framework propio basado en los capítulos 6 y 13 del estudio (modelos de madurez digital).

#### Errores comunes

- **Hacer un copy-paste de la web institucional** — el docente se da cuenta inmediatamente. Reescribir con propias palabras y agregar el ángulo del TPI.
- **Hablar de toda la organización cuando el TPI es sobre un área** — delimitá el alcance desde acá. Si trabajás sobre "atención al cliente del área comercial", no describas la planta industrial en detalle.
- **No mencionar tamaño / contexto numérico** — sin números, el problema parece abstracto.

#### Referencias del estudio

- Capítulo 06 — IA en estrategia organizacional (modelo 4E).
- Capítulo 14 — Estado de las organizaciones McKinsey 2026 (contexto LATAM).

---

### 3.b — Bloque (b) Definición de problema u oportunidad

**Consigna textual** (p. 2):

> "Identificar un problema específico que limita la eficiencia o efectividad de un proceso, o una oportunidad para mejorar algún aspecto del negocio utilizando IA. Este problema u oportunidad debe estar claramente definido y relacionado con el contexto presentado.
> *Optativo*: Investigación sobre cómo otros en la industria están abordando problemas similares con IA."

#### Problema vs oportunidad — la diferencia que la mayoría no entiende

| Problema | Oportunidad |
|---|---|
| Algo que **está mal hoy** y duele. | Algo que **podría ser mejor** aunque hoy no duela. |
| "Tenemos 4h de tiempo de respuesta promedio y los clientes se quejan." | "Podríamos personalizar las recomendaciones de producto en tiempo real para aumentar conversión." |
| Justificación: **eliminar dolor**. | Justificación: **capturar valor adicional**. |
| ROI más fácil de defender (ahorro de costos directos). | ROI más difícil (incremento de revenue, requiere supuestos). |

Para el TPI, **elegir uno** y declararlo explícitamente. Mezclar los dos da textos confusos.

#### Cómo formular un buen problema u oportunidad

Plantilla:

```markdown
**Problema**: [Verbo en infinitivo o frase declarativa con sujeto + verbo + objeto + contexto cuantificado].

Ejemplo: "Sobrecarga del equipo de atención al cliente del área comercial,
que recibe 6.000 consultas mensuales por WhatsApp con un tiempo de
respuesta promedio de 8 horas y una tasa de escalamiento del 35%."

**Causas raíz** (3-5):
1. ...
2. ...
3. ...

**Consecuencias / impacto** (3-5):
1. ...
2. ...
3. ...

**Población afectada**: [Clientes externos, empleados internos, ambos]
**Frecuencia**: [Cuántas veces ocurre por unidad de tiempo]
**Magnitud económica estimada**: [Costo del problema, aunque sea aproximado]
```

#### Errores comunes

- **Problema demasiado amplio**: "Mejorar la experiencia del cliente." Eso no es problema, es objetivo de empresa.
- **Problema sin métrica**: "Hay muchas consultas." ¿Cuántas? ¿Comparado con qué?
- **Problema disfrazado de solución**: "El problema es que no tenemos un chatbot." NO. El problema es la sobrecarga; el chatbot es UNA solución posible.
- **Problema cuyo costo de resolver supera el costo del problema**: no chequear esto antes de proponer USD 100k de inversión para un dolor de USD 5k/año.

#### Optativo: benchmark industrial

Investigar cómo competidores o referentes del sector resolvieron problemas similares. **Esto suma muchísimo** porque:

1. Demuestra investigación seria.
2. Da respaldo al approach elegido.
3. Permite anticipar objeciones del docente ("¿pero esto realmente funciona?" → "Sí, John Deere lo aplicó así").

Estructura sugerida:

```markdown
**Cómo abordan este problema en la industria**

1. **[Competidor / referente 1]**: [qué hace, qué tecnología usa, qué resultados publicó]
2. **[Competidor / referente 2]**: [idem]
3. **[Competidor / referente 3]**: [idem]

**Síntesis**: [Patrón común que se repite + diferenciación que nosotros proponemos]
```

#### Referencias del estudio

- Capítulo 03 — Estrategia organizacional (qué es un problema procesable).
- Capítulo 07 — Gestión por procesos (cómo se diagnostica un problema de proceso).

---

### 3.c — Bloque (c) Análisis del Proceso Actual (AS IS)

**Consigna textual** (pp. 2–3):

> "Describir cómo se lleva a cabo el proceso a mejorar actualmente. Utilizar diagrama de flujo del proceso, identificación de tareas, roles y responsabilidades.
> (Ejemplo: si el proceso es selección de personal, no se debe detallar el proceso completo desde la detección de vacante hasta la incorporación, solo la parte de selección)."

#### Qué es AS IS

AS IS = "como es hoy". Es la representación del proceso **antes** de cualquier intervención. Su objetivo es **diagnosticar**, no proponer (la propuesta viene en el bloque d).

Referencia obligatoria: **capítulo 07 — Gestión por procesos** del estudio (BPMN, símbolos, modelado de procesos).

#### Cómo armar el diagrama AS IS

**Paso 1 — Delimitar el alcance**. ¿Dónde empieza el proceso? ¿Dónde termina? La consigna lo dice explícito: **sé quirúrgico**. No abarques de punta a punta toda la cadena.

Ejemplo: si el proceso es "responder consultas técnicas por WhatsApp", el AS IS empieza cuando entra el mensaje y termina cuando se cierra la conversación. **No** empieza cuando el cliente compró el producto 6 meses antes.

**Paso 2 — Identificar actores (roles)**.

```markdown
- Cliente externo
- Operador de atención al cliente (humano)
- Especialista técnico (escalamiento)
- Supervisor (autorizaciones)
- Sistema CRM
```

**Paso 3 — Listar actividades**.

```markdown
1. Cliente envía mensaje
2. Operador recibe notificación
3. Operador lee mensaje
4. Operador clasifica mentalmente: técnica / comercial / queja
5. Operador busca info en CRM / manuales / consulta a compañero
6. Operador redacta respuesta
7. Operador envía respuesta
8. (Si no resolvió) Escala a especialista
9. (Si requiere acción) Crea ticket / pedido / reclamo
10. Cierre de conversación
```

**Paso 4 — Identificar decisiones (gateways en BPMN)**.

```markdown
- ¿Es consulta repetitiva? → respuesta plantilla / respuesta nueva
- ¿Operador tiene conocimiento? → resuelve / escala
- ¿Requiere acción del backoffice? → crea ticket / cierra
```

**Paso 5 — Identificar puntos de dolor (bottlenecks)**. Esto se marca con anotaciones o iconos en el diagrama.

```markdown
- Punto de dolor 1: paso 3-5 toma 15 min promedio
- Punto de dolor 2: paso 5 depende del conocimiento individual del operador
- Punto de dolor 3: paso 8 escalamiento tarda hasta 4h
```

**Paso 6 — Dibujar el diagrama**. Herramientas:

- **bpmn.io** — gratis, no requiere login, exporta SVG/PNG. Ideal para BPMN estándar.
- **draw.io / diagrams.net** — gratis, integra con Google Drive, plantillas variadas.
- **Miro** — colaborativo en tiempo real, freemium.

Símbolos básicos BPMN:

| Símbolo | Significado |
|---|---|
| Círculo vacío | Inicio |
| Círculo grueso | Fin |
| Rectángulo redondeado | Actividad |
| Rombo | Decisión (gateway) |
| Flecha sólida | Flujo de secuencia |
| Flecha punteada | Flujo de mensaje (entre actores) |
| Pool / Lane | Actor o área responsable |

#### Plantilla de descripción narrativa que acompaña al diagrama

```markdown
### Descripción del proceso AS IS

**Disparador**: [Qué inicia el proceso, ej. cliente envía mensaje]

**Flujo**:
1. [Actor A] hace [actividad 1].
2. [Actor B] recibe [output 1] y hace [actividad 2].
3. ...

**Decisiones críticas**:
- [Decisión 1]: criterios actuales → consecuencias.
- ...

**Tiempos promedio por actividad** (estimación o medición):
| Actividad | Tiempo promedio | Variabilidad |
|---|---|---|
| ... | ... | ... |

**Cuellos de botella identificados**:
1. ...
2. ...

**Errores recurrentes**:
- ...
```

#### Errores comunes en AS IS

- **Saltarse el AS IS y pasar directo a la propuesta**: el docente lo nota y baja la nota.
- **AS IS demasiado optimista** ("todo funciona, solo queremos mejorarlo"): si no hay dolor, no hay justificación para invertir.
- **AS IS sin números**: sin tiempos, sin volúmenes, sin tasas de error, el diagnóstico parece de pasillo.
- **Diagrama ilegible** o con notación inventada: usá BPMN estándar.
- **Confundir AS IS con TO BE**: en AS IS NO hay IA todavía. Si en el diagrama AS IS aparece un chatbot, está mal.

#### Referencias del estudio

- Capítulo 07 — Gestión por procesos.
- Capítulo 09 — Automatización integral (ahí está la conexión con BPMN y RPA).

---

### 3.d — Bloque (d) Análisis de mejora

**Consigna textual** (p. 2):

> "Identificar las mejoras sobre el proceso incorporando herramientas de IA. **Justificar la elección.**"

#### Qué se espera

Tomar el AS IS y proponer **mejoras concretas** que incorporen IA u otras herramientas vistas en la diplomatura. **Justificar** cada mejora con un porqué técnico y de negocio.

#### Toolkit para identificar mejoras (de capítulo 07)

1. **Los 5 porqués (Toyota)** — pregunta "¿por qué?" cinco veces sobre cada cuello de botella hasta llegar a la causa raíz.

   Ejemplo:
   - Tiempo de respuesta es 8h. **¿Por qué?**
   - Porque hay backlog. **¿Por qué?**
   - Porque cada consulta toma 15 min. **¿Por qué?**
   - Porque el operador busca info manualmente. **¿Por qué?**
   - Porque no hay base de conocimiento centralizada con búsqueda. **¿Por qué?**
   - Porque nunca se invirtió en eso → causa raíz.
   - **Acción**: implementar base de conocimiento con RAG.

2. **Diagrama de Ishikawa (espina de pescado)** — organiza causas en 6 categorías: Mano de obra, Método, Material, Máquina, Medición, Medio ambiente. Útil para problemas con múltiples causas.

3. **Pareto (80/20)** — ¿qué 20% de las consultas representan el 80% del volumen? Si hay un patrón, ahí está la oportunidad de automatización masiva.

#### Cómo priorizar mejoras

Matriz **Impacto vs Esfuerzo**:

```
       Alto impacto
            ▲
   QUICK    │   GRAN
   WINS     │   PROYECTO
            │
  ──────────┼──────────► Esfuerzo
            │
   IGNORAR  │   REPENSAR
            │
       Bajo impacto
```

- **Quick wins** (alto impacto, bajo esfuerzo): hacelos primero.
- **Gran proyecto** (alto impacto, alto esfuerzo): justifican el TPI.
- **Repensar** (bajo impacto, alto esfuerzo): no hacer.
- **Ignorar** (bajo impacto, bajo esfuerzo): no vale ni el tiempo de explicarlo.

#### Plantilla de mejora propuesta

```markdown
### Mejora N°[X]: [Nombre corto]

**Cuello de botella que ataca**: [Referenciar AS IS]

**Descripción**: [Qué se va a cambiar concretamente]

**Tecnología propuesta**: [Chatbot WhatsApp + RAG / Clasificador ML / RPA / etc.]

**Justificación**:
- Técnica: [Por qué esta tecnología y no otra]
- De negocio: [Qué KPI mueve, qué ahorro genera, qué experiencia mejora]

**Impacto esperado**: [Cuantitativo si se puede, ej. "reducir tiempo de respuesta de 8h a 5 min"]

**Esfuerzo estimado**: [Bajo / Medio / Alto + 1-2 frases de por qué]

**Riesgos**: [Qué puede salir mal y cómo se mitiga]
```

#### Errores comunes

- **Proponer IA porque es IA, no porque resuelva el problema**: "Vamos a poner un chatbot porque la diplomatura es de IA." Eso es decisión por moda, no por análisis.
- **No justificar la elección entre alternativas**: ¿por qué OpenAI y no Claude? ¿Por qué Botmaker y no Twilio? Si no comparás, parece que tiraste un dardo.
- **Saltarse mejoras no-IA que son evidentes**: si lo que necesitás es organizar mejor el backoffice, decilo. La IA no es la solución a todo.
- **Confundir mejora con solución técnica**: la mejora es "reducir tiempo de respuesta automatizando consultas frecuentes". La solución técnica (RAG + chatbot) viene en el bloque (e).

#### Referencias del estudio

- Capítulo 07 — Gestión por procesos (toolkit de análisis).
- Capítulo 09 — Automatización integral (cuándo elegir RPA vs IA vs híbrido).

---

### 3.e — Bloque (e) Detalle de Solución

**Consigna textual** (p. 3):

> "**Requisitos Funcionales y No Funcionales**: Definir qué debe hacer la solución propuesta y las condiciones bajo las cuales debe operar. Ejemplo: integración con sistemas existentes, usabilidad, tiempos de respuesta.
> **Arquitectura de Solución**: Describir la arquitectura de alto nivel de la solución. Evaluar la escalabilidad y seguridad de la solución. Se espera que los grupos presenten **un diagrama de la arquitectura propuesta**, mostrando cómo los diferentes componentes tecnológicos interactúan entre sí."

#### Sub-bloque e.1: Requisitos funcionales (RF) vs no funcionales (RNF)

Esta distinción es la que más se confunde. Memorízala:

| Requisitos Funcionales (RF) | Requisitos No Funcionales (RNF) |
|---|---|
| **Qué hace** el sistema. | **Cómo lo hace** / bajo qué condiciones. |
| Describen comportamientos visibles. | Describen restricciones, calidades, atributos. |
| Verbos de acción: "el sistema debe permitir..." | Cualidades: rendimiento, seguridad, usabilidad, escalabilidad. |
| Ejemplo: "El chatbot debe responder consultas frecuentes en español." | Ejemplo: "El chatbot debe responder en menos de 3 segundos el 95% del tiempo." |

#### Plantilla ERS (Especificación de Requisitos del Sistema) — simplificada

```markdown
### Requisitos Funcionales (RF)

| ID | Requisito | Prioridad |
|---|---|---|
| RF-01 | El sistema debe recibir mensajes desde WhatsApp Business API. | Alta |
| RF-02 | El sistema debe clasificar cada consulta en categorías predefinidas (técnica, comercial, queja, otro). | Alta |
| RF-03 | El sistema debe consultar la base de conocimiento (RAG) para responder consultas técnicas. | Alta |
| RF-04 | El sistema debe escalar a un agente humano cuando la confianza de la respuesta IA sea menor a [X]. | Alta |
| RF-05 | El sistema debe registrar todas las conversaciones en el CRM. | Media |
| RF-06 | El agente humano debe contar con un copiloto IA que sugiera respuestas en tiempo real. | Media |
| RF-07 | El sistema debe permitir al supervisor consultar dashboards de KPIs en tiempo real. | Media |
| RF-08 | El sistema debe soportar consultas en español rioplatense con terminología agrícola. | Alta |

### Requisitos No Funcionales (RNF)

| ID | Categoría | Requisito | Métrica |
|---|---|---|---|
| RNF-01 | Rendimiento | Tiempo de respuesta del chatbot. | <3 seg en p95. |
| RNF-02 | Escalabilidad | Volumen de consultas simultáneas. | Soportar 500 conversaciones simultáneas sin degradación. |
| RNF-03 | Disponibilidad | Uptime del servicio. | ≥99,5% mensual. |
| RNF-04 | Seguridad | Protección de datos personales. | Cumplir Ley 25.326 (Argentina) y buenas prácticas WhatsApp Business. |
| RNF-05 | Usabilidad | Curva de aprendizaje del copiloto interno. | Agentes operativos en <2h de capacitación. |
| RNF-06 | Integrabilidad | Compatibilidad con sistemas existentes. | Integración con CRM actual vía API REST. |
| RNF-07 | Mantenibilidad | Actualización de base de conocimiento. | <1 día desde nuevo documento hasta indexado en RAG. |
| RNF-08 | Costos | Costo por interacción automatizada. | < USD 0,10 por conversación resuelta sin escalamiento. |
| RNF-09 | Privacidad | Manejo de PII en logs. | Anonimización antes de almacenar conversaciones >30 días. |
| RNF-10 | Auditabilidad | Trazabilidad de decisiones IA. | Log estructurado de cada respuesta con fuente RAG citada. |

```

#### Sub-bloque e.2: Arquitectura de Solución

Tenés que presentar **un diagrama de arquitectura de alto nivel** que muestre los componentes y cómo se conectan.

#### Componentes típicos de una solución de IA conversacional + RAG

```
┌──────────────────┐
│ Canal de entrada │  ← WhatsApp Business API, web chat, Instagram, etc.
└────────┬─────────┘
         │
┌────────▼─────────┐
│  Orquestador /   │  ← Plataforma de bot (Botmaker, Aivo, propio)
│  Plataforma bot  │
└────────┬─────────┘
         │
    ┌────┼────┐
    │    │    │
┌───▼─┐ ┌▼───┐ ┌▼──────────┐
│Clasif.│LLM│  │Base de    │
│ML    ││  │  │conocimiento│
└──────┘└──┘  └─────┬──────┘
                    │
              ┌─────▼──────┐
              │Vector DB   │  ← Pinecone, Qdrant, Weaviate
              │(embeddings)│
              └────────────┘

┌──────────────────────────────┐
│  Backoffice / CRM             │  ← Salesforce, HubSpot, propio
│  + Copiloto interno           │
└──────────────────────────────┘

┌──────────────────────────────┐
│  Analítica / Dashboard       │  ← Power BI, Looker Studio
└──────────────────────────────┘
```

#### Plantilla descriptiva de arquitectura

```markdown
### Arquitectura de la solución

**Visión general**: [3-5 oraciones explicando el flujo end-to-end]

**Componentes**:

| Componente | Función | Tecnología propuesta |
|---|---|---|
| Capa de canales | Recibe mensajes desde WhatsApp, redes, web | WhatsApp Business API + integrador |
| Orquestador conversacional | Maneja el flujo del bot, intent detection | [Botmaker / Aivo / Twilio + custom] |
| Clasificador | Categoriza consultas | OpenAI GPT-4o-mini con few-shot, o modelo ML clásico |
| Motor RAG | Recupera info relevante de la base de conocimiento | LangChain / LlamaIndex + Vector DB |
| Vector DB | Almacena embeddings de docs técnicos | Pinecone Serverless / Qdrant Cloud |
| LLM generativo | Genera respuesta basada en contexto RAG | GPT-4o / Claude Sonnet |
| CRM | Registra conversaciones, contactos, casos | [Sistema existente o nuevo: HubSpot, Salesforce] |
| Copiloto interno | Asiste al agente humano | OpenAI Assistants / panel custom |
| Dashboard | KPIs operativos y de negocio | Power BI / Looker Studio |
| Capa de seguridad | Autenticación, logs, anonimización | OAuth2 + KMS + audit logs |

**Diagrama**:

[Insertar diagrama de arquitectura aquí — ver herramientas en sección 2.4]

### Evaluación de escalabilidad

- **Carga esperada**: [X] conversaciones/mes en Y1, [X*2] en Y2.
- **Cuellos potenciales**: tokens del LLM (mitigar con caching), throughput del vector DB (mitigar con sharding), rate limits de WhatsApp (negociar tier).
- **Estrategia de escalado**: serverless en proveedores cloud (Pinecone, OpenAI) escala automáticamente; orquestador con autoescalado horizontal.

### Evaluación de seguridad

- **Datos sensibles que se manejan**: nombre, teléfono, email, consultas técnicas.
- **Cumplimiento**: Ley 25.326 (Protección de Datos Personales — Argentina), buenas prácticas WhatsApp Business Platform.
- **Controles**:
  - Cifrado en tránsito (TLS 1.2+) y en reposo (AES-256).
  - Anonimización de PII en logs de >30 días.
  - Auditoría de accesos al CRM.
  - Acuerdos de procesamiento de datos (DPA) con proveedores cloud.
  - Política de retención: conversaciones se eliminan a los [X] meses.
```

#### Decisión Build / Buy / Partner

Antes de cerrar la arquitectura, justificá cada componente con la decisión Build/Buy/Partner (ver capítulo 09 del estudio):

| Componente | Decisión | Justificación |
|---|---|---|
| Plataforma de bot | **Buy** (Botmaker) | Caro construir desde cero, mejor TTM con producto LATAM. |
| Vector DB | **Buy** (Pinecone serverless) | Operación managed, pay-per-use, escala automática. |
| LLM | **Buy** (OpenAI API) | No reentrenar modelo, pagar por uso. |
| Conectores CRM | **Build** | Integración custom porque CRM es propio. |
| Dashboard | **Buy** (Power BI) | Ya está en la empresa, no duplicar. |
| Capacitación | **Partner** | Consultor externo especializado en gestión del cambio. |

#### Errores comunes

- **Listar componentes sin diagrama**: la consigna pide diagrama explícitamente.
- **Arquitectura "espagueti" con flechas en todas las direcciones**: simplificá. Si no se entiende a primera vista, está mal.
- **Mezclar RF y RNF**: si decís "el sistema debe responder rápido" no es RF ni RNF — definí qué es responder rápido (≤3 seg = RNF).
- **No evaluar escalabilidad ni seguridad**: la consigna lo pide explícito.
- **Asumir que la nube resuelve todo**: la nube es elástica pero los costos crecen con uso. Hay que dimensionar.

#### Referencias del estudio

- Capítulo 08 — Arquitectura tecnológica organizacional.
- Capítulo 09 — Automatización integral (build/buy/partner).
- Capítulo 11 — Ética, privacidad y marco legal AR (Ley 25.326).

---

### 3.f — Bloque (f) Análisis de Proveedores y Costos

**Consigna textual** (p. 3):

> "Identificar proveedores y realizar una estimación de los costos asociados con la implementación de la solución. Debe incluir de mínima costos de **licencias, desarrollo, integración, capacitación y mantenimiento**."

#### Estrategia para investigar proveedores en Argentina

1. **Empezar por LATAM**: proveedores con presencia regional dan mejor soporte, pricing en USD pero facturación local, idioma español. Ej: Botmaker, Aivo, Cliengo.
2. **Sumar globales**: para infra y modelos IA (OpenAI, Anthropic, Pinecone) no hay alternativa local equivalente todavía. Pagás en USD vía tarjeta corporativa.
3. **Evaluar open source self-hosted**: si la organización tiene equipo técnico, alternativas como n8n, Qdrant, Ollama bajan TCO pero suben costos de mantenimiento.
4. **Consultar partners de implementación locales**: si la organización no tiene equipo IA, agregar costo de consultora local en el cálculo.

#### Plantilla comparativa de proveedores

```markdown
### Comparativa de proveedores — [Categoría: Chatbot WhatsApp]

| Proveedor | País | Pricing modelo | Costo estimado | Pros | Contras |
|---|---|---|---|---|---|
| Botmaker | Argentina | Sesiones + add-ons | USD ~100-1.000/mes | Producto LATAM, español nativo, integraciones locales | Curva inicial, dependencia de plataforma |
| Aivo | Argentina | Custom / sin pricing público | A consultar | Líder LATAM, omnicanal | Sin pricing transparente, contratos enterprise |
| Twilio + WhatsApp | EEUU | Por mensaje + WhatsApp fees | USD 0,005 + fee Meta | Flexible, API directa, ecosistema | Necesita desarrollo propio (más TCO) |
| Asisteclick | Colombia | SaaS por agente | Desde USD ~16-99/mes | Económico, pyme | Menos features enterprise |

**Decisión**: [Cuál se elige y por qué — referenciar criterios objetivos: TCO, soporte local, integración con CRM existente]
```

#### Estructura del análisis de costos (lo mínimo obligatorio)

La consigna pide **cinco rubros mínimos**:

1. **Licencias**: costos de plataformas SaaS, APIs, software de pago (mensual o anual).
2. **Desarrollo**: horas de equipo interno o consultora para construir lo custom.
3. **Integración**: conectar con sistemas existentes (CRM, ERP, IVR, etc.).
4. **Capacitación**: entrenar al equipo que va a operar y mantener la solución.
5. **Mantenimiento**: soporte, evolución, parches, monitoreo, actualizaciones.

> **Bonus que suma**: separar **CAPEX** (gasto único de implementación) y **OPEX** (gasto recurrente operativo). Esto demuestra criterio financiero.

#### Plantilla de cálculo de costos

```markdown
### Estimación de costos — [Solución XYZ]

#### CAPEX (inversión inicial, una sola vez)

| Rubro | Detalle | Cantidad | Costo unitario (USD) | Total (USD) |
|---|---|---|---|---|
| Desarrollo | Construcción del orquestador custom | 200 hs | 35 | 7.000 |
| Integración | Conectores CRM + WhatsApp | 80 hs | 35 | 2.800 |
| Setup plataformas | Configuración Botmaker + Pinecone | 1 | 1.500 | 1.500 |
| Indexación inicial RAG | Procesamiento de docs técnicos | 1 | 2.000 | 2.000 |
| Capacitación | 2 jornadas equipo operativo | 1 | 1.500 | 1.500 |
| Capacitación supervisores | 1 jornada + materiales | 1 | 800 | 800 |
| **CAPEX total** | | | | **15.600** |

#### OPEX (gasto mensual recurrente)

| Rubro | Detalle | Cantidad | Costo unitario (USD/mes) | Total (USD/mes) |
|---|---|---|---|---|
| Botmaker | Plan empresa | 1 | 500 | 500 |
| WhatsApp conversaciones | 6.000 conv/mes a USD 0,05 | 6.000 | 0,05 | 300 |
| OpenAI API | GPT-4o mini para clasificación + GPT-4o para RAG | ~10M tokens/mes | (mix) | 250 |
| Pinecone | Serverless 1M vectores | 1 | 70 | 70 |
| Hosting/infra | Servidores + backups | 1 | 100 | 100 |
| Mantenimiento | 10 hs/mes consultor externo | 10 | 35 | 350 |
| Monitoreo / observabilidad | Stack monitoreo | 1 | 50 | 50 |
| **OPEX total/mes** | | | | **1.620** |
| **OPEX anualizado** | | | | **19.440** |

#### TCO a 3 años

| Año | CAPEX | OPEX anual | Total año | Acumulado |
|---|---|---|---|---|
| 1 | 15.600 | 19.440 | 35.040 | 35.040 |
| 2 | — | 19.440 | 19.440 | 54.480 |
| 3 | — | 19.440 | 19.440 | 73.920 |

**Supuestos clave**:
- Tipo de cambio: USD a ARS oficial del mes de cálculo (aclarar fecha).
- Volumen: 6.000 conversaciones/mes constante.
- Hora de desarrollo: USD 35 (rango pyme Argentina 2026, ajustar según tarifa real).
- No incluye inflación ni ajustes de pricing de proveedores.
```

#### Rangos orientativos USD/mes para Argentina 2026 (verificados online)

> **Nota**: estos son rangos orientativos basados en pricing público de proveedores al 2026. **Verificá los números actualizados** al momento de armar el TPI — los proveedores cambian planes y el USD oficial AR fluctúa.

| Categoría | Proveedor | Rango (USD) | Modelo |
|---|---|---|---|
| Chatbot WhatsApp SaaS | Botmaker | Setup gratis hasta 300 sesiones, luego planes USD 100-1.000/mes | Por sesiones + add-ons |
| Chatbot WhatsApp SaaS | Aivo | Custom (a consultar) | Enterprise |
| Chatbot WhatsApp SaaS | Asisteclick / B2Chat | USD 16-99/mes | Por agente / chats |
| WhatsApp Business API | Twilio | USD 0,005 por mensaje + fees Meta | Por mensaje |
| WhatsApp Business API | Setup BSP general | USD 99 una vez (registro Meta) + USD 0,03-0,07 por conversación | Setup + por conv |
| LLM API | OpenAI GPT-4o | USD 2,50 / 1M tokens input, USD 10 / 1M tokens output | Por token |
| LLM API | OpenAI GPT-4o-mini | USD 0,15 / 1M input, USD 0,60 / 1M output (16× más barato que GPT-4o) | Por token |
| LLM API | Anthropic Claude Sonnet 4.x | USD 3 / 1M input, USD 15 / 1M output | Por token |
| LLM API | Anthropic Claude Haiku 4.x | USD 1 / 1M input, USD 5 / 1M output | Por token |
| Vector DB | Pinecone Serverless | Free starter; luego USD 0,33/GB/mes + USD 0,33/1M reads. Builder USD 20/mes flat. | Serverless / flat |
| Vector DB | Qdrant Cloud | Free tier (0,5 vCPU); planes USD 30-200/mes | Por nodo/hora |
| Vector DB | Qdrant self-hosted | USD 20-50/mes en VPS (Hetzner/DO) hasta 10M vectores | VPS |
| Vector DB | Weaviate Cloud (Flex) | Desde USD 45/mes | Plan |
| Automatización | Make.com | Desde USD 9/mes (10k operaciones) | Por operación |
| Automatización | Zapier | USD 20-100/mes business tiers | Por tarea |
| Automatización | n8n cloud | EUR 20-667/mes | Por ejecución |
| Automatización | n8n self-hosted | USD 5/mes VPS, unlimited | VPS |
| BI / dashboard | Power BI Pro | USD 14 / usuario / mes | Por usuario |
| BI / dashboard | Looker Studio | Gratis (con Google Cloud opcional pago) | Gratis |

#### Errores comunes

- **Solo poner precios de licencias y olvidarse del resto** — la consigna pide los 5 rubros mínimo.
- **No separar CAPEX de OPEX** — un proyecto que parece barato porque solo mostrás OPEX miente al patrocinador.
- **No declarar supuestos** — ¿qué tipo de cambio usaste? ¿cuántas conversaciones/mes? ¿qué tarifa horaria? Si no lo decís, no se puede auditar.
- **Precios "de oído" sin fuente** — referenciá la fuente de pricing (página oficial, fecha de consulta).
- **Olvidarse de la capacitación** — la consigna la lista explícitamente.
- **Subestimar mantenimiento** — un proyecto IA en producción necesita al menos 10-20% del costo de desarrollo anual en mantenimiento (incluye actualización de modelos, re-indexación, monitoreo, fixes).

#### Referencias del estudio

- Capítulo 09 — Automatización integral (criterios build/buy).
- Capítulo 16 — Frameworks cheatsheet (matriz TCO).

---

### 3.g — Bloque (g) Implementación (cronograma)

**Consigna textual** (p. 3):

> "Cronograma de implementación (Puede ser GANTT)."

#### Fases típicas de un proyecto IA

Esto es un molde, ajustá según tu caso:

| Fase | Duración típica | Actividades clave |
|---|---|---|
| **1. Análisis y descubrimiento** | 2-4 semanas | Entrevistas, relevamiento, validación de AS IS, refinamiento de requisitos. |
| **2. Diseño** | 2-3 semanas | Arquitectura, mockups, definición de KPIs, plan de gestión del cambio. |
| **3. Desarrollo / Build** | 6-12 semanas | Construcción de integraciones, configuración de plataformas, indexación RAG, prompts iniciales. |
| **4. Pruebas y ajustes** | 2-4 semanas | QA funcional, pruebas de carga, fine-tuning de prompts, ajuste de umbrales de escalamiento. |
| **5. Capacitación** | 1-2 semanas | Entrenamiento operadores, supervisores, sponsors. Documentación. |
| **6. Piloto controlado** | 2-4 semanas | Despliegue en un canal o segmento limitado. Medición. Iteración. |
| **7. Salida en vivo (go-live)** | 1 semana | Lanzamiento full. Monitoreo intensivo. War room. |
| **8. Estabilización y optimización** | 4-8 semanas | Ajustes finos, ampliación de base de conocimiento, optimización de costos. |

**Duración total típica**: 4-6 meses para un proyecto IA conversacional + RAG medio.

#### Hitos clave a marcar

- **Hito 0**: Kickoff (firma de proyecto).
- **Hito 1**: Aprobación de requisitos y arquitectura.
- **Hito 2**: Demo MVP funcional (típicamente al final de la semana 8-10).
- **Hito 3**: Inicio del piloto.
- **Hito 4**: Go-live.
- **Hito 5**: Revisión de KPIs a 30/60/90 días post go-live.

#### Cómo hacer el GANTT

Herramientas (de menor a mayor complejidad):

1. **Google Sheets / Excel** — usar formato condicional para colorear celdas por semana. Simple, suficiente para el TPI.
2. **GanttProject** (gratis, desktop) — genera GANTT visual exportable.
3. **ClickUp / Notion** — si el grupo ya usa una de estas, tiene vista GANTT integrada.
4. **MS Project** — sobrado para el TPI, pero si alguien lo maneja, da resultados profesionales.

#### Plantilla GANTT minimalista (Excel/Sheets)

```
Semana       1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24
Fase 1       ██ ██ ██ ██
Fase 2          ██ ██ ██
Fase 3                ██ ██ ██ ██ ██ ██ ██ ██ ██ ██
Fase 4                                  ██ ██ ██ ██
Fase 5                                        ██ ██
Fase 6                                           ██ ██ ██ ██
Fase 7                                                       ██
Fase 8                                                          ██ ██ ██ ██ ██ ██ ██
Hito 0       ●
Hito 1             ●
Hito 2                            ●
Hito 3                                                 ●
Hito 4                                                       ●
Hito 5                                                                            ●
```

#### Asignación de responsables

Por cada fase, listar:

- **Responsable principal** (RACI: R).
- **Aprobador / sponsor** (A).
- **Consultados** (C): especialistas técnicos, negocio.
- **Informados** (I): gerencia general, áreas adyacentes.

#### Errores comunes

- **Comprimir las fases** para que entre en 2 meses — no es realista, el docente se da cuenta.
- **No incluir fase de capacitación** — es obligatoria por consigna.
- **No mostrar dependencias** entre fases (fase 3 no puede arrancar sin que termine fase 1, etc.).
- **No marcar hitos** — un GANTT sin hitos es solo una barra de progreso.
- **Asumir cero buffers** — siempre dejar 10-15% de buffer por fase para imprevistos.

#### Referencias del estudio

- Capítulo 09 — Automatización integral (fases de implementación).

---

### 3.h — Bloque (h) KPIs + ROI

**Consigna textual** (p. 3):

> "**Indicadores del Proceso**: Definir cómo se medirá el impacto de la solución en el proceso.
> **Retorno de Inversión (ROI)**: Calcular el retorno de la inversión proyectado para la solución."

#### Sub-bloque h.1: KPIs

Un KPI bien definido tiene:

1. **Nombre claro**.
2. **Fórmula explícita**.
3. **Línea de base** (valor actual, antes de la mejora).
4. **Meta** (valor esperado post-implementación).
5. **Frecuencia de medición**.
6. **Fuente del dato**.
7. **Responsable de la medición**.

#### Plantilla de KPI

```markdown
### KPI: [Nombre del indicador]

| Atributo | Valor |
|---|---|
| **Definición** | [Una oración] |
| **Fórmula** | [Cómo se calcula] |
| **Unidad** | [Segundos / % / cantidad / USD] |
| **Línea de base (AS IS)** | [Valor actual] |
| **Meta (TO BE)** | [Valor esperado] |
| **Plazo para alcanzar meta** | [Meses post go-live] |
| **Frecuencia de medición** | [Diaria / semanal / mensual] |
| **Fuente del dato** | [CRM / Dashboard / Logs] |
| **Responsable** | [Rol o persona] |
```

#### KPIs típicos por tipo de proyecto IA

##### Proyectos de IA conversacional / chatbots

| KPI | Fórmula | Meta típica |
|---|---|---|
| Tiempo medio de primera respuesta | (Suma tiempos primera respuesta) / cantidad conversaciones | Reducir 80-95% (de horas a segundos) |
| Tasa de resolución automática | Conversaciones resueltas por bot / total conversaciones × 100 | 50-75% |
| Tasa de escalamiento a humano | Conversaciones escaladas / total × 100 | 25-50% |
| Satisfacción del cliente (CSAT) | Promedio de encuestas post-conversación (1-5) | ≥4,2 / 5 |
| Costo por conversación | Costo total OPEX / cantidad conversaciones | Reducir 60-80% vs baseline |
| Volumen total atendido | Conversaciones/mes | Crecimiento sostenido sin sumar headcount |

##### Proyectos de ML predictivo (clasificación, scoring)

| KPI | Fórmula | Meta típica |
|---|---|---|
| Accuracy / F1 | Métricas estándar de clasificación | Dependiente de dominio, típico ≥85% |
| Precisión vs recall | Trade-off según costo de error | Definir según asimetría |
| Latencia de predicción | Tiempo entre input y output | <1 seg |
| Cobertura | % de casos donde el modelo opina con confianza | ≥90% |
| Drift detectado | Variación de distribución vs baseline | Alertas cuando > X% |

##### Proyectos de automatización (RPA + IA)

| KPI | Fórmula | Meta típica |
|---|---|---|
| Horas-hombre ahorradas / mes | Tareas automatizadas × tiempo unitario | A definir |
| Tasa de éxito de ejecución | Ejecuciones exitosas / total × 100 | ≥98% |
| Tiempo medio de proceso end-to-end | De inicio a fin | Reducir 50-90% |
| Errores por proceso | Errores detectados / volumen × 100 | <0,5% |

#### Sub-bloque h.2: ROI

**Fórmula básica**:

```
                  Beneficio neto (período)
ROI (%)  =   ─────────────────────────────────   ×  100
                  Inversión total
```

Donde:
- **Beneficio neto** = Ahorros (o ingresos incrementales) − Costos operativos del nuevo sistema.
- **Inversión total** = CAPEX + OPEX acumulado en el período evaluado.

#### Variantes útiles

##### Payback Period (período de recupero)

```
Payback (meses)  =   Inversión inicial (CAPEX) / Beneficio neto mensual
```

##### VAN (Valor Actual Neto) — si querés ser fino

```
VAN  =  Σ [ Flujo año t / (1 + r)^t ]  −  Inversión inicial
```

Donde **r** es la tasa de descuento (típica 10-15% para proyectos corporativos en Argentina).

#### Plantilla de cálculo ROI

```markdown
### Cálculo del ROI

**Período evaluado**: 12 meses post go-live.

#### Beneficios estimados

| Concepto | Cálculo | Valor anual (USD) |
|---|---|---|
| Ahorro horas operativas | Reducción de X hs/mes × USD Y/hora × 12 meses | ... |
| Reducción de errores | Costo evitado de retrabajo / reclamos | ... |
| Aumento de conversión comercial | Ventas adicionales por mejor respuesta × margen | ... (si aplica) |
| Reducción de churn | Clientes retenidos × LTV | ... (si aplica) |
| **Beneficio anual total** | | **[Z]** |

#### Costos

| Concepto | Valor (USD) |
|---|---|
| CAPEX (inversión inicial) | [A] |
| OPEX anual | [B] |

#### Cálculo ROI

```
ROI año 1  =  (Beneficio - OPEX año 1) / CAPEX × 100
ROI año 1  =  (Z - B) / A × 100
ROI año 1  =  [X]%
```

#### Payback

```
Beneficio neto mensual  =  (Z - B) / 12
Payback (meses)        =  A / (beneficio neto mensual)
Payback                =  [Y] meses
```

#### Supuestos (críticos, declarar siempre)

1. Volumen: [X consultas / mes].
2. Tiempo unitario actual: [Y min/consulta].
3. Costo hora interno: [USD Z/hora].
4. Tipo de cambio: USD oficial AR del [mes/año].
5. Tasa de automatización esperada: [W%].
6. No incluye inflación ni ajuste de tarifas de proveedores en año 2 y 3.

#### Análisis de sensibilidad

| Escenario | Volumen consultas/mes | Tasa automatización | ROI año 1 |
|---|---|---|---|
| Pesimista | -30% | 40% | [%] |
| Base | 100% | 60% | [%] |
| Optimista | +30% | 75% | [%] |

```

#### Errores comunes en ROI

- **Inflar el ROI con supuestos optimistas y sin declararlos**: el docente revisa los supuestos. Si dicen "ROI 300%" sin sensibilidad, baja la nota.
- **No considerar el OPEX** en el cálculo: solo dividir beneficios sobre CAPEX da números ficticios.
- **Confundir ROI con beneficio**: ROI es **porcentaje**, no monto.
- **No declarar el período**: ROI anual ≠ ROI a 3 años. Aclarar siempre.
- **Calcular ROI sobre beneficios "soft" sin cuantificar**: "mejora la marca" o "satisfacción" están bien como KPIs pero NO como beneficios monetarios sin metodología.
- **Olvidar análisis de sensibilidad**: con supuestos fijos, parece falsa precisión. Mostrar escenarios.

#### Referencias del estudio

- Capítulo 10 — Gestión estratégica de datos (KPIs y métricas).
- Capítulo 16 — Frameworks cheatsheet (fórmulas ROI/VAN/Payback).

---

## 4. Checklist final antes de entregar (16/06/2026)

Imprimí esto y tachá:

### Formato

- [ ] Resumen ejecutivo en **1 hoja** (no se pasa).
- [ ] Desarrollo del proyecto **no excede 12 hojas** (chequear con Word/Docs contando solo desarrollo, no anexos).
- [ ] Anexos al final, separados del desarrollo.
- [ ] Portada con nombre del TPI, integrantes (con DNI o legajo), cohorte, fecha de entrega.
- [ ] Índice / tabla de contenidos.
- [ ] Numeración de páginas.
- [ ] Tipografía y tamaños consistentes en todo el documento.
- [ ] Tablas y figuras numeradas con título y fuente.

### Contenido obligatorio

- [ ] **(a) Contexto**: organización, tamaño, desafíos, área foco delimitada.
- [ ] **(b) Problema u oportunidad**: claramente definido y cuantificado.
- [ ] **(c) AS IS**: descripción + **diagrama de flujo visible**.
- [ ] **(d) Análisis de mejora**: mejoras identificadas y justificadas.
- [ ] **(e.1) Requisitos funcionales y no funcionales** explicitados (no en bullets vagos).
- [ ] **(e.2) Arquitectura**: diagrama + descripción + evaluación de escalabilidad y seguridad.
- [ ] **(f) Proveedores y costos**: tabla comparativa de proveedores + cálculo desagregado (licencias, desarrollo, integración, capacitación, mantenimiento). **CAPEX y OPEX separados**.
- [ ] **(g) Cronograma**: GANTT u otra forma visual + hitos + responsables.
- [ ] **(h.1) KPIs**: definidos con fórmula, línea de base y meta.
- [ ] **(h.2) ROI**: calculado con fórmula visible + supuestos explícitos + análisis de sensibilidad.

### Calidad

- [ ] Coherencia narrativa entre secciones (no contradicciones entre AS IS y mejora, entre arquitectura y costos, entre solución y ROI).
- [ ] Tono homogéneo (idealmente alguien del equipo pasó como editor/a final).
- [ ] Sin faltas de ortografía graves (correr corrector).
- [ ] Citas y referencias bibliográficas al final.
- [ ] Imágenes en buena resolución (≥300 dpi para impresión, mínimo 1080px de ancho para pantalla).

### Optativos (puntos extra)

- [ ] Madurez digital evaluada (bloque a).
- [ ] Benchmark de industria (bloque b).
- [ ] Análisis de sensibilidad multi-escenario (bloque h).
- [ ] Estudio de gestión del cambio (anexo).
- [ ] Roadmap a 3 años (anexo).

### Entrega

- [ ] PDF final generado (no editable).
- [ ] Versión editable (.docx o .gdoc) en backup para correcciones.
- [ ] Subido al Campus Virtual UNRaf por el responsable designado (1 por grupo).
- [ ] Confirmación de subida guardada (captura de pantalla).

---

## 5. Apéndice A — Plantillas reutilizables

### A.1 Plantilla de Resumen Ejecutivo (1 hoja)

```markdown
# [Nombre del proyecto] — Resumen Ejecutivo

**Organización**: [Nombre, sector, tamaño]
**Área de foco**: [Comercial / Servicio técnico / etc.]
**Integrantes**: [Lista]
**Fecha**: [DD/MM/2026]

## El problema
[2-3 oraciones cuantificadas]

## La propuesta
[2-3 oraciones describiendo la solución a alto nivel + tecnologías clave]

## Beneficios esperados
- KPI 1: de [valor actual] a [valor meta]
- KPI 2: de [valor actual] a [valor meta]
- KPI 3: de [valor actual] a [valor meta]

## Inversión y ROI
- CAPEX: USD [X]
- OPEX anual: USD [Y]
- ROI proyectado año 1: [Z%]
- Payback: [N] meses

## Plazo de implementación
[N] meses desde kickoff a go-live, con piloto a partir del mes [X].

## Riesgos principales
1. ...
2. ...
3. ...
```

### A.2 Plantilla ERS (Especificación de Requisitos)

(Ver bloque 3.e arriba).

### A.3 Plantilla GANTT (fases típicas)

(Ver bloque 3.g arriba).

### A.4 Plantilla cálculo ROI

(Ver bloque 3.h arriba).

### A.5 Plantilla matriz Build/Buy/Partner

```markdown
| Componente | Decisión | Costo estimado | Riesgo de hacer (build) | Riesgo de comprar (buy) | Justificación final |
|---|---|---|---|---|---|
| ... | ... | ... | ... | ... | ... |
```

### A.6 Plantilla benchmark de industria

```markdown
## Benchmark — Cómo otros resuelven este problema

| Empresa | Sector | Solución | Tecnologías clave | Resultados publicados | Diferenciación nuestra |
|---|---|---|---|---|---|
| [Empresa A] | ... | ... | ... | ... | ... |
| [Empresa B] | ... | ... | ... | ... | ... |
```

---

## 6. Apéndice B — Trampas comunes (no caigas)

### Trampa 1: Inflar ROI con supuestos optimistas no declarados

> **Síntoma**: "ROI proyectado 350% en año 1."
> **Diagnóstico**: Probablemente asumiste 100% de automatización, sin OPEX recurrente, sin pérdidas por errores del bot.
> **Cura**: análisis de sensibilidad obligatorio. Mostrar escenarios pesimista/base/optimista.

### Trampa 2: Saltarse el AS IS

> **Síntoma**: el documento pasa del contexto a la propuesta de solución sin diagnóstico intermedio.
> **Diagnóstico**: no entendiste el proceso actual, por lo que la solución parece inventada.
> **Cura**: invertí 1 sesión del grupo solo en AS IS. Si nadie puede dibujarlo, nadie lo entiende.

### Trampa 3: Proponer solución sin entender el problema

> **Síntoma**: "Vamos a usar GPT-4 y RAG porque está de moda."
> **Diagnóstico**: decisión por hype, no por análisis.
> **Cura**: justificá cada decisión técnica con un porqué de negocio. Si no podés, la solución está mal elegida.

### Trampa 4: Olvidar requisitos no funcionales

> **Síntoma**: solo hay RF, los RNF aparecen como bullets sueltos sin métricas.
> **Diagnóstico**: subestimás seguridad, escalabilidad, costos, integraciones.
> **Cura**: usar la plantilla ERS con tabla obligatoria de RNF.

### Trampa 5: Comprimir el cronograma de manera irreal

> **Síntoma**: GANTT de 6 semanas para un proyecto de chatbot + RAG + capacitación + go-live.
> **Diagnóstico**: no hay buffer, no hay piloto, no hay estabilización.
> **Cura**: cronograma realista 4-6 meses para soluciones IA conversacional + RAG medianas. Mínimo 3 meses para algo muy chico.

### Trampa 6: No declarar supuestos

> **Síntoma**: aparecen números sin explicación de dónde salieron.
> **Diagnóstico**: el docente no puede auditar, asume que inventaste.
> **Cura**: cada número tiene un supuesto al lado o referencia a tabla de supuestos.

### Trampa 7: Anexos vacíos o sin propósito

> **Síntoma**: anexos con 50 páginas de capturas sin orden.
> **Diagnóstico**: relleno.
> **Cura**: cada anexo tiene título descriptivo, propósito (qué demuestra) y referencias desde el cuerpo principal.

### Trampa 8: No usar referencias al material de la diplomatura

> **Síntoma**: el TPI parece sacado de un libro genérico de IA.
> **Diagnóstico**: no aprovechás el frame conceptual de la diplomatura.
> **Cura**: citá explícitamente conceptos vistos (modelo 4E, BPMN, RPA, modelos de madurez, fases de mejora continua) y enganchá con autores y docentes vistos en cada módulo.

### Trampa 9: No revisar el documento como conjunto

> **Síntoma**: cada sección está bien por separado pero al leer corrido se nota Frankenstein.
> **Diagnóstico**: nadie pasó como editor/a final.
> **Cura**: alguien del grupo se queda con la última semana para coherencia narrativa, sin escribir contenido nuevo.

### Trampa 10: Confiar en el deadline

> **Síntoma**: "Tenemos hasta el 16/06, vamos relajados."
> **Diagnóstico**: en universidad, todo se cae la última semana.
> **Cura**: deadline interno **1 semana antes** del entregable real. Esa última semana es para limpieza, no para escribir contenido.

---

## 7. Cierre y conexión con el Trabajo Final IA-TO

Si estás en el camino del Trabajo Final IA-TO (caso Plantium) además del TPI, leé el capítulo siguiente: **[20 — Apoyo al Trabajo Final IA-TO V2](20-apoyo-trabajo-final-iato.md)**. Ahí está el mapa específico de tu proyecto, qué falta, qué reutilizar y cómo cerrar.

Si solo te interesa el TPI, esta guía cubre todo lo que necesitás. Aplicá la checklist final, dejá que alguien del grupo haga de editor/a, y entregá con **al menos 5 días de margen** sobre el 16/06.

> **Última palabra**: el TPI no es solo un trabajo de carrera. Es la mejor demo que vas a tener para mostrar en una entrevista o para defender una propuesta interna en tu trabajo. Tomátelo en serio — el esfuerzo se ve.

---

[← 18 — Capítulo previo](18-template.md) · [Volver al índice](README.md) · [20 — Apoyo Trabajo Final IA-TO →](20-apoyo-trabajo-final-iato.md)
