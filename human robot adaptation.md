## 1. Introduction

- The course focuses on **human-robot co-adaptation**, particularly within the field of rehabilitation and assistive robotics.
- **Rehabilitation robotics** is considered an instance of **translational medicine**, aiming to bring ideas, concepts, and technologies from robotics into rehabilitation.
- The course explores devices such as **prostheses, exoskeletons**, and **virtual reality** for rehabilitation.
- **Medical robotics** encompasses robots working with or for people, including surgical robots, prosthetics, exoskeletons and care robots.
- The course will address key questions including:
    - How to build effective devices
    - How to control these devices, sharing control between the patient, therapist and device
    - How to measure effectiveness, usability, and acceptance of the devices
- **Rehab/Assistive Robotics** combines mechatronics, medicine, psychology, and mathematics. It involves both basic research and applied research, with a strong emphasis on user studies and clinical deployment.
- **Basic research** includes understanding patient needs, connecting to nerves and muscles through neuroscience, and using AI to interpret neural signals
- **Making it work** focuses on putting the patient at the center of research, testing devices in the field, and ensuring medical robots are useful outside of a lab.
- Key aspects of devices include making them ergonomic, comfortable, usable, friendly, intuitive, light, and unobtrusive, while ensuring precision, repeatability, smoothness, and "humanoidness" of motion.
- The interface should allow the patient to choose their actions, utilise biosignals, and incorporate AI to adapt to the patient over time.
- **Prosthetics** is considered a frontier for interfacing humans and machines, requiring body-compatibility and the use of body signals. Reliability is paramount for prosthetics due to the risk of trauma or accident.
- **Co-adaptation** is essential. This involves devices that learn from the user and interfaces that adapt to the user as the user learns to use them. This concept applies to surgical robots, walking exoskeletons and rehabilitation devices.
- The **user is a teacher for medical robots, and a learner from them**.
- **The main takeaway of the introduction is that human-robot interaction is a crucial paradigm to explore**
- The lecture provides an introduction, an overview of Rehabilitation and Assistive Robotics (RAR), the motivation behind the course, and why co-adaptation is important

These notes should provide a good overview of the key concepts discussed in the introduction to the Human-Robot Co-Adaptation course.

---

## 3. Intent Detection

- **Intent detection** involves using sensors to control a device by associating stable, repeatable signal patterns to desired actions and their intensities.
- Every action in mammals is achieved through movement, which is caused by muscle activity. Therefore, sensors must detect signals related to muscle activity, which include electrical, mechanical, and optical patterns.
- **Machine learning** plays a significant role in intent detection, so the data collected and the semantics given to it through labelling are critical.
- Data is usually labelled either manually or mechanically using sensors, but in this context, it's more complex, as data and semantics are user-dependent.
- **The process of intent detection**: A user wants to perform a specific action, which activates muscles, generating a detectable signal pattern that is associated with the intended action.
- **A key challenge is that disabled persons cannot usually produce reliable ground-truth**. It is difficult to know what they want to do because they may lack sensori-motor feedback, or have incorrect or painful feedback. Therefore, researchers must ask or induce the user to reveal their intent.
- Experimental protocols induce users to perform actions, and signals recorded in close time proximity are associated with the requested action. Errors in labelling are corrected by collecting more data and updating the model.
- **Three methods for inducing actions in amputees:**
    - Imitating the experimenter's hand
    - Performing bilaterally symmetric actions
    - Looking at a mirror
- **Offline vs. online intent detection is a big problem**:
    - **Offline intent detection** involves inducing a user to do something, recording the signals, and then using part of the data to map signals to actions. The model is then evaluated on the remaining data. This approach is not very useful and has essentially no correlation with online performance measures, making it a waste of time and effort.
    - **Online intent detection** involves continuous interaction where the user remains in the experiment, all data is used to update the mapping, and the model is tested in real-life conditions.
