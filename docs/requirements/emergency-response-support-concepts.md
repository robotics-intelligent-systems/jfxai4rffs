# Emergency-response support concepts

Proposed baseline · 13 October 2026. Both concepts are owned by **jfxai4rffs**. They extend research and training for emergency-response logistics; they are not implemented firefighting vehicles. Neither artwork establishes a suppression payload, autonomous operation or certified protection.

| Concept | Migration source | Artwork | Editable requirements |
| --- | --- | --- | --- |
| OpenTwin modular protected truck | jfxai4mass | [Concept](../../MBSE/CAD/opentwin-modular-armor-truck-digital-twin-concept.jpg) | [Draw.io](../../MBSE/CAS/Drawio/opentwin-modular-armor-truck-high-level-requirements.drawio) |
| Hydrogen-hybrid amphibious transport | jfxmbdss | [Concept](../../MBSE/CAD/hydrogen-hybrid-amphibious-transport-concept.jpg) | [Draw.io](../../MBSE/CAS/Drawio/hydrogen-hybrid-amphibious-transport-high-level-requirements.drawio) |

The truck retains ARM-01–06 and the transferred COM-01–09 baseline. The aircraft adds HAT-01–08. COM IDs remain scoped to this transferred baseline; they are not replacements for R01–R12 of the training platform. The [machine-readable register](../../MBSE/requirements/concept-requirements.json) is authoritative for the statements below.

The aircraft preserves gaseous hydrogen, fuel cells and a buffer battery from the source specification; liquid hydrogen is not assumed. The truck propulsion and protective threat basis remain open choices. Both twins connect through versioned asset, configuration, mission and state records; instructors retain command authority. Physical vehicle development is outside the existing 16-week simulator MVP.

| ID | Proposed obligation | Allocation / responsible role | Acceptance |
| --- | --- | --- | --- |
| COM-01 — Operational envelope | The system shall define approved missions, actors, operating modes and environmental limits for each configuration. | Mission / environment / Systems engineering | Review mission scenarios, boundaries and measurable envelope; no unresolved operating limit at release. |
| COM-02 — Module interoperability | The system shall provide versioned mechanical, power and data interface contracts for interchangeable modules. | Interface control / Integration | Demonstrate module substitution against interface contracts, including incompatible-module rejection. |
| COM-03 — Local fault response | The system shall execute a defined local safe or degraded response to each identified critical fault. | Safety control / Safety / controls | Inject critical faults and connectivity loss; measured response meets the approved fault-response matrix. |
| COM-04 — Energy provision | The system shall supply mission and essential safety loads within the approved energy budget. | Energy / Energy engineering | Analyze and test worst-case coincident loads and reserve against the configured mission profile. |
| COM-05 — Twin identity and provenance | The digital twin shall associate each state record with asset identity, configuration, timestamp, source and validity. | OpenTwin / Data / twin | Replay records and reject or flag stale, missing and mismatched states according to the data contract. |
| COM-06 — Model verification | The project shall maintain versioned executable models and reproducible scenarios for each claimed system capability. | Simulation / Simulation / MBSE | Reproduce model runs and correlate selected outputs with bench or prototype data within approved tolerances. |
| COM-07 — Maintenance access | The system shall provide documented inspection and replacement procedures for serviceable modules. | Lifecycle / Maintenance | Demonstrate inspection and replacement using approved tools, isolation steps and service limits. |
| COM-08 — Command authorization | The system shall accept control commands only from authenticated and authorized sources. | Control gateway / Security | Test unauthorized, replayed and malformed commands; verify rejection and event recording. |
| COM-09 — Configuration traceability | The project shall trace each requirement to its allocated element, verification result and released configuration. | Configuration / MBSE / quality | Audit complete requirement-to-evidence links and disposition of failures before baseline release. |

