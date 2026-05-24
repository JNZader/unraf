# 05 — IA Generativa y modelo 4E: cómo adoptar IAG en una organización sin romper nada

> **Módulo DIATO**: Módulo 2 — Herramientas de IA generativa para el trabajo
> **Docente**: Mg. María Della Torre
> **Cohorte**: 5 (2026)

---

## 1. Concepto

La **Inteligencia Artificial Generativa (IAG)** es la rama de la IA que **no selecciona contenido existente sino que produce contenido nuevo** en respuesta a una indicación en lenguaje natural. La cátedra la define textual:

> *"Rama de la IA capaz de generar contenido de manera automática en respuesta a indicaciones escritas en interfaces conversacionales de lenguaje natural. En lugar de seleccionar contenidos de páginas webs existentes, estas tecnologías toman esos insumos y producen contenido nuevo que puede aparecer en formatos que comprenden todas las representaciones simbólicas del pensamiento humano: textos, escritos en lenguaje natural, imágenes, videos, música y código de software."* (Della Torre, M2-C2 p. 9–10)

La propia docente acompaña esa definición con una provocación que aparece dos veces en las slides: **"¿Dónde está la/s obsolescencia/s?"**. Es una invitación a no leer la definición como dogma: en un campo que se mueve cada seis meses, **toda definición tiene fecha de vencimiento**. Hoy, por ejemplo, esa definición se queda corta para describir agentes, ejecución de código en sandbox, búsqueda web en vivo, generación de video temporal o razonamiento multi-paso.

Sobre esa base, el módulo introduce el **Modelo 4E (Explorar – Evaluar – Ejecutar – Escalar)** como **metodología de adopción organizacional** de cualquier herramienta de IAG. No es un modelo técnico: es un modelo de gestión del cambio.

---

## 2. Intuición

Si tu organización decidiera mañana incorporar un proveedor nuevo —digamos, una plataforma de gestión de RR.HH.—, ¿qué harías? Primero **explorás** opciones, después **evaluás** cuál encaja con tu realidad (precio, seguridad, soporte), después **ejecutás** una prueba piloto en un área, y si funciona, **escalás** al resto.

Eso es 4E. La cátedra simplemente aplica esa lógica clásica de adopción tecnológica al universo IAG, donde el problema no es la falta de herramientas (sobran) sino **la dispersión y el ruido**. Hay decenas de chatbots, cientos de plug-ins, miles de "GPTs personalizados" y agregadores que listan miles de herramientas más. Sin método, lo que pasa es que:

- O probás todo y no profundizás en nada → te quedás con la sensación de que "la IA es para jugar".
- O te enamorás de la primera que probaste → quedás atado a una herramienta sin haber evaluado seguridad ni costos.
- O nunca arrancás → "no sé por dónde empezar" y la organización queda atrás.

El modelo 4E es la receta para **moverse en ese mar sin ahogarse**: explorar con criterio, evaluar con tres aristas concretas, ejecutar acotado, escalar solo lo que ya validaste.

---

## 3. Cuerpo desarrollado

### 3.1 Conceptos previos que conviene fijar

- **Modelo fundacional**: modelo de gran escala entrenado sobre enormes corpus (texto, imagen, audio, código) que sirve como base para múltiples tareas. GPT-4o, Claude Opus 4, Gemini 2.5 y Llama 3 lo son.
- **LLM**: modelo fundacional especializado en lenguaje. Pieza detrás de ChatGPT, Claude, Gemini.
- **Multi-modal**: entiende/genera más de un tipo de contenido (texto + imagen + audio + video).
- **Ventana de contexto**: cuántos tokens (≈palabras) puede leer el modelo en un mismo prompt. Hoy 8k–2M según el modelo. Define cuánto documento le podés pegar.
- **Token**: unidad mínima de procesamiento. ~1 palabra en español = 1,5–2 tokens. Unidad de facturación de las APIs.
- **Fine-tuning vs prompting**: reentrenar (caro, requiere equipo técnico) vs dar buenas instrucciones (barato). Para el 95% de los casos organizacionales, **prompting alcanza**.
- **RAG**: combinar un buscador sobre tus documentos con un LLM. Base de la mayoría de los asistentes corporativos en producción.
- **Agente**: prompt persistente con acceso a herramientas externas. Los Gems de Google son una primera aproximación; el tema se profundiza en Módulo 4.

