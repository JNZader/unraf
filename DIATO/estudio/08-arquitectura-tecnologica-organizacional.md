# 08. Arquitectura tecnológica organizacional

> **Módulo 6 — Unidad 1 (DIATO, UNRaf Cohorte 5)**
> Docentes: Ing. Ives Minetti (Director TI en Limansky SA) + Ana Lucía Tolini (Lic. RRTT, Analista de Compensaciones e Innovación en Bertolaccini).

---

## 1. Concepto

**Arquitectura tecnológica organizacional** es el conjunto de decisiones sobre **qué sistemas usás, cómo los conectás y dónde corren** para sostener la operación y la estrategia de la organización. No es "el área de IT", es el **mapa de cómo el negocio se materializa en software, hardware y datos**.

Esa arquitectura tiene tres capas que conviene separar mentalmente:

1. **Tipología de sistemas** (qué pieza cumple qué rol): ERP, CRM, WMS, sistemas Legacy, IoT/IIoT, suites colaborativas.
2. **Arquitectura de software** (cómo está construida cada pieza por dentro): Monolítica, Microservicios, SOA, Cloud-Native.
3. **Arquitectura de IT** (dónde corre): On-Premise, SaaS, PaaS, IaaS, Híbrida.

Encima de las tres se monta la **Arquitectura de Negocios**, que es el puente que asegura que cada decisión tecnológica esté justificada por un objetivo estratégico y un KPI medible. La cátedra lo formula así:

> *"La Estrategia define el 'Qué' y el 'Para qué'. La tecnología es simplemente el 'Cómo'. Si la tecnología no mueve la aguja de los KPIs estratégicos, es un gasto, no una inversión."* (Part 1, p. 30)

---

## 2. Intuición

Pensá una organización como una **fábrica de procesos**. Cada proceso (vender, despachar, cobrar, contratar) necesita herramientas. Si cada área compra la suya sin hablar con las demás, terminás con cinco planillas Excel y tres sistemas que no se conocen entre sí. Eso es lo que la cátedra llama un **archipiélago de aplicaciones**: islas de información que obligan a humanos a hacer de puente.

Una buena arquitectura tecnológica es lo opuesto: **un ecosistema donde cada sistema sabe con quién hablar, cómo y para qué**. El ERP sabe avisarle al WMS que entró un pedido, el WMS le dice al CRM que el cliente ya tiene su despacho, el CRM dispara una encuesta de satisfacción. Nadie copia y pega.

La analogía cátedra que conviene tener en la cabeza es la del **archivo `Proyecto_Final_v2_final_ESTE_SI.docx`** (Part 1, p. 16): cuando la herramienta es mala, la organización termina pariendo workarounds barrocos que esconden el problema real (en este caso, falta de co-autoría en la nube). La arquitectura existe justamente para que esos workarounds no escalen.

---

## 3. Cuerpo desarrollado

### 3.1. Tipologías de sistemas

#### ERP — Enterprise Resource Planning

> *"Gestión administrativa y financiera integral (Back-office)."* (Part 1, p. 7)

El ERP es el **sistema nervioso central** de la operación administrativa. Características cátedra:

- **Integración total** — unifica departamentos (ventas, compras, contabilidad, RRHH, producción) y elimina silos de información.
- **Base de Datos única** — una sola fuente de verdad para finanzas, stock, clientes y proveedores.
- **Modularidad** — implementás los módulos que necesitás (Contabilidad primero, después Producción, después RRHH).
- **Automatización de procesos** — una venta cargada dispara automáticamente la orden de despacho y el asiento contable.
- **Estandarización** — los ERPs traen "mejores prácticas" que obligan a profesionalizar procesos internos. Esto es virtud y trampa al mismo tiempo (ver anti-patrón "Adaptarse al Enlatado").

**Ejemplos del mercado:**
- **Internacionales**: SAP S/4HANA (líder histórico en grandes empresas), Oracle NetSuite (cloud-first PYME-friendly), Microsoft Dynamics 365.
- **Argentinos / regionales**: **Bejerman** (clásico contable-fiscal), **Tango Gestión** (Axoft, muy difundido en PYME argentina), **Calipso**, **Finnegans** (cloud nacional). Estos sistemas locales tienen la ventaja de venir con la normativa AFIP, ARCA y particularidades fiscales argentinas pre-cargadas, lo que ahorra meses de parametrización vs adaptar un SAP genérico.

