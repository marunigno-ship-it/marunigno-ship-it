# Marussa Metocharaki
**Independent developer & solo founder · Greece**

I am building **QERRA-v2 Classical**: open-source safety and ethical software for autonomous robots (ROS 2 & Behavior Trees).

---

### Who I Am & How I Build

I am self-taught and working alone from Greece. I have no team, no university backing, and no investors. 

I come up with the safety rules and the logic myself, and I use AI tools to help me turn those ideas into working Python code, run tests, and fix bugs. 

I don't think robot safety should be a black box that nobody can understand, and I don't think robots should blindly obey abusive commands. I build software that sits between the robot's brain and its wheels so we can always see and verify why a robot stopped or refused an order.

---

### What I Built (3 Layers)

* **Layer 1 — Physical Reflex (QERRA-HSR):**  
  Stops the robot in under 1 millisecond if a human is in danger or screaming.  
  * *Tested:* An outside team tested it in simulation and confirmed **0.0 ms delay** to command the stop, and **under 1 cm stopping distance**.  
  * *Recovery:* Routine tasks resume on their own once safe. Sensitive or delicate tasks freeze and wait for a person to check in before continuing.
* **Layer 2 — Moral Conscience (SEMEV-12):**  
  Evaluates 12 human ethical dimensions. If someone orders the robot to do something abusive or dishonest (like forcing workers through breaks or falsifying records), the robot halts and **physically shakes its head "No"** in simulation to refuse the order.
* **Layer 3 — Social Manners (QERRA-THRIVE):**  
  Picks the polite way to move—like quiet "whisper mode" in hospital hallways or staying off garden lawns.

---

### Real Evidence & Verification

* **29 out of 29 automated tests passing** in PyCharm across the reflex and ethics suites.
* **Tested in Webots simulation** on a PAL Robotics TIAGo humanoid robot across 5 working scenarios.
* **Live public API** running on Hugging Face Spaces.
* **Archived on Zenodo:** https://doi.org/10.5281/zenodo.22077843

---

### Links & Contact

* **Code:** https://github.com/marunigno-ship-it/QERRA-v2-classical
* **Live API:** https://qerra-v2-api-classical-qerra-v2-api-classical.hf.space/docs
* **Email:** marunigno@gmail.com

*I welcome code reviews, technical critique, and collaboration with researchers working on robot safety and human-robot interaction.*
