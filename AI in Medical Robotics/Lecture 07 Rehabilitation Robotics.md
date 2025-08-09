

**The Need for Rehabilitation Robotics:**

- The WHO estimates that **1 in 3 people live with a health condition that would benefit from rehabilitation**.
- The need for rehabilitation is **expected to increase** due to longer life expectancy, more chronic diseases and disabilities, and global conflicts and disasters.
- Rehabilitation aims at **optimising functions and reducing the experience of disability**, enabling people to stay independent and participate in daily life.

**Motion Impairments Addressed:**

Rehabilitation robotics can be useful for a variety of motion impairments resulting from:

- **Stroke:** Recovery of arm and leg movement, and fine motor skills. Post-stroke, individuals may experience limb-shaking, involuntary muscle contractions, and tremor.
- **Spinal Cord Injury (SCI):** Gait training, strengthening of weakened limbs, and improving core strength and balance. SCI results in loss of muscle function, sensation, or autonomic functions below the injury.
- **Traumatic Brain Injury (TBI):** Addressing motor deficits and cognitive challenges, and improving coordination and balance.
- **Parkinson's Disease:** Enhancing movement and balance, and assisting with tasks challenging due to tremors.
- **Multiple Sclerosis:** Improving muscle strength, balance, and gait, and addressing spasticity and coordination issues.
- **Cerebral Palsy (CP):** Movement and strengthening of limbs, and enhancing fine motor skills and coordination. CP affects the ability to move and maintain balance and posture, often due to abnormal brain development or damage. Types of CP include stiff muscles (spasticity), uncontrollable movements (dyskinesia), poor balance and coordination (ataxia), and weak muscles.
- **Orthopedic Conditions:** Rehabilitation after joint replacements, and recovery from fractures or surgeries.

**Neuroplasticity:**

- **Neuroplasticity** is the brain's ability to change and adapt due to experience by reorganising or growing neural networks.
- **Structural plasticity** refers to experience or learning changing the brain's physical structure.
- **Functional plasticity** refers to brain functions moving from damaged to undamaged areas.
- Rehabilitation often involves **repetitive training of motor functions to trigger neuroplasticity**. However, neuroplasticity has limitations, especially with complete damage to key brain regions.

**Challenges of Manual Training:**

Manual rehabilitation therapy can be:

- Physically exhausting and ergonomically inconvenient for the therapist.
- Result in non-optimal and uncontrollable gait patterns, and limited training duration for the patient.

**Rehabilitation Robotics:**

- **Rehabilitation robots** are primarily designed for therapeutic purposes, focusing on the restoration and improvement of physical abilities affected by injury, surgery, or disability. Examples include ArmIN and Lokomat.
- **Assistive robots** aid individuals with disabilities or the elderly in performing daily tasks like lifting or navigating.

**Robot-Assisted Therapy Concepts:**

Robot-assisted therapy can involve:

- **Replicating the therapist:** Moving limbs passively, actively-assisted, or actively-resisted.
- **Augmenting the therapist:** Adding simulation, games, or VR to motivate the patient.
- **Designing the super-therapist:** Adding or removing force fields, or enabling virtual borders.
- **Enabling the inner therapist:** Fostering high motivation and active participation to enhance motor learning, with the desirable goal of controlling mental state.

**Types of Rehabilitation Robots:**

- **End-effector based robots** connect to the patient's limb at the end-effector. They are easy to adjust but don't fully determine limb posture or individual joint torques. An example is MIT-Manus.
- **Exoskeletal robots** resemble human anatomy, offering better guidance and determined body posture, but are more difficult to adapt to different body sizes. The ARMin series is an example. Human arms have approximately 7 degrees of freedom (DOF) in the shoulder, elbow, forearm, and wrist, plus additional DOF in the hand. Robots with 7 axes offer a more comprehensive range of motion.

**Upper and Lower Limb Rehabilitation Robotics:**

- **Upper-limb rehabilitation** systems like ARMin and MIT-Manus target different parts of the arm. MIT-Manus focuses on proximal (shoulder and elbow) movements with InMotion Arm, and distal (wrist and forearm) movements with InMotion Wrist.
- **Lower-limb rehabilitation** systems include Lokomat, LOPES II, and G-EO Revolution. Lokomat allows for active training where higher EMG activity is observed when the subject actively follows the robot's motion.

**Control Strategies in Rehabilitation Robotics:**

Various control strategies are employed in rehabilitation robots:

- **Position Controller:** Simple PD controller reacting to actual and derivative errors, but lacks individual adaptation.
- **Impedance-based Assistance:** Allows variable deviation from a trajectory, becoming passive when the patient moves adequately and increasing assistance with deviation. Impedance control regulates the relationship between force and velocity. The robot's resistance to motion (impedance) can include stiffness, damping, and inertia.
- **Admittance Control:** The inverse of impedance control, where the robot's motion is the output in response to an external force input, allowing for passive guidance and adaptation to patient movements.
- **Assistance-as-needed Controller:** Assists the patient only as much as needed to accomplish a task, based on clinical practice and aiming to always challenge the patient.
- **Tunnel Controller:** Creates a virtual tunnel allowing some error variability, with additional force if motion is too slow.
- **Counterweight-based Control:** Uses harnesses and counterweights to unload the body during gait training, examples include FLOAT.
- **EMG-based Control:** Uses electromyography signals to drive assistance based on the patient's effort. It allows patient control but requires calibration. EEG systems can provide additional insight into human intent.

Early control systems often forced predetermined motion, which can hinder motor learning. Cooperative assistive control is preferred, allowing for variability and errors ("repetition without repetition"). Ideal control strategies should be intensive, cooperative (assist-as-needed), mechanically transparent, engaging, rewarding, and task-specific.

**Patient Engagement:**

- **Patient engagement** through games or Virtual Reality (VR) is crucial for motivation and successful rehabilitation.
- Motivation and mental activity alongside physical activity enhance the neuroplastic effect and lead to more successful rehabilitation.

**Evaluation:**

- The **Fugl-Meyer Assessment (FMA)** is a widely used tool to evaluate motor functioning, balance, sensation, and joint functioning in stroke patients to track post-stroke recovery. The upper limb maximum score is 66, and the lower limb is 34.

**Key Takeaways:**

- Rehabilitation robotics addresses a growing need for therapy for various motion impairments.
- It leverages neuroplasticity through repetitive and intensive training.
- Assist-as-needed and cooperative control strategies are crucial for effective robotic rehabilitation.
- Patient activity is key to increasing the neuroplastic and therapeutic effects.
- The effectiveness of robotic rehabilitation is still an ongoing area of investigation.