#### CRM — Customer Relationship Management

> *"Gestión de la relación y ciclo de vida del cliente (Front-office)."* (Part 1, p. 9)

Si el ERP mira para adentro, el CRM mira para afuera. Es donde vive la **historia comercial** de cada cliente: cuándo te contactó, qué cotizó, qué compró, qué reclamó, qué te abrió, qué te ignoró.

Capacidades centrales:
- Gestión de contactos y oportunidades.
- Automatización de marketing (campañas, nurturing, scoring).
- Seguimiento de interacciones multicanal (email, WhatsApp, llamadas).
- Post-venta y casos de soporte.
- Analítica de embudo (conversión por etapa, tiempo de ciclo).

**Ejemplos del mercado:**
- **Salesforce** (Sales Cloud, Service Cloud, Marketing Cloud) — líder mundial, ecosistema gigante de integraciones.
- **HubSpot** — free-tier generoso, muy fuerte en inbound marketing y PYMES.
- **Zoho CRM** — opción económica, fuerte en LATAM.
- **Microsoft Dynamics 365 Sales** — natural si la empresa ya vive en M365.
- **Pipedrive** — minimalista, orientado a equipos comerciales chicos.

#### WMS — Warehouse Management System

> *"Gestión y optimización operativa de depósitos y logística."* (Part 1, p. 11)

El WMS es el cerebro del depósito. Sus funciones cátedra:

- **Inventario en tiempo real** (no "inventario al final del día").
- **Optimización de ubicación** (qué SKU va dónde para minimizar recorridos del operario).
- Recepción y despacho con validación contra órdenes.
- **Picking / packing** dirigidos por sistema.
- **Trazabilidad total** (lote, vencimiento, número de serie).
- Sincronización con escáneres de código de barras y RFID.

Muchas empresas viven un dolor crónico porque su ERP "tiene un módulo de stock" pero **no tiene un WMS real**. La diferencia es operacional: un ERP te dice cuánto stock hay, un WMS te dice dónde está, quién lo tocó y qué orden ejecutar a continuación.

#### Sistemas Legacy (heredados)

> *"Sistemas antiguos (muchas veces desarrollados a medida) que siguen siendo críticos para la operación. Es la 'verdad incómoda' en toda transformación digital."* (Part 1, p. 13)

| Pros | Contras |
|------|---------|
| Probados (corren hace años sin caer) | Difíciles de integrar (sin APIs modernas) |
| Amortizados (la inversión ya se hizo) | Talento escaso ("programadores Cobol") |
| Aislados (no exponen superficie de ataque) | Mantenimiento caro y proveedores únicos |
| | Vulnerabilidades sin parches |

El Legacy no es "lo malo del pasado": es el **músculo que sigue facturando**. Reemplazarlo de un día para otro es una receta para el desastre. Por eso la estrategia más madura suele ser **encapsularlo con APIs** (Strangler Fig pattern de Martin Fowler) y reemplazar funcionalidad por funcionalidad, no de golpe.

#### IoT / IIoT

- **IoT (Internet of Things)** — *"Red de objetos cotidianos con sensores que recolectan datos (Ej: sensores de luz o temperatura en oficinas, cámaras, etc)."* (Part 1, p. 14)
- **IIoT (Industrial IoT)** — *"Sensores y dispositivos en entornos industriales (fábricas). El IIoT requiere mucha mayor precisión y suele operar bajo requerimientos de seguridad mucho más estrictos que el IoT doméstico."* (Part 1, p. 14)

Diferencias prácticas:

| Dimensión | IoT | IIoT |
|-----------|-----|------|
| Precisión exigida | Aceptable rango medio | Sub-milímetro / sub-milisegundo |
| Latencia | Tolerante (segundos) | Crítica (ms) |
| Seguridad | Importante | Vida humana en juego |
| Conectividad | WiFi / Bluetooth | Cableado industrial, OPC-UA, MQTT |
| Vida útil esperada | 2-5 años | 10-15 años |

El IIoT es la base material del **mantenimiento predictivo** (Caso 3 del capítulo 09): sensores de vibración y temperatura que generan series de tiempo que la IA aprende a leer.

#### Suites colaborativas