| ID | Proposed obligation | Allocation / responsible role | Acceptance |
| --- | --- | --- | --- |
| ARM-01 — Ground mobility | The vehicle shall provide propulsion, steering and braking throughout its approved terrain and loading envelope. | Chassis / mobility / Vehicle engineering | Analyze and test handling, braking and grade performance for the worst approved payload and panel configuration. |
| ARM-02 — Panel interchange | The vehicle shall permit replacement of designated protective panels through documented mounting interfaces. | Panels / mounts / Mechanical integration | Demonstrate panel exchange, correct installation and retention under approved structural loads. |
| ARM-03 — Protection objective | The project shall specify a threat and protection acceptance basis for each claimed protective configuration. | Cabin / protective assembly / Protection / safety | Approve threat cases and assembly-level evaluation plan; close performance evidence before making protection claims. |
| ARM-04 — Occupant egress | The vehicle shall provide occupant emergency egress in each approved occupied configuration. | Cabin / access / Human factors | Demonstrate access and emergency exit with representative occupants and equipment under defined fault cases. |
| ARM-05 — Payload retention | The vehicle shall retain cargo and installed modules under the approved service and emergency load cases. | Cargo / chassis / Structures | Analyze and test mounts with representative payloads and configuration-specific mass and center of gravity. |
| ARM-06 — Condition monitoring | The system shall report the health of monitored vehicle and protective modules with their configuration identity. | Sensors / twin / Sensors / twin | Introduce monitored faults and verify detection, operator indication and twin association. |

| ID | Proposed obligation | Allocation / responsible role | Acceptance |
| --- | --- | --- | --- |
| HAT-01 — Mission and loading envelope | The aircraft concept shall define cargo, crew, mass/CG, ground, flight and water operating envelopes. | Mission / configuration / Systems engineering / Mission / configuration | Review configuration-specific payload, mass/CG and environmental limits before model verification. |
| HAT-02 — Airframe and cargo retention | The airframe, floats and cargo restraints shall withstand the selected operational and emergency load cases. | Airframe / cargo / Systems engineering / Airframe / cargo | Analyze structure, float attachments and cargo retention against approved load cases. |
| HAT-03 — Flight dynamics | The configured aircraft shall meet defined aerodynamic, propulsion and handling targets. | Flight model / Systems engineering / Flight model | Run reproducible aerodynamic and flight-dynamics cases with fixed geometry and mass/CG; correlate before physical claims. |
| HAT-04 — Flotation and water transition | The twin-float configuration shall meet approved buoyancy, stability and water-transition criteria. | Floats / hydrodynamics / Systems engineering / Floats / hydrodynamics | Analyze displacement, trim, stability and hydrodynamic loads for each loading case; evaluate transition guards. |
| HAT-05 — Gaseous hydrogen isolation | The energy configuration shall model gaseous hydrogen storage, leak detection, ventilation and isolation. | Hydrogen / safety / Systems engineering / Hydrogen / safety | Review tank packaging and hazard cases; inject leak and sensor faults into an isolated model and verify local response. |
| HAT-06 — Hybrid energy and cooling | The fuel-cell and buffer-battery system shall supply propulsion and essential loads within its approved power, thermal and reserve budgets. | Energy / thermal / Systems engineering / Energy / thermal | Reproduce mission energy and cooling cases including fuel-cell loss and battery limits. |
| HAT-07 — Supervised mission interfaces | The concept twin shall exchange versioned mission, cargo and state records with the instructor and robotic-training services. | Twin / mission services / Systems engineering / Twin / mission services | Replay authorized, stale and conflicting commands; verify local authority and asset/configuration identity. |
| HAT-08 — Occupant and recovery scenarios | The concept shall define access, emergency egress and recovery scenarios for each occupied configuration. | Human factors / recovery / Systems engineering / Human factors / recovery | Review access and evacuation scenarios against defined occupants, cargo and ground/water conditions. |

## Verification and migration

Select mission envelopes, configurations and numerical acceptance limits before verification. Evidence must include scenario, model/software revision, mass/CG and energy parameters, measured outputs, reviewer and pass/fail disposition. Preserve source provenance; no simulation or prototype results are claimed. No `.sysml`, `.sysml2` or executable SysML model was found in the three project trees. The existing AI/haptic and humanoid Draw.io views remain training/architecture references.