- **Residual limb muscle activity** is surprisingly rich and diverse, even decades after amputation. The more proximal the amputation, the harder it is to detect relevant residual activity.
- **Electromyography (EMG)**:
    - EMG signals are related to muscle contraction, with a bandwidth of 15-450Hz and an amplitude of 1µV-10mV.
    - The frequency and amplitude denote the intensity of muscle contraction.
    - Processing involves bandpass filtering, rectification, and low-pass filtering.
    - The averaged rectified value (ARV) is roughly proportional to the intensity of muscle contraction.
- **Force Myography (FMG)**:
    - Muscle activation causes deformation, which can be measured using pressure sensors.
    - Potential advantages over EMG include being less influenced by fatigue and sweat, and having simpler, cheaper electronics.
    - Whether FMG is better or worse than sEMG is still controversial.
- **Ultrasound Scanning**:
    - Ultrasound provides "deep" information using tomography.
    - High-frequency pressure waves are injected into the body, and the echo is detected, using a transducer to emit and detect.
    - By timing the emission and detection, an image can be formed.
- **Pros and cons of different methods:**
    - FMG: cheap, high density, stable, but prone to movement artefacts and unclear features.
    - US: extremely rich in information, easy digital processing, but not cheap and has miniaturisation issues.
- **Intent detection pipeline**:
    - Involves preprocessing input signals, extracting features, non-linear mapping, and classification or regression.
- **Classification** maps signals to actions. It involves mapping a D-dimensional signal to an action.
- Many classification approaches have been tried on EMG.
- Commercially available pattern recognition systems use on-demand recalibration.
- **The main challenges in intent detection include reliability, and only after that comes dexterity**.

These notes should provide a concise overview of the key concepts covered in the third lecture of the Human-Robot Co-Adaptation course.

---
## 4. Somatosensory Feedback

- The lecture focuses on closing the **human-in-the-loop** loop through somatosensory feedback.
- The course explores different **types of actuators and feedback**, as well as what information is most useful to feed back to the user.
- **Visual and auditory feedback** are already present in many devices; users can see what the devices are doing, and hear the noise of the motors. However, this may not always be the case, and users may not want or need this type of feedback.
- Direct stimuli on the body can be provided to simulate **proprioception and touch**.
- Users naturally perceive the **weight and resistance** of a prosthesis or rehabilitation device.
- **Force-feedback** is available "for free" in some cases, such as body-powered prostheses.
- There are **many different receptors in the limbs**, and more afferent (sensory) axons than efferent (motor) ones in the forearm.
- **Lack of somatosensory feedback** can make motion essentially impossible.
- **Fake somatosensory feedback** can trick the user.
- **Sensory substitution** can be useful.
- There are essentially **two ways of providing somatosensory feedback**:
    - Mechanical (vibrotactile, indenting)
    - Electrical (small currents through the skin)
- Research shows that adding **vibrotactile feedback** to a myoelectric-controlled hand can improve performance when visual feedback is disturbed.
- **Artificial redirection of sensation** from prosthetic fingers to the phantom hand map can be achieved through vibrotactile or mechanotactile feedback.
- **Electrotactile EMG feedback** can improve the control of prosthesis grasping force.
- The lecture also considers whether the current methods for providing feedback are effective and practical.
- The lecture explores **actuators** and the **somatosensory response**, what to feed back to the user, and the effectiveness and practicality of these methods.
- Key references for somatosensory feedback include the works of Raspopovic, Valle, and Petrini; Gesslbauer et al.; Botvinick and Cohen; Bach-y-Rita; Raveh, Portnoy and Friedman; Antfolk et al.; and Schweisfurth et al..

These notes should help with exam preparation by summarising the key concepts of somatosensory feedback in the context of human-robot co-adaptation.

---
## 5. Closing the Loop

Okay, here are some notes on lecture 05, "closing the loop," with an emphasis on easy-to-memorise points, and some extrapolation:

**Core Concept: Human-in-the-Loop**

- The main challenge in human-robot co-adaptation is that we're dealing with a complex system with a human in the loop. This means the system isn't just about the device, but also how a human interacts with it.
- It is difficult to create a comprehensive mathematical model of this system. Instead, the focus should be on creating a dynamic environment that allows for the user to teach and control the device.
- The system requires a feedback loop consisting of sensors, actuators, and processing.