- **Google Workspace** — *"100% colaborativo y cloud-first, ideal para startups y equipos remotos."* (Part 1, p. 15)
- **Microsoft 365** — *"Evolución de la suite de escritorio clásica, ideal para empresas consolidadas y procesamiento de datos complejos."* (Part 1, p. 15)

Características transversales: co-autoría en tiempo real (mata el archivo `Proyecto_Final_v2_final_ESTE_SI.docx`), ubicuidad multiplataforma, búsqueda inteligente sobre todo el corpus, y plataformas de automatización low-code embebidas (**Power Automate** y **Apps Script**) que se cubren en el capítulo 09.

### 3.2. Requerimientos: funcionales vs no funcionales

> *"Es la descripción de una necesidad, funcionalidad, característica o restricción que un sistema, software o producto debe cumplir para satisfacer a los usuarios y objetivos del negocio."* (Part 1, p. 20)

**Funcionales — el "Qué"**: acciones, procesos, reglas de negocio.

Ejemplos cátedra:
- WMS: *"El sistema debe generar un aviso cuando el stock baje de 10 unidades."*
- Legacy fiscal: *"El sistema debe emitir la factura fiscal según la normativa vigente."*

**No funcionales — el "Cómo"**: atributos de calidad y restricciones técnicas.

Ejemplos cátedra:
- IoT: tiempo de respuesta < 500 ms.
- ERP: procesar hasta 10.000 pedidos por hora.
- Autenticación con 2FA.
- Encriptación AES-256 para datos sensibles del CRM.

> **Regla mental:** si lo podés escribir como "El sistema debe hacer X", es funcional. Si lo escribís como "El sistema debe hacer X **en menos de** / **con disponibilidad de** / **con seguridad de**", es no funcional.

#### Plantilla ERS — Especificación de Requerimientos

| Campo | Contenido | Ejemplo |
|-------|-----------|---------|
| **ID único** | Identificador trazable | `RF-001` / `RNF-014` |
| **Nombre** | Frase corta | "Aviso de stock bajo" |
| **Descripción** | El "qué" detallado | "Notificar a Compras cuando el SKU baje del umbral mínimo" |
| **Precondiciones** | Estado previo necesario | "El SKU tiene umbral mínimo configurado" |
| **Postcondiciones** | Estado resultante esperado | "Existe un email enviado al rol Compras + un registro de auditoría" |
| **Flujo de eventos** | Pasos del happy path + alternativos | 1) Movimiento de stock; 2) Recalcular saldo; 3) Si < umbral, disparar notificación |
| **Criterios de aceptación** | Cómo se valida que está cumplido | "Test: bajar stock a 9 con umbral 10 → email recibido en < 30 s" |

La ERS no es burocracia: es lo que **te salva cuando el proveedor te dice "eso no estaba en el alcance"** seis meses después. Documentar requerimientos antes de elegir herramienta es uno de los tres pilares cátedra para evitar los anti-patrones (Part 1, p. 34).

### 3.3. Arquitectura de software

Componentes universales: Frontend, Backend, Base de Datos, Middleware / APIs.

#### Monolítica

**Todo en una sola aplicación**: frontend, backend y lógica de negocio empaquetados como una unidad. Se despliega de una sola vez.

| Cuándo SÍ | Cuándo NO |
|-----------|-----------|
| Producto en etapa MVP / startup chica | Equipo de más de 30 devs |
| Equipo pequeño (< 10 devs) | Dominio con bounded contexts claramente distintos |
| Dominio acotado y bien entendido | Necesidad de escalar partes específicas (solo el carrito en Cyber) |
| Necesitás simplicidad operacional | Hay funcionalidad con SLA / privacidad muy distinta |

Mito: "Monolito = malo". Falso. **Shopify y Stack Overflow corren monolitos modulares**. El monolito es problemático solo cuando crece sin disciplina y se vuelve un *big ball of mud*.

#### Microservicios

> *"Si falla una (ej. el carrito), el resto sigue funcionando. Ideal para integrar IA específica sin romper el núcleo del negocio."* (Part 1, p. 27)

Servicios chicos, independientes, cada uno con su base de datos, comunicándose por APIs (REST, gRPC, mensajería). Martin Fowler los popularizó en su artículo *"Microservices"* (2014), que sigue siendo lectura obligatoria.

