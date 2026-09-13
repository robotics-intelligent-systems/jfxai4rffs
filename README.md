# jfxai4rffs — Arquitectura de IA, simulación háptica y formación profesional

**Robotics Intelligent Systems · Propuesta técnica y académica · Versión 1.0 · 13 de septiembre de 2026**

**Repositorio de referencia:** [robotics-intelligent-systems/jfxai4rffs](https://github.com/robotics-intelligent-systems/jfxai4rffs). Revisión consultada: `8f8524616b3c07108f7b9f8255ac0cc9f5308e00`.

**Entregables:** esta propuesta editable y `jfxai4rffs-arquitectura-ia-haptica.drawio`, con cuatro pestañas: arquitectura integral, simulador háptico, formación profesional y evolución del MVP. Las decisiones, horas, objetivos de rendimiento y plazos que siguen son propuestas de diseño; no representan una implementación ya disponible ni una acreditación obtenida.

## 1. Propuesta ejecutiva

Evolucionar **AI-Powered Robotic Fire Fighting Platform** hacia una plataforma abierta que integre prevención de incendios, apoyo a operadores de robots y drones, entrenamiento inmersivo y evaluación profesional. El producto combinará un gemelo digital del recinto, percepción multimodal, un asistente de IA con consulta documental, una estación de realidad virtual con háptica y un sistema de gestión del aprendizaje.

El primer producto será un **centro de entrenamiento y apoyo a decisiones que funcione en red local**. Permitirá ensayar incidentes en instalaciones comerciales, industriales y logísticas; registrar actuaciones; explicar errores con evidencia; y entrenar la coordinación entre seguridad privada, brigadas internas y servicios de emergencia.

La IA propondrá escenarios, recuperará procedimientos y elaborará borradores de informes. Las decisiones sobre intervención y la evaluación final corresponderán a profesionales responsables. Los controladores de movimiento y fuerza tendrán límites verificables independientes del modelo de lenguaje.

| Resultado | Contenido propuesto |
|---|---|
| Plataforma de integración | ROS 2, adaptadores del compendio, servicios de IA, datos y consola de instructor |
| Simulador | Godot/OpenXR, escenas de incendio basadas en FDS, instrumentos físicos y dos niveles de háptica |
| Programa profesional | 240 horas de seguridad privada, prevención, tecnología y coordinación de emergencias |
| Curso avanzado | 120 horas adicionales de entrenamiento contra incendios con simulación háptica |
| Piloto de software | 16 semanas, dos estaciones XR, tres escenarios base y un robot virtual |
| Itinerario académico completo | 360 horas; 18 semanas a 20 horas semanales, una vez disponible el laboratorio |

## 2. Punto de partida y alcance de la revisión

El [README consultado](https://github.com/robotics-intelligent-systems/jfxai4rffs/blob/8f8524616b3c07108f7b9f8255ac0cc9f5308e00/README.md) enumera herramientas de drones, teleoperación, háptica, aprendizaje y simulación robótica. El árbol revisado contiene ese README y un diagrama de plataforma humanoide, además de su copia de respaldo. El diagrama tiene un único bloque, «Motion Description Language». No se encontró en ese árbol una aplicación integrada, un manifiesto de dependencias, pruebas de integración ni un archivo LICENSE del proyecto.

Por ello, el compendio se interpreta como **cartera de tecnologías candidatas**. Las interfaces y servicios de esta propuesta deberán desarrollarse. No se supone compatibilidad directa entre todos los proyectos enumerados. La ausencia de una licencia en el árbol consultado debe resolverse antes de distribuir el nuevo código; cada dependencia conservará su licencia propia.

Se verificaron fuentes primarias de las piezas determinantes: XTDrone/XTDrone2, SenseShift, BeaVR, un candidato de Prometheus con fuerza, ROS/Gazebo, MoveIt, Godot, CHAI3D, FDS, el modelo Qwen3 y Moodle. Los nombres sin un repositorio inequívoco en el compendio permanecen identificados como pendientes; no se les asignan capacidades o licencias no verificadas.

## 3. Usuarios, competencias y límites operativos

| Perfil | Funciones dentro de la plataforma | Alcance formativo |
|---|---|---|
| Especialista de seguridad privada | Prevención, verificación de alertas, comunicaciones, evacuación, control de accesos y entrega de información | Actuación conforme a su designación, entrenamiento y plan del establecimiento |
| Brigadista designado | Respuesta inicial y tareas autorizadas por la organización | Escenarios y práctica correspondientes a competencias previamente acreditadas |
| Bombero o instructor de incendios | Validación técnica, conducción de ejercicios y evaluación especializada | Intervención avanzada simulada; práctica real según instalaciones, habilitaciones y procedimientos aplicables |
| Operador de robots o drones | Reconocimiento y teleoperación supervisada | Simulación inicial; habilitación específica antes de usar equipos reales |
| Ingeniero de IA/robótica | Integración, calibración, pruebas y trazabilidad | Sin potestad para certificar competencias operativas por motivos técnicos solamente |

El curso avanzado tendrá **dos perfiles de escenario**. En el perfil de seguridad privada se evalúan prevención, aviso, evacuación, decisión de retirada y respuesta inicial autorizada. En el perfil de brigada/bomberos se añaden tareas virtuales de intervención compatibles con la formación previa. Completar el programa de seguridad privada no habilita automáticamente para combate estructural, rescate técnico o uso de equipos respiratorios.

## 4. Integración del compendio existente

Las decisiones de esta matriz son de arquitectura. «Candidato» significa que requiere prueba de integración; «referencia» significa que aporta modelos o métodos sin incorporarse necesariamente al producto.

| Elemento del compendio | Papel propuesto e interfaz | Decisión inicial |
|---|---|---|
| XTDrone | Escenarios UAV y referencia de integración PX4/ROS/Gazebo | Conservar ejemplos; evaluar XTDrone2 en un entorno separado |
| Langostino | Posible plataforma UAV para reconocimiento | Candidato; confirmar repositorio, hardware y licencia |
| Mission-Directed Swarm | Distribución de misiones de reconocimiento | Investigación posterior al piloto; identidad por confirmar |
| DroneFleet Optimizer | Vista y asignación de recursos de flota mediante API | Candidato; confirmar API, licencia y funcionamiento local |
| Altnautica Mission Control | Estación de operación y seguimiento de misiones | Candidato a adaptador de consola; identidad/API por confirmar |
| SenseShift | Chaleco o guantes para avisos táctiles y eventos de simulación | Integración háptica inicial, condicionada a placa/protocolo verificados |
| Neural Motion Simulator — MoSim | Avatares, análisis o generación de movimiento | Referencia; confirmar identidad y validez para el movimiento requerido |
| PyLabRobot | Referencia de abstracción de hardware para banco de pruebas | Fuera del control de extinción; la automatización de laboratorio no demuestra aptitud para bombas contra incendios |
| Prometheus, teleoperación con fuerza | Referencia de sensado de fuerza y teleoperación bilateral | Banco aislado; revisar límites antes de adaptar al dispositivo físico |
| BeaVR | Captura de demostraciones y teleoperación mediante poses/acciones | Adaptador experimental; reutilizar backend y datos tras revisión |
| Virtual Reality Teleoperation of a Humanoid Robot | Interacción humanoide y cinemática | Referencia; falta enlace inequívoco y contrato técnico |
| VR-Robo | Evaluación de navegación y transferencia entre simulación y realidad | Investigación; separar métricas simuladas de pruebas físicas |
| Unity VR Robot Realtime Manipulation | Patrones de interfaz y teleoperación | Referencia de migración a Godot; el núcleo propuesto no dependerá de Unity |
| WFH_locobot | Teleoperación de una base móvil con manipulador | Candidato para robot de inspección virtual; revisar dependencias |
| Centauro | Modelo de robot de respuesta a desastres | Evaluación posterior de activos y controladores; no asumir hardware disponible |
| Phantom | Aprendizaje desde demostraciones humanas | Investigación offline con datos autorizados; identidad/licencia por confirmar |
| AeroFlameGuard | Baseline de detección visual de fuego | Evaluar frente a reflejos, vapor, iluminación y humo; no tratarlo como detector certificado |
| Contract Net Protocol para UAV | Asignación negociada de tareas | Implementación explícita en simulación; el protocolo no constituye por sí solo un paquete listo |
| Fast-Planner | Referencia de planificación de trayectorias aéreas | Comparación offline; verificar versión, entorno y adaptación |
| MoveIt para ROS 2 | Planificación y restricciones de manipuladores | Núcleo de la extensión robótica; configuración específica por robot |
| Brax | Entrenamiento acelerado de políticas y experimentación | Laboratorio separado de la simulación de incendio y del control háptico |
| Darwin OP en Gazebo | Modelo educativo de locomoción | Referencia heredada; revisar formatos y soporte antes de migrar |
| WALK-MAN | Arquitectura de robot para entornos degradados | Referencia MBSE para capacidades y requisitos futuros |
| Backhoe Arm with Hydraulic Actuation | Modelo de brazo hidráulico | Investigación de dinámica y actuadores; identidad/licencia por confirmar |

### Hallazgos que afectan a la integración

**XTDrone2.** El repositorio original enlaza a XTDrone2 como evolución para ROS 2. Su README declara desarrollo temprano, uso de PX4/ROS 2/Gazebo Ignition y funciones todavía previstas. Es una vía de evaluación, no una dependencia que pueda darse por compatible con el piloto. Para reducir riesgo se propone fijar una pareja documentada, ROS 2 Jazzy y Gazebo Harmonic, y portar o aislar cada adaptador. No se presenta esta pareja como la versión más reciente. [XTDrone](https://github.com/robin-shaun/XTDrone), [XTDrone2](https://github.com/andy-zhuo-02/XTDrone2), [matriz oficial ROS/Gazebo](https://gazebosim.org/docs/harmonic/ros_installation/).

**SenseShift.** Su firmware documenta accesorios DIY y protocolos concretos. OpenXR no convierte automáticamente un chaleco SenseShift en un periférico compatible: se necesita un adaptador probado. Tampoco el soporte de vibración demuestra capacidad para generar la fuerza de reacción de una manguera. [Firmware y hardware documentados](https://github.com/senseshift/senseshift-firmware).

**BeaVR.** Se aprovecharán la captura de demostraciones y su separación de componentes. El README contiene una mención a BSD y una sección MIT; el archivo LICENSE consultado es MIT. Se registrará la licencia del commit elegido y se revisarán por separado app, activos y dependencias. El cliente descrito depende de su entorno XR y no se dará por libre toda la cadena de ejecución. [README](https://github.com/ARCLab-MIT/beavr-bot), [LICENSE](https://github.com/ARCLab-MIT/beavr-bot/blob/main/LICENSE).

**Prometheus.** Se encontró un candidato que coincide con la descripción en [sdk2035/Prometheus-telos](https://github.com/sdk2035/Prometheus-telos). Su README advierte que se desactivaron comprobaciones de límites articulares. Se tratará como material de investigación: hay que revisar y verificar límites antes de conectar hardware. No debe confundirse con Prometheus, el sistema de métricas.

## 5. Arquitectura de referencia

### 5.1 Capas y responsabilidades

| Capa | Componentes propuestos | Responsabilidad y separación |
|---|---|---|
| Experiencia y aprendizaje | Consola web, Moodle, cliente Godot/OpenXR | Acceso por rol, ejercicios, progreso, reproducción y evaluación del instructor |
| Aplicación y orquestación | FastAPI, gestor de sesiones, gestor de escenarios, LangGraph | Coordinar flujos, validar solicitudes y conservar el estado de cada ejercicio |
| IA y conocimiento | Qwen3-8B local, llama.cpp, Qdrant, embeddings multilingües, percepción | Consulta de procedimientos, detección experimental, tutor y borradores con evidencia |
| Simulación y robótica | FDS/Smokeview, escenarios interactivos, Gazebo, ROS 2, MoveIt | Incendio, escena visual, dinámica robótica y contratos de teleoperación separados |
| Dispositivos y protección | SenseShift, controlador C++/CHAI3D, instrumentación, parada física | Señales táctiles, fuerza limitada, diagnóstico y transición segura ante fallos |
| Datos y operación | PostgreSQL, archivos de sesión, rosbag2/MCAP, identidad, auditoría | Versionado, registros, recuperación y sincronización local/central |

La separación permite cambiar el LLM sin modificar el control háptico y cambiar de robot sin rehacer el curso. Los servicios de identidad, permisos y auditoría son transversales, con despliegues distintos para entrenamiento y experimentación con equipos reales.

### 5.2 Flujo de una sesión formativa

1. El instructor elige competencia, perfil del alumno y escenario aprobado. El gestor crea una sesión con versiones congeladas de escena, rúbrica, modelo y fuentes.
2. El servidor carga el caso de incendio precalculado y los objetos del recinto. El simulador publica estado y eventos con un reloj de simulación común.
3. Godot presenta la escena; los instrumentos aportan posición, orientación, activación y fuerza medida. El controlador local genera únicamente señales dentro del perfil físico autorizado.
4. Un motor de reglas calcula evidencias observables: avisos emitidos, accesos bloqueados, decisiones, uso de instrumentos y coordinación. La IA puede explicar resultados, pero no cambiar retroactivamente la rúbrica.
5. El instructor reproduce la sesión y confirma o corrige la evaluación. Un adaptador publica resultados en Moodle mediante sus servicios externos y conserva una cola si la red no está disponible.

Moodle ofrece una plataforma abierta de aprendizaje y servicios de integración; la conexión concreta al simulador y a su libro de calificaciones será trabajo del proyecto. [Moodle](https://github.com/moodle/moodle), [servicios externos](https://moodledev.io/docs/4.5/apis/subsystems/external).

### 5.3 Flujo de reconocimiento robótico

Sensores y simulación alimentan percepción y estimación del estado. El planificador propone una tarea de inspección; el operador comprueba contexto y la autoriza. Un supervisor determinista valida límites y vigencia del comando antes del controlador del robot. La pérdida de seguimiento, conectividad o condiciones admisibles provoca una respuesta predefinida según el equipo.

En el piloto las acciones serán virtuales. La extensión física empezará por inspección teleoperada en un recinto controlado. La descarga de agentes extintores, las misiones autónomas y el trabajo en incendios reales quedan fuera del MVP y necesitan un proyecto de validación propio.

### 5.4 Contratos de integración propuestos

| Contrato | Transporte | Contenido mínimo | Propiedad técnica |
|---|---|---|---|
| `Session` y `ScenarioManifest` | REST/JSON | ID, perfil, semilla, versiones, objetivos y referencias | Orquestador; cambios aprobados antes de comenzar |
| `Observation` | ROS 2/DDS local | Marca temporal, marco espacial, sensor, calidad y validez | Adaptador del sensor o simulador |
| `HazardHypothesis` | API/eventos | Evidencia, localización, confianza calibrada y fecha de expiración | Servicio de percepción; expresa hipótesis |
| `ActionProposal` | API/eventos | Objetivo, precondiciones, límites, expiración y aprobación | Orquestador; no es un comando de motor |
| `ValidatedRobotCommand` | Interfaz ROS 2 del equipo | Secuencia, objetivo permitido y vigencia | Supervisor de control |
| `HapticCue` | IPC local o protocolo documentado | Tipo, duración y amplitud dentro del perfil autorizado | Adaptador háptico; sin acceso directo del LLM |
| `TrainingEvent` | HTTPS con cola persistente | Sesión, actor seudónimo, evento, tiempo, rúbrica y evidencia | Registro del ejercicio |
| `GradeDecision` | Servicios de Moodle | Resultado, evaluador, rúbrica, observaciones y trazabilidad | Instructor identificado |

Estos nombres son contratos por desarrollar. Para reproducción, registrar además `schema_version`, `event_id`, `session_id`, `source`, `sim_time`, tiempo UTC y número de secuencia. Definir unidades SI y transformaciones explícitas entre ejes de XR, ROS y modelos. Los comandos caducados se descartan; los reintentos de resultados utilizan claves de idempotencia. Los clientes XR no obtienen acceso general al dominio de control de robots.

Para una integración futura con asistentes externos puede añadirse un servidor MCP con consultas al catálogo, procedimientos e informes. No se expondrán por esa interfaz funciones que envíen órdenes directas a motores o cambien límites de fuerza. MCP es una ampliación posterior, no requisito del MVP.

## 6. Servicios de inteligencia artificial

### 6.1 Tutor y asistente documental local

Se propone **Qwen3-8B con llama.cpp** como punto de partida medible; la cuantización, contexto y recursos se fijarán tras evaluar español, terminología y concurrencia. Qwen publica esa familia de pesos bajo Apache 2.0 y documenta motores de ejecución locales. Esto no demuestra por sí solo que toda la cadena de entrenamiento y datos sea reproducible. [Fuente del fabricante del modelo](https://qwenlm.github.io/blog/qwen3/).

El RAG combinará búsqueda textual y vectorial sobre procedimientos aprobados, manuales autorizados, fichas del escenario y materiales docentes. Cada fragmento conservará documento, versión, vigencia, jurisdicción, permiso de acceso y ubicación de la evidencia. Qdrant almacenará vectores y metadatos; PostgreSQL conservará identidades y relaciones del dominio. [Documentación de Qdrant](https://qdrant.tech/documentation/).

La respuesta incluirá citas a pasajes recuperados. Si hay fuentes contradictorias, vencidas o insuficientes, el sistema lo indicará y remitirá al instructor. Los documentos recuperados se tratarán como datos, sin permitir que sus instrucciones modifiquen permisos o invoquen herramientas. El flujo con revisión humana se implementará en LangGraph. [Documentación de LangGraph](https://docs.langchain.com/oss/python/langgraph/overview).

### 6.2 Agentes y salidas verificables

| Servicio lógico | Entrada | Salida | Revisión necesaria |
|---|---|---|---|
| Tutor RAG | Consulta y competencias del curso | Explicación con fuentes y límites | Instructor en contenidos críticos o conflictivos |
| Diseñador de escenarios | Objetivo y catálogo aprobado | Borrador de parámetros dentro de rangos permitidos | Validación técnica y docente antes de publicarlo |
| Analista de percepción | Imágenes, térmica y calidad de sensores | Hipótesis de peligro con evidencia | Operador; no sustituye alarmas reglamentarias |
| Asistente de recursos | Recursos disponibles y tareas | Propuesta de asignación en simulación | Instructor u operador responsable |
| Analista de sesión | Eventos y rúbrica congelada | Cronología y borrador de retroalimentación | Instructor decide calificación |

Son roles de servicio; no necesitan cinco modelos independientes. El MVP utilizará un único servidor de inferencia con colas y permisos diferentes por función.

### 6.3 Entrenamiento y evaluación de los modelos

La primera etapa utilizará recuperación documental, reglas y un modelo existente. El ajuste fino solo se justificará por errores medidos que el RAG y los ejemplos no resuelvan. Las demostraciones robóticas se capturarán con consentimiento y metadatos del entorno, separadas de los expedientes laborales.

El vídeo se procesará en un servicio de visión independiente del LLM textual. Para percepción, separar entrenamiento y validación por edificio, fecha y cámara; no repartir fotogramas contiguos entre ambos conjuntos. Incluir situaciones negativas: vapor, reflejos, soldadura simulada, iluminación variable y oclusiones. Medir sensibilidad, precisión, falsas alarmas por hora y tiempo de detección por escenario; no publicar un único porcentaje de exactitud como garantía de seguridad.

Para el tutor, preparar al menos 100 preguntas revisadas por especialistas, con casos fuera de alcance y fuentes contradictorias. Medir corrección, respaldo documental y abstención adecuada. Para políticas robóticas, empezar en simulación y evaluar cambios de sensores y dinámica; una puntuación simulada no acredita desempeño en un incendio.

## 7. Simulador virtual háptico de lucha contra incendios

### 7.1 Arquitectura del gemelo digital

**Modelo físico del incendio.** FDS calcula transporte de calor y humo; Smokeview permite inspeccionar sus resultados. Se generará un catálogo de casos offline con geometría, materiales, condiciones y limitaciones documentadas. El producto no presupone que un cálculo CFD completo pueda ejecutarse a la frecuencia del visor. [NIST FDS/Smokeview](https://www.nist.gov/services-resources/software/fds-and-smokeview).

**Experiencia interactiva.** Godot/OpenXR representa visibilidad, objetos, ocupantes, herramientas y comunicaciones. El estado interactivo selecciona ramas precalculadas o un modelo reducido dentro de un dominio validado. Si el alumno sale de ese dominio, el sistema informa al instructor y detiene o cambia de forma explícita el ejercicio. Godot dispone de entradas, poses y salidas hápticas a través de acciones XR; se requiere desarrollar la lógica propia del curso. [Acciones XR de Godot](https://docs.godotengine.org/en/stable/tutorials/xr/xr_action_map.html).

**Dinámica robótica.** Gazebo será responsable de colisiones y movimiento del robot; MoveIt de planificación del manipulador. Godot reflejará esos estados sin simular un segundo robot físico independiente. Un único gestor de escenario coordinará incendio, ocupantes y eventos. La evacuación usará un módulo propio validado: NIST informa que FDS+Evac dejó de tener soporte y no se adopta como dependencia nueva. [FDS-SMV](https://pages.nist.gov/fds-smv/), [MoveIt 2](https://moveit.picknik.ai/main/index.html).

No se utilizará un efecto visual de partículas como evidencia de exactitud física. En los escenarios de descarga se documentará la aproximación de interacción del agente y el fuego, sus datos de referencia y los límites de extrapolación.

### 7.2 Dos niveles de háptica

| Nivel | Componentes | Qué permite entrenar | Límites de representación |
|---|---|---|---|
| H1 — Háptica táctil | Mandos XR, accesorios SenseShift, instrumento inerte con sensores | Activación, contacto, orientación, avisos y secuencias de manejo | Vibración y señales táctiles; no reproduce el empuje real de una manguera |
| H2 — Fuerza instrumentada | Mando/boquilla inerte, sensores de fuerza/posición, mecanismo limitado y controlador dedicado | Resistencia graduada y coordinación bajo un perfil mecánico validado | No reproduce automáticamente peso, caudal, calor o dinámica de un equipo real |

H1 será la primera versión. H2 se incorporará después de validar el banco con personal competente en háptica y seguridad mecánica. CHAI3D aporta algoritmos y abstracciones de interacción por fuerza; no convierte por sí mismo un mecanismo en un equipo seguro. Sus parámetros deben respetar las características del dispositivo. [Documentación de renderizado háptico](https://www.chai3d.org/download/doc/html/chapter17-haptics.html).

### 7.3 Estación física y protección

La estación tendrá visor con seguimiento, instrumentos inertes, sensores de activación/orientación, zona despejada, observación del instructor y parada accesible. Los dispositivos de fuerza incorporarán un circuito independiente de inhibición, watchdog, límites de recorrido y un mecanismo de liberación diseñado para el equipo. La respuesta segura se definirá por análisis mecánico: retirar energía no debe producir una caída o liberación peligrosa.

Los perfiles de fuerza y variación de fuerza se calibrarán con instrumentación. Sus valores no se deducirán de una respuesta del LLM. Se ensayarán pérdida de seguimiento, retraso, lectura inválida, bloqueo del proceso y reconexión. El sistema no rearmará actuadores automáticamente después de una parada.

El calor se representará mediante señales visuales, audio o vibración diferenciada. El diseño base no incorpora quemadores, humo real ni generación de dolor. Para fatiga y mareo, se proponen bloques inmersivos de 10–15 minutos, pausas y alternativas de pantalla/observación. La duración se ajustará al usuario y al criterio del instructor; no se presentará como límite clínico universal.

### 7.4 Ritmos de ejecución y objetivos iniciales

| Subsistema | Objetivo de diseño | Validación |
|---|---|---|
| Render XR | 90 Hz cuando lo admita el visor; presupuesto de cuadro de aproximadamente 11,1 ms | Medir estabilidad de cuadros y latencia en escena representativa |
| Interacción de escena | Paso fijo, inicialmente 60 Hz | Reproducción consistente de eventos y reglas |
| Control local de fuerza | Objetivo inicial de 1 kHz, sujeto al dispositivo | Medir jitter, estabilidad y fallos de plazo con ingeniero responsable |
| Avisos táctiles H1 | Frecuencia y latencia propias del protocolo probado | Medición extremo a extremo; no confundir con el lazo de fuerza |
| Tutor IA | Respuesta útil p95 en 5 s como objetivo inicial de consulta | Banco de preguntas y concurrencia documentada |
| Cálculo FDS | Ejecución offline; tiempo dependiente del caso y malla | Convergencia y contraste con casos de referencia |

Son presupuestos para dimensionar y probar, no mediciones actuales. Las órdenes de fuerza no pasarán por nube, Moodle, mensajería de negocio ni inferencia del LLM. La telemetría podrá copiarse de forma asíncrona para evaluación.

### 7.5 Catálogo de escenarios

| ID | Situación simulada | Competencia principal | Evidencia observada |
|---|---|---|---|
| S01 | Oficina con indicio de incendio y salida disponible | Verificar, avisar y decidir entre respuesta inicial autorizada y evacuación | Secuencia, comunicación y conservación de una salida segura |
| S02 | Almacén con humo y ruta habitual bloqueada | Coordinar evacuación y contabilizar personas | Ruta elegida, apoyo a ocupantes y entrega de información |
| S03 | Sala eléctrica o UPS con riesgo incierto | Reconocer límites y solicitar apoyo competente | Decisión de no improvisar una intervención y delimitación del área |
| S04 | Cocina comercial | Identificar el contexto y el procedimiento aprobado | Selección de protocolo, aviso y escalamiento |
| S05 | Aparcamiento con vehículo eléctrico afectado | Reconocer un escenario especializado y proteger a terceros | Evacuación, información y coordinación con bomberos |
| S06 | Instalación industrial próxima a vegetación | Coordinar observación y recursos | Mapa de incidentes, comunicaciones y vigilancia de cambios |
| S07 | Inspección con robot en visibilidad degradada | Teleoperar dentro de límites y recuperar control | Trayectoria, pérdida de enlace, parada y reporte |
| S08 | Ejercicio combinado con alarma, evacuación y datos contradictorios | Liderazgo y transferencia de mando | Resolución de discrepancias, trazabilidad y revisión posterior |

S01–S03 forman el MVP. S04–S08 son ampliaciones. Todos los casos se adaptarán al perfil del alumno y al plan del establecimiento. Las escenas avanzadas de humo y ambientes peligrosos son virtuales; su uso docente no equivale a una autorización para entrar en esos ambientes.

## 8. Curso avanzado: intervención simulada y coordinación contra incendios — 120 horas

### 8.1 Admisión, objetivos y modalidad

Dirigido a especialistas de seguridad, brigadistas y profesionales de emergencias con formación básica demostrable. Antes de matricular, se revisan sus funciones, experiencia y requisitos para las prácticas previstas. El instructor asigna perfil de seguridad privada o perfil de brigada/bomberos.

Al finalizar, el participante deberá interpretar un escenario, reconocer cuándo no intervenir, ejecutar en simulación las tareas de su perfil, comunicarse con el mando, utilizar instrumentos hápticos y producir un informe con evidencias. La formación combina teoría, laboratorio XR y práctica presencial supervisada.

**Duración:** seis semanas a 20 horas. T = teoría/casos; XR = laboratorio, briefing, turnos inmersivos, observación y debriefing; P = práctica presencial fuera del visor. Las 70 horas de laboratorio XR no son 70 horas de exposición continua al visor.

### 8.2 Malla del curso avanzado

| Módulo | Contenidos y resultado observable | T | XR | P | Total |
|---|---|---:|---:|---:|---:|
| A1. Riesgo y límites de actuación | Principios del incendio, rol asignado y criterios de retirada; justificar una decisión | 4 | 4 | 0 | 8 |
| A2. Lectura del escenario | Humo, visibilidad, información térmica y señales inciertas; distinguir dato de inferencia | 4 | 8 | 0 | 12 |
| A3. Instrumentos y háptica | Inspección del equipo de entrenamiento, extintor/boquilla inertes y coordinación; completar tareas del perfil | 2 | 12 | 6 | 20 |
| A4. Evacuación y mando | Comunicaciones, recuento, accesibilidad y coordinación; transferir información sin omisiones | 4 | 8 | 4 | 16 |
| A5. Escenarios complejos | Industria, electricidad, cocina y baterías; reconocer límites y escalar a especialistas | 4 | 12 | 0 | 16 |
| A6. Robótica de apoyo | Inspección virtual, teleoperación, percepción y pérdida de enlace; mantener control autorizado | 2 | 10 | 4 | 16 |
| A7. Transferencia y equipo | Ejercicios coordinados y estaciones con material inerte; demostrar habilidades fuera del visor | 2 | 8 | 10 | 20 |
| A8. Evaluación integrada | Escenario desconocido, reporte, defensa de decisiones y plan de mejora | 2 | 8 | 2 | 12 |
| **Total** | | **24** | **70** | **26** | **120** |

Las prácticas P utilizan equipos de entrenamiento, ejercicios de comunicación, recorridos de evacuación y estaciones supervisadas. El fuego real no se incluye en estas 120 horas: si una entidad formadora lo incorpora, deberá rediseñar y validar esa práctica específica, sus requisitos y su carga horaria.

### 8.3 Evaluación del curso avanzado

| Dimensión | Peso | Evidencia |
|---|---:|---|
| Interpretación del riesgo y decisión | 30 % | Justificación, contexto, información ausente y elección de actuar/retirarse |
| Manejo de instrumentos según perfil | 25 % | Activación, orientación, coordinación y cuidado del equipo |
| Comunicación y trabajo en equipo | 20 % | Mensajes, confirmaciones, recuento y transferencia al mando |
| Cumplimiento de límites de seguridad | 15 % | Respeto a zonas, parada, funciones y criterios de abandono |
| Informe y debriefing | 10 % | Cronología, fuentes, errores identificados y acciones de mejora |

**Aprobación propuesta:** mínimo 85/100 y cumplimiento de todos los criterios críticos. Una infracción crítica no se compensa con velocidad o buen promedio. Ejemplos: ignorar una parada, ejecutar una tarea fuera del perfil o continuar una intervención simulada cuando el guion exige retirada.

La evaluación contiene estación práctica, escenario individual, ejercicio de equipo e informe. El instructor valida los resultados y ofrece recuperación específica. Se proponen comprobaciones de retención a 30 y 90 días para evaluar transferencia del aprendizaje; son decisiones académicas, no periodicidades normativas.

## 9. Plan de estudios: especialista profesional en seguridad privada — 240 horas

### 9.1 Perfil de egreso

Profesional capaz de analizar riesgos del servicio, prevenir incidentes, gestionar accesos, utilizar sistemas de vigilancia respetando derechos, documentar eventos y coordinar emergencias. Podrá interpretar el alcance y las limitaciones de herramientas de IA y apoyar operaciones de inspección con robots o drones dentro de sus funciones.

El plan está orientado a seguridad corporativa, instalaciones logísticas, comercio, hotelería e industria. Es una propuesta de especialización; no sustituye la formación básica, autorizaciones o acreditaciones exigibles en cada jurisdicción.

**Duración:** doce semanas a 20 horas. T = teoría; L = laboratorio/casos/simulación, con o sin XR; P = práctica presencial supervisada.

### 9.2 Malla curricular

| Módulo | Competencias y evidencia de aprendizaje | T | L | P | Total |
|---|---|---:|---:|---:|---:|
| P1. Ética, derechos y marco aplicable | Funciones, límites, trato digno y privacidad; resolver casos de actuación profesional | 12 | 4 | 0 | 16 |
| P2. Análisis de riesgos | Activos, amenazas, vulnerabilidades y medidas; elaborar una matriz del establecimiento | 10 | 10 | 4 | 24 |
| P3. Protección física y accesos | Visitantes, contratistas, rondas y prevención de pérdidas; diseñar un procedimiento de acceso | 8 | 8 | 8 | 24 |
| P4. Comunicación y desescalada | Escucha, conflictos, atención inclusiva y coordinación; resolver un incidente simulado | 6 | 8 | 6 | 20 |
| P5. CCTV, alarmas e IA | Monitoreo, falsas alarmas, límites de analítica y protección de datos; revisar una alerta con evidencia | 8 | 12 | 4 | 24 |
| P6. Ciberseguridad aplicada al servicio | Identidades, credenciales, phishing y reporte de fallos; ejecutar un ejercicio defensivo | 8 | 10 | 2 | 20 |
| P7. Prevención y respuesta inicial al incendio | Inspecciones, avisos, equipos y criterios de actuación; demostrar el procedimiento autorizado | 8 | 10 | 6 | 24 |
| P8. Evacuación y coordinación de emergencias | Plan del recinto, roles, recuento y mando; conducir un ejercicio de evacuación | 6 | 8 | 6 | 20 |
| P9. Primeros auxilios y apoyo inicial | Reconocimiento de emergencias y ayuda dentro de la formación; evaluación práctica por instructor competente | 4 | 0 | 12 | 16 |
| P10. Drones y robots de inspección | Uso responsable, observación y límites operativos; misión virtual y reporte | 4 | 10 | 2 | 16 |
| P11. Informes y preservación de evidencia | Cronologías, registro, conservación y escalamiento; producir un parte verificable | 6 | 8 | 2 | 16 |
| P12. Proyecto integrador | Plan de seguridad y ejercicio combinado; defender decisiones ante un panel | 0 | 10 | 10 | 20 |
| **Total** | | **80** | **98** | **62** | **240** |

El módulo P9 describe un área de formación y requiere un programa práctico impartido por personal competente; este documento no contiene instrucciones clínicas. La vigilancia con IA se centrará en eventos y revisión humana: no se incorporarán puntuaciones opacas de personas ni inferencias de atributos sensibles como competencia curricular.

### 9.3 Secuencia y evaluación

Las semanas 1–4 cubren fundamentos, riesgo, accesos y comunicación; las semanas 5–8, tecnología, prevención y respuesta; las semanas 9–12, práctica integrada, documentación y proyecto. La distribución concreta de módulos se ajustará a disponibilidad de instructores, manteniendo sus horas y prerrequisitos.

P1 y P2 preceden a P3/P5; P7 precede a las prácticas de emergencia de P8; P5/P6 preceden a P10; todos alimentan P12. Los contenidos de P7/P8 introducen competencias que el curso avanzado retoma con escenarios de mayor complejidad, por lo que sus horas no se convalidan automáticamente.

**Evaluación propuesta:** conocimientos y casos 25 %, estaciones prácticas 35 %, simulaciones de equipo 20 % y proyecto final 20 %. Se exige mínimo 80/100, evidencia de todas las prácticas esenciales y cumplimiento de todos los criterios críticos. La IA aporta retroalimentación; un evaluador humano firma el resultado.

El portafolio del egresado contendrá matriz de riesgos, procedimiento de acceso, revisión de alertas, plan de coordinación de emergencia, informe de incidente y evidencia del ejercicio final. Estos documentos serán seudonimizados cuando se usen para docencia.

### 9.4 Encaje institucional y adaptación a Perú

Como posible aplicación en Perú, la entidad interesada deberá contrastar el programa con la regulación vigente de SUCAMEC y las atribuciones del centro de formación o departamento de capacitación elegido. La entidad mantiene un [directorio oficial de CEFOESP y departamentos autorizados](https://www.gob.pe/institucion/sucamec/informes-publicaciones/4764413-departamentos-de-capacitacion-o-centros-de-formacion-y-especializacion-en-seguridad-privada-cefoesp-autorizados-por-sucamec). El acceso íntegro a esa página no estuvo disponible durante la revisión; se identificó su ficha oficial, sin validar aquí un centro específico.

**Las cargas de 240 y 120 horas son propuestas propias.** No se presentan como horas obligatorias de SUCAMEC ni como cursos autorizados, y no se confirmó una equivalencia regulatoria. Antes de comercializarlos, la entidad formadora debe mapear contenidos, modalidad, prácticas e instructores con los requisitos que le correspondan.

Para mando de incidentes se puede usar como referencia conceptual el curso [FEMA IS-100.C](https://training.fema.gov/programs/independent-study/courseoverview.aspx?code=IS-100.c&lang=en). Citarlo no convierte el programa en un curso FEMA ni garantiza un certificado de esa institución. La formación de incendios adoptará los procedimientos y normas aplicables al establecimiento y las competencias del organismo de respuesta participante.

## 10. Datos, despliegue y continuidad

### 10.1 Despliegue inicial

| Nodo | Servicios | Hipótesis inicial de dimensionamiento |
|---|---|---|
| Estación XR, dos unidades | Godot, seguimiento y adaptador de instrumentos | PC con 32 GB de RAM y GPU dedicada; capacidad final según visor y escena medidos |
| Controlador háptico | Proceso local C++ y electrónica del mecanismo | Recursos reservados; inhibición física independiente; sin dependencia de internet |
| Servidor local de aula | API, PostgreSQL, Qdrant, Moodle e inferencia | Punto de ensayo: 64 GB de RAM; GPU independiente si se requiere concurrencia de IA |
| Nodo de cálculo de escenarios | FDS y preparación de casos | CPU/RAM según malla; trabajos offline, sin competir con la sesión XR |
| Servidor central opcional | Copias, catálogo y administración de sedes | Sincronización posterior; no forma parte del control háptico |

Son hipótesis de prueba, no una lista de compra. No se infiere que una cantidad de memoria asegure una frecuencia de visor determinada. Una sede pequeña puede compartir servicios si las mediciones demuestran aislamiento suficiente.

El MVP empleará contenedores para servicios de aplicación y datos, con dispositivos y procesos de baja latencia administrados localmente. Kubernetes se reservará para una necesidad demostrada de varias sedes o mayor escala. Se probarán restauración de PostgreSQL, recuperación de archivos y sincronización idempotente de resultados.

### 10.2 Identidad, trazabilidad y conservación

Cada centro y curso tendrá permisos propios. Instructor, alumno, administrador y operador dispondrán de funciones distintas. Los datos que salen del centro se minimizarán; vídeo y voz se conservarán solo con finalidad y plazo definidos. La política de retención será una decisión documentada de la entidad según su contexto, sin imponer aquí un plazo universal.

Se almacenarán versión de escenario y rúbrica, hash de activos, calibración del dispositivo, versiones de modelos y documentos, eventos, decisión del evaluador y motivo de correcciones. Las grabaciones permitirán reconstruir la secuencia; no se promete determinismo bit a bit de GPU, física o inferencia.

La evaluación no alimentará automáticamente decisiones de contratación, aptitud médica o sanciones laborales. Los participantes podrán revisar sus evidencias y solicitar correcciones al responsable académico.

## 11. Requisitos verificables y criterios de aceptación

| ID | Requisito propuesto | Evidencia de aceptación |
|---|---|---|
| R01 | Sesión completa sin internet | Ejecutar y cerrar un ejercicio local; sincronizar una sola vez al recuperar red |
| R02 | Escenario identificado y versionado | Recuperar manifiesto, semilla, activos, fuentes y rúbrica de cada sesión |
| R03 | IA documental trazable | Banco revisado; cada afirmación procedimental evaluada tiene fuente pertinente o abstención |
| R04 | Separación IA/control | Prueba de permisos demuestra que el LLM no publica comandos de actuador |
| R05 | Parada háptica independiente | Ensayos instrumentados de fallo y respuesta segura según límites aprobados del dispositivo |
| R06 | Manejo de pérdida de tracking | Detectar dato inválido, inhibir la interacción afectada y requerir rearme consciente |
| R07 | Validez del modelo de incendio | Fichas de verificación/validación por caso y límites visibles para el instructor |
| R08 | Evaluación explicable | Reconstruir cada puntuación desde rúbrica y evidencia; firma del evaluador |
| R09 | Interoperabilidad espacial | Prueba de unidades, ejes, marcos, latencia y sincronización XR/ROS |
| R10 | Protección de expedientes | Ensayar acceso entre cursos/sedes y registrar intentos rechazados |
| R11 | Integración académica | Publicación sin duplicados de resultados y corrección controlada en Moodle |
| R12 | Transferencia del aprendizaje | Comparar pre/post y retención con estaciones prácticas; informar muestra y límites |

Los objetivos numéricos se fijarán antes de las pruebas. Para el tutor se propone como puerta inicial ≥90 % de respuestas correctas y fundamentadas en un banco de al menos 100 casos, con todos los casos críticos revisados. Alcanzar esa meta no constituye una garantía universal. Para percepción se pactarán umbrales por escenario después de medir el baseline; no se inventa una precisión de detección.

Un piloto académico de 12–20 participantes puede servir para detectar problemas de usabilidad y ajustar rúbricas. No bastará por sí solo para afirmar reducción de lesiones o equivalencia con entrenamiento real. La validación física de háptica precede al piloto con usuarios.

## 12. Hoja de ruta ejecutable del MVP — 16 semanas

| Fase | Semanas | Entregables | Puerta de salida |
|---|---|---|---|
| F0. Definición y selección | 1–2 | Perfil de usuario, matriz de competencias, requisitos MBSE, manifiesto de licencias e interfaces | Instructor y responsable técnico aceptan alcance; dependencias del MVP identificadas |
| F1. Simulación base | 3–5 | Escenario S01, cliente Godot, eventos, consola y caso FDS documentado | Sesión sin háptica de fuerza reproducible y coherente |
| F2. Háptica inicial | 6–8 | H1, instrumentos inertes, calibración, diagnóstico y registro | Ensayos de fallo aprobados; práctica supervisada con H1 |
| F3. IA y aprendizaje | 9–11 | Tutor RAG, rúbrica, S02/S03, integración Moodle y reproducción | Evaluación docente del corpus, control de acceso y resultados sin duplicados |
| F4. Robótica y banco H2 | 12–14 | Robot virtual ROS/Gazebo, adaptador de poses y banco de fuerza opcional | Robot simulado validado; H2 solo pasa a usuarios si supera su revisión mecánica |
| F5. Piloto y entrega | 15–16 | Prueba académica, correcciones, manuales, copia/restauración y expediente técnico | Instructor acepta piloto; limitaciones y resultados publicados en informe interno |

La ruta crítica es la validación de escenarios y el banco físico. Si H2 no está listo, el MVP se entrega con H1 y se identifica claramente que la simulación de fuerza sigue pendiente. Las 16 semanas no incluyen desarrollar un robot contra incendios certificado ni impartir todo el itinerario académico de 18 semanas.

### Equipo y esfuerzo

Propuesta de equipo con cinco funciones técnicas: arquitectura/backend, XR, robótica/háptica, IA/datos y pruebas/operación. Añadir un especialista en incendios y un responsable académico de seguridad privada con dedicación planificada. Se admite que algunas funciones se combinen si se mantiene revisión competente de los elementos físicos.

Como estimación de planificación, cinco dedicaciones técnicas durante 16 semanas equivalen a 80 persona-semanas, más docencia, revisión especializada y tiempo de fabricación. Esta cifra es un supuesto de capacidad, no una cotización. El presupuesto se calculará con tarifas acordadas, equipos, fabricación, mantenimiento, seguros o autorizaciones aplicables y contingencias identificadas.

### Backlog inicial priorizado

| Prioridad | Trabajo | Dependencia |
|---|---|---|
| P0 | Catálogo de competencias y criterios críticos por perfil | Instructor y plan del establecimiento |
| P0 | Manifiesto de escena y contrato de eventos | Arquitectura de datos |
| P0 | S01 interactivo con evaluación por reglas | Activos y caso físico revisados |
| P0 | Instrumento H1 con registro y manejo de fallos | Protocolo y hardware seleccionados |
| P0 | Tutor documental con corpus aprobado | Permisos y materiales docentes |
| P0 | Consola, reproducción y calificación firmada | Eventos y rúbrica |
| P1 | S02/S03 e integración Moodle | Base del simulador y servicios externos |
| P1 | Robot virtual y teleoperación | Pareja ROS/Gazebo fijada y marcos espaciales |
| P2 | Banco H2 y modelos reducidos adaptativos | Validación mecánica y física específica |
| P2 | Flota, demostraciones y políticas aprendidas | Interfaces y evidencia del piloto |

## 13. Organización propuesta para el repositorio

Los siguientes son destinos sugeridos para una futura incorporación. Los entregables de esta propuesta no modifican el repositorio remoto.

| Ruta propuesta | Contenido |
|---|---|
| `README.md` | Visión, alcance, arquitectura resumida y guía de navegación |
| `docs/architecture/` | Decisiones, contratos, despliegue y límites de integración |
| `docs/training/` | Mallas, rúbricas y guías del instructor |
| `MBSE/requirements/` | Requisitos, trazabilidad y verificaciones |
| `MBSE/CAD/` | Instrumentos inertes, estación y documentación de hardware |
| `MBSE/CAM/` | Fabricación, montaje y control de revisiones |
| `MBSE/CAS/Drawio/` | Diagramas editables de arquitectura y evolución |
| `MBSE/CAS/fds/` | Casos físicos, parámetros y reportes de validación |
| `simulator/godot/` | Cliente XR, escenas y adaptadores |
| `robotics/` | Paquetes ROS 2, modelos y contratos de control |
| `haptics/` | Controladores, perfiles, calibraciones y pruebas del banco |
| `services/` | Sesiones, IA, evaluación, datos e integración académica |
| `tests/acceptance/` | Evidencias ligadas a R01–R12 |
| `deploy/` | Contenedores, configuración y recuperación |
| `third_party/manifest.yaml` | Origen, commit, licencia y estado de cada dependencia |

Arcadia/Capella, ya mencionado por el proyecto, puede organizar necesidades operativas, funciones, componentes lógicos y asignación física. Cada requisito deberá vincularse con un componente, una competencia y una prueba. El draw.io adjunto comunica esas vistas; no se presenta como un modelo Capella ejecutable.

## 14. Política de software libre y decisiones pendientes

| Componente verificado | Licencia/fuente consultada | Decisión |
|---|---|---|
| Godot | MIT, [página oficial](https://godotengine.org/license/) | Motor XR principal; conservar avisos y revisar activos |
| FDS/Smokeview | Dominio público según [NIST](https://pages.nist.gov/fds-smv/) | Referencia física; conservar procedencia y límites |
| CHAI3D | BSD de tres cláusulas según [página oficial](https://www.chai3d.org/download/license) | Candidato de renderizado de fuerza; revisar SDK del dispositivo por separado |
| SenseShift firmware | GPL-3.0 declarada en [README](https://github.com/senseshift/senseshift-firmware) | Mantener condiciones de distribución y revisar hardware/dependencias |
| BeaVR backend | MIT en [LICENSE consultado](https://github.com/ARCLab-MIT/beavr-bot/blob/main/LICENSE) | Revisar app y activos de manera independiente |
| XTDrone2 | MIT declarada en [README](https://github.com/andy-zhuo-02/XTDrone2) | Investigación hasta verificar compatibilidad |
| Qwen3-8B | Pesos Apache 2.0 según [publicación oficial](https://qwenlm.github.io/blog/qwen3/) | Modelo candidato; fijar archivo, revisión y cuantización |
| Moodle | GPLv3 según [README](https://github.com/moodle/moodle) | Plataforma académica autohospedada |

Para el código nuevo se propone una licencia abierta definida por el titular después de revisar cómo se distribuyen los componentes. No se aplica una licencia única al material de terceros. «Código visible», «gratuito», «pesos abiertos» y «software libre» no se usarán como sinónimos.

El objetivo de una cadena abierta requiere revisar también runtime del visor, firmware, controladores GPU, modelos 3D, voces, datasets y manuales incorporados al RAG. OpenXR es una interfaz; su uso no implica que cualquier runtime o dispositivo sea libre. Las dependencias comerciales o restringidas se declararán y se ofrecerán alternativas cuando exista una combinación compatible.

Antes de comenzar F1 quedan cinco decisiones concretas: recinto piloto y perfil del alumno; hardware H1; conjunto de documentos autorizados; entidad académica responsable; y versiones/licencias del pequeño subconjunto de repositorios que realmente entre en el MVP. Los proyectos de flota y humanoides pendientes de identificación no bloquean ese inicio.

## 15. Índice de fuentes primarias

Las fuentes se enlazan junto a las afirmaciones que respaldan. Este índice facilita su consulta; no implica que sus autores avalen la propuesta.

| Área | Fuentes |
|---|---|
| Compendio y estado inicial | [README fijado a la revisión](https://github.com/robotics-intelligent-systems/jfxai4rffs/blob/8f8524616b3c07108f7b9f8255ac0cc9f5308e00/README.md), [diagrama existente](https://github.com/robotics-intelligent-systems/jfxai4rffs/blob/8f8524616b3c07108f7b9f8255ac0cc9f5308e00/MBSE/CAS/Drawio/humanoid-platform.drawio) |
| Drones y robótica | [XTDrone](https://github.com/robin-shaun/XTDrone), [XTDrone2](https://github.com/andy-zhuo-02/XTDrone2), [ROS/Gazebo](https://gazebosim.org/docs/harmonic/ros_installation/), [MoveIt 2](https://moveit.picknik.ai/main/index.html) |
| Teleoperación | [BeaVR](https://github.com/ARCLab-MIT/beavr-bot), [candidato Prometheus-telos](https://github.com/sdk2035/Prometheus-telos) |
| Háptica y XR | [SenseShift](https://github.com/senseshift/senseshift-firmware), [CHAI3D haptics](https://www.chai3d.org/download/doc/html/chapter17-haptics.html), [Godot XR](https://docs.godotengine.org/en/stable/tutorials/xr/index.html) |
| Simulación de incendios | [NIST FDS/Smokeview](https://www.nist.gov/services-resources/software/fds-and-smokeview), [documentación y estado FDS-SMV](https://pages.nist.gov/fds-smv/) |
| IA y conocimiento | [Qwen3](https://qwenlm.github.io/blog/qwen3/), [LangGraph](https://docs.langchain.com/oss/python/langgraph/overview), [Qdrant](https://qdrant.tech/documentation/) |
| Formación | [Moodle](https://github.com/moodle/moodle), [servicios externos](https://moodledev.io/docs/4.5/apis/subsystems/external), [FEMA ICS 100](https://training.fema.gov/programs/independent-study/courseoverview.aspx?code=IS-100.c&lang=en), [ficha SUCAMEC de centros autorizados](https://www.gob.pe/institucion/sucamec/informes-publicaciones/4764413-departamentos-de-capacitacion-o-centros-de-formacion-y-especializacion-en-seguridad-privada-cefoesp-autorizados-por-sucamec) |
