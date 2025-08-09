

**Surgical Process Models (SPMs)** are defined as **simplified, formal, or semiformal representations of a network of surgery-related activities**. These activities are **sequential and parallel** and executed by clinical and technical team members with different expertise. SPMs reflect a predefined subset of interest and offer qualifiable and quantifiable information on the course of an intervention.

**Motivation for SPMs:**

- **Clinical:** Modelling, analysis and organisation of resources (OR management) and surgical training and assessment.
- **Technical:** Requirements analysis, product specification and devices (quantifiable data and processes), comparison between different surgical strategies/use-cases, prerequisite for automation / robotic assistance in the OR, and models can be stored, shared, and refined.

**Workflow/Process Modelling** is a **simplified (formal or semiformal) representation of a suitable excerpt of reality using a suitable method for representation**. Modelling strategies are characterised by granularity levels, data acquisition methods, modelling approach, model representation, and generalisation.

**Five Concepts of Surgical Process Modeling:**

1. **Granularity Level:** Defines the **level of detail** of the description of a procedure, chosen according to the purpose of a study. It has a hierarchical decomposition: Procedure, Phase, Step, Activity/Task, Motion.
2. **Data Acquisition:** Methods to gather information about the surgical intervention. These include **observer-based data acquisition** (better insight into ergonomics and human interaction, but prone to human error) and **sensor-based data acquisition** (video recording, tracking, audio, robot-supported recording, patient-monitoring systems). Key aspects to observe for modelling include what is done (functional), who is performing the task (organisational), instruments used (operational), where it is performed (spatial), and how long the workstep is (temporal).
3. **Model Representation:** The way the system behaviour is described. This can be through **symbolical models** (plain text, easier to comprehend but relations not fully defined) or **numeric models** (numbers and mathematical relations, detailed relations, basis for simulation, but reduced flexibility).
4. **Modelling Approach:** How the model is created. **Top-Down Modelling** breaks down a complex process into individual tasks, relies on experienced clinicians, is flexible but has low quantification and can be subjective. **Bottom-Up Modelling** describes individual steps linked together based on data and knowledge abstraction algorithms, offering quantifiable steps and high precision but can be very complex and requires large data.
5. **Generalization:** Addressing the fact that each treatment is a unique process. This leads to the concepts of **patient-individual SPM (iSPM)** and **generalized SPM (gSPM)**, which is a statistical combination of several iSPMs calculating transition frequency.

**Modelling Languages:** Many different modelling languages exist. Widely used examples include **Extensible Markup Language (XML)**, **Unified Modeling Language (UML)**, and **Business Process Model and Notation (BPMN)**. The appropriate language should be chosen according to the task.

**Unified Modeling Language (UML)** is a **standardized graphical language for specifying, visualizing, constructing and documenting software systems and processes**. It allows for a simplified description of surgical processes through various diagrams. Key UML diagram types for surgical process modelling include:

- **Class Diagram:** Provides an **analysis of an application**, offering a **static view** and visualising the **responsibilities of a system**. It is used to describe all entities or classes present in the system.
- **Activity Diagram:** Shows the **workflow from start to end point**, detailing several decision paths. It highlights decision points, parallel tasks, and end results, where an action represents a single step.

**Learning Approaches:**

- **Hidden Markov Models (HMM):** A statistical description used to **learn about hidden states from observations**. They are used to **classify and generate time series (sequence)**. HMMs are defined by a quintuplet (N, M, A, B, 𝜋) representing the number of hidden states, observation probabilities, transition probabilities, probability distribution over observations, and initial state distribution. Use cases for HMM in surgery include skill assessment and training, automatic phase detection, surgical workflow analysis, and tool usage patterns.
- **Decision Trees:** A **non-parametric supervised learning algorithm used for classification and regression tasks** with a hierarchical tree structure. They can be used in surgical decision-making to identify the probability threshold for intervention. Advantages include being easy to understand and requiring little data preprocessing, while disadvantages include overfitting, instability, and bias.
- **Random Forests:** An **ensemble learning method** that constructs a multitude of decision trees during training and outputs the mode of classes or mean prediction. It reduces overfitting and handles large datasets efficiently.

**Surgical Datasets:** Challenges include class imbalance, patient-individual vs. generalised process model variations, input noise, incompatibility of different data sources, annotation quality and cost, granularity of phases, and the size of datasets.

**Example Scenario: External Ventricular Drain Placement:** This exercise involves watching a video of the procedure and formalising all classes present in the system using UML class diagrams and the workflow using UML activity diagrams or BPMN. Teachable Machine (provided by Google) is suggested as an easy-to-train online classifier for tasks like phase recognition, particularly using an image-based classifier.

**Key Take-Aways:** Surgical Process Models are essential for understanding and improving surgical workflows. Their creation involves considering granularity, data acquisition, model representation, and the chosen modelling approach. Learning approaches like HMMs and Random Forests can be applied to analyse and understand surgical processes and phases.