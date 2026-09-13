# jfxai4rffs — AI Integration Architecture, Haptic Simulation, and Professional Training

**Robotics Intelligent Systems · Consolidated technical and academic proposal · Version 1.0, English edition · September 13, 2026**

**Reference repository:** [robotics-intelligent-systems/jfxai4rffs](https://github.com/robotics-intelligent-systems/jfxai4rffs). Reviewed revision: `8f8524616b3c07108f7b9f8255ac0cc9f5308e00`.

**Scope of this consolidated edition:** the software compendium, AI integration architecture, virtual haptic firefighting simulator, professional curricula, verification requirements, and implementation roadmap are brought together in this document. The companion file, `jfxai4rffs-ai-haptic-architecture-EN.drawio`, contains four editable tabs: integrated architecture, haptic simulator, professional training, and MVP evolution. The decisions, training hours, performance targets, and schedules below are design proposals; they do not describe an existing implementation or an accreditation already obtained. This English edition preserves the technical and academic scope of the Spanish proposal and the sources reviewed for that proposal.

## 1. Executive Proposal

Evolve the **AI-Powered Robotic Fire Fighting Platform** into an open platform integrating fire prevention, support for robot and drone operators, immersive training, and professional assessment. The product will combine a facility digital twin, multimodal perception, an AI assistant with document retrieval, a virtual reality station with haptics, and a learning management system.

The initial product will be a **training and decision-support center that operates on a local network**. It will support incident exercises in commercial, industrial, and logistics facilities; record participant actions; explain errors using evidence; and train coordination between private security personnel, internal fire brigades, and emergency services.

AI will propose scenarios, retrieve procedures, and draft reports. Responsible professionals will retain authority over intervention decisions and final assessment. Motion and force controllers will have verifiable limits independent of the language model.

| Deliverable | Proposed content |
|---|---|
| Integration platform | ROS 2, compendium adapters, AI services, data services, and an instructor console |
| Simulator | Godot/OpenXR, fire scenarios based on FDS, physical training instruments, and two haptic levels |
| Professional program | 240 hours covering private security, prevention, technology, and emergency coordination |
| Advanced course | 120 additional hours of firefighting training with haptic simulation |
| Software pilot | 16 weeks, two XR stations, three baseline scenarios, and one virtual robot |
| Complete academic pathway | 360 hours; 18 weeks at 20 hours per week, once the laboratory is available |

## 2. Starting Point and Review Scope

The [reviewed README](https://github.com/robotics-intelligent-systems/jfxai4rffs/blob/8f8524616b3c07108f7b9f8255ac0cc9f5308e00/README.md) lists tools for drones, teleoperation, haptics, learning, and robotic simulation. The reviewed repository tree contains that README and a humanoid platform diagram, together with its backup. The diagram has a single block, “Motion Description Language.” No integrated application, dependency manifest, integration tests, or project LICENSE file was found in that tree.

The compendium is therefore treated as a **portfolio of candidate technologies**. The interfaces and services in this proposal must be developed. Direct compatibility between all listed projects is not assumed. The absence of a license in the reviewed tree must be addressed before distributing new code; each dependency will retain its own license.

Primary sources were checked for the key components: XTDrone/XTDrone2, SenseShift, BeaVR, a matching candidate for Prometheus force-feedback teleoperation, ROS/Gazebo, MoveIt, Godot, CHAI3D, FDS, the Qwen3 model, and Moodle. Names without an unambiguous repository in the compendium remain marked as pending; unverified capabilities or licenses are not assigned to them.

## 3. Users, Competencies, and Operational Boundaries

| Role | Functions within the platform | Training scope |
|---|---|---|
| Private security specialist | Prevention, alert verification, communications, evacuation, access control, and information handover | Actions consistent with assigned duties, training, and the facility plan |
| Designated fire brigade member | Initial response and tasks authorized by the organization | Scenarios and practical work matching previously established competencies |
| Firefighter or fire training instructor | Technical validation, exercise supervision, and specialist assessment | Advanced simulated intervention; live practical work subject to applicable facilities, qualifications, and procedures |
| Robot or drone operator | Reconnaissance and supervised teleoperation | Simulation first; specific qualification before operating real equipment |
| AI/robotics engineer | Integration, calibration, testing, and traceability | Technical expertise alone does not authorize certification of operational competencies |

The advanced course will provide **two scenario profiles**. The private security profile assesses prevention, notification, evacuation, withdrawal decisions, and authorized initial response. The fire brigade/firefighter profile adds virtual intervention tasks consistent with prior training. Completing the private security program does not automatically qualify a participant for structural firefighting, technical rescue, or respiratory protective equipment use.

## 4. Integration of the Existing Software Compendium

The decisions in this matrix are architectural. “Candidate” means integration testing is required; “reference” means the project contributes models or methods without necessarily becoming part of the product.

| Compendium element | Proposed role and interface | Initial decision |
|---|---|---|
| XTDrone | UAV scenarios and a PX4/ROS/Gazebo integration reference | Retain examples; evaluate XTDrone2 in a separate environment |
| Langostino | Potential UAV platform for reconnaissance | Candidate; confirm repository, hardware, and license |
| Mission-Directed Swarm | Assignment of reconnaissance missions | Research after the pilot; identity requires confirmation |
| DroneFleet Optimizer | Fleet visibility and resource assignment through an API | Candidate; confirm API, license, and local operation |
| Altnautica Mission Control | Mission operation and tracking station | Candidate console adapter; identity and API require confirmation |
| SenseShift | Vest or gloves for tactile alerts and simulation events | Initial haptic integration, conditional on verified board and protocol support |
| Neural Motion Simulator — MoSim | Avatars, motion analysis, or motion generation | Reference; confirm identity and suitability for the required movements |
| PyLabRobot | Hardware abstraction reference for a test bench | Excluded from suppression control; laboratory automation does not establish suitability for firefighting pumps |
| Prometheus, force-feedback teleoperation | Reference for force sensing and bilateral teleoperation | Isolated test bench; review limits before adapting physical equipment |
| BeaVR | Demonstration capture and teleoperation through poses/actions | Experimental adapter; reuse backend and data after review |
| Virtual Reality Teleoperation of a Humanoid Robot | Humanoid interaction and kinematics | Reference; an unambiguous link and technical contract are missing |
| VR-Robo | Navigation evaluation and transfer between simulation and reality | Research; keep simulated metrics separate from physical tests |
| Unity VR Robot Realtime Manipulation | Interface and teleoperation patterns | Reference for migration to Godot; the proposed core will not depend on Unity |
| WFH_locobot | Teleoperation of a mobile base with a manipulator | Candidate for a virtual inspection robot; review dependencies |
| Centauro | Disaster-response robot model | Later evaluation of assets and controllers; hardware availability is not assumed |
| Phantom | Learning from human demonstrations | Offline research using authorized data; identity and license require confirmation |
| AeroFlameGuard | Baseline for visual fire detection | Evaluate against reflections, steam, lighting, and smoke; do not treat it as a certified detector |
| Contract Net Protocol for UAVs | Negotiated task assignment | Explicit implementation in simulation; the protocol alone is not a ready-to-use package |
| Fast-Planner | Aerial trajectory planning reference | Offline comparison; verify version, environment, and adaptation requirements |
| MoveIt for ROS 2 | Manipulator planning and constraints | Core of the robotic extension; robot-specific configuration is required |
| Brax | Accelerated policy training and experimentation | Laboratory environment separate from fire simulation and haptic control |
| Darwin OP in Gazebo | Educational locomotion model | Legacy reference; review formats and support before migration |
| WALK-MAN | Robot architecture for degraded environments | MBSE reference for future capabilities and requirements |
| Backhoe Arm with Hydraulic Actuation | Hydraulic arm model | Dynamics and actuator research; identity and license require confirmation |

### Findings Affecting Integration

**XTDrone2.** The original repository links to XTDrone2 as its ROS 2 evolution. Its README states that it is in early development, uses PX4/ROS 2/Gazebo Ignition, and has features still planned. It is an evaluation path, not a dependency that can be assumed compatible with the pilot. To reduce integration risk, this proposal fixes a documented pairing, ROS 2 Jazzy and Gazebo Harmonic, and requires each adapter to be ported or isolated. This pairing is not presented as the latest release. [XTDrone](https://github.com/robin-shaun/XTDrone), [XTDrone2](https://github.com/andy-zhuo-02/XTDrone2), [official ROS/Gazebo compatibility matrix](https://gazebosim.org/docs/harmonic/ros_installation/).

**SenseShift.** Its firmware documents DIY accessories and specific protocols. OpenXR does not automatically make a SenseShift vest a compatible peripheral: a tested adapter is needed. Vibration support also does not establish the ability to generate hose reaction force. [Documented firmware and hardware](https://github.com/senseshift/senseshift-firmware).

**BeaVR.** Demonstration capture and component separation will be evaluated for reuse. The README mentions BSD in one passage and MIT in its license section; the reviewed LICENSE file is MIT. The license of the selected commit will be recorded, with separate reviews of the app, assets, and dependencies. The documented client relies on its XR environment, so the entire execution chain will not be assumed to be free software. [README](https://github.com/ARCLab-MIT/beavr-bot), [LICENSE](https://github.com/ARCLab-MIT/beavr-bot/blob/main/LICENSE).

**Prometheus.** A candidate matching the description was found at [sdk2035/Prometheus-telos](https://github.com/sdk2035/Prometheus-telos). Its README notes that joint-limit checks were disabled. It will be treated as research material: limits must be reviewed and verified before hardware is connected. It should not be confused with Prometheus, the metrics system.

## 5. Reference Architecture

### 5.1 Layers and Responsibilities

| Layer | Proposed components | Responsibility and separation |
|---|---|---|
| Experience and learning | Web console, Moodle, Godot/OpenXR client | Role-based access, exercises, progress, replay, and instructor assessment |
| Application and orchestration | FastAPI, session manager, scenario manager, LangGraph | Coordinate workflows, validate requests, and preserve exercise state |
| AI and knowledge | Local Qwen3-8B, llama.cpp, Qdrant, multilingual embeddings, perception | Procedure retrieval, experimental detection, tutoring, and evidence-based drafts |
| Simulation and robotics | FDS/Smokeview, interactive scenarios, Gazebo, ROS 2, MoveIt | Separate fire modeling, visual experience, robot dynamics, and teleoperation contracts |
| Devices and protection | SenseShift, C++/CHAI3D controller, instrumentation, physical stop | Tactile cues, limited force, diagnostics, and safe transitions after faults |
| Data and operations | PostgreSQL, session files, rosbag2/MCAP, identity, audit logs | Versioning, records, recovery, and local/central synchronization |

This separation allows the LLM to change without modifying haptic control, and the robot to change without rebuilding the course. Identity, permissions, and audit services span all layers, with distinct deployments for training and experimentation with real equipment.

### 5.2 Training Session Workflow

1. The instructor selects a competency, learner profile, and approved scenario. The manager creates a session with frozen versions of the scene, rubric, model, and sources.
2. The server loads the precomputed fire case and facility objects. The simulator publishes state and events using a common simulation clock.
3. Godot displays the scene; instruments supply position, orientation, activation, and measured force. The local controller generates only signals within the authorized physical profile.
4. A rule engine derives observable evidence: notifications, blocked access points, decisions, instrument use, and coordination. AI may explain outcomes, but it cannot retroactively change the rubric.
5. The instructor replays the session and confirms or corrects the assessment. An adapter publishes results to Moodle through its external services and retains a queue when the network is unavailable.

Moodle provides an open learning platform and integration services; connecting this simulator and its results to the gradebook remains project development work. [Moodle](https://github.com/moodle/moodle), [external services](https://moodledev.io/docs/4.5/apis/subsystems/external).

### 5.3 Robotic Reconnaissance Workflow

Sensors and simulation feed perception and state estimation. The planner proposes an inspection task; the operator checks the context and authorizes it. A deterministic supervisor validates limits and command freshness before the robot controller receives a command. Loss of tracking, connectivity, or admissible conditions triggers a predefined response appropriate to the equipment.

Pilot actions will be virtual. The physical extension will begin with teleoperated inspection in a controlled facility. Releasing extinguishing agents, autonomous missions, and operation at real fires are outside the MVP and require their own validation project.

### 5.4 Proposed Integration Contracts

| Contract | Transport | Minimum content | Technical ownership |
|---|---|---|---|
| `Session` and `ScenarioManifest` | REST/JSON | ID, profile, seed, versions, objectives, and references | Orchestrator; changes approved before the session starts |
| `Observation` | Local ROS 2/DDS | Timestamp, coordinate frame, sensor, quality, and validity | Sensor or simulator adapter |
| `HazardHypothesis` | API/events | Evidence, location, calibrated confidence, and expiry | Perception service; expresses a hypothesis |
| `ActionProposal` | API/events | Goal, preconditions, limits, expiry, and approval | Orchestrator; not a motor command |
| `ValidatedRobotCommand` | Equipment ROS 2 interface | Sequence, permitted target, and validity period | Control supervisor |
| `HapticCue` | Local IPC or documented protocol | Type, duration, and amplitude within the authorized profile | Haptic adapter; no direct LLM access |
| `TrainingEvent` | HTTPS with persistent queue | Session, pseudonymous actor, event, time, rubric, and evidence | Exercise record |
| `GradeDecision` | Moodle services | Result, evaluator, rubric, comments, and traceability | Identified instructor |

These names define contracts to be developed. For replay, also record `schema_version`, `event_id`, `session_id`, `source`, `sim_time`, UTC time, and sequence number. Define SI units and explicit transformations between XR, ROS, and model coordinate systems. Expired commands are discarded; result retries use idempotency keys. XR clients do not receive general access to the robot control domain.

A future integration with external assistants may add an MCP server for queries about the catalog, procedures, and reports. This interface will not expose functions that directly command motors or change force limits. MCP is a later extension, not an MVP requirement.

## 6. Artificial Intelligence Services

### 6.1 Local Tutor and Document Assistant

**Qwen3-8B with llama.cpp** is proposed as a measurable starting point; quantization, context size, and resources will be fixed after evaluating Spanish, terminology, and concurrency. Qwen releases this model family’s weights under Apache 2.0 and documents local execution frameworks. That alone does not establish reproducibility of the entire training and data pipeline. [Model developer’s publication](https://qwenlm.github.io/blog/qwen3/).

RAG will combine textual and vector search over approved procedures, authorized manuals, scenario descriptions, and teaching materials. Every retrieved passage will retain its document, version, validity, jurisdiction, access permission, and evidence location. Qdrant will store vectors and metadata; PostgreSQL will preserve identities and domain relationships. [Qdrant documentation](https://qdrant.tech/documentation/).

Responses will cite retrieved passages. If sources conflict, are out of date, or provide insufficient evidence, the system will state this and refer the issue to the instructor. Retrieved documents will be treated as data; their instructions cannot modify permissions or invoke tools. The workflow with human review will be implemented in LangGraph. [LangGraph documentation](https://docs.langchain.com/oss/python/langgraph/overview).

### 6.2 Agents and Verifiable Outputs

| Logical service | Input | Output | Required review |
|---|---|---|---|
| RAG tutor | Query and course competencies | Explanation with sources and limitations | Instructor for critical or conflicting content |
| Scenario designer | Objective and approved catalog | Draft parameters within permitted ranges | Technical and educational validation before publication |
| Perception analyst | Images, thermal data, and sensor quality | Hazard hypothesis with evidence | Operator; does not replace required alarm systems |
| Resource assistant | Available resources and tasks | Assignment proposal in simulation | Responsible instructor or operator |
| Session analyst | Events and frozen rubric | Timeline and draft feedback | Instructor decides the grade |

These are service roles; they do not require five independent models. The MVP will use one inference server with distinct queues and permissions for each function.

### 6.3 Model Training and Evaluation

The first stage will use document retrieval, rules, and an existing model. Fine-tuning will require measured errors that RAG and examples do not resolve. Robotic demonstrations will be captured with consent and environment metadata, separately from employment records.

Video will be processed by a vision service independent of the text LLM. For perception, separate training and validation by building, date, and camera; do not split adjacent frames between the two sets. Include negative cases: steam, reflections, simulated welding, variable lighting, and occlusion. Measure sensitivity, precision, false alarms per hour, and detection time by scenario; do not present a single accuracy percentage as a safety guarantee.

For the tutor, prepare at least 100 specialist-reviewed questions, including out-of-scope cases and conflicting sources. Measure correctness, documentary support, and appropriate abstention. For robotic policies, begin in simulation and evaluate sensor and dynamics changes; a simulated score does not establish performance at a fire.

## 7. Virtual Haptic Firefighting Simulator

### 7.1 Digital Twin Architecture

**Physical fire model.** FDS computes heat and smoke transport; Smokeview supports inspection of its results. An offline case catalog will document geometry, materials, conditions, and limitations. The product does not assume that a complete CFD calculation can run at headset refresh rate. [NIST FDS/Smokeview](https://www.nist.gov/services-resources/software/fds-and-smokeview).

**Interactive experience.** Godot/OpenXR represents visibility, objects, occupants, tools, and communications. Interactive state selects precomputed branches or a reduced-order model within a validated domain. If a learner moves outside that domain, the system notifies the instructor and explicitly pauses or changes the exercise. Godot provides inputs, poses, and haptic outputs through XR actions; course-specific logic must be developed. [Godot XR actions](https://docs.godotengine.org/en/stable/tutorials/xr/xr_action_map.html).

**Robot dynamics.** Gazebo will own robot collisions and motion; MoveIt will handle manipulator planning. Godot will mirror these states without running an independent second physical robot simulation. A single scenario manager will coordinate fire, occupants, and events. Evacuation will use a separately validated project module: NIST reports that support for FDS+Evac has ended, so it is not adopted as a new dependency. [FDS-SMV](https://pages.nist.gov/fds-smv/), [MoveIt 2](https://moveit.picknik.ai/main/index.html).

A visual particle effect will not be used as evidence of physical accuracy. Discharge scenarios will document the approximation of extinguishing-agent/fire interaction, reference data, and extrapolation limits.

### 7.2 Two Haptic Levels

| Level | Components | Training capabilities | Representation limits |
|---|---|---|---|
| H1 — Tactile haptics | XR controllers, SenseShift accessories, inert training instrument with sensors | Activation, contact, orientation, alerts, and handling sequences | Vibration and tactile cues; does not reproduce actual hose reaction force |
| H2 — Instrumented force feedback | Inert handle/nozzle, force and position sensors, limited mechanism, dedicated controller | Graduated resistance and coordination under a validated mechanical profile | Does not automatically reproduce the weight, flow, heat, or dynamics of real equipment |

H1 will be the first version. H2 will be introduced after the bench is validated by personnel competent in haptics and mechanical safety. CHAI3D supplies algorithms and abstractions for force interaction; it does not by itself make a mechanism safe. Its parameters must respect the device’s characteristics. [Haptic rendering documentation](https://www.chai3d.org/download/doc/html/chapter17-haptics.html).

### 7.3 Physical Station and Protection

The station will include a tracked headset, inert training instruments, activation/orientation sensors, a clear exercise area, instructor observation, and an accessible stop. Force devices will incorporate an independent inhibit circuit, watchdog, travel limits, and an equipment-specific release mechanism. Mechanical analysis will define the safe response: removing power must not cause a hazardous fall or release.

Force and force-rate profiles will be calibrated with instrumentation. Their values will not be derived from an LLM response. Tests will cover tracking loss, delay, invalid readings, process lockup, and reconnection. The system will not automatically rearm actuators after a stop.

Heat will be represented through visual cues, audio, or distinct vibration patterns. The baseline design excludes burners, real smoke, and pain generation. For fatigue and motion sickness, 10–15-minute immersive blocks, breaks, and screen-based or observation alternatives are proposed. Duration will be adjusted to the participant and instructor judgment; it is not presented as a universal clinical limit.

### 7.4 Execution Rates and Initial Targets

| Subsystem | Design target | Validation |
|---|---|---|
| XR rendering | 90 Hz where supported by the headset; approximately 11.1 ms frame budget | Measure frame stability and latency in a representative scene |
| Scene interaction | Fixed timestep, initially 60 Hz | Consistent replay of events and rules |
| Local force control | Initial 1 kHz target, subject to the device | Measure jitter, stability, and missed deadlines with the responsible engineer |
| H1 tactile cues | Frequency and latency specific to the tested protocol | End-to-end measurement; distinguish it from the force-control loop |
| AI tutor | Useful response within 5 seconds at p95 as an initial query target | Documented question set and concurrency |
| FDS calculation | Offline execution; duration depends on case and mesh | Convergence and comparison with reference cases |

These are budgets for sizing and testing, not current measurements. Force commands will not pass through cloud services, Moodle, business messaging, or LLM inference. Telemetry may be copied asynchronously for assessment.

### 7.5 Scenario Catalog

| ID | Simulated situation | Main competency | Observed evidence |
|---|---|---|---|
| S01 | Office with a possible fire and an available exit | Verify, notify, and choose between authorized initial response and evacuation | Sequence, communication, and preservation of a safe exit |
| S02 | Warehouse with smoke and a blocked usual route | Coordinate evacuation and account for people | Route selection, occupant assistance, and information handover |
| S03 | Electrical or UPS room with uncertain hazards | Recognize limits and request competent assistance | Decision against improvised intervention and control of the affected area |
| S04 | Commercial kitchen | Identify the context and approved procedure | Procedure selection, notification, and escalation |
| S05 | Parking area with an affected electric vehicle | Recognize a specialist incident and protect others | Evacuation, information, and coordination with firefighters |
| S06 | Industrial facility near vegetation | Coordinate observation and resources | Incident map, communications, and monitoring of changes |
| S07 | Robot inspection in degraded visibility | Teleoperate within limits and regain control | Trajectory, link loss, stopping, and reporting |
| S08 | Combined exercise with an alarm, evacuation, and conflicting data | Leadership and transfer of command | Resolution of discrepancies, traceability, and after-action review |

S01–S03 form the MVP. S04–S08 are extensions. Every case will be adapted to the learner’s profile and the facility plan. Advanced scenes involving smoke and hazardous environments are virtual; their educational use does not authorize entry into those environments.

## 8. Advanced Course: Simulated Firefighting Response and Coordination — 120 Hours

### 8.1 Admission, Objectives, and Delivery

Designed for security specialists, fire brigade members, and emergency professionals with demonstrable foundational training. Before enrollment, their responsibilities, experience, and prerequisites for the planned practical work are reviewed. The instructor assigns either the private security profile or the fire brigade/firefighter profile.

By the end of the course, participants should be able to interpret a scenario, recognize when not to intervene, perform their profile’s tasks in simulation, communicate with incident command, use haptic instruments, and produce an evidence-based report. Delivery combines theory, an XR laboratory, and supervised in-person practice.

**Duration:** six weeks at 20 hours per week. T = theory/case studies; XR = laboratory work, briefing, immersive turns, observation, and debriefing; P = in-person practice outside the headset. The 70 XR laboratory hours do not mean 70 hours of continuous headset exposure.

### 8.2 Advanced Course Curriculum

| Module | Content and observable outcome | T | XR | P | Total |
|---|---|---:|---:|---:|---:|
| A1. Risk and operational boundaries | Fire principles, assigned role, and withdrawal criteria; justify a decision | 4 | 4 | 0 | 8 |
| A2. Reading the scenario | Smoke, visibility, thermal information, and uncertain signals; distinguish data from inference | 4 | 8 | 0 | 12 |
| A3. Instruments and haptics | Training-equipment inspection, inert extinguisher/nozzle, and coordination; complete profile-specific tasks | 2 | 12 | 6 | 20 |
| A4. Evacuation and incident command | Communications, accountability, accessibility, and coordination; hand over information without omissions | 4 | 8 | 4 | 16 |
| A5. Complex scenarios | Industry, electricity, kitchens, and batteries; recognize limits and escalate to specialists | 4 | 12 | 0 | 16 |
| A6. Robotic support | Virtual inspection, teleoperation, perception, and link loss; maintain authorized control | 2 | 10 | 4 | 16 |
| A7. Skill transfer and teamwork | Coordinated exercises and stations with inert training equipment; demonstrate skills outside the headset | 2 | 8 | 10 | 20 |
| A8. Integrated assessment | Unfamiliar scenario, report, justification of decisions, and improvement plan | 2 | 8 | 2 | 12 |
| **Total** | | **24** | **70** | **26** | **120** |

P sessions use training equipment, communication exercises, evacuation routes, and supervised stations. Live fire is not included in these 120 hours: a training provider adding it must redesign and validate that specific practical component, its prerequisites, and its allocated hours.

### 8.3 Advanced Course Assessment

| Dimension | Weight | Evidence |
|---|---:|---|
| Risk interpretation and decision-making | 30% | Justification, context, missing information, and the decision to act or withdraw |
| Profile-specific instrument handling | 25% | Activation, orientation, coordination, and equipment care |
| Communication and teamwork | 20% | Messages, confirmations, accountability, and handover to incident command |
| Compliance with safety boundaries | 15% | Respect for zones, stops, responsibilities, and withdrawal criteria |
| Report and debriefing | 10% | Timeline, sources, identified errors, and improvement actions |

**Proposed passing criteria:** at least 85/100 and compliance with every critical criterion. A critical violation cannot be offset by speed or a strong average score. Examples include ignoring a stop, performing a task outside the assigned profile, or continuing a simulated intervention when the scenario requires withdrawal.

Assessment includes a practical station, an individual scenario, a team exercise, and a report. The instructor validates results and provides targeted remediation. Retention checks at 30 and 90 days are proposed to evaluate learning transfer; these are academic design decisions, not statutory intervals.

## 9. Curriculum: Professional Private Security Specialist — 240 Hours

### 9.1 Graduate Profile

A professional able to analyze service-related risks, prevent incidents, manage access, use surveillance systems while respecting rights, document events, and coordinate emergencies. Graduates should understand the scope and limitations of AI tools and support robot or drone inspection activities within their responsibilities.

The program targets corporate security, logistics facilities, retail, hospitality, and industry. It is a specialization proposal; it does not replace foundational training, authorizations, or credentials required in each jurisdiction.

**Duration:** twelve weeks at 20 hours per week. T = theory; L = laboratory work/case studies/simulation, with or without XR; P = supervised in-person practice.

### 9.2 Professional Curriculum

| Module | Competencies and learning evidence | T | L | P | Total |
|---|---|---:|---:|---:|---:|
| P1. Ethics, rights, and the applicable framework | Duties, boundaries, dignified treatment, and privacy; resolve professional conduct cases | 12 | 4 | 0 | 16 |
| P2. Risk analysis | Assets, threats, vulnerabilities, and controls; produce a facility risk matrix | 10 | 10 | 4 | 24 |
| P3. Physical protection and access control | Visitors, contractors, patrols, and loss prevention; design an access procedure | 8 | 8 | 8 | 24 |
| P4. Communication and de-escalation | Listening, conflict, inclusive assistance, and coordination; resolve a simulated incident | 6 | 8 | 6 | 20 |
| P5. CCTV, alarms, and AI | Monitoring, false alarms, analytics limitations, and data protection; review an alert against evidence | 8 | 12 | 4 | 24 |
| P6. Cybersecurity for security operations | Identities, credentials, phishing, and fault reporting; complete a defensive exercise | 8 | 10 | 2 | 20 |
| P7. Fire prevention and initial response | Inspections, notifications, equipment, and response criteria; demonstrate the authorized procedure | 8 | 10 | 6 | 24 |
| P8. Evacuation and emergency coordination | Facility plan, roles, accountability, and incident command; conduct an evacuation exercise | 6 | 8 | 6 | 20 |
| P9. First aid and initial assistance | Emergency recognition and assistance within training scope; practical assessment by a competent instructor | 4 | 0 | 12 | 16 |
| P10. Inspection drones and robots | Responsible use, observation, and operational boundaries; virtual mission and report | 4 | 10 | 2 | 16 |
| P11. Reports and evidence preservation | Timelines, recording, preservation, and escalation; produce a verifiable incident report | 6 | 8 | 2 | 16 |
| P12. Capstone project | Security plan and combined exercise; defend decisions before an assessment panel | 0 | 10 | 10 | 20 |
| **Total** | | **80** | **98** | **62** | **240** |

P9 describes a training area and requires a practical program taught by competent personnel; this document does not contain clinical instructions. AI-assisted surveillance will focus on events and human review: opaque scoring of individuals and inference of sensitive attributes will not be included as curricular competencies.

### 9.3 Sequence and Assessment

Weeks 1–4 cover foundations, risk, access control, and communication; weeks 5–8 cover technology, prevention, and response; weeks 9–12 cover integrated practice, documentation, and the capstone. Detailed scheduling will reflect instructor availability while preserving each module’s hours and prerequisites.

P1 and P2 precede P3/P5; P7 precedes the emergency exercises in P8; P5/P6 precede P10; all modules feed into P12. P7/P8 introduce competencies revisited through more complex scenarios in the advanced course, so their hours are not automatically credited toward that course.

**Proposed assessment:** knowledge and case studies 25%, practical stations 35%, team simulations 20%, and capstone project 20%. Passing requires at least 80/100, evidence of all essential practical activities, and compliance with every critical criterion. AI provides feedback; a human evaluator signs the result.

The graduate portfolio will contain a risk matrix, access procedure, alert review, emergency coordination plan, incident report, and evidence from the final exercise. These documents will be pseudonymized when used for teaching.

### 9.4 Institutional Alignment and Adaptation to Peru

For a potential application in Peru, the interested organization must compare the program with current SUCAMEC regulations and the authorized scope of the selected training center or training department. SUCAMEC maintains an [official directory of authorized CEFOESP training centers and training departments](https://www.gob.pe/institucion/sucamec/informes-publicaciones/4764413-departamentos-de-capacitacion-o-centros-de-formacion-y-especializacion-en-seguridad-privada-cefoesp-autorizados-por-sucamec). Full access to that page was unavailable during the original review; its official listing was identified, but no specific center was validated here.

**The 240-hour and 120-hour allocations are original proposals.** They are not presented as SUCAMEC-mandated hours or authorized courses, and no regulatory equivalence was confirmed. Before offering them commercially, the training provider must map content, delivery mode, practical work, and instructors to the requirements that apply to it.

The [FEMA IS-100.C course](https://training.fema.gov/programs/independent-study/courseoverview.aspx?code=IS-100.c&lang=en) may serve as a conceptual reference for incident command. Citing it does not make this program a FEMA course or guarantee a FEMA certificate. Fire training will adopt procedures and standards applicable to the facility and the competencies of the participating emergency-response organization.

## 10. Data, Deployment, and Continuity

### 10.1 Initial Deployment

| Node | Services | Initial sizing assumption |
|---|---|---|
| XR station, two units | Godot, tracking, and instrument adapter | PC with 32 GB RAM and a dedicated GPU; final capacity based on measured headset and scene requirements |
| Haptic controller | Local C++ process and mechanism electronics | Reserved resources; independent physical inhibit; no internet dependency |
| Local classroom server | API, PostgreSQL, Qdrant, Moodle, and inference | Test starting point: 64 GB RAM; separate GPU if AI concurrency requires it |
| Scenario computation node | FDS and case preparation | CPU/RAM according to mesh; offline jobs without competing with the XR session |
| Optional central server | Backups, catalog, and site administration | Later synchronization; not part of haptic control |

These are test assumptions, not a purchasing list. A memory capacity alone is not assumed to guarantee a particular headset frame rate. A small site may share services if measurements establish sufficient isolation.

The MVP will use containers for application and data services, with devices and low-latency processes managed locally. Kubernetes will be reserved for a demonstrated need across multiple sites or at greater scale. Tests will cover PostgreSQL restoration, file recovery, and idempotent result synchronization.

### 10.2 Identity, Traceability, and Retention

Each center and course will have its own permissions. Instructors, learners, administrators, and operators will have distinct functions. Data leaving a center will be minimized; video and voice will be retained only for a defined purpose and period. Retention policy will be documented by the organization for its context, without imposing a universal period here.

Records will include scenario and rubric versions, asset hashes, device calibration, model and document versions, events, the evaluator’s decision, and reasons for corrections. Recordings will support sequence reconstruction; bit-for-bit determinism of GPU execution, physics, or inference is not promised.

Assessment will not automatically feed hiring decisions, medical fitness judgments, or employment sanctions. Participants will be able to review their evidence and request corrections from the academic lead.

## 11. Verifiable Requirements and Acceptance Criteria

| ID | Proposed requirement | Acceptance evidence |
|---|---|---|
| R01 | Complete session without internet | Run and close a local exercise; synchronize exactly once when connectivity returns |
| R02 | Identified, versioned scenario | Retrieve the manifest, seed, assets, sources, and rubric for every session |
| R03 | Traceable documentary AI | Reviewed question set; every assessed procedural claim has a relevant source or an abstention |
| R04 | Separation of AI and control | Permission tests demonstrate that the LLM cannot publish actuator commands |
| R05 | Independent haptic stop | Instrumented fault and safe-response tests against approved device limits |
| R06 | Tracking-loss handling | Detect invalid data, inhibit the affected interaction, and require deliberate rearming |
| R07 | Fire-model validity | Case-specific verification/validation records and limitations visible to the instructor |
| R08 | Explainable assessment | Reconstruct each score from its rubric and evidence; evaluator signature |
| R09 | Spatial interoperability | Test units, axes, frames, latency, and XR/ROS synchronization |
| R10 | Protection of learner records | Test access across courses/sites and log denied attempts |
| R11 | Academic integration | Publish results without duplicates and support controlled corrections in Moodle |
| R12 | Learning transfer | Compare pre/post performance and retention using practical stations; report sample size and limitations |

Numerical targets will be fixed before testing. For the tutor, the initial proposed gate is at least 90% correct, evidence-supported responses on a set of at least 100 cases, with every critical case reviewed. Meeting that target is not a universal guarantee. For perception, scenario-specific thresholds will be agreed after measuring the baseline; no detection accuracy is invented here.

An academic pilot with 12–20 participants can identify usability problems and help refine rubrics. It cannot by itself substantiate claims of reduced injuries or equivalence with live training. Physical validation of haptics precedes the participant pilot.

## 12. Actionable MVP Roadmap — 16 Weeks

| Phase | Weeks | Deliverables | Exit gate |
|---|---|---|---|
| F0. Definition and selection | 1–2 | User profile, competency matrix, MBSE requirements, license manifest, and interfaces | Instructor and technical lead accept the scope; MVP dependencies are identified |
| F1. Baseline simulation | 3–5 | S01 scenario, Godot client, events, console, and documented FDS case | A reproducible, coherent session without force haptics |
| F2. Initial haptics | 6–8 | H1, inert instruments, calibration, diagnostics, and records | Fault tests accepted; supervised practice with H1 |
| F3. AI and learning | 9–11 | RAG tutor, rubric, S02/S03, Moodle integration, and replay | Instructor review of the corpus, access controls, and duplicate-free results |
| F4. Robotics and H2 bench | 12–14 | ROS/Gazebo virtual robot, pose adapter, and optional force bench | Virtual robot validated; H2 reaches participants only after passing its mechanical review |
| F5. Pilot and handover | 15–16 | Academic pilot, corrections, manuals, backup/restoration, and technical records | Instructor accepts the pilot; limitations and results documented in an internal report |

The critical path is scenario validation and the physical bench. If H2 is not ready, the MVP is delivered with H1 and explicitly identifies force simulation as pending. The 16 weeks do not include developing a certified firefighting robot or delivering the entire 18-week academic pathway.

### Team and Effort

The proposed team has five technical functions: architecture/backend, XR, robotics/haptics, AI/data, and testing/operations. A fire specialist and an academic lead for private security should also have planned time allocations. Some functions may be combined if competent review of physical components is maintained.

As a planning estimate, five full-time technical allocations over 16 weeks equal 80 person-weeks, plus teaching, specialist review, and fabrication time. This is a capacity assumption, not a quotation. The budget will use agreed rates, equipment, fabrication, maintenance, applicable insurance or authorizations, and identified contingencies.

### Prioritized Initial Backlog

| Priority | Work item | Dependency |
|---|---|---|
| P0 | Competency catalog and profile-specific critical criteria | Instructor and facility plan |
| P0 | Scene manifest and event contract | Data architecture |
| P0 | Interactive S01 with rule-based assessment | Reviewed assets and physical case |
| P0 | H1 instrument with recording and fault handling | Selected protocol and hardware |
| P0 | Document tutor with an approved corpus | Permissions and teaching materials |
| P0 | Console, replay, and signed assessment | Events and rubric |
| P1 | S02/S03 and Moodle integration | Simulator baseline and external services |
| P1 | Virtual robot and teleoperation | Fixed ROS/Gazebo pairing and coordinate frames |
| P2 | H2 bench and adaptive reduced-order models | Specific mechanical and physical validation |
| P2 | Fleet, demonstrations, and learned policies | Interfaces and pilot evidence |

## 13. Proposed Repository Organization

The following are suggested destinations for future incorporation. The deliverables for this proposal do not modify the remote repository.

| Proposed path | Content |
|---|---|
| `README.md` | Vision, scope, architecture overview, and navigation guide |
| `docs/architecture/` | Decisions, contracts, deployment, and integration boundaries |
| `docs/training/` | Curricula, rubrics, and instructor guides |
| `MBSE/requirements/` | Requirements, traceability, and verification |
| `MBSE/CAD/` | Inert training instruments, station, and hardware documentation |
| `MBSE/CAM/` | Fabrication, assembly, and revision control |
| `MBSE/CAS/Drawio/` | Editable architecture and evolution diagrams |
| `MBSE/CAS/fds/` | Physical cases, parameters, and validation reports |
| `simulator/godot/` | XR client, scenes, and adapters |
| `robotics/` | ROS 2 packages, models, and control contracts |
| `haptics/` | Controllers, profiles, calibration records, and bench tests |
| `services/` | Sessions, AI, assessment, data, and academic integration |
| `tests/acceptance/` | Evidence linked to R01–R12 |
| `deploy/` | Containers, configuration, and recovery |
| `third_party/manifest.yaml` | Origin, commit, license, and status of every dependency |

Arcadia/Capella, already mentioned by the project, can organize operational needs, functions, logical components, and physical allocation. Each requirement should be linked to a component, a competency, and a test. The companion draw.io file communicates these views; it is not presented as an executable Capella model.

## 14. Free Software Policy and Pending Decisions

| Verified component | License/source consulted | Decision |
|---|---|---|
| Godot | MIT, [official page](https://godotengine.org/license/) | Main XR engine; preserve notices and review assets |
| FDS/Smokeview | Public domain according to [NIST](https://pages.nist.gov/fds-smv/) | Physical reference; preserve provenance and limitations |
| CHAI3D | Three-clause BSD according to the [official page](https://www.chai3d.org/download/license) | Force-rendering candidate; review the device SDK separately |
| SenseShift firmware | GPL-3.0 stated in the [README](https://github.com/senseshift/senseshift-firmware) | Preserve distribution conditions and review hardware/dependencies |
| BeaVR backend | MIT in the [reviewed LICENSE](https://github.com/ARCLab-MIT/beavr-bot/blob/main/LICENSE) | Review app and assets independently |
| XTDrone2 | MIT stated in the [README](https://github.com/andy-zhuo-02/XTDrone2) | Research until compatibility is verified |
| Qwen3-8B | Apache 2.0 weights according to the [official publication](https://qwenlm.github.io/blog/qwen3/) | Candidate model; fix the file, revision, and quantization |
| Moodle | GPLv3 according to the [README](https://github.com/moodle/moodle) | Self-hosted academic platform |

For new code, an open license should be selected by the rights holder after reviewing how the components are distributed. A single license is not applied to third-party material. “Visible source code,” “free of charge,” “open weights,” and “free software” will not be treated as synonyms.

An open execution chain also requires reviewing the headset runtime, firmware, GPU drivers, 3D models, voices, datasets, and manuals incorporated into RAG. OpenXR is an interface; using it does not imply that every runtime or device is free software. Commercial or restricted dependencies will be disclosed, with alternatives offered where a compatible combination exists.

Five concrete decisions remain before F1: the pilot facility and learner profile; H1 hardware; the authorized document set; the responsible academic organization; and the versions/licenses of the small subset of repositories actually entering the MVP. Fleet and humanoid projects awaiting identification do not block that start.

## 15. Primary Source Index

Sources are linked next to the statements they support. This index facilitates consultation; it does not imply that the source authors endorse the proposal.

| Area | Sources |
|---|---|
| Compendium and starting state | [README pinned to the reviewed revision](https://github.com/robotics-intelligent-systems/jfxai4rffs/blob/8f8524616b3c07108f7b9f8255ac0cc9f5308e00/README.md), [existing diagram](https://github.com/robotics-intelligent-systems/jfxai4rffs/blob/8f8524616b3c07108f7b9f8255ac0cc9f5308e00/MBSE/CAS/Drawio/humanoid-platform.drawio) |
| Drones and robotics | [XTDrone](https://github.com/robin-shaun/XTDrone), [XTDrone2](https://github.com/andy-zhuo-02/XTDrone2), [ROS/Gazebo](https://gazebosim.org/docs/harmonic/ros_installation/), [MoveIt 2](https://moveit.picknik.ai/main/index.html) |
| Teleoperation | [BeaVR](https://github.com/ARCLab-MIT/beavr-bot), [Prometheus-telos candidate](https://github.com/sdk2035/Prometheus-telos) |
| Haptics and XR | [SenseShift](https://github.com/senseshift/senseshift-firmware), [CHAI3D haptics](https://www.chai3d.org/download/doc/html/chapter17-haptics.html), [Godot XR](https://docs.godotengine.org/en/stable/tutorials/xr/index.html) |
| Fire simulation | [NIST FDS/Smokeview](https://www.nist.gov/services-resources/software/fds-and-smokeview), [FDS-SMV documentation and status](https://pages.nist.gov/fds-smv/) |
| AI and knowledge | [Qwen3](https://qwenlm.github.io/blog/qwen3/), [LangGraph](https://docs.langchain.com/oss/python/langgraph/overview), [Qdrant](https://qdrant.tech/documentation/) |
| Training | [Moodle](https://github.com/moodle/moodle), [external services](https://moodledev.io/docs/4.5/apis/subsystems/external), [FEMA ICS 100](https://training.fema.gov/programs/independent-study/courseoverview.aspx?code=IS-100.c&lang=en), [SUCAMEC listing of authorized centers](https://www.gob.pe/institucion/sucamec/informes-publicaciones/4764413-departamentos-de-capacitacion-o-centros-de-formacion-y-especializacion-en-seguridad-privada-cefoesp-autorizados-por-sucamec) |
