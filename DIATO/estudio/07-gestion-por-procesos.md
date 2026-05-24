# 07 — Gestión por procesos

> Módulo 4 de DIATO (Zinggerling & Contreras). Si el capítulo 06 te dio el "hacia dónde" estratégico, este capítulo te da el "cómo se hace en la operación". Y arranca con una distinción que te conviene tatuarte: **transformación digital no es lo mismo que digitalización**.

---

## 1. Concepto

**Gestión por procesos** es el enfoque que **comprende y administra los procesos interrelacionados de una organización como un sistema**, con el objetivo de contribuir a la eficacia y eficiencia en el logro de los resultados previstos.

Suena a definición de norma ISO porque, en parte, lo es. Pero el módulo lo lleva a un terreno operativo: gestionar por procesos es la alternativa a gestionar por funciones (el clásico organigrama vertical donde cada gerencia tira para su lado y se desentiende del resultado final que ve el cliente).

Antes de entrar a procesos, una distinción ineludible que la cátedra (Zinggerling & Contreras, 2026) marca de entrada:

| Concepto | Definición | Ejemplo cátedra |
|---|---|---|
| **Digitalización** | Convertir datos analógicos a formato digital | UNRaf reemplaza el envío de escaneos por un Google Forms para pre-inscripciones |
| **Transformación digital** | Cambios profundos por aplicación de tecnología digital con foco en experiencia, eficiencia y nuevas oportunidades de negocio. **Rediseña procesos.** | Supermercado que integra compra online, gestión de pedidos, fidelización y entrega en una sola app |

La diferencia no es retórica: **digitalizar un proceso ineficiente lo único que hace es escalar la ineficiencia**. Esto se llama, técnicamente, "automatizar el silo". Más adelante volvemos.

---

## 2. Intuición

Pensá en cómo se prepara un mate (el ejemplo de la cátedra — el Profesor Zinggerling tira esto con cariño rioplatense):

- **Inicio**: ganas de tomar mate
- **Entradas**: agua, yerba, azúcar (NO!)
- **Actividades**: poner agua del dispenser en el termo → pasar a la pava eléctrica → calentar a 85° → volver el agua al termo → colocar yerba en el mate
- **Salida**: mate listo para tomar

Eso es un proceso: una **secuencia ordenada de actividades, con entradas y salidas, que agrega valor a un cliente** (en este caso, vos mismo).

Ahora imaginate la misma escena pero en una organización con efecto silo:

- "Comprar yerba" depende de la gerencia de Compras (que tiene su propio proveedor preferido)
- "Calentar agua" depende de Mantenimiento (que decide cuándo se prende la pava según consumo eléctrico)
- "Servir el mate" depende de Recepción
- Y cada uno mide su propio KPI: Compras mide costo por kilo, Mantenimiento mide consumo eléctrico, Recepción mide tiempo de atención.

Resultado: nadie es responsable de que el mate llegue caliente. Cada uno cumplió su métrica, pero el cliente final tomó agua tibia con yerba vieja. Esto es **efecto silo**.

El enfoque por procesos atraviesa **horizontalmente** ese organigrama vertical y dice: *"el responsable del mate caliente es el dueño del proceso 'preparar mate', y todas las áreas le rinden cuentas a ese proceso, no a su jefe funcional"*. Esto cambia poder, métricas y cultura. No es menor.

---

## 3. Cuerpo desarrollado

### 3.1. Proceso vs Función — el clásico que sigue vigente

Las organizaciones tradicionales se estructuran por **funciones** (Marketing, Ventas, Finanzas, Operaciones, RRHH). Cada función tiene su jefe, su presupuesto, su métrica. El cliente, mientras tanto, **atraviesa todas esas funciones** para recibir el producto o servicio.

El **efecto silo** es lo que pasa cuando cada función optimiza lo suyo sin mirar el flujo completo:

- El equipo de I+D diseña un producto técnicamente óptimo… pero imposible de fabricar a costo razonable.
- Operaciones produce con la mejor calidad… pero llega tarde al cliente porque Logística no fue consultada.
- Atención al cliente baja tiempos de respuesta… pero deriva todo al área técnica que se ve desbordada.

El ejemplo de cátedra es brutal y reconocible: **un contrato de I+D universitario** que pasa por Labs, Transferencia Tecnológica, Despacho, Legales, Administración y Rectorado. Cada área tiene su propio criterio, su propio tiempo, su propio formulario. El investigador que necesita el contrato espera 4 meses para algo que en flujo lineal se hace en 3 semanas.

La **gestión por procesos** define el contrato como un **proceso end-to-end**, con dueño claro, indicadores claros y todas las áreas alineadas al output.

### 3.2. BPM y BPMN 2.0 — el lenguaje compartido

**BPM** (Business Process Management) es el modelo de gestión de negocio por procesos. Es la disciplina.

**BPMN** (Business Process Modelling and Notation) es la **notación** estándar para modelar procesos. Es como las partituras de la música: te permite que un consultor en Buenos Aires, un desarrollador en Bombay y un analista en Berlín lean el mismo diagrama y entiendan lo mismo.

BPMN 2.0 es un estándar **OMG** (Object Management Group) — la especificación oficial está en [omg.org/spec/BPMN/2.0/](http://www.omg.org/spec/BPMN/2.0/) y también está formalizada como **ISO/IEC 19510:2013**. Recurso público de referencia: [bpmn.org](https://www.bpmn.org/).

Símbolos básicos que tenés que reconocer:

| Símbolo | Significado |
|---|---|
| **Óvalo / círculo** | Inicio y fin del proceso |
| **Rectángulo redondeado** | Actividad o tarea |
| **Rombo** | Decisión (gateway) — Sí/No, exclusivo, paralelo |
| **Flecha** | Flujo de secuencia |
| **Carril (swim lane)** | Responsable (área, rol, sistema) |
| **Sobre** | Mensaje (evento de comunicación) |
| **Reloj** | Evento temporal |

Con esto y un poco de criterio modelás el 90% de los procesos de una organización mediana.

### 3.3. Etapas de diseño — Identificación → Modelado → Validación

Tres etapas del framework de cátedra:

**Identificación** — definir **objetivo** (qué problema resuelve, frase corta), **indicadores** (tiempo de ciclo, % errores, costo unitario), **alcance** (sin boil the ocean), **dueño/a** (UN nombre con autoridad real) y **participantes**. Sin esto todo lo demás es arena.

**Modelado** — (a) **Relevamiento**: cómo es hoy (info previa, entrevistas individuales y grupales, observación directa). Trampa: relevar el manual en vez de lo que hace la gente; ahí está el 80% de los problemas. (b) **Modelado**: bajar a diagrama el actual (**AS IS**), identificar mejoras con el toolkit y diseñar el propuesto (**TO BE**). Las dos son obligatorias. Saltarse el AS IS es el pecado capital.

**Validación** — documentación (descriptivos, procedimientos) + comunicación (verificación con dueño/a y referentes, difusión). Un proceso modelado que no se valida es un PDF lindo que no cambia nada.

### 3.4. Anti-patrón fundacional — automatizar procesos ineficientes

Cita de Bill Gates (mil veces atribuida a él, mil veces apropiada por la disciplina BPM) que la cátedra parafrasea:

> *"Automation applied to an inefficient operation will magnify the inefficiency."*

Traducido: si automatizás un proceso ineficiente, no obtenés eficiencia — obtenés **ineficacia escalada**. Antes de meter RPA, agentes IA o cualquier capa de software encima, **rediseñá el proceso**. Si no, lo único que vas a lograr es que los errores ocurran más rápido y a mayor volumen.

Esto se conecta con la diferencia digitalización/transformación digital del inicio:

- **Digitalizar** un proceso roto = automatización del problema.
- **Transformar digitalmente** = rediseñar el proceso aprovechando lo que la tecnología habilita.

### 3.5. Toolkit de mejora — las 6 herramientas que la cátedra usa

Cuando ya tenés el AS IS modelado, viene el análisis de problemas:

#### 3.5.1. 5 por qués (Toyota)

Técnica de Sakichi Toyoda. Frente a un problema, preguntás "¿por qué?" cinco veces y llegás a la **causa raíz**. Ejemplo: cliente recibió tarde el pedido → salió tarde del depósito → sistema no emitió orden → pago no confirmado → banco demora 4hs → seguimos con cobro batch en vez de instantáneo. Solución: cambiar el método de cobro, no presionar al depósito.

#### 3.5.2. Diagrama de Ishikawa (causa-efecto)

Visualiza un problema central y causas agrupadas en las **6 M**: Materiales, Métodos, Maquinaria, Mano de obra, Medio ambiente, Mediciones. Excelente para sesiones grupales con causas concurrentes.

#### 3.5.3. Diagrama de Pareto (80/20)

**El 20% de las causas genera el 80% de los problemas**. Histograma ordenado + línea de acumulado. Prioridad sin discusión política.

#### 3.5.4. Simulación

Modelar el proceso en software (Bizagi, Disco) y correrlo con distintas configuraciones de recursos y volúmenes. Probar el TO BE antes de implementarlo, especialmente cuando el cambio tiene costo alto de reversa.

#### 3.5.5. Minería de procesos (process mining)

**Reconstruye el proceso real** a partir de logs de los sistemas (ERP, CRM, ticketing). Dibuja el AS IS **objetivo** — no el que la gente dice, sino el que las máquinas registran. Herramienta de referencia: **Disco** de Fluxicon ([fluxicon.com/disco/](https://fluxicon.com/disco/)), [User Guide](https://fluxicon.com/book/read/reference/). Revelación típica: descubrir que el proceso real tiene 40 variantes cuando el manual dice 3.

#### 3.5.6. IA generativa para procesos

Aporte fresco del módulo: ChatGPT/Gemini/Copilot para generar diagramas de flujo desde texto, sugerir mejoras al AS IS (5 por qué + Ishikawa), documentar procedimientos desde transcripciones de entrevistas, detectar inconsistencias entre modelo y política interna.

### 3.6. Herramientas operativas que vas a usar en el módulo

- **Miro** ([miro.com](https://miro.com/app)) — pizarra colaborativa para modelar AS IS / TO BE en equipo. Tiene plantillas de diagramas de flujo multifuncionales (con carriles).
- **Napkin.ai** ([napkin.ai](https://www.napkin.ai/)) — convierte texto en diagramas visuales automáticamente. Útil para borradores rápidos y comunicación.
- **Disco** (Fluxicon) — minería de procesos sobre logs reales.
- **Bizagi / Camunda / Signavio** — modeladores BPMN profesionales (no cubiertos en el módulo, pero estándar de mercado).
- **ChatGPT / Gemini / Copilot** — asistentes para texto-a-diagrama, análisis de causa raíz, generación de procedimientos.

### 3.7. La paradoja de la generación IA

Cita literal de la cátedra (Zinggerling & Contreras), referenciando datos de 2025:

> *"Casi ocho de cada diez empresas han implementado IA de alguna forma, pero aproximadamente el mismo porcentaje no informa ningún impacto material en las ganancias. A esto lo llamamos la **paradoja de la generación IA**."*

El dato se alinea con el [*State of AI 2025* de McKinsey](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai): 88% adopción, sólo 6% captura valor diferencial. El "scaling gap" es el síntoma, y la causa raíz suele estar en los **procesos**: organizaciones que metieron IA encima de procesos rotos, esperando un milagro que nunca llega.

La gestión por procesos es **la condición de posibilidad** para que la IA genere valor real, no fuegos artificiales.

### 3.8. Estado del arte — qué prioriza 2026

La cátedra menciona los cinco frentes prioritarios identificados para 2026:

1. **Experiencia del cliente individualizada y en tiempo real**
2. **Operaciones eficientes y resilientes que se adaptan y evolucionan**
3. **Investigación y desarrollo acelerados e innovación disruptiva**
4. **Planificación estratégica predictiva basada en IA**
5. **Experiencia de talento personalizada y basada en datos**

Los cinco tienen un denominador común: **procesos rediseñados con datos en tiempo real**. Ninguno funciona sobre una capa de Excel mensual.

---

## 4. Caso real organizacional

### Caso 1 — Universidad: contrato de I+D end-to-end

El caso que la cátedra trae como ejemplo de efecto silo. Antes:

- **AS IS**: investigador necesita contrato → 6 áreas en serie con criterios desalineados → 4 meses de espera → pérdida de oportunidad de convenio.
- **TO BE**: dueño del proceso designado en Transferencia Tecnológica → checklist único validado por las 6 áreas en paralelo → 3 semanas con SLA por área → trazabilidad pública del estado.

Resultado típico de este rediseño: bajar de 4 meses a 21 días sin contratar gente nueva, solo cambiando el flujo y dándole autoridad al dueño del proceso.

### Caso 2 — Fábrica argentina de envases plásticos

Implementó minería de procesos con Disco sobre su ERP. Hallazgos: el proceso de "atención de pedido" tenía **24 variantes reales** vs las 2 documentadas; 60% de los retrabajos venía de UNA causa (clientes nuevos sin código confirmado); cuello de botella en validación de crédito manual (3 días promedio).

Rediseño: scoring automático con override sólo para excepciones, alta de cliente bloqueante al inicio, tablero en vivo de cuellos. Resultado: ciclo de 11 a 5 días, retrabajos del 18% al 4%.

### Caso 3 — Banco regional: apertura de cuenta PyME

AS IS: 7 pasos en 4 áreas, papel, 9 días. TO BE con IA: onboarding digital con OCR + validación AFIP/IGJ, IA asistente que rellena formularios desde la conversación oficial-cliente, KYC con scoring automático + revisión humana sólo en alertas. Resultado: de 9 a 2 días, errores del 12% al 3%.

### Caso 4 — Supermercado integrado (cátedra)

Antes: web + WhatsApp + fidelización interna + delivery tercerizado, cada canal con su sistema. Transformación digital: una sola app integrada con **rediseño completo del proceso "cliente compra"**, no digitalización por canal. NPS sube, CAC baja, recompra sube.

---

## 5. Aplicación a la transformación organizacional

Pasos concretos para iniciar un proyecto BPM con IA:

1. **Elegí UN proceso con dolor concreto** — no arranques modelando todos los procesos (boil the ocean). El proceso elegido debe tener dolor visible, volumen y sponsor con autoridad.
2. **Asigná un dueño con autoridad real** — UN nombre, no "el comité". Sin autoridad para pisar pies a gerentes funcionales, modelás un PDF lindo que nadie obedece.
3. **Relevá el AS IS sin atajos** — entrevistas + observación + minería de procesos con Disco si hay logs. **No saltes esta etapa**: la cátedra es enfática.
4. **Analizá causas raíz con el toolkit** — 5 por qués (causa raíz) + Ishikawa (causas concurrentes) + Pareto (80% del impacto).
5. **Diseñá el TO BE con IA generativa como copiloto** — prompts ROCEF (cap. 06) para sugerir mejoras, generar BPMN en Miro/Napkin, documentar procedimientos, detectar inconsistencias. **El humano valida siempre**.
6. **Simulá antes de implementar** — cuando el cambio tiene costo alto de reversa, usá Bizagi simulator, Disco simulación o mesa con el equipo.
7. **Implementá con métricas desde día 1** — definí KPIs del TO BE **antes** de implementar. Si a 90 días no mejora, volvé al diseño.
8. **Iterá** — el TO BE de hoy es el AS IS del año que viene. BPM es continuo, no un proyecto con fecha de cierre.

---

## 6. Errores comunes / mitos

- **"Transformación digital = digitalización"** — el error que más cuesta. Digitalizar es subir el form a Google Forms; transformar es rediseñar el proceso aprovechando que ya no necesitás el form. Sin esa distinción, gastás millones en software y la gente sigue trabajando como en 1995.
- **"Saltar el AS IS para ir al TO BE"** — el pecado capital. Resultado: TO BE diseñado en una sala con consultores que nunca pisaron la planta. La gente sabe que es mentira y lo ignora.
- **"Automatizar lo ineficiente lo hace eficiente"** — lo contrario: lo hace **ineficaz a mayor escala**. RPA encima de un proceso roto = errores a velocidad de máquina. Primero rediseñás, después automatizás.
- **"BPMN es para consultores aburridos"** — BPMN es **lenguaje compartido**. Sin notación común cada gerencia dibuja con sus símbolos y nadie entiende a nadie. Aprender los 7 símbolos básicos toma un día y ahorra años.
- **"El dueño del proceso es 'el equipo'"** — no. UN nombre, con autoridad y métricas. Si el dueño es "el equipo", el dueño es nadie.
- **"La IA generativa va a rediseñar mis procesos sola"** — la IA propone y acelera; la **validación contextual** la hace un humano que conoce el terreno. La **paradoja de la generación IA** (alta adopción + bajo impacto) se resuelve con rediseño con criterio, no con más herramientas.
- **"Software enlatado se adapta a mi proceso"** — la cátedra dice: *"el software enlatado trae mejores prácticas de industria embebidas"*. En el 80% de los casos conviene rediseñar tu proceso para alinearlo al software, no al revés. Si tu proceso es tan único que ningún software lo cubre, probablemente esté mal.
- **"Eliminar todos los controles porque agregan demora"** — cuidado con el péndulo. Hay controles que agregan valor (cumplimiento regulatorio, anti-fraude) y otros que no (firmas redundantes, "siempre se hizo así"). Pregunta: *"¿evita un riesgo real con costo razonable?"*

---

## 7. Checklist

Antes de cerrar el diseño de un proceso, repasá:

- [ ] ¿Diferencié bien si estoy haciendo **digitalización** o **transformación digital**?
- [ ] ¿Definí objetivo, indicadores, alcance, dueño/a y participantes del proceso?
- [ ] ¿Identifiqué el **dueño/a con autoridad real** (UN nombre)?
- [ ] ¿Relevé el **AS IS** con entrevistas + observación + (si hay datos) minería de procesos?
- [ ] ¿Identifiqué los problemas con **5 por qué + Ishikawa + Pareto**?
- [ ] ¿Diseñé el **TO BE** sin caer en "lo soñado" — con restricciones reales (presupuesto, tiempo, cultura)?
- [ ] ¿El TO BE elimina cuellos de botella, retrabajos, tareas innecesarias y exceso de controles?
- [ ] ¿Modelé en notación **BPMN** estándar (no en símbolos inventados)?
- [ ] ¿Simulé el TO BE antes de implementar si el cambio tiene costo alto de reversa?
- [ ] ¿Tengo métricas claras y dashboard en vivo para medir el TO BE desde día 1?
- [ ] ¿Comuniqué y validé el proceso con dueño/a y referentes?
- [ ] ¿Si voy a meter IA o RPA, **rediseñé primero** o estoy automatizando el problema?
- [ ] ¿Definí cuándo se considera "fracaso" el TO BE y se vuelve al diseño?

---

## 8. Para profundizar

### Académicos foundacionales

- **Hammer, M. & Champy, J. (1993)**. *Reengineering the Corporation: A Manifesto for Business Revolution*. HarperCollins, New York. El clásico de BPR (Business Process Reengineering). Definición: *"el rethinking fundamental y el rediseño radical de procesos de negocio para lograr mejoras dramáticas en medidas críticas de performance como costo, calidad, servicio y velocidad"*. Lectura controversial pero indispensable. [Referencia](https://www.scirp.org/reference/referencespapers?referenceid=1504676).
- **Davenport, T. H. (2005)**. *The Coming Commoditization of Processes*. Harvard Business Review, 83(6), 100–108. Plantea cómo los procesos se vuelven estándares comparables y cuáles conviene tercerizar. [Artículo HBR](https://hbr.org/2005/06/the-coming-commoditization-of-processes).

### Estándares y especificaciones

- **OMG — BPMN 2.0 specification**. Especificación oficial: [omg.org/spec/BPMN/2.0/](http://www.omg.org/spec/BPMN/2.0/). Portal con recursos: [bpmn.org](https://www.bpmn.org/). Formalizada como ISO/IEC 19510:2013.

### Reportes industriales actualizados

- **McKinsey — The state of AI 2025**. [Página oficial](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai). Datos del "scaling gap" y la paradoja adopción/valor.

### Herramientas prácticas

- **Disco** (Fluxicon) — minería de procesos. [Producto](https://fluxicon.com/disco/) · [User Guide](https://fluxicon.com/book/read/reference/). Estándar académico-comercial.
- **Miro** — [miro.com](https://miro.com/app). Pizarra colaborativa con plantillas BPMN.
- **Napkin.ai** — [napkin.ai](https://www.napkin.ai/). Texto a diagrama automático.
- **Bizagi Modeler** — modelador BPMN gratuito de uso profesional.
- **Camunda Modeler** — open source, fuerte adopción en proyectos serios.
- **Signavio** (SAP) — modelado + governance corporativa.

### Citas para enmarcar

> *"La paradoja de la generación IA: casi ocho de cada diez empresas han implementado IA de alguna forma, pero aproximadamente el mismo porcentaje no informa ningún impacto material en las ganancias."* — Zinggerling & Contreras, Módulo 4 DIATO

> *"La gestión basada en procesos apunta a la comprensión y gestión de los procesos interrelacionados como un sistema para contribuir a la eficacia y eficiencia de la organización en el logro de sus resultados previstos."* — Zinggerling & Contreras, Módulo 4 DIATO

> *"Reengineering is the fundamental rethinking and radical redesign of business processes to achieve dramatic improvements in critical contemporary measures of performance."* — Hammer & Champy, 1993

---

## Próximo paso

Procesos sin arquitectura tecnológica es como tener buena receta sin cocina equipada. En el capítulo 08 vas a ver cómo se diseña la **arquitectura tecnológica organizacional** que sostiene esa transformación digital y permite que la IA + los procesos rediseñados se ejecuten con confiabilidad.

→ Continuá con [`08-arquitectura-tecnologica-organizacional.md`](08-arquitectura-tecnologica-organizacional.md)

---

## Referencias

- Zinggerling, D. & Contreras, L. (2026). *Módulo 4 — Gestión de procesos y nuevas tecnologías para la mejora, Clase 1*. DIATO, UNRaf Cohorte 5.
- Hammer, M. & Champy, J. (1993). *Reengineering the Corporation: A Manifesto for Business Revolution*. HarperCollins, New York.
- Davenport, T. H. (2005). The Coming Commoditization of Processes. *Harvard Business Review*, 83(6), 100–108.
- Object Management Group (2011/2013). *Business Process Model and Notation (BPMN), Version 2.0*. OMG / ISO/IEC 19510:2013.
- Fluxicon. *Disco — Process Mining and Automated Process Discovery Software*. Documentación y User Guide.
- McKinsey & Company (2025). *The state of AI in 2025: Agents, innovation, and transformation*.
- Toyoda, S. (s/f). *Cinco por qué*. Sistema de Producción Toyota.
- Ishikawa, K. (1968). *Guide to Quality Control*. Asian Productivity Organization.
- Pareto, V. (1896). *Cours d'économie politique*. Lausanne.
