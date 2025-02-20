### **Background of Human-Robot Co-Adaptation**

- **Rehab/Assistive Robotics** combines **mechatronics, medicine, psychology, and mathematics**.
- This is a field of **basic research** that needs **user studies**, **clinical deployment**, and connections to **industry**.
- **Basic research** focuses on understanding the patient's problems, treatments, needs and desires, connecting to nerves and muscles, and using artificial intelligence to interpret neural signals.
- **"Make it work!"** focuses on putting the patient at the centre of research, testing devices in the field early, and deploying in clinics. Medical robots that only work in a lab are useless.
- **Exoskeletons**, **prostheses**, and **virtual reality for rehabilitation** are some devices explored in the course.
- **Prosthetics** is a frontier for interfacing man and machine that needs to be almost permanent and totally body compatible.
- **Prosthetics** rely on body signals and need to be reliable, as errors could cause trauma or accidents.
- **Co-adaptation** is necessary, where the interfaces learn from the user and the user learns how to use them.
- Man and machine adapt to each other.
- This **co-adaptation paradigm** applies to surgical robots, walking exoskeletons, rehabilitation devices, and prostheses.
- The course uses the example of an **amputated person teleoperating** a humanoid platform using electromyography signals.


### **Rehabilitation and Assistive Robotics**

- **Rehabilitation** aims to aid people with reduced motor functions.
- The devices need to be ergonomic, comfortable, usable, friendly, intuitive, light and unobtrusive.
- Effectiveness is determined by precision, repeatability, smoothness, and humanoidness of motion.
- Interfaces should let the patient choose what they want to do and use biosignals, needing AI and coupling with the patient over time.
- The course considers how to improve prosthetics integration by exploiting the brain's plasticity.
---

## **Lecture 02: Human-Robot Interaction in RAR (Rehabilitation and Assistive Robotics)**

### **Human-Robot Interaction (HRI)**

- HRI is a key area in the field of robotics.
- It encompasses how humans and robots interact in general, and specifically within **Rehabilitation and Assistive Robotics (RAR)**.
- The study of HRI is covered by resources like humanrobotinteraction.org.
- A survey of HRI can be found in the work of Michael A. Goodrich and Alan C. Schultz (2008).

### **Human-Machine Interface (HMI)**

- A HMI is the system or channel through which interaction happens.
- It converts signals from a human into control commands and translates environmental signals into physical stimuli.
- **Feedforward** HMI converts human-generated signals into control commands to operate a machine.
- **Feedback** HMI converts environmental signals into physical stimuli.
- Examples include:
    - The handles of a wheelbarrow.
    - The cockpit of a car.
    - The surface of a smartphone and its operating system.
- Characteristics of a good HMI include:
    1. **Reliability**: The HMI should enable precise control of the machine, ensuring it does exactly what is intended, when and only when it is intended.
    2. **Dexterity**: The HMI should allow full control of the machine, utilising its full potential and all its degrees of freedom.
    3. **Ease of Use**: The HMI should be easy to learn and use, with a clear user manual and an enjoyable experience.
    4. **Flexibility**: The HMI should require minimal adaptation from the user and be suitable for both end-users and experts.

### **HMIs for the Disabled**

- Most HMIs are designed for operation through arms, hands, and fingers, which presents a challenge for those with disabilities.
- For users with limb differences, HMIs need to be adapted. This can be done by:
    - Replacing commands issued via fingers and hands with signals that represent the intended activity.
    - Replacing force/contact feedback with somato-sensory feedback.
    - Replacing physical interacting devices like joysticks, handles, and touchscreens with a socket.
- The four main characteristics of a good HMI (reliability, dexterity, ease of use, and flexibility) should still hold for HMIs designed for people with disabilities.
- The HMI system includes: sensors, signal processing (ADC filtering, sensor fusion, feature extraction), intent detection (ML), somatosensory feedback, and audio and visual feedback.
- The HMI connects the user, the device, and the environment through a socket.

### **Improving Data Quality in HRI**

- Involve the user from the beginning of the design process to improve the quality of the data.
- **Exploit the user** to provide good data to the system.
- Improve sensors by making them:
    - High-density
    - Multi-modal
    - Wearable, wireless and unobtrusive
- Improve interaction through better experimental protocols and interactive machine learning that can obtain new data or forget old data on demand.
- Design appropriate human-machine interfaces to promote interactive human learning.

### **HRI in Upper-Limb Prosthetics**

- In upper-limb prosthetics, the robot is a hand prosthesis and the user is an amputated person.
- The prosthesis must learn that specific signals from the user's muscles correspond to specific desired actions (intent detection).
- If the user changes position, the signals can change even if the intended action remains the same.
- A simple solution to this issue is to provide **feedback** to the user when the prosthesis makes an error, indicating it needs more data.
- The user can then hover in that position, allowing the prosthesis to capture more data and improve its performance.

### **Feedback-Aided Learning**

