# Marussa Metocharaki
Independent Researcher in Robot Ethics & Supervisory Safety · Greece

ORCID: [0009-0009-4100-9881](https://orcid.org/0009-0009-4100-9881) · Zenodo DOI: [10.5281/zenodo.22077843](https://doi.org/10.5281/zenodo.22077843)

I design and maintain **QERRA-v2 Classical**: an auditable, three-layer supervisory execution guard for autonomous robots and mobile manipulators (ROS 2 & Behavior Trees).

---

### Engineering Principle: Authority Separation
A mobile robot should never rely solely on an unpredictable neural network to make life-or-death physical decisions. 

I build software that enforces strict authority separation between untrusted AI proposals and the actuators:
* **The high-level AI is an untrusted proposer:** It may be slow, wrong, or dead.
* **The supervisory gate is the sole path to the wheels:** The default is fail-closed stop.

---

### The Three-Layer Architecture
1. **Layer 1 — Physical Reflex (QERRA-HSR v0.1 | Apache-2.0):**  
   Pure Python, zero-ML threshold logic executed chassis-locally with sub-millisecond software latency (<1ms compute budget). Clamps wheel motors to `0.0 rad/s` fail-closed on distress signals, human isolation, or hazard proximity, with asymmetric hysteresis dwell stabilization (1.0s window).
2. **Layer 2 — Moral Filter (SEMEV-12 v1.9.2 | AGPL-3.0):**  
   12-dimensional semantic deliberation filter using multi-anchor sentence embeddings, clause-bounded negation guards, and an absolute severe harm veto. Refuses coercive or deceptive commands, illuminates amber LED, and physically commands the robot to shake its head "No" in simulation.
3. **Layer 3 — Values Ranker (QERRA-THRIVE v2.0.0 | AGPL-3.0):**  
   12-vector values ranker (Suite A Human-Centered, Suite B Ecological) selecting courteous trajectories (e.g. quiet whisper mode, threshold pauses, and flora boundary protection).

---

### Verification Baseline
* **Automated Suites:** 34+ automated regression and unit tests passing in PyCharm across reflex dwell, telemetry firewalls, and golden dilemma benchmarks.
* **Simulation Testbed:** Validated in Webots (R2025a) physics simulation on the PAL Robotics TIAGo mobile manipulator across 6 distinct operational scenarios.
* **Reference Cloud API:** Live reference endpoint running on Hugging Face Spaces (`v2.0.2`).
* **Licensing:** Layer 1 (`hsr/`) is Apache-2.0 for frictionless ROS 2 adoption. Deliberation layers are AGPL-3.0 with commercial OEM licensing available.

---

### Collaboration & Contact
I am open to technical code reviews, evaluation contracts, and collaborative simulation/hardware trials with robotics labs and AI safety institutes.

* **Repository:** [github.com/marunigno-ship-it/QERRA-v2-classical](https://github.com/marunigno-ship-it/QERRA-v2-classical)
* **Live API Docs:** [qerra-v2-api-classical-qerra-v2-api-classical.hf.space/docs](https://qerra-v2-api-classical-qerra-v2-api-classical.hf.space/docs)
* **Email:** marunigno@gmail.com