**What is Co-adaptation?**

- Co-adaptation is the dynamic process of the **user learning to control the device** while **the device learns from the user**.
- It involves a continuous exchange of information between the user and the device.
- A key aim is to achieve a steady state, where the user is happy with the control and the device is confident in its predictions.

**Why is Co-adaptation Important?**

- It is essential because **humans and machines must adapt to each other** for effective human-robot interaction. This is crucial for any medical robot, including surgical robots, exoskeletons, rehabilitation devices and prostheses.
- Co-adaptation is needed so that interfaces can learn from users and vice-versa.

**Measuring Co-adaptation**

- Co-adaptation can be measured through various objective and subjective means.
    
    - **Objective measures:**
        - Success rate in completing tasks
        - Time taken to complete a task
        - Smoothness and "naturalness" of movement
    - **Subjective measures:**
        - Usability, ease of use, and user-friendliness of the device
        - The user's feeling of embodiment or control over the device
    - **User’s Internal measures:**
        - Separation of action-related clusters in control signals
        - Repeatability of action-related clusters
        - Coverage of the input space
    - **Device's internal measures:**
        - Changes in the signal-to-action map
- Changes in user's muscle signals (EMG) and performance (accuracy and stability) are also indicators of co-adaptation.
    
- It is important to measure the changes in the user's signals, performance and muscle activation patterns over time.
    
- The user's ability to adapt to new situations and achieve difficult tasks is a measure of successful co-adaptation.
    

**Key Insights from Research**

- **Regression is better than classification** for co-adaptation. This is because it allows more interaction in the control loop.
- **User adaptation is crucial,** and users can adapt to different situations.
- The brain is **plastic**, therefore it is vital to encourage the user to learn through experience and not overwhelm them with information.

**Extrapolation and Key Takeaways**

- **Focus on User Experience:** The design of the device should prioritise the user's needs, provide a positive experience, and make the user feel in control.
- **Importance of Feedback:** Sensory feedback, both visual, auditory and somatosensory (touch and proprioception), plays a key role in effective co-adaptation.
- **Real-world testing:** It is crucial to test devices outside of the lab in real-world conditions that are meaningful and ecologically valid.
- **Personalised and Adaptive Systems:** Co-adaptation is about creating personalized systems that are tailored to the specific needs and characteristics of each user.

**In summary, co-adaptation is:**

- **A two-way learning process** between user and device.
- **Essential for effective human-robot interaction**.
- **Measurable** through objective and subjective factors.
- **Enhanced by a user-centered approach**, good feedback, and a focus on real-world application.
- **Facilitated when the system is allowed to adapt to the user**, rather than expecting the user to adapt to the system.



----
## 6. User- Centered Design

User-centered design (UCD) focuses on designing products and services that are easy to use and efficient for their intended users. It emphasises human needs in real contexts, and requires ecologically valid settings, similar to real-world scenarios, to understand these needs and match user expectations.

Here are some key aspects of user-centered design discussed in the sources:

- **Usability** is a crucial concept, defined by the International Organisation for Standardisation (ISO) as the effectiveness, efficiency, and satisfaction with which users can achieve specific goals in a particular environment.
    - **Effectiveness** refers to doing the expected task.
    - **Efficiency** is achieving the task with minimal resources.
    - **Satisfaction** involves maximal enjoyment.
    - Usability also considers **learnability** (learning quickly), **memorability** (recollecting easily), and minimising **errors**.
- **User Experience (UX)** is about the reactions and expectations that influence the use of a product, and should fulfill user needs and provide a positive and meaningful experience.
- **Design Considerations** include establishing constraints and invitations to use (affordances) that hinder or facilitate interactions between users and tools, typically within the user interface. It is crucial to design for human minds, considering that the interactions between humans and tools are not always predictable or optimal.
- **Accessibility** is also a key consideration, and it is noted that by solving problems for one group of users, solutions for others can be found.
- **Context** is vital and that products, devices, services, and environments should be usable by people with temporary, situational, or permanent limitations.
	- **Ergonomics and Human Factors** are interdisciplinary approaches that consider human skills, limitations, and needs in real contexts. They aim to improve human well-being and system performance.
    - Ergonomics includes physical, cognitive, and organisational branches.
    - **Physical ergonomics** focuses on human physical features.
    - **Cognitive ergonomics** focuses on human mental processes.
    - **Organisational ergonomics** focuses on socio-technical systems and processes.