- Providing as much good feedback as possible is critical to improving the performance of the system.
- Involve the user to improve data quality.
- Define a precise interaction strategy.
- A study by Gigli, A. et al. (2020) showed that feedback-aided data acquisition improves myoelectric control of a prosthetic hand.

---

### ** 3. Intent Detection: Definition**
	
- **Intent detection** is the process of associating stable, repeatable signal patterns to desired actions and their intensities.
- It's essentially about figuring out what a user wants to do by analysing signals related to their muscle activity.
- The goal is to associate a specific muscle activation pattern with an intended action.

### **Signals for Intent Detection**

- **Muscle activity** is the basis for all actions in mammals.
- Sensors need to detect stable, repeatable electrical, mechanical or optical patterns related to muscle activity.
- These patterns are generated when a user activates muscles in a specific way to perform an action.
- **Electromyography (EMG)** is a key method that measures the electrical signals produced by muscle contractions.
    - EMG signals are oscillating signals with a bandwidth of 15-450Hz and an amplitude of 1µV-10mV.
    - The frequency and amplitude of these oscillations denote the intensity of muscle contraction.
    - EMG signals are often processed using a bandpass filter (15-500Hz), rectification (absolute value), and a low-pass filter (~5Hz).
    - The Averaged Rectified Value (ARV) is roughly proportional to the intensity of muscle contraction, but it’s controversial if this is better than raw signals.
- **Force Myography (FMG)** is another method that measures muscle deformation using pressure sensors inside a socket.
    - FMG detects changes in body shape caused by muscle bulges.
    - Potential advantages include being less influenced by fatigue and sweat, as well as simpler, cheaper electronics.
    - The effectiveness of FMG compared to EMG is still controversial.
- **Ultrasound scanning** can provide deeper information by imaging muscle deformation using high-frequency pressure waves.
    - It involves emitting and detecting "echoes" of pressure waves to create an image of the tissue.
    - Ultrasound is very rich in information and easy to process but it is not cheap and miniaturisation is a problem.
- These methods attempt to capture patterns that can be associated with an intended action.

### **Data Collection and Labelling**

- **Data collection** and **labelling** are crucial, as machine learning relies on these.
- Data labels are typically done manually or mechanically.
- However, for disabled users, things are more complex since the data and semantics depend on the user.
- Disabled users can’t usually produce reliable ground-truth, and standard motion capture methods may not work.
- To label data, researchers might ask the user or induce them to perform an action, then record signals.
- The experimental protocol induces the user to perform an action (stimulus), and the signal recorded is associated with that requested action.
- The correctness of the labelling is not guaranteed, and must be updated by collecting more data as the participant gains awareness of the procedure.

### **Offline vs. Online Intent Detection**

- **Offline intent detection** involves inducing the user to perform an action at a specific time, recording input signals and then using part of the data to map data to the intended action, with the model tested on the remaining data. The user is not part of the process at the stage of model evaluation.
- **Online intent detection** involves the user doing something at a specific time while the signals are recorded, and all data are used to update the mapping between the data and the action. The model is tested in real life with the user.
- Offline intent detection has very little correlation with online performance and is essentially a waste of time.
    - It has been shown that there is almost no correlation between offline and online performance measures.

### **The Residual Limb**

- The residual limb has surprisingly rich, diverse and persistent muscle activity, even decades after amputation.
    - This muscle activity can sometimes cause pain or discomfort.
- The more proximal the amputation, the harder it is to detect relevant residual activity.
- Even in cases like trans-humeral amputations, where a user wants to move their thumb, residual muscle activity can still be detected.

### **Intent Detection Pipeline**

- The general intent detection process involves:
    - **Input signals:** Raw data from sensors.
    - **Preprocessing:** Filtering and subsampling of raw signals.
    - **Feature extraction:** Extracting relevant features from the processed signals.
    - **Non-linear mapping:** Using machine learning to map features to actions.
    - **Classification / regression:** Identifying the intended action.

### **Classification**

- Classification involves mapping multi-dimensional signals to an action.
- It is a function that maps an input space to an element of a discrete set of labels/classes.
- Many classification approaches have been tried on EMG.
- Two commercially available pattern recognition-based upper limb prosthesis (ULP) systems use on-demand re-calibration with (probably) a Linear Discriminant Analysis (LDA).
- These use six to eight sEMG sensors to perform different actions.
- Examples include the Complete Control by COAPT Engineering, Inc. and the Myo Plus Pattern Recognition by Ottobock.


---

## **Lecture 04: Somatosensory Feedback**,

### **Somatosensory Feedback: The Basics**

- **Somatosensory feedback** is about closing the human-in-the-loop by providing sensory information back to the user.
- It is an essential aspect of human-robot co-adaptation.
- This feedback aims to simulate **proprioception** and **touch**, giving the user a sense of their body's position and interaction with the environment.
- Visual and auditory feedback are often already present in human-robot interaction, however they might not always be useful or wanted by the user.
    - Users can see what their devices do, although not always, and sometimes they don’t want to.
    - Users can also hear what their devices do, like the noise associated with motors.

