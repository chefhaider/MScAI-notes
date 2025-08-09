Here is a summary of the lecture on surgical robots to help you prepare for your exams, drawing from the source "05_Surgical Robotics_1.pdf":

**Current Surgical Robots:** Current surgical robots like the **Da Vinci system** are primarily **teleoperated** and lack autonomy. These systems offer benefits such as **high precision** and **motion scaling**. However, they typically use **rigid instruments** and have **idle instruments** when not directly controlled.

**Co-operation with Robots:** The future of medical robotics involves **co-operation between surgeons and robots**, where the surgeon leads and supervises based on experience and creativity, while autonomous robots and intelligent instruments provide active support. This envisions a scenario where everyone does what they do best.

**Autonomy Levels for Surgical Robots:** The lecture outlines different **levels of automation** for surgical robots, ranging from Level 0 to Level 5.

- **Level 0 (No Autonomy):** Robot motion is exclusively controlled by the surgeon, with no supports or constraints. **Telemanipulation** is an example.
- **Level 1 (Robot Assistance):** The robot can interact with the surgeon to guide or support task execution, including active constraints and virtual fixtures to enhance visualisation. The **MAKO System by Stryker** for knee/hip replacement is an example, offering patient-specific planning and manual guidance within virtual limits.
- **Level 2 (Task Autonomy):** The robot can accomplish specific surgical tasks based on surgeon specifications, with control switching to the machine for the task duration. **Robot-assisted bone cutting** according to a surgical plan without hand-guidance, as seen in the **Carlos by AOT** system, exemplifies this level.
- **Level 3 (Conditional Autonomy):** The robot has perceptual capabilities to understand the surgical scenario, plan and execute specific tasks, and update the plan during execution, with control switching between surgeon and machine.
- **Level 4 (High Autonomy):** The robot can interpret pre- and intraoperative information, devise and autonomously execute an interventional plan, and replan if necessary, under surgeon supervision.
- **Level 5 (Full Autonomy):** These systems do not currently exist outside of research. This field relates to **cognitive robots**.

**AI Enables Autonomy:** **Artificial Intelligence (AI)** is crucial for enabling autonomy in surgical robots.

**Requirements for Autonomous Surgical Robots:** Developing autonomous surgical robots requires advancements in several areas:

- **Visualization & interfaces**.
- **Perception & Cognition:** This involves **sensing and understanding** tasks and processes (i.e., surgical phases).
- **Autonomous Robot Control**.
- **Human-Robot Co-Operation**.
- **Real World Tasks**.
- **Planning & Optimization**.
- **Demonstrations**.
- **Simulation**.
- **Tissue Properties & Modeling**.

**Robot Perception and Cognition:**

- **Perception:** The robot must **perceive its environment** through sensors (images, videos, depth, proximity, tactile).
- **Cognition:** The robot must **understand and interact** with the environment through data processing and analysis (image analysis, instrument tracking, personnel tracking) and decision-making and planning (suggesting plans, calculating trajectories, anticipating issues). Examples include understanding the surgeon through robust instrument activity localization and understanding the surgical site via semantic segmentation of organs and tissue.

**Surgical Simulation:** Surgical simulation is vital for:

- Residency education and skills practice.
- Evaluating surgeons.
- Training for adverse events and special cases.
- Training on patient-specific anatomy and plans.
- **Non-destructive robot learning**, policy evaluation and optimization.

VR training systems like the **Da Vinci Skills Simulator** help surgeons familiarise themselves with the system, provide more learning opportunities, measure progress, and warm up before surgery. Frameworks like the **Simulation Open Framework Architecture (SOFA)** are used for research in medical simulations, supporting biomechanical simulation, surgical planning, and training with real-time capabilities and multi-physics support (rigid, deformable, and fluid models). Surgical simulation for robot learning involves creating surgical environments with deformable objects, topological changes, contact-rich manipulation, and multi-step tasks, often using frameworks like SOFA zoo and Sofa Godot for defining reward functions, learning scripts, and path planning considering the **fulcrum effect** of pivotized instruments.

**Generative Adversarial Networks (GANs):** GANs are used to address the **small availability of medical data** and the expense of annotation.

- They involve a **generative model (G)** that creates synthetic data and a **discriminative model (D)** that tries to distinguish between real and synthetic data. The goal of G is to fool D.
- **CycleGAN** is a type of GAN primarily used for **image-to-image translation** without requiring paired images. It uses two generators and two discriminators and introduces a **cycle-consistency loss** to ensure that translating an image from one domain to another and back results in an image close to the original. This can be used to generate realistic-looking synthetic images from simpler simulations, potentially providing labels for medical data.

**Reinforcement Learning (RL) for Autonomous Surgery:** RL is an approach where a robot (**agent**) learns surgical steps through trial-and-error interactions with a simulated or real-world environment, receiving rewards for performing actions. **Multi-agent RL** can involve each surgical instrument being represented by an agent executing specific tasks, for example, in a simulation of lifting and cutting the gallbladder.

**Sim-to-Real Transfer:** Bringing agents trained in simulation to the real world (**sim2real transfer**) is a key challenge. Techniques like **domain translation** using **image-to-image translation** with GANs (e.g., CycleGAN, CUT, DCL) can help bridge the **sim-to-real gap** by making synthetic images more realistic.

**Take-Away Points:**

- Autonomy levels range from no autonomy to full autonomy, with no fully autonomous systems currently existing.
- Robotic autonomy requires perception (sensing) and cognition (interpretation and interaction).
- Surgical simulation is crucial for training both humans and robots.
- GANs, including CycleGANs, can be used for synthetic data generation and image-to-image transfer to obtain labelled and realistic images.