- **Limitations and Actions:** Users need to be informed about what they can do and what consequences their actions have, and they should be in optimal mental and physical condition to make rational decisions and avoid risks. They also need to be trained to work with a system at their best and instruct the system to work autonomously.
- **Neuroergonomics** is an approach that uses neuroscientific methods to investigate and design interactions between humans and systems in real-world contexts. It includes assessing interactions, training users, and making systems able to adapt to users. It also aims to increase neuroscientific knowledge. Neuroergonomics emphasizes the need for data on users' actions and reactions, which must be ecologically valid, meaningful, significant, and temporally associated with specific events.
- **Value-Sensitive Design** is important, as ergonomics (and neuroergonomics) involve values such as well-being, accessibility, and safety, which should be translated into human-centered design principles.

The sources also highlight that systems should be designed to consider human cognitive limitations, like the fact that people can typically manage 7±2 chunks of information. If a system exceeds these capabilities, it can lead to high workload and errors.

In summary, user-centered design prioritises the user's needs, abilities, and limitations, and aims to create usable, effective, and enjoyable experiences while considering real-world contexts and ethical considerations.


---

## 7. User Centered Rehabilitation Robotics
	

- **Medical Needs and Conditions**
    
    - Rehabilitation robots are needed due to various conditions like trauma, musculoskeletal degeneration (e.g., ALS), stroke, spinal cord injury (SCI), and traumatic brain injury (TBI).
    - There are 30 million people worldwide in need of prosthetic or orthotic devices.
    - A significant number of amputations occur annually in the USA and EU, with 25% affecting the upper limb.
    - Spinal cord injuries affect up to 500,000 people each year, particularly young and older adults, resulting in loss of movement and sensation, altered bodily functions, and pain.
    - Stroke affects 15 million people globally each year, with 70% surviving with long-term disabilities including paralysis, cognitive issues, speech problems, and emotional difficulties.
- **Rehabilitation Technologies**
    
    - ==Rehabilitation technologies== include ==virtual and augmented reality== settings, robotic systems, ==wearable robots==, and end-effectors.
    - **Rehabilitation robots** are composed of links connected by ==rotational or prismatic joints==.
    - The lecture discusses ==forward kinematics== (calculating end-effector configuration from joint space) and ==inverse kinematics== (calculating ==joint parameters== from ==Cartesian space==).
    - ==Iterative methods== are needed to solve ==inverse kinematics== when analytical solutions are not available, using the Jacobian matrix.
    - The lecture also discusses generalized forces and torques acting on the end effector, and the importance of system dynamics for compensating effects like gravity and inertia.
    - The use of the ==Lagrange formalism== is mentioned to ==derive the system dynamics==.
    - ==Impedance control,== which is characterized by the equation ==_F(t) = mẍ + bẋ + kx_== is also mentioned.
- **User-Centered Design and Evaluation**
    
    - The lecture stresses that for rehabilitation robots to be truly user-centered, ==mental workload== and ==user engagement== must be considered.
    - ==The Technology Acceptance Model (TAM)== and ==System Usability Scale (SUS)== are used for ==evaluating== ==user experience== with the robots, assessing factors like perceived ease of use and complexity.
- Mental workload is another important consideration in using rehabilitation robots.
    
- Studies have shown that using medical ==exoskeletons== can increase ==functional== ==connectivity== in the brain of ==stroke== ==patients== but can ==increase mental workload without any changes== in gait for spinal cord injury patients.
    
- **User engagement** is seen as important and should involve final users and stakeholders like clinicians in co-design.
    
- ==Self-Determination Theory== suggests that motivation, ==engagement==, feeling competent, autonomous, and in a relationship are important for the ==rehabilitation process==.
    