### **Importance of Direct Somatosensory Feedback**

- Direct stimuli on the body can be provided to simulate proprioception and touch.
- Users naturally perceive the weight and resistance of any prosthesis or rehabilitation device.
- In some cases, direct force-feedback is available "for free," such as with body-powered prostheses.
- **Lack of somatosensory feedback makes motion essentially impossible**.

### **Receptors and Afferent Axons**

- There are many different receptors in the limbs.
- There are actually **more afferent (sensory) axons than efferent (motor) ones** in the forearm.

### **The Power of Fake Feedback**

- **Fake somatosensory feedback can trick the brain**.
- The "rubber hand illusion" is an example of this, where a person can feel touch on a rubber hand they see.

### **Types of Somatosensory Feedback**

- There are two main ways to provide somatosensory feedback:
    - **Mechanical feedback**: This includes **vibrotactile** feedback and **indenting** the skin.
    - **Electrical feedback**: This uses **small electrical currents through the skin**.

### **Sensory Substitution**

- **Sensory substitution** is a technique that allows users to perceive information through different sensory channels.
    - It is useful to provide information when normal sensory feedback is unavailable.

### **Does Somatosensory Feedback Improve Control?**

- Yes, studies show that somatosensory feedback can improve control.
- Adding **vibrotactile feedback to a myoelectric-controlled hand** can improve performance, especially when visual feedback is disturbed.
- **Artificial redirection of sensation** from prosthetic fingers to the phantom hand map can be achieved with both vibrotactile and mechanotactile feedback.
- **Electrotactile EMG feedback** can also improve the control of prosthesis grasping force.

---
## **Lecture 05: Closing the Loop**
	
### **Closing the Loop: Core Concepts**

- **Closing the loop** refers to creating a system where information about the state of the world is fed back into the system.
- This creates a closed-loop system that aims to keep values within a specific range.
- The system receives information about its state, compares it with the desired state, and adjusts accordingly.
- In human-robot co-adaptation, this is a complex process because it includes a human in the loop.

### **Human-in-the-Loop Complexity**

- The main challenge in human-robot co-adaptation is the inclusion of a human in the loop, making the system extremely complex.
- It is practically impossible to create a complete mathematical model of the entire system.
- Instead, the focus shifts to creating a dynamic environment where:
    - The user can properly control and teach the device.
    - The device reacts appropriately and provides feedback or requests new data.

### **Key Elements of a Closed-Loop System**

- **Sensors:** These collect information about the state of the world.
- **Stimulators:** These provide feedback to the user.
- **Signal Processing:** This includes steps like ADC filtering and feature extraction.
- **Intent Detection:** This uses machine learning to determine the user's intended actions.
- **Feedback:** This provides somatosensory, audio, and visual cues to the user.

### **Co-adaptation**

- **Co-adaptation** is the process where both the user and the device learn and adapt to each other.
- It aims to reach a **steady-state** where:
    - The user is satisfied with the accuracy and reliability of control.
    - The device no longer needs additional data and is confident in its action prediction.

### **Measuring Co-adaptation**

- Co-adaptation can be measured through:
    - **Objective "external" measures:** These relate to performance changes, including success rate, time to complete a task, and smoothness of trajectory.
    - **Subjective "external" measures:** These relate to acceptance changes, including usability, easiness, friendliness, embodiment and sense of agency, which are often measured using questionnaires.
    - **User’s "internal" measures:** These relate to changes in control signals, including the separatedness of action-related clusters, repeatability of action-related clusters, and coverage of the input space.
    - **Device's "internal" measures:** These relate to changes in the signals-to-actions map.

### **Changes During Learning**

- During learning, there are changes in:
    - **User's EMG signals:** These changes occur as the user learns to control a prosthesis.
    - **Performance:** This includes changes in classification accuracy, time, and stability.
    - **Muscle activation patterns:** These changes lead to more efficient control, better retention, and generalisation.

### **Importance of Interaction**

- **Regression** is considered better than classification due to the added interaction in the system.
- **Proper closed-loop adaptation** is vital for optimal performance.
- Subjects can adapt to various situations and achieve difficult tasks with co-adaptation.
    - This includes disabled users achieving performance levels similar to able-bodied individuals.

##### summary
- **Co-adaptation is highly desirable** in human-robot interaction.
- It is not completely clear how to measure and foster co-adaptation.
- It is crucial to remember the **brain is plastic**, and users should be encouraged to learn by themselves with minimal interference.

---
### **6. Core Concepts of User-Centered Design (UCD)**

- **User-Centered Design (UCD)** focuses on creating products and services that are **easy to use and efficient** for their intended users.
- **Human-Centered Design (HCD)** takes a broader view, considering the **overall human experience and emotions**.
- **Human-Centric Design (HCeD)** puts humans at the centre of the design process, making them co-creators. This approach emphasizes ethical, sustainable, and socially responsible design.
- The main idea behind UCD is to focus on **human needs in real-world contexts**, beyond just laboratory settings. This involves using **ecologically valid settings** to understand human needs and ensure the value of solutions matches user expectations.