**Origen técnico**: todo este universo nace del paper *"Attention is All You Need"* (Vaswani et al., 2017, Google Brain), que introduce la arquitectura **Transformer**: procesar texto en paralelo usando mecanismos de *atención* en vez de secuencialmente. GPT, Claude, Gemini, Llama son descendientes directos. No hace falta la matemática, pero sí saber que **estamos sobre 8 años de evolución de una sola arquitectura, no es magia**.

### 3.2 Las 3 alertas de IAG según la cátedra

Clase 2 (p. 20) presenta tres alertas con "estado de mitigación":

| Alerta | Estado cátedra | Lectura honesta |
|---|---|---|
| **Fuente** | mitigada | Parcial. Con *grounding* y *citations* (Anthropic, OpenAI) se piden fuentes, pero el modelo **también inventa fuentes que no existen**. Mitigación real, no total. |
| **Sesgo** | aún en proceso | Honesto. Problema activo sin solución cerrada. Todas las big tech tienen equipos dedicados; nadie declara "resuelto". |
| **Alucinación** | mitigada | **Discutible**. RAG, grounding y citaciones la atenúan, no la eliminan. En 2025 los modelos siguen alucinando en datos numéricos, citas legales, código y eventos recientes. |

> **Matiz**: declarar "alucinación: mitigada" en material formativo es fuerte. La lectura responsable: **la alucinación es estructural a los LLMs actuales**. Se reduce con grounding y prompts que autorizan "no sé", pero **nunca asumas que el modelo no alucinó hasta verificar**. La cátedra es honesta con Sesgo; el mismo criterio aplica a Alucinación.

Los **AI Principles de Google** (2018+), Anthropic y OpenAI suman tres dimensiones a incorporar:

- **Privacidad y seguridad**: qué hace la herramienta con tus datos (reentrena/almacena/expone).
- **Supervisión humana** (*human oversight*): toda decisión consecuente con humano validador.
- **Responsabilidad atribuible**: la Resolución 4/2025 de la Provincia de Buenos Aires consagra **"Responsabilidad Humana"**: cualquier error o filtración derivado de IAG es legalmente atribuido al funcionario que autorizó/supervisó.

### 3.3 Herramientas presentadas por la cátedra

**Gemini Deep Research** (Clase 3 pp. 5–9): funcionalidad de Gemini para investigación en profundidad. Le das un objetivo, arma un plan de investigación, te lo muestra para que apruebes, ejecuta búsquedas iterativas en web + documentos a los que tenga acceso, y sintetiza un informe con citas. Aplicación cátedra: **búsqueda de clientes, proveedores y señales de futuro** (puente directo al Módulo 3).

**Google Gems** (Clase 3 pp. 10–11): *"expertos de IA personalizados que te ayudan con cualquier tema"*. En la práctica, una Gem es un **prompt sistémico guardado** sobre Gemini con rol, objetivo, contexto y archivos. Equivale a *GPTs personalizados* (OpenAI) y *Projects* (Claude). La docente las conceptualiza como **primera aproximación a agentes** (el tema se profundiza en Módulo 4).

**Gemini Canvas** (Clase 3 p. 12): trabajo iterativo sobre documento/código en panel separado. Equivale a *Claude Artifacts* y *ChatGPT Canvas*.

### 3.4 Comparación de las 4 herramientas IAG principales (gap del extract)