- **Engagement Strategies**
    
    - ==Playful engagement==, social robots, serious games, and gamification are suggested methods to enhance user engagement and sustain effort.
    - ==Digital therapeutics== can leverage engaging settings, controlled conditions, and personalized difficulty to improve clinical outcomes.
    - ==VR/XR technologies== can be used to engage patients in robot use for prosthetic training and rehabilitation.
    - 
- **Rehabilitation Neurotechnologies**
    
    - ==Rehabilitation neurotechnologies==, including monitoring biosignals, providing multimodal stimulations, and guiding motor-cognitive exercises can improve neural plasticity.
    - ==Peripheral neuroergonomics== and co-adaptive interaction are also important aspects of rehabilitation.

**Advantages of Rehabilitation Robotics** * Rehabilitation robots can enable occupational therapy, allow free movement in a large workspace, and provide gravity compensation. * They adhere to safety standards and offer richer indices on patient progress, data-driven AI strategies, and "assistance-as-needed". * They offer the potential for novel assistive applications, better cost-benefit ratios, synergies with neuroadaptive systems, home rehabilitation, and virtual/augmented settings.



---

## 8. Methods for User Studies

- The lecture focuses on methods for making rehabilitation robots **user-centred**.
- The topics covered include **mental workload, engagement**, and how to design machines that are truly user-centered.
- The lecture begins by highlighting that there are **30 million people worldwide in need of a prosthetic or orthotic device**.
- In the USA and Europe, there are **300,000 amputations every year, with 25% affecting the upper limbs**.
- **Spinal cord injuries (SCI)** affect up to 500,000 people worldwide each year, most often young people (15-30 y.o.) and older adults (60+).
- **Stroke** affects 15 million people worldwide annually, with about 70% surviving with long-term disabilities.
- **Medical reasons** for the usage of exoskeletons include trauma, musculoskeletal degeneration, stroke, spinal cord injury, and traumatic brain injury (TBI).
- **Spinal cord injuries (SCI)** can result in loss of movement, altered sensation, loss of bowel or bladder control, changes in sexual function, pain, and difficulties breathing.
- **Strokes** can lead to paralysis, cognitive and emotional issues, speech problems, and issues with bladder and bowel control.
- **Rehabilitation technologies** include virtual and augmented settings, robotic systems, wearable robots, and end-effectors.
- **Rehabilitation robots** often involve a finite number of links of length connected by rotational or prismatic joints.
- The **configuration of a robot's end-effector** is denoted as _e_, and the **position of the joints** is denoted as _θ_.
- The **control of rehabilitation robots** often involves translating a desired configuration in Cartesian space into a configuration in joint space.
- A **vector of generalised forces** or wrenches acting on the end effector is denoted as _F_, and a vector of generalised torques acting on the joints is denoted as _τ_.
- **Forward kinematics** is the computation of the end-effector's configuration in Cartesian space from a given configuration in joint space.
- **Inverse kinematics** is the computation of a set of joint parameters from a given configuration in Cartesian space.
- **Iterative methods**, using the **Jacobian matrix**, are often necessary to solve the inverse kinematics problem.
- The **system dynamics** must be derived in order to compensate for the effects of gravity, inertia and gyroscopic forces.
- **Lagrange formalism** can be used to derive the system dynamics, based on the kinetic and potential energy.
- **Impedance control** is used in physical human-robot interaction.
- **Kinematics and neuromusculoskeletal models** map between muscle space, joint space, and task space.
- **Combining exoskeletons and end-effectors** can enable occupational therapy, provide a large workspace, offer gravity compensation, and comply with safety standards.
- Advantages of **rehabilitation robotics** include richer indices on patient progress, data-driven strategies, "assistance-as-needed", potential for novel applications, cost-benefit improvements, synergies with neuroadaptive systems and virtual settings, and options for home rehabilitation.
- **Technology Acceptance Models (TAM)** and **user-centered design** are key aspects of evaluating a system.
- **Questionnaires** such as the System Usability Scale are used to assess rehabilitation robots.
- **Mental workload** is an important consideration in the design of medical and occupational exoskeletons. Increased functional connectivity between different brain regions can indicate increased mental workload in SCI patients.
- **User engagement** is a crucial step away from workload, and co-design processes must involve final users and clinicians.
- **Self-determination theory** highlights the importance of motivation, engagement, feeling competent, autonomous, and in relationship for user engagement.
- **Playful engagement**, social robots, and serious games can sustain user effort.
- **Digital therapeutics** use engaging settings to empower functional recovery, with controlled conditions, personalised difficulty, data-driven digital biomarkers, distraction from fatigue and pain, and low cost and portable technologies.
- **VR/XR** offers advantages in prosthetic training and rehabilitation by enabling embodied training and promoting technology acceptance.
- **Rehabilitation neurotechnologies** influence the nervous system by monitoring biosignals and guiding motor-cognitive exercises based on neural principles.
- **Peripheral neuroergonomics** and **co-adaptive interaction** are also important for integration.