### **Key Elements of UCD**

- **Understanding Users, Interactions, Contexts**: It's crucial to understand users' skills, limitations, and needs within specific contexts.
- **Design for Human Minds**: Design should consider how people think, not just how they move their hands. This also includes considering how people interact with others.
- **Usability**: This is defined as the extent to which a product can be used by specific users to achieve specific goals with effectiveness, efficiency and satisfaction.
    - **Effectiveness**: Doing the expected task.
    - **Efficiency**: Using minimal resources.
    - **Satisfaction**: Maximizing enjoyment.
    - **Learnability**: Being able to learn quickly how to use the product.
    - **Memorability**: Being able to easily remember how to use the product.
- **Errors**: Doing tasks without the risk of mistakes.
- **Accessibility**: Making products usable for people with temporary, situational, or permanent limitations. Solving accessibility issues for one group of users may provide solutions for others.
- **User Experience (UX)**: This includes the reactions and expectations that influence the use of a product.
    - Design should fulfil the user's needs.
    - It should also provide a positive and meaningful experience.

### **Design Principles**

- **Affordances**: Establishing constraints and invitations to use to influence actions between the user and the tool. This includes designing the **user interface**.
- **Feedback Control**: This is essential for effective interactions.

### **The Importance of Context**

- **Ecological Validity**: Designs must be tested in settings similar to real contexts to match user expectations.
- **Real-World Interactions**: Interactions between humans and tools are not always predictable and can lead to errors if not designed well.

### **Ergonomics and Human Factors**

- **Ergonomics** involves studying how people interact with systems to improve human well-being and system performance.
- It is an **interdisciplinary approach** that considers human skills, limitations and needs in real contexts.
- The three main branches of ergonomics are:
    - **Physical Ergonomics**: Focuses on human physical features.
    - **Cognitive Ergonomics**: Focuses on human mental processes.
    - **Organizational Ergonomics**: Focuses on socio-technical systems and organizational processes.
- **Limitations and Actions**: Users must be informed about what they can do, the consequences of their actions, and be in optimal conditions to make rational decisions.

### **Neuroergonomics**

- **Neuroergonomics** investigates neurocognitive processes related to human-system interactions in ecologically valid contexts. It integrates user research and human-centered design.
- It uses neuroscientific methods to investigate and design interactions between humans and systems in real-world contexts.
- Neuroergonomics is used for assessing interactions, training users, and making systems adapt to users.
- It also aims at increasing neuroscientific knowledge.

### **Ethical Considerations**

- **Value-Sensitive Design**: Ergonomics and neuroergonomics involve key values like well-being, accessibility, and safety that should be translated into human-centered design principles.
- **Privacy by Design**: It is essential to consider privacy implications when collecting data from users.

####### **Summary**

- User-Centered Design places the **user at the heart of the design process**.
- It is important to understand user needs, skills and limitations in real-world contexts.
- **Usability**, **accessibility**, and **user experience** are all important elements to consider in the design.
- **Ergonomics and neuroergonomics** play a key role in developing human-centred technologies.
- The focus is on creating designs that are **effective, efficient, and enjoyable** for the user, and that adapt to the user's needs and reactions.
---
### **7. Rehabilitation Robots and Their Users**
Okay, here are some notes on what appears to be **Lecture 7: Rehabilitation Robotics**, based on the provided sources, formatted to help you prepare for exams:

### **Introduction to Rehabilitation Robotics**

- The lecture focuses on **rehabilitation robots** and their role in assisting and rehabilitating patients with various conditions.
- Key aspects of these robots include **mental workload and user engagement** to ensure they are truly user-centred.
- The lecture aims to cover the **users, the robots, and the methods** involved in this field.

### **Medical Reasons for Using Exoskeletons**

- Exoskeletons and other rehabilitation robots are used to aid patients with:
    - Trauma.
    - Musculoskeletal degeneration conditions (e.g., ALS).
    - Stroke.
    - Spinal cord injuries.
    - Traumatic brain injuries (TBI).

### **Medical Conditions Requiring Assistance or Rehabilitation**

- A significant number of people worldwide require prosthetic or orthotic devices:
    - **30 million** people need prosthetic or orthotic devices globally.
    - In the USA and Europe, there are **300,000 amputations** each year, with 25% involving the upper limb.
    - **500,000 people** suffer spinal cord injuries each year, primarily in young (15-30 years old) and older adults (60+).
    - **15 million people** worldwide suffer a stroke each year, and about 70% survive with long-term disabilities.

### **Spinal Cord Injury (SCI) and its Symptoms**

- Spinal cord injuries can lead to significant and often permanent changes in strength, sensation, and body functions below the injury site.
- SCI is categorised by completeness (complete/incomplete) and by the lowest part of the injury (paraplegia/tetraplegia).
- Outcomes include:
    - Loss of movement.
    - Altered sensation, including the ability to feel heat, cold, and touch.
    - Loss of bowel or bladder control.
    - Changes in sexual function, sensitivity, and fertility.
    - Pain or stinging sensations caused by nerve damage.
    - Difficulty breathing or coughing.

### **Stroke and its Symptoms**

- Strokes can cause various long-term disabilities.
- Strokes are categorised as either ischemic or hemorrhagic.
- Outcomes of a stroke include:
    - Paralysis or weakness on one side of the body.
    - Cognitive issues, such as problems with thinking, awareness, attention, and memory.
    - Problems with understanding or forming speech.
    - Trouble controlling emotions.
    - Numbness or strange sensations.
    - Pain in hands and feet, worsened by movement or temperature changes.
    - Trouble chewing or swallowing.
    - Problems with bladder and bowel control.
    - Depression.
- **"Time is brain!"** highlights the importance of acting quickly during a stroke.

### **Rehabilitation Technologies**

- Rehabilitation technologies include:
    - **Virtual and augmented reality settings**.
    - **Robotic systems**.
    - **Wearable robots and end-effectors**.

### **Robotic Systems**

- Conventional robots can be simplified to a series of links connected by rotational or prismatic joints.
- The lecture introduces notation for:
    - **End-effector configuration** as _e_
    - **Joint positions** as _θ_
    - **End-effector forces** as _F_
    - **Joint torques** as _τ_
- The main goal of robot control is often translating a desired configuration in Cartesian space to one in joint space which is then translatable into control inputs for the actuators.
- The total power acting on the system must respect a specific relationship between end-effector forces/torques and joint forces/torques.

### **Kinematics**

- **Forward kinematics** is the computation of the end-effector's configuration in Cartesian space based on joint space configuration.
- **Inverse kinematics** is the computation of joint parameters based on a desired configuration in Cartesian space.
- Analytical solutions may not always exist; thus, iterative methods using the Jacobian matrix are needed.
- The Jacobian is used to adjust the joint position from a starting pose to a desired pose iteratively.

### **Dynamics**

- Deriving the **system dynamics** is essential to compensate for gravity, inertia, and gyroscopic forces.
- System links are characterised by mass, center of mass, and inertial momentum tensor.
- The **Lagrange formalism** is used to derive the system dynamics from known parameters.
- Dynamics can be derived in Cartesian and joint space.
- Robot dynamics usually have a standard form.

### **Impedance Control**

- Impedance control defines the relationship between the robot's position and the force it applies.
- It is essential for physical human-robot interaction.

### **Neuromusculoskeletal Models**

- These models map between muscle space, joint space, and task space.
- They also establish a relationship between positions and forces in these spaces.

### **Wearable Robots**

- Wearable robots include exoskeletons and exosuits.
- They are used to enable occupational therapy, provide a large workspace, and compensate for gravity.
- They adhere to safety standards and offer the potential for richer indices on patient progress.
- Data-driven and AI-based strategies can be used for diagnosis and treatment.
- "Assistance-as-needed" strategies aim to prevent patient reliance on the robot.
- They offer potential for novel assistive applications, cost-benefit improvements, synergies with neuroadaptive systems, and options for home rehabilitation.
- They also have synergies with virtual and augmented settings.

### **User-Centred Design and Evaluation**

- **Technology Acceptance Models (TAM)** are used to evaluate user acceptance of systems.
- The **System Usability Scale (SUS)** is used to assess the usability of rehabilitation robots.
- This includes aspects such as ease of use, complexity, and user confidence.
- Mental workload is also a key consideration, with excessive mental effort potentially hindering performance.
- This includes the effort to follow the device pace and the strain felt while using the device.
- Increased mental workload in medical exoskeletons has been associated with improved gait performance in stroke patients but without gait changes in SCI patients.

### **User Engagement**

- User engagement is essential and should come before considering mental workload.
- **Co-design** processes must include final users and clinicians.
- Engagement is crucial during device use and calibration.
- Key aspects of user engagement include motivation, feeling competent, autonomous, and in relationship.
- **Playful engagement**, social robots, and serious games are used to sustain user effort.
- **Digital therapeutics** use digital excipients to engage the users and allow for personalization of treatment.

### **Virtual Reality (VR) and Augmented Reality (XR) Advantages**

- VR/XR can provide engaging settings, controlled conditions, and personalised difficulty.
- VR/XR can lead to digital biomarkers, distract from fatigue and pain, and are low-cost and portable.
- **Neural principles**, like plasticity, show that motor activity influences and shapes the nervous system.
- VR/XR promote embodiment training, including spatially augmented respiratory biofeedback, observed action, haptic feedback, EMG activity, and motor command.
- They engage users in technology use, promoting technology acceptance and prosthetic embodiment.

### **Rehabilitation Neurotechnologies**

- These technologies influence the nervous system through:
    - Monitoring biosignals to control multimodal stimulation (e.g., neurofeedback, neuromodulation).
    - Guiding motor-cognitive exercises based on neural principles (e.g., plasticity).
- Peripheral neuroergonomics is also essential for rehabilitation.
- Integration via co-adaptive interaction is the aim.

---
## **Lecture 8: Methods for User Studies**

### **Introduction to User Study Methods**

- The lecture focuses on **methods for user studies**, beginning with **experimental design and data analysis**.
- The session will cover **measurement** as a fundamental aspect of user studies.
- The lecture aims to address the **importance of a well-designed experiment**.

### **Measurement as a Problem**

- **Lord Kelvin (William Thomson)** stated that if something exists, it exists in some quantity and can therefore be measured.
- **Gustav Theodor Fechner** founded **psychophysics**, which explores the quantitative relationships between psychological events (sensations) and physical events (stimuli).
- **Psychometrics** is the branch of psychology dedicated to the design and use of psychological tests, applying statistical and mathematical techniques to psychological testing.
- **Ronald A. Fisher** highlighted that consulting a statistician after an experiment is finished is like asking for a post-mortem examination, stressing the need to involve statistical considerations in experimental design.

### **Priority to Experimental Design**

- A well-designed experiment is crucial to avoid wasting resources, including the cost of experiments, materials, time, and the energy of researchers and subjects.
- Poorly designed experiments can lead to biased datasets, which violates principles of ethical sustainability.
- A well-designed experiment should be based on the following:
    - **Clear objectives** and **precise measures**.
    - **Simple** and **unbiased approaches**.
    - **Compatibility with statistical analyses**.
    - **Appropriate power** in statistical tests.
    - **Randomised comparisons**.
    - **Reproducible methodologies**.
    - **Control of sources of variation** (e.g., noise caused by physio-motor processes and technical noise from devices).

### **Measures of Central Tendency and Dispersion**

- **Measures of Central Tendency** describe the overall distribution of data.
    - **Mean:** The average value, sensitive to outliers.
    - **Median:** The middle value in an ordered set, useful in case of outliers.
    - **Mode:** The most frequent value in a distribution, particularly useful for discrete or categorical data.
- **Measures of Dispersion** describe the variability in a dataset.
    - **Range:** The difference between the maximum and minimum values.
    - **Standard Deviation:** The standard deviation from the mean.
    - **Variance:** The squared standard deviation from the mean.

### **The Median and Quantiles**

- The **median** is found by ordering the data and identifying the middle value (or the average of the middle couple for an even number of items). For example, in the dataset: `12 13 15 16 16 18 19 20 21 25 27 30`, the median is 18.5.
- **Quantiles** are statistical measures that divide a dataset into equal parts.
    - **Quartiles** divide the data into four parts.
        - **Q0 (Zero Quartile):** The minimum value.
        - **Q1 (First Quartile):** The median of the lower half of the data, representing the 25th percentile.
        - **Q2 (Second Quartile):** The median of the entire dataset, representing the 50th percentile.
        - **Q3 (Third Quartile):** The median of the upper half of the data, representing the 75th percentile.
        - **Q4 (Fourth Quartile):** The maximum value.

### **Quantitative vs Qualitative Methods**

- The lecture distinguishes between **quantitative** and **qualitative** methods, as well as **subjective** and **objective** methods.
- The **levels of measurement** in data are also relevant.
- **Likert-type scales** are often used in subjective measurements.

### **Experimental Design**

- The lecture covers different **experimental design** models, including **mixed models**.
- In a **mixed model**, each subject may experience one level of one condition (between-factor) and all levels of another condition (within-factor).
- Alternatively, each subject can experience all levels of one condition (within-factor) and one level of another condition (between-factor).
- The term "**treatment**" is equivalent to a "**level**" within a condition.
- **Randomisation** is essential in experiments to avoid the effect of prior experience on results.

### **Inferential Tests**

- **Inferential tests** make the **main assumption of normality** in data distribution.
- **Statistical significance** is determined through these tests.
- Results can be described as "**not significantly different**" or "**significantly different**".
- **Sample size** and **power analysis** are important considerations in experimental design.

### **Power Analysis and Sample Size**

- Key elements in determining the appropriate sample size include:
    - **Sample size:** How many subjects are needed to find an effect.
    - **Power:** The probability of detecting a real effect.
    - **Effect size:** The magnitude of the effect that needs to be detected.
    - **Significance level (Type I error):** The probability of incorrectly claiming an effect that does not exist (False Positive).
    - **Type II error:** The probability of missing a real effect (False Negative).
    - **Standard deviation:** The variability in the outcome after accounting for the effect.
- The **Type I error** is the probability of incorrectly rejecting a true null hypothesis, while **Type II error** is the probability of incorrectly failing to reject a false null hypothesis.
- **Power** is the probability of correctly rejecting a false null hypothesis and identifying a true positive result.
- Calculating the sample size is crucial to minimise effort, maximise the chance of finding an effect, and satisfy ethical and funding requirements.