| Ventajas | Costos |
|----------|--------|
| Escalado independiente por servicio | Complejidad operacional (observabilidad, deploy, redes) |
| Tolerancia parcial a fallos | Latencia entre servicios (no más llamadas en memoria) |
| Equipos autónomos por servicio | Eventual consistency en datos |
| Heterogeneidad tecnológica permitida | Requiere DevOps maduro (CI/CD, contenedores, k8s) |

**Advertencia cátedra implícita**: no es para cualquier organización. Si no tenés equipo platform que sostenga Kubernetes, observabilidad distribuida y service mesh, vas a comprarte un quilombo mucho más grande del que tenías.

#### SOA — Service-Oriented Architecture

SOA precede a microservicios y los conceptualiza a una escala más gruesa. La referencia canónica es Thomas Erl, *"Service-Oriented Architecture: Concepts, Technology, and Design"* (2005).

Diferencia esencial con microservicios:
- **SOA**: servicios grandes orquestados por un **ESB (Enterprise Service Bus)** central, contratos rígidos (SOAP, WS-*).
- **Microservicios**: servicios chicos, comunicación punto a punto (REST, eventos), contratos ligeros.

SOA sigue vivo en banca, telco y administración pública, donde el ESB es el corazón de la integración entre sistemas heterogéneos. Si en tu organización aparece la sigla **ESB / TIBCO / IBM Integration Bus**, estás en una arquitectura SOA.

#### Cloud-Native / Serverless

Aplicaciones diseñadas **para correr en la nube desde el día cero**, no migradas. Características: contenedores (Docker), orquestación (Kubernetes), funciones serverless (Lambda, Cloud Functions, Azure Functions), bases de datos administradas, *infrastructure as code* (Terraform).

La **Cloud Native Computing Foundation (CNCF)** mantiene un mapa de tecnologías que es de facto el currículo de esta arquitectura.

### 3.4. Arquitectura de IT

Mientras la arquitectura de software responde "cómo está construido", la arquitectura de IT responde **"dónde corre y quién lo opera"**.

#### On-Premise

Servidores propios, en data center propio (o colocation). Control total: vos elegís el hardware, vos parchás el SO, vos hacés los backups, vos te bancás la electricidad y el aire acondicionado.

| Pros | Contras |
|------|---------|
| Control total sobre datos y hardware | CAPEX altísimo (hardware + licencias) |
| Latencia local mínima | Equipo de operaciones grande |
| Cumple normativas que exigen residencia local | Escalado lento (comprar y rackear servidores) |
| Sin dependencia de internet | Obsolescencia tecnológica |

#### SaaS — Software as a Service

> *"Software listo vía navegador."* (Part 1, p. 28)

El proveedor te entrega la aplicación funcionando, vos solo entrás con usuario y contraseña. **Ejemplos**: Salesforce, HubSpot, Slack, Google Workspace, Microsoft 365, Notion, Asana.

Pagás por uso (usualmente por usuario por mes). No instalás nada, no parchás nada, no escalás nada. Tampoco controlás versiones ni tenés acceso al código.

#### PaaS — Platform as a Service

> *"Entornos para developers."* (Part 1, p. 28)

El proveedor te da una plataforma para correr tus apps sin preocuparte por el sistema operativo, el servidor web, ni el escalado. **Ejemplos**: Heroku, Vercel, Netlify, Google App Engine, Azure App Service, AWS Elastic Beanstalk.

Subís tu código y la plataforma se encarga del resto. Ideal para equipos chicos que quieren productividad sin operar infraestructura.

#### IaaS — Infrastructure as a Service

> *"Recursos básicos alquilados."* (Part 1, p. 28)

El proveedor te alquila máquinas virtuales, almacenamiento, red. Vos seguís siendo responsable del SO para arriba. **Ejemplos**: **Amazon EC2 (AWS)**, **Microsoft Azure Virtual Machines**, **Google Compute Engine (GCP)**.

| Modelo | Vos controlás | El proveedor controla |
|--------|---------------|----------------------|
| **IaaS** | OS, runtime, app, datos | Hardware, virtualización, red |
| **PaaS** | App, datos | Hardware, OS, runtime |
| **SaaS** | Solo datos / configuración | Todo lo demás |

#### Híbrida

> *"Lo mejor de ambos mundos; seguridad para datos críticos y agilidad en la nube."* (Part 1, p. 28)