La Actividad 4 (Clase 1 p. 28) propone comparar **4 herramientas IAG**. Las slides no las nombran. Por contexto (Clase 3 da fuerte peso al ecosistema Google) y por consenso de mercado 2025, las 4 son **ChatGPT (OpenAI), Gemini (Google), Claude (Anthropic) y Copilot (Microsoft)**.

> **Nota honesta del autor**: Perplexity podría ser la cuarta (#2 en cuota de mercado de chatbots 2025). Acá se toma Copilot porque es el default en organizaciones con Microsoft 365 (gran parte de pymes y sector público argentino). Si la docente confirma otra lista, corregir.

| Dimensión | **ChatGPT** | **Gemini** | **Claude** | **Copilot** |
|---|---|---|---|---|
| **Fortaleza** | Versatilidad, GPTs custom | Integración Google Workspace, Deep Research, Gems | Razonamiento, redacción extensa, código | Integración Microsoft 365, uso empresarial |
| **Ventana contexto** | 128k–1M | 1M–2M | 200k–1M | Depende (GPT-4/5 vía OpenAI) |
| **Multi-modal** | Sí | Sí (nativo) | Sí (texto+imagen) | Sí |
| **Funcionalidad agéntica** | GPTs, Operator | Gems, Deep Research | Projects, Claude Code, MCP | Copilot Studio |
| **Privacidad plan business** | No entrena con tus datos | No entrena | No entrena | No entrena, data residency |
| **Privacidad plan gratuito** | Reentrena (desactivable) | Reentrena (desactivable) | No reentrena por defecto | N/A (Copilot es empresarial) |
| **Mejor para** | Brainstorming, GPTs custom | Workspace, investigación documental | Texto largo, código, razonamiento | M365, sector corporativo y gubernamental |
| **Cuota mercado 2025** | ~82% | Top 5 | Top 5 | ~3% (creciendo en empresas) |

**Lectura ejecutiva**: las 4 son comparables en capacidad bruta. Lo que define la elección es **el ecosistema preexistente** (Google → Gemini, Microsoft → Copilot), **el tipo de tarea dominante** (Claude para texto largo/código, ChatGPT para brainstorming, Gemini para investigación) y **la política de privacidad** (siempre plan empresarial para datos sensibles).

### 3.5 Modelo 4E en detalle (eje del módulo)

Clase 3 (pp. 13–22) presenta el ciclo **Explorar → Evaluar → Ejecutar → Escalar** como diagrama de cuatro cuadrantes que se retroalimenta. No es lineal: al terminar de escalar, **volvés a explorar**. Mejora continua explícita.

#### Fase 1 — EXPLORAR

> *"Búsqueda de herramientas adecuadas para resolver el problema/desafío. Se proponen explorar recursos existentes que condensan múltiples herramientas de IA."* (M2-C3 p. 14)

**Qué hacer**: definir primero el **problema** (no la herramienta); buscar en agregadores (*There's An AI For That*, *Futuretools*); mirar casos análogos; shortlist de **3–5 candidatas máximo**.

**Output**: shortlist documentada con una línea por candidata explicando qué promete resolver.

#### Fase 2 — EVALUAR (3 aristas)

> *"Guía de preguntas en tres categorías: Seguridad y privacidad, potencia de uso y características (T&C)."* (M2-C3 p. 16)

**Arista 1 — Potencia de uso**: ¿resuelve el caso con calidad? ¿curva de aprendizaje? ¿se integra al stack actual? ¿ventana de contexto suficiente? ¿API o solo web?

**Arista 2 — Seguridad y privacidad**: ¿qué hace con mis datos (reentrena/almacena/cuánto tiempo)? ¿certificaciones (SOC 2, ISO 27001, HIPAA)? ¿zero-data-retention? ¿dónde residen los datos? (importa para Ley 25.326 y sector público).

**Arista 3 — Características (T&C)**: ¿costo y modelo? ¿responsabilidad por contenido infractor? ¿propiedad intelectual de los outputs? ¿qué pasa si cambian T&C o discontinúan? ¿lock-in?

**Output**: matriz comparativa con puntaje por arista. La que mejor balancea las 3 pasa a Ejecutar.

#### Fase 3 — EJECUTAR

> *"Implementación de la herramienta en la solución del desafío."* (M2-C3 p. 18)

**Qué hacer**: piloto acotado (un caso, un equipo, un trimestre); métricas de éxito definidas **antes** (tiempo, calidad, satisfacción, NPS interno); documentar prompts y workflows desde el día 1; capacitación (ROCEF, alertas, T&C).

**Output**: reporte de piloto con métricas, biblioteca de prompts, lista de issues.

#### Fase 4 — ESCALAR

> *"Extrapolar la experiencia a otros procesos. El proceso toma el concepto de **mejora continua** y retroalimenta al proceso iniciado, por lo cual la metodología vuelve a iniciar en la instancia de exploración."* (M2-C3 p. 18)

**Qué hacer**: extender a equipos análogos; estandarizar biblioteca de prompts; gobernanza (quién aprueba nuevos casos, quién audita, quién decide upgrades); **volver a Explorar** (cada 12 meses como máximo).

**Output**: política interna de IAG, programa de adopción, hoja de ruta de próximos pilotos.

---

## 4. Caso real organizacional

### Caso: Provincia de Buenos Aires — Resolución 4/2025

En 2025, la Provincia de Buenos Aires se convirtió en **la primera jurisdicción argentina con un marco vinculante específico para uso de IAG en el sector público** (Agenda Digital 2024-2027). Aplicación implícita del 4E:

- **Explorar**: relevó herramientas en uso informal y riesgos.
- **Evaluar**: aplicó las 3 aristas. Definió cuáles son aceptables, condiciones de seguridad y T&C compatibles con normativa pública.
- **Ejecutar**: emitió la Resolución 4/2025 que **obliga a autorización jerárquica formal** y consagra el principio de **"Responsabilidad Humana"** (todo error o filtración es atribuible al funcionario que autorizó el uso).
- **Escalar**: aplica a toda la administración provincial, con actualización continua.

Caso doble valioso: **es argentino y reproducible** en cualquier organización pública o privada, y **resuelve la responsabilidad** sin prohibir (uso clandestino) ni liberar (caos).

### Caso: contraste con Globant (sector privado, escala global)

Globant escaló de modo radicalmente distinto. Su 4E empresarial: R&D interno 2023-2024 (Explorar/Evaluar), lanzamiento de AI Pods y Enterprise AI en producción (Ejecutar), y *The Station* en agosto 2025 con +50 agentes certificados accesibles a cualquier empleado (Escalar).

**Contraste**: Buenos Aires escaló **regulando**, Globant escaló **productizando**. Ambos casos son válidos. Lo que comparten: ninguno improvisó, ambos tienen proceso documentado de Evaluación y Ejecución antes de escalar.

---

## 5. Aplicación a la transformación organizacional

El modelo 4E es la **piedra angular operativa** del módulo para cualquiera que tenga que llevar IAG a una organización real. Tres lineamientos clave:

### 5.1 No empieces por la herramienta, empezá por el desafío

Si la conversación arranca por "comprémonos ChatGPT Enterprise" sin problema asociado, gastás plata y perdés credibilidad. Empezá por: *¿qué proceso tarda mucho, tiene baja calidad o frustra al equipo?*

### 5.2 La evaluación de 3 aristas es un comité

**Potencia de uso** la evalúa el área usuaria. **Seguridad y privacidad** la evalúa IT. **T&C** los evalúa Legales/Compras. Si decide una sola persona, alguna arista queda floja. **Comité de 3 que firma conjuntamente.**

### 5.3 Escalar sin capitalizar el piloto = fracaso

Mayor error de organizaciones que adoptan IAG: escalar acceso sin documentar aprendizajes. Resultado: 200 personas con la herramienta, cero prompts compartidos, cada uno reinventa la rueda. Escalar exige llegar con **biblioteca de prompts versionada, política, training mandatorio y métricas**. Sin eso no escalás: **dispersás**.

### 5.4 Reaplicación a casos concretos

4E aplica idéntico a: **RRHH** (descripciones de puesto, filtro de CVs), **Atención al cliente** (asistente de tickets nivel 1), **Finanzas** (resúmenes de informes), **Legales** (comparación de contratos, detección de cláusulas anómalas), **Operaciones** (procedimientos a partir de transcripciones). La receta es la misma: explorar, evaluar 3 aristas, ejecutar piloto, escalar con gobernanza.

---

## 6. Errores comunes / mitos

| Error / mito | Corrección |
|---|---|
| *"La IA es 100% confiable, ya no alucina"* | Las alucinaciones siguen vivas en 2025 (datos numéricos, citas legales, eventos recientes). Verificar fuentes. Activar grounding/RAG. Autorizar "no sé" en el prompt. |
| *"No leo los T&C, todas las herramientas son iguales"* | Diferencias enormes entre gratuito (reentrena) y empresarial (no). Leer T&C o usar plan empresarial con cláusula de no-reentrenamiento. |
| *"Probamos una herramienta, no funcionó, descartamos IA"* | Confunde "esta herramienta" con "la categoría". Iterar herramientas o caso de uso. Una sola prueba no concluye. |
| *"Le damos acceso a toda la organización, que cada uno se las arregle"* | Salto directo a Escalar sin piloto. Receta para caos. Piloto → biblioteca → capacitación → escalar con gobernanza. |
| *"La alucinación se resuelve con la IA más cara"* | Modelos premium reducen errores pero no los eliminan. Combinar buen modelo + buen prompt + verificación humana. |
| *"Si el modelo cita una fuente, la fuente existe"* | Los modelos inventan papers, URLs y autores con apariencia de verdadero. Chequear cada cita en entregables formales. |
| *"Compramos Gemini porque es de Google y es lo mejor"* | Decidir por marca, no por adecuación. Aplicar la matriz de 4 herramientas + 3 aristas. |
| *"Una vez adoptada la herramienta, ya está"* | Ignora la naturaleza cíclica del 4E. Mercado cambia cada 6 meses. Volver a Explorar cada 12 meses. |
| *"El piloto fue exitoso, escalamos mañana"* | Escalar requiere infraestructura organizacional (políticas, training, métricas), no solo licencias. |
| *"Cuando algo sale mal, la culpa es de la IA"* | Principio de Responsabilidad Humana (Resolución 4/2025, Google AI Principles, OpenAI, Anthropic). El humano que autorizó/supervisó es el responsable. |

---

## 7. Checklist

### Para evaluar una herramienta IAG antes de adoptarla

- [ ] **Desafío organizacional** claramente definido (no empezar por la herramienta).
- [ ] **Shortlist de 3 a 5 candidatas** documentada.
- [ ] **Arista 1 — Potencia de uso**: probada con casos reales del equipo que la va a usar.
- [ ] **Arista 2 — Seguridad y privacidad**: T&C leídos, residencia de datos confirmada, política de reentrenamiento clara.
- [ ] **Arista 3 — Características (T&C comerciales)**: costo, modelo de suscripción, política de IP, condiciones de salida (lock-in).
- [ ] **Matriz comparativa** firmada por área usuaria + IT + Legales.

### Para ejecutar un piloto

- [ ] **Caso de uso acotado** (un equipo, un proceso, un trimestre).
- [ ] **Métricas de éxito** definidas **antes** del piloto.
- [ ] **Biblioteca de prompts** versionada desde el día 1.
- [ ] **Capacitación** del equipo en ROCEF + alertas + T&C.
- [ ] **Plan de verificación humana** de outputs sensibles.
- [ ] **Responsable identificado** por cada uso (principio de Responsabilidad Humana).

### Para escalar

- [ ] **Reporte de piloto** con métricas y aprendizajes documentados.
- [ ] **Política interna de IAG** publicada (casos permitidos, prohibidos, autorización, datos sensibles).
- [ ] **Training mandatorio** para nuevos usuarios.
- [ ] **Gobernanza**: comité que aprueba nuevos casos de uso, audita, decide upgrades.
- [ ] **Plan de revisión cíclica**: cuándo volvemos a Explorar (recomendado: cada 12 meses).

---

## 8. Para profundizar

- **Andrew Ng — *Generative AI for Everyone*** (Coursera/DeepLearning.AI, gratis con auditoría): curso de referencia para no-técnicos. Fundamentos, ciclo de vida, prompt engineering, impacto societal, oportunidades de negocio. Imprescindible para mandos medios.
- **Google AI Principles** (*ai.google/principles/*): marco vigente desde 2018. Lectura corta y fundamental.
- **OpenAI Usage Policies** y **Anthropic Acceptable Use Policy**: leerlos en paralelo da el mapa de lo prohibido.
- **Vaswani et al. (2017). *Attention is All You Need*. NeurIPS** (arxiv.org/abs/1706.03762): paper origen de todos los LLMs actuales. Leer abstract e intro alcanza para perspectiva histórica.
- **Resolución 4/2025 — Subsecretaría de Gobierno Digital, Provincia de Buenos Aires**: template argentino para sector público y privado.
- **Globant — AI Pods, Enterprise AI 2.0, The Station**: caso de escalamiento empresarial argentino (Bloomberg Línea, La Nación, Infobae).
- **CEPE-Fundar — Encuesta Nacional sobre Adopción de IA**: datos por provincia, sector y tamaño.
- **Stanford HAI — *Artificial Intelligence Index Report***: informe anual con métricas globales. Útil para benchmarking.

---

## Próximo paso

En el próximo capítulo (**06 — IA en estrategia organizacional**) vamos a salir del nivel "herramienta" y subir al nivel "estrategia": cómo se integra la IA en la planificación organizacional, qué KPIs se redefinen, qué procesos se rediseñan y qué cambia en la conducción cuando la IA pasa de ser un asistente personal a ser un componente estructural de la operación.

---

## Referencias

### Cátedra
- Della Torre, M. (2026). *Módulo 2 — Herramientas de IA generativa para el trabajo*. Clases 2 y 3 (slides completas). DIATO, UNRaf, Cohorte 5.

### Externas (consultadas para este capítulo)
- **Ng, A.** *Generative AI for Everyone*. DeepLearning.AI / Coursera.
- **Google** — *AI Principles* (ai.google/principles/) y *Responsible AI Framework*.
- **Anthropic** — *Acceptable Use Policy* y *Responsible Scaling Policy*.
- **OpenAI** — *Usage Policies* y *Model Spec*.
- **Vaswani et al.** (2017). *Attention is All You Need*. NeurIPS. arXiv:1706.03762.
- **Phoenix, J. & Taylor, M.** (2024). *Prompt Engineering for Generative AI*. O'Reilly. ISBN 9781098153434.
- **Provincia de Buenos Aires** — Resolución 4/2025, Subsecretaría de Gobierno Digital.
- **Globant** — comunicaciones corporativas 2025 (AI Pods, Enterprise AI 2.0, The Station, YPF). Cobertura: Bloomberg Línea, La Nación, Infobae, Investing.com.
- **CEPE-Fundar** — *Encuesta Nacional sobre Adopción de IA*.
- **Gmelius / Infobae / La Nación / Profesional Review** — comparativas de mercado 2025 (ChatGPT, Gemini, Claude, Copilot, Perplexity).

> **Próximo capítulo**: [06-ia-en-estrategia-organizacional.md](./06-ia-en-estrategia-organizacional.md)