### **Prosthetic Embodiment**

- **Prosthetic embodiment** involves how a user engages with and feels a part of their body scheme, particularly related to technology use.
- Research in this area includes:
    - **Spatially Augmented Respiratory Biofeedback (SARB)** approach.
    - **Observed Action**.
    - **Haptic Feedback**.
    - **EMG Activity**.
    - **Motor Command**.
- These approaches promote technology acceptance and engagement in technology use.
- Determining the number of subjects to recruit for statistically significant comparisons is important for prosthetic embodiment research.
---
## **Lecture 9: The Rubber-Hand Illusion and Embodiment**

### **Introduction to Human-Robot Co-Adaptation**

- This lecture is part of a series on **Human-Robot Co-Adaptation**.
- The lecture specifically explores the **rubber hand illusion** and the concept of **embodiment**.
- The lecture includes information about the **research group** at the Lehrstuhl für Autonome Systeme und Mechatronik (ASM) at FAU Erlangen-Nürnberg.

### **Research at ASM**

- Research at ASM focuses on **components and control, interfaces and interaction, wearable systems, and cognitive systems**.
- The curriculum at ASM includes modules on fundamental and specialised topics, such as:
    - **Fundamental modules**: Grundlagen der Elektrotechnik III, Sensorik, Mechatronic Components and Systems, Electrical Engineering II.
    - **Specialisation modules**: Robot Mechanisms and user Interfaces, Human-centered Mechatronics and Robotics, Autonomous Systems: From Research to Products.
    - **Laboratories**: Grundlagen der Elektrotechnik III, Automatisierungstechnik, Sensorik.
    - **Seminars**: Autonomous Systems and Mechatronics, Human-Robot Interaction.

### **What is Embodiment?**

- **Embodiment** is defined as the sense of owning and perceiving one's own body.
- It involves two key concepts:
    - **Body schema**: A subconscious model of body properties.
    - **Body image**: The perception of one's own outer appearance.

### **Why is Embodiment Important?**

- **Embodied cognition** suggests that the human mind is largely determined by the structures of the human body, including morphology, sensory and motor systems, and interactions with the physical environment.

### **Studying Embodiment**

- The lecture mentions studies by Kim et al. (2020) and Khoury et al. (2022) as relevant to the study of embodiment.

### **The Rubber Hand Illusion**

- The **rubber hand illusion** is a well-known paradigm used to study embodiment by inducing the feeling of ownership of an artificial limb.
- During the illusion, stimulation of an artificial hand leads to the illusion that it is part of one's own body.
- It also causes a tendency to locate the real limb closer to the artificial limb.
- **Embodiment** in this context is caused by the **multisensory integration** of vision, touch, and proprioception.
- Various factors can modulate the experience of the participants.

### **Factors Influencing the Illusion**

- **Peripersonal space**, which is the space surrounding a person used to avoid collisions and protect from potential threats, adapts with experience and can influence the illusion.
- **Cognitive modelling** is used to understand which factors are important in the illusion.

### **Cognitive Modeling**

- **Cognitive science** is a multidisciplinary approach to studying the mind, incorporating disciplines such as psychology, philosophy, linguistics, anthropology, neuroscience, and artificial intelligence.
- **Cognitive models** can be computational, mathematical, or verbal-conceptual.
    - **Computational models** present mechanistic and process details.
    - **Mathematical models** describe the relationship between variables using equations.
    - **Verbal-conceptual models** describe entities, relations, or processes in natural language.

### **Bayesian Modeling**

- **Bayes' Theorem** is used in modeling the rubber hand illusion. The theorem is expressed as:
    - P(A|B) = [P(B|A) * P(A)] / P(B)
    - Where, for example, P(Rain|Cloud) can be calculated using P(Cloud|Rain), P(Rain) and P(Cloud).
- Bayesian inference modeling is often used for multisensory integration.

### **The Robotic Limb Illusion**

- **Robotic prostheses** are studied as a way to regain functionality after limb loss, as rubber limbs may not be sufficient.
- This approach adds active movement by the participant to the rubber limb illusion.
- Research includes the study of **robotic prostheses** for the leg and arm.

### **Robotic Leg Illusion Experiment**

- Participants perform **squats** while a robotic leg mirrors their movements.
- Vision is focused on the **robotic leg**.
- The experiment uses both **close** (17.5 cm) and **far** (35 cm) distances for the robotic leg.
- **Measurements** include **proprioceptive drift** and an **embodiment questionnaire**.
- The study has a **within-subject design** and includes factors for **synchronous** and **asynchronous** motion of the robotic leg.

### **Hypotheses and Results of Robotic Leg Experiment**

- **Hypothesis 1**: Proprioceptive drift (PPD) is significantly larger with synchronous movement of the robotic leg.
- **Hypothesis 2**: Subjectively perceived embodiment is significantly stronger with synchronous movement of the robotic leg.
- Auditory perception of sounds from the robotic limb may also have an effect.
- The likelihood of the rubber/robotic limb being embodied and proprioceptive drift are predicted using Bayesian inference.

### **Modeling the Robotic Limb Illusion**

- **Bayesian inference modeling** is used to predict the likelihood of the rubber/robotic limb being embodied and proprioceptive drift.
- The model takes into account the likelihood of perceived visual information, proprioceptive information, visual timing and tactile timing.
- Priors in the model include:
    - **Uniform prior**: All hand positions are equally likely.
    - **Conceptually-informed prior**: Hand positions around the expected location are most likely.
    - **Empirical-informed prior**: Hand positions around the pre-test localisation are most likely.
- The model can be used for **active motion** (robotic illusion).
- **Informed priors** improve results of the model.
- The **visual prior** influences the results significantly.
- Integration for both distances predicted for higher visual variance.

### **Robotic Hand Illusion**

- Experiments with the robotic hand involve 5 positions for the robotic and real hand.
- These experiments use a **full factorial design** with both **synchronous** and **asynchronous** conditions.

### **Structurally Varying Bodies**

- Research also includes studies of embodiment in structurally varying bodies.

---
## **Lecture 10: Functional Assessment**


### **Introduction to Functional Assessment**

- This lecture focuses on **functional assessment** in the context of human-robot co-adaptation.
- It explores how to measure the effectiveness of rehabilitation devices.
- The lecture covers both **objective and subjective metrics**, as well as learning curves.

### **Key Questions for Functional Assessment**

- How do we know if a rehabilitation device is effective?
- How do we measure the quality of a rehabilitation system?
- What should patients do in functional assessments?
- How do we measure significant improvement?

### **Standardised Tests**

- To measure the effectiveness of a rehabilitation system, **standardised tests** are issued to patients using a specific prosthetic solution.
- These tests allow comparison of a patient's performance to average values, or normative data.
- When evaluating a test, it is essential to consider its:
    - **Standardisability**
    - **Inter-rater reliability**
    - **Intra-rater reliability**
    - **Test-retest reliability**
    - **Internal consistency**

### **Useful Metrics**

- To assess a patient's performance, it's useful to compare their results to:
    - The average performance of able-bodied individuals
    - The average performance of patients with similar conditions
    - The patient's own previous performance

### **Specific Functional Assessment Protocols**

- Several functional assessment protocols are available for testing upper limb function. These include:
    - **Box and Blocks Test (BBT)**: This test involves moving as many blocks as possible from one side of a box to the other using only one hand in one minute. This test measures manual dexterity.
    - The BBT is described in Mathiowetz et al., 1985.
    - **Southampton Hand Assessment Procedure (SHAP)**: This test requires the patient to perform a series of single-handed tasks as quickly as possible while being timed.
        - The SHAP is detailed in Light et al., 2002.
    - **Clothespin Relocation Test (CRT)**: Involves grasping, carrying, and releasing a clothespin from one rod to another and involves wrist pronation/supination.
        - The CRT is described in Kuiken et al., 2005.
    - **Assessment of Capacity for Myoelectric Control (ACMC)**: A less structured assessment where patients perform daily-living activities while a rater evaluates their performance.
        - The ACMC is discussed in Hermansson et al., 2005.
    - **Fugl-Meyer Assessment:** This assessment is used for measuring motor recovery after stroke.
        ssments/fugl-meyer-assessment-of-sensorim otor-recovery-after-stroke-fma
    - **Wolf Motor Function Test:** This test is specifically designed for assessing upper extremity function.

### **Limitations of Current Assessments**

- Current functional assessments still lack:
    - **Realism**: They don’t always fully reflect daily-living and occupational activities.
    - **Objective assessment**: More objective measures, such as motion tracking and gaze tracking are needed.
    - **Tracking changes**: The assessments should track changes and adaptations in the myocontrol system.
### **Lower Limb Exoskeletons**

- Research also includes the use of robotic exoskeletons for lower limb rehabilitation following stroke.
- One study focuses on the use of robotic exoskeletons for overground walking in stroke patients.
    - This work was done by Nolan et al. in 2021.

### **Upper Limb Rehabilitation**

- Upper limb rehabilitation involves assisting the patient to perform tasks, either through pre-programmed movements or by detecting the patient's intent.
- The goal is to gradually reduce the amount of assistance provided, encouraging the patient to use their own strength.
- Tasks for upper limb rehabilitation are not typically periodical or cyclical.
- While serious games are sometimes used, their usefulness is still being evaluated.
- Simple solutions can often be quite effective.

### **Effectiveness of Upper Limb Robotic Rehabilitation**

- The effectiveness of upper limb robotic rehabilitation after stroke has been investigated in clinical trials.
- One multicenter, randomized clinical trial was conducted by Aprile et al. in 2020.