Combinación de On-Premise + Cloud. Patrón típico: datos sensibles (clínicos, financieros, militares) on-prem, todo lo demás en cloud. Requiere arquitectura de integración seria (VPN site-to-site, AWS Direct Connect, Azure ExpressRoute).

### 3.5. Arquitectura de negocios — el puente

> *"La Estrategia define el 'Qué' y el 'Para qué'. La tecnología es simplemente el 'Cómo'. Si la tecnología no mueve la aguja de los KPIs estratégicos, es un gasto, no una inversión."* (Part 1, p. 30)

La arquitectura de negocios es la disciplina que asegura que cada decisión tecnológica esté **anclada a un objetivo estratégico medible**. Sin esto, IT se convierte en un centro de costos que compra herramientas para "estar al día" en vez de para "mover la aguja".

#### Los tres anti-patrones cátedra (textual)

**1. "Adaptarse al Enlatado"**
> *"En lugar de configurar el software para que siga el proceso eficiente de la empresa, la empresa cambia sus procesos (incluso los que eran su ventaja competitiva) simplemente porque 'el sistema funciona así'. Consecuencia: La empresa pierde su identidad y su diferencial estratégico para volverse una copia de cualquier otra que use el mismo software."* (Part 1, p. 31)

Síntoma: escuchás a un gerente decir "el SAP no nos deja hacer eso, así que ahora vamos a trabajar como nos pide el SAP". Si lo que el SAP no te deja hacer **era parte de tu ventaja competitiva**, acabás de regalarla.

**2. "Herencia Técnica" (Legacy)**
> *"La gerencia quiere lanzar un nuevo producto, pero IT responde: 'No se puede porque nuestro sistema actual no lo permite'. La estrategia está limitada por las paredes de la infraestructura actual."* (Part 1, p. 32)

Síntoma: cuando la estrategia de negocio depende de lo que el sistema viejo permita, la organización dejó de manejar su rumbo. Está siendo manejada por una decisión de software de hace 12 años.

**3. "Automatización de Procesos Ineficientes"**
> *"Un error clásico es usar IA o automatización para acelerar un proceso que ya estaba mal diseñado. 'Estamos haciendo más rápido algo que no deberíamos estar haciendo'. Se genera una falsa sensación de progreso."* (Part 1, p. 33)

Síntoma: medís ahorro de horas y mejora de tiempos de ciclo, pero los KPIs de negocio (satisfacción, conversión, margen) no se mueven. Estás corriendo más rápido en la dirección equivocada.

#### Tres pilares para evitarlos (Part 1, p. 34)

1. **Definir requerimientos antes que herramientas.** Primero el "qué" y el "por qué", después el "con qué".
2. **Arquitectura de integración.** Que ERP/CRM/WMS "hablen el mismo idioma" via APIs y eventos.
3. **Gobierno de IT en la mesa de directorio.** Las decisiones tecnológicas estratégicas se toman donde se decide el rumbo del negocio, no en una reunión de IT aislada.

---

## 4. Caso real organizacional

**PYME industrial argentina del sector alimenticio (450 empleados, 3 plantas en Buenos Aires y Santa Fe).**

**Situación inicial (2019):**
- Sistema contable Bejerman On-Premise, sin módulo de producción.
- Excel para gestión de stock en cada planta (uno por planta, sin sincronización).
- CRM = una planilla compartida por Google Drive con los contactos comerciales.
- Reporting a gerencia: el contador armaba un PDF mensual a mano, llegaba el día 20 del mes siguiente.

**Punto de dolor identificado** (Part 1, p. 30: *"Identificar un 'punto de dolor' y luego buscar la tecnología que mejor lo resuelva"*):

> "No sabemos cuánto ganamos ni perdemos hasta que el contador cierra el mes. Cuando lo sabemos, ya pasaron 50 días. Si una planta tuvo un mes malo en abril, lo descubrimos en junio."

**Lo que NO hicieron (anti-patrones evitados):**

- No compraron SAP. *"Para una empresa de 450 personas, implementar SAP S/4HANA sale más caro que el ERP entero los próximos 8 años, y obliga a rediseñar todos los procesos para adaptarse al software"* — anti-patrón 1.
- No "automatizaron Excel". Migrar el quilombo de planillas a Power Automate hubiera sido el anti-patrón 3 en vivo.

**Lo que SÍ hicieron:**

1. **Rediseñaron los procesos primero.** Tres meses con un consultor externo definiendo el flujo "ideal" de compra-producción-venta antes de tocar tecnología.
2. **Documentaron requerimientos** con plantilla ERS. Resultado: 47 requerimientos funcionales y 18 no funcionales (residencia de datos en Argentina, integración con AFIP, tiempo de respuesta < 2s para reportes, etc.).
3. **Eligieron un ERP cloud argentino** (Finnegans): SaaS, integración nativa con AFIP, parametrización local mucho más rápida que un SAP genérico.
4. **Mantuvieron Bejerman 18 meses en paralelo** durante la transición (Strangler Fig pattern), reemplazando módulo por módulo.
5. **Sumaron un WMS específico** (no el módulo de stock del ERP) para una de las plantas porque el operador necesitaba escaneo con handheld y picking dirigido.
6. **Conectaron todo con n8n self-hosted** (anticipando el capítulo 09): los pedidos cargados en el ERP disparan automáticamente la orden de despacho al WMS, y la factura se emite vía AFIP cuando el despacho se confirma.

**Resultado a 24 meses:**
- Reporting de margen disponible al día 3 del mes siguiente (antes: día 20).
- Stock en tiempo real entre las 3 plantas (antes: foto del último viernes).
- Equipo de IT pasó de 3 a 5 personas (no se eliminó trabajo, se reasignó: menos soporte de Excel, más analítica).

**Lecciones cátedra aplicadas:**
- Rediseño antes que automatización (Part 2, p. 9).
- Arquitectura híbrida realista (cloud para gestión, on-premise para los SCADA de planta).
- Gobierno de IT con asiento en directorio: el Gerente de Operaciones aprobó el roadmap, no fue una decisión solo de IT.

---

## 5. Aplicación a la transformación organizacional

Cuando tu objetivo es **meter IA en la organización**, la arquitectura tecnológica deja de ser un tema "del área de IT" y pasa a ser un habilitador o un freno estratégico. Tres preguntas que tenés que poder responder antes de comprar nada con la palabra "IA" en el marketing:

### 5.1. ¿Dónde están mis datos hoy y cómo se conectan?

La IA come datos. Si tus datos están en cinco silos sin APIs, ningún modelo va a funcionar bien. Antes de pensar en LLMs y agentes, mapeá:

- Qué sistemas son **fuentes de verdad** para cada dominio (cliente, producto, transacción).
- Qué sistemas **consumen** esos datos y por qué medio (API, archivo, base de datos directa, copia manual).
- Dónde hay **datos duplicados** sin sincronización (el síntoma más común: el cliente está cargado en 3 lugares con apellido distinto).

### 5.2. ¿Mi arquitectura permite enchufar IA sin romper el núcleo?

Acá es donde **microservicios y SaaS pagan dividendos**: si tu CRM es Salesforce, podés conectar un modelo de análisis de sentimiento via API sin tocar el core. Si tu CRM es un Legacy en Cobol que no tiene API, tenés que envolverlo primero (Strangler Fig) o forzarte a workarounds frágiles.

Pregunta de litmus: *"¿Puedo enchufar un servicio de OCR a mi flujo de cuentas a pagar sin pedirle al proveedor del ERP que lo desarrolle dentro del ERP?"* Si la respuesta es "no", tenés un problema de arquitectura, no de IA.

### 5.3. ¿Mi gobierno de datos está a la altura del riesgo?

La IA introduce dos riesgos nuevos:

- **Sesgo y explicabilidad** — si el modelo aprueba o rechaza créditos / contratos / compras, necesitás poder auditar por qué.
- **Soberanía de datos** — si tus datos salen a un AIaaS de un proveedor estadounidense, ¿estás cumpliendo Ley 25.326 de Protección de Datos Personales? ¿Hay datos de salud que caen en la Ley 26.529?

Estos dos riesgos se gestionan **a nivel arquitectura** (qué corre on-prem vs cloud, qué se anonimiza antes de salir), no a nivel "le ponemos un check de seguridad".

### Criterio de decisión sintético

| Pregunta | Si la respuesta es "sí" | Implicancia |
|----------|------------------------|-------------|
| ¿La IA va a ser core diferencial? | Considerar desarrollo interno + on-prem o cloud privada | Capítulo 09, framework Build vs Buy |
| ¿Los datos son ultra-sensibles? | Híbrida con anonimización antes de salir | Arquitectura híbrida |
| ¿Necesito time-to-market en meses? | SaaS + AIaaS + plataforma de orquestación tipo n8n | Anti-patrón evitado: no desarrollar lo que ya existe |
| ¿Tengo equipo platform fuerte? | Microservicios + Cloud-Native viable | Si no, monolito modular |