---

## 10. Functional Assessment

- The lecture focuses on how to measure the effectiveness of a rehabilitation device.
- **Standardised tests** are issued to patients using a specific prosthetic solution.
- Useful metrics include:
    - How able-bodied people perform on average.
    - How average patients in the same conditions perform on average.
    - How the specific patient performs, and how they compare to the average values (normative data).
- The **validity of a test** is assessed by:
    - Standardisability.
    - Inter-rater reliability.
    - Intra-rater reliability.
    - Test-retest reliability.
- Specific functional assessment protocols include:
    - **Box and Blocks Test (BBT)**: Moving as many blocks as possible from one side of a box to the other in one minute, using one hand only.
    - **Southampton Hand Assessment Procedure (SHAP)**: Performing a series of single-handed tasks on a table as quickly as possible, while timing.
    - **Clothespin Relocation Test (CRT)**: Grasping, carrying, and releasing a clothespin from one rod to another, involving wrist pronation and supination.
    - **Assessment of Capacity for Myoelectric Control (ACMC)**: Performing daily-living-like activities while a rater assesses performance.
    - **Fugl-Meyer Assessment**: A well-known assessment protocol for motor recovery after stroke.
    - **Wolf Motor Function Test**: A test specifically for the upper extremity.
- There is a need for more **realistic assessments** that adhere to daily-living and occupational activities.
- **Objective assessments** are also needed, such as motion tracking and gaze tracking.
- There is a need for **tracking changes and adaptation** in the (ML-based) myocontrol system.
- The lecture notes ask, "_so just what do we try and have patients do?_" and, "_how do we measure whether our system yields a significant improvement?_"
- Functional assessment protocols and tests must have good:
    - Internal consistency.
    - Inter-rater consistency.
    - Test-retest reliability.
- **Effectiveness** of upper limb robotic rehabilitation after stroke has been studied in a multicenter, randomized clinical trial.
- The key lesson is that there is a need for ways to assess the effectiveness of a system and match it against a baseline, against time, and against competitors.
- **Co-adaptation** is achieved when the improvement in functional assessment matches the changes in the system and the signals produced by the user.
- **Electromyography (EMG)** signals can be recorded from an amputated person at the beginning and end of a myocontrol experiment.
- **Lower-limb exoskeletons** are also relevant. The use of robotic exoskeletons for overground walking in acute and chronic stroke has been researched.
- **Upper-limb rehabilitation** is similar to lower limb rehabilitation, with the goal of helping the patient do things either pre-programmed or detected through intent detection.
- Upper limb rehabilitation is designed to induce the patient to gradually use their own strength over time.
- Tasks for upper limb rehabilitation are not usually periodical or cyclical.
- Serious games are sometimes used but their usefulness is still questionable.
- Simple solutions for upper limb rehabilitation can work quite well.
- Examples of upper limb rehabilitation that aid mobility after stroke can be found at https://www.hmw.it/en/robotic-neurorehabilitation/motore.
- The lecture references the website https://www.sralab.org/rehabilitation-measures for more functional assessment protocols.
