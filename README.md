# Marussa Metocharaki
Independent Researcher in Robot Ethics & Supervisory Safety · Greece

ORCID: [0009-0009-4100-9881](https://orcid.org/0009-0009-4100-9881) · Zenodo DOI: [10.5281/zenodo.23559804](https://doi.org/10.5281/zenodo.23559804)

I design and maintain **QERRA-v2 Classical**: an auditable, three-layer supervisory execution guard for autonomous robots and mobile manipulators (ROS 2 & Behavior Trees).

---

### Engineering Principle: Authority Separation
A mobile robot should never rely solely on an unpredictable neural network to make physical safety decisions.

I build software that enforces strict authority separation between untrusted AI proposals and the actuators:
- **The high-level AI is an untrusted proposer:** It may be slow, wrong, or dead.
- **The supervisory gate is the sole path to the wheels:** The default is fail-closed stop.

---

### The Three-Layer Architecture

1. **Layer 1 — Deterministic Safety & Assistive Reflex:**
   - **Layer 1A — Supervisory Gate (`gate/` v0.3 | AGPL-3.0-only):** Pure Python standard-library integer state machine holding exclusive motor actuator authority. Enforces dynamic stopping envelopes ($d_{stop} = \lceil v^2 / (2a) \rceil + margin$), a 150 ms proposer freshness watchdog, and latched fail-closed recovery requiring a continuous 1.0 s clear dwell and operator reset. Logs every tick to a rolling SHA-256 flight recorder with bit-for-bit offline replay audit capabilities.
   - **Layer 1B — Physical Reflex (QERRA-HSR v0.1 | Apache-2.0):** Pure Python threshold logic under ISO 13482 principles. Evaluates distress telemetry, human isolation, and hazard proximity to clamp commanded velocity in under 1 ms, with asymmetric dwell stabilization and Property HSR-5 human-in-the-loop recovery directives.

2. **Layer 2 — Moral Filter (SEMEV-12 v1.9.2 | AGPL-3.0):**
   12-dimensional semantic deliberation filter using multi-anchor sentence embeddings, clause-bounded negation guards, and an absolute severe harm veto. Refuses coercive or deceptive commands, illuminates an amber status LED, and commands the robot to physically shake its head "No" in simulation.

3. **Layer 3 — Values Ranker (QERRA-THRIVE v2.0.0 | AGPL-3.0):**
   12-vector values ranker (Suite A Human-Centered, Suite B Ecological) selecting courteous trajectories (such as quiet whisper mode, threshold pauses, and flora boundary protection), with an emergency medical override.

---

### Testing & Simulation Baseline
- **Automated Test Suites:** 127 standard-library unit tests running in automated CI (103 Supervisory Gate, 20 QERRA-HSR, 4 License Boundary Guard) plus 15 SEMEV-12 benchmark regression cases.
- **Simulation Testbed:** Evaluated in Webots (R2025a) physics simulation on a PAL Robotics TIAGo base across 8 distinct scenarios, culminating in Demo 7 (actuator authority separation) and Demo 8 (multi-fault lifecycle with watchdog hardening).
- **Flight Recorder Audit:** Chained flight recorder logs reproduce bit-for-bit against anchored SHA-256 seals through offline deterministic replay.
- **Licensing Architecture:** Layer 1B (`hsr/`) is Apache-2.0 for permissive ROS 2 adoption. The Supervisory Gate (`gate/`) and deliberation layers are AGPL-3.0. Commercial OEM licensing is available for closed-source integrations.

---

### Collaboration & Contact
Open to technical code reviews, evaluation contracts, and collaborative simulation/hardware trials with robotics labs, safety researchers, and system integrators.

- **Repository:** [github.com/marunigno-ship-it/QERRA-v2-classical](https://github.com/marunigno-ship-it/QERRA-v2-classical)
- **Live API Docs:** [qerra-v2-api-classical-qerra-v2-api-classical.hf.space/docs](https://qerra-v2-api-classical-qerra-v2-api-classical.hf.space/docs)
- **Email:** marunigno@gmail.com