---

## 6. Errores comunes / mitos

**1. "Compremos microservicios."**
Microservicios no se compran, se construyen y se operan. Si no tenés DevOps maduro, CI/CD automatizado y observabilidad distribuida, vas a tener todos los costos del modelo y ninguno de los beneficios.

**2. "Cloud es siempre más barato."**
A escala chica sí. A escala grande, los costos variables de cloud pueden superar al on-premise. Netflix gasta más de **$1B/año en AWS**. Dropbox migró parte de su infraestructura **fuera** de AWS para ahorrar. La decisión es un cálculo de TCO, no una creencia.

**3. "El ERP resuelve todo."**
El ERP es bueno en gestión administrativa y financiera. No es CRM (sub-utilizar el módulo CRM de un ERP grande es un clásico), no es WMS de verdad, no es BI moderno, y no es plataforma de IA. Querer que el ERP sea todo termina en customizaciones caras que se rompen en cada upgrade.

**4. "Si pagamos SaaS, no necesitamos arquitectura."**
Sí necesitás. La arquitectura de integración entre tus 12 SaaS distintos es **el** nuevo problema (a esto se le llama "spaghetti SaaS"). Sin gobierno y sin una plataforma de integración (iPaaS), terminás con APIs colgando por todos lados.

**5. "Vamos directo a microservicios desde cero."**
Anti-patrón conocido como *premature distribution*. Recomendación moderna (Martin Fowler, Sam Newman): **monolito-first**, extraer microservicios cuando el dolor de mantenimiento del monolito supere el costo de operar servicios distribuidos.

**6. "El Legacy lo reemplazamos en un Big Bang."**
Receta para el desastre. La estrategia probada es **Strangler Fig**: dejás el Legacy corriendo, lo encapsulás con APIs, y reemplazás funcionalidad por funcionalidad hasta que un día el Legacy ya no atiende ningún request.

**7. "Saltarse el discovery de requerimientos no funcionales."**
Es el error más caro y más invisible. Recién lo descubrís cuando el sistema cae en horario pico, cuando un auditor pide cifrado de datos en reposo, o cuando el cliente reclama latencia. Los NFR se piensan **antes** de elegir herramienta, no después.

---

## 7. Checklist

**Antes de elegir o cambiar un sistema central (ERP/CRM/WMS):**
- [ ] ¿Tengo escrito el "punto de dolor" en una frase entendible por una persona no técnica?
- [ ] ¿Tengo identificados los KPIs estratégicos que esta decisión va a mover?
- [ ] ¿Levanté requerimientos funcionales con plantilla ERS (ID, descripción, pre/postcondiciones, criterios de aceptación)?
- [ ] ¿Levanté requerimientos no funcionales (performance, seguridad, residencia de datos, disponibilidad)?
- [ ] ¿Hice análisis de los 3 anti-patrones (Adaptarse al Enlatado / Herencia Técnica / Automatización de Ineficiencias)?
- [ ] ¿La decisión está validada por alguien con asiento en directorio (no solo el área de IT)?

**Antes de elegir arquitectura de software:**
- [ ] ¿El tamaño del equipo justifica la complejidad operacional elegida?
- [ ] ¿Tengo presupuesto de DevOps / Platform Engineering si elijo microservicios?
- [ ] ¿Documenté la decisión en un ADR (Architecture Decision Record) con tradeoffs?
- [ ] ¿Pensé la estrategia de integración con sistemas existentes?

**Antes de elegir arquitectura de IT:**
- [ ] ¿Calculé TCO a 3-5 años, no solo costo inicial?
- [ ] ¿Identifiqué qué datos NO pueden salir del país por normativa?
- [ ] ¿Tengo plan de DR (Disaster Recovery) y RPO/RTO definidos?
- [ ] ¿Evalué vendor lock-in y plan de salida?

**Para la integración futura con IA:**
- [ ] ¿Los sistemas exponen APIs (REST/GraphQL) o solo bases de datos directas?
- [ ] ¿Tengo una capa de integración (iPaaS o ESB) o todo se conecta punto a punto?
- [ ] ¿Hay gobierno de datos: dueño, calidad, ciclo de vida?
- [ ] ¿Pensé qué datos NO pueden ir a un AIaaS de terceros?

---

## 8. Para profundizar

**Libros de referencia:**
- Sam Newman, *"Building Microservices"* (2ª ed., 2021) — la biblia operacional de microservicios.
- Martin Fowler & Pramod Sadalage, *"NoSQL Distilled"* (2012) — para entender cuándo NO usar relacionales.
- Thomas Erl, *"Service-Oriented Architecture: Concepts, Technology, and Design"* (Prentice Hall, 2005) — el clásico de SOA.
- Gregor Hohpe & Bobby Woolf, *"Enterprise Integration Patterns"* (2003) — patrones de integración entre sistemas que siguen vigentes 22 años después.
- Eric Evans, *"Domain-Driven Design"* (2003) — para diseñar bounded contexts antes de partirse en microservicios.
- Werner Vogels (CTO Amazon), publicaciones en `allthingsdistributed.com` sobre arquitecturas a escala.

**Artículos seminales:**
- Martin Fowler & James Lewis, *"Microservices"* (martinfowler.com, 2014) — definición original que popularizó el término.
- Martin Fowler, *"StranglerFigApplication"* (martinfowler.com) — patrón canónico para migrar Legacy.
- Sam Newman, *"Don't start with a Monolith... or do? "* — debate clásico monolito-first.

**Plataformas y docs oficiales:**
- SAP S/4HANA: `help.sap.com`
- Salesforce Trailhead: `trailhead.salesforce.com` — cursos gratuitos.
- AWS Well-Architected Framework: `aws.amazon.com/architecture/well-architected`
- Microsoft Azure Architecture Center: `learn.microsoft.com/azure/architecture/`
- Google Cloud Architecture Framework: `cloud.google.com/architecture/framework`

**ERPs argentinos:**
- Bejerman (Axoft) — clásico fiscal-contable.
- Tango Gestión — el más difundido en PYME argentina.
- Finnegans — cloud nacional con foco en industria.
- Calipso — fuerte en industria y gobierno.

**Para profundizar en transformación digital con foco PYME:**
- Cámara Argentina de Comercio Electrónico (CACE) — reportes anuales sobre adopción tecnológica.
- INTI — programas de transformación digital industrial.

---

## Próximo paso

En el capítulo 09 vamos a salir de la arquitectura "qué sistemas tenés y cómo están construidos" para entrar a la pregunta operativa: **¿cómo los hacés trabajar juntos para automatizar procesos integrales?** Vas a ver el concepto cátedra de **Automatización Integral**, la diferencia entre automatización tradicional y **IA-Driven**, la progresión hacia **Automatización Agéntica**, las plataformas iPaaS (con foco en **n8n**), y el framework **Construir / Alquilar / Delegar** para decidir cuándo desarrollás internamente, cuándo consumís AIaaS y cuándo llamás a un consultor.

→ Seguir con **[09. Automatización integral](./09-automatizacion-integral.md)**

---

## Referencias

- DIATO Módulo 6 — Parte 1 (Tema 6), pp. 6-34. Ing. Ives Minetti & Ana Lucía Tolini.
- Fowler, M. & Lewis, J. (2014). *"Microservices"*. martinfowler.com.
- Fowler, M. *"StranglerFigApplication"*. martinfowler.com.
- Erl, T. (2005). *Service-Oriented Architecture: Concepts, Technology, and Design*. Prentice Hall.
- Newman, S. (2021). *Building Microservices* (2ª ed.). O'Reilly.
- Hohpe, G. & Woolf, B. (2003). *Enterprise Integration Patterns*. Addison-Wesley.
- Evans, E. (2003). *Domain-Driven Design*. Addison-Wesley.
- AWS Well-Architected Framework. `aws.amazon.com/architecture/well-architected`.
- Microsoft Azure Architecture Center. `learn.microsoft.com/azure/architecture/`.
- Google Cloud Architecture Framework. `cloud.google.com/architecture/framework`.
- SAP S/4HANA — documentación oficial: `help.sap.com`.
- Salesforce Trailhead. `trailhead.salesforce.com`.
- Cloud Native Computing Foundation (CNCF). `cncf.io`.
- Ley 25.326 — Protección de Datos Personales (Argentina).
