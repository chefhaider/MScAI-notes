


---

**Early Inspiration for AI:** Humans have long dreamt of artificial intelligence and living machines. Mary Shelley's _Frankenstein_ (1818) can be interpreted as an early mention of the desire to infuse life into inanimate bodies. Marvin Minsky (1970) optimistically predicted machines with the general intelligence of an average human within a few years and even speculated about them keeping us as pets.

**History of AI:** The field has evolved through several periods:

- **Foundation (1950s):** The **Turing Test** (1950) was established, and the term **"Artificial Intelligence"** was suggested by McCarthy and Minsky in 1956.
- **Early Optimism (1960s):** Programs like **ELIZA** (emulating a psychotherapist, 1966) and **SHRDLU** (natural language understanding, 1968-1970) demonstrated early progress.
- **AI Winter & Reality Checks (1970s):** Difficulties in achieving early goals led to a reduction in funding for AI research. **Expert systems**, based on specific domain knowledge and rules, emerged towards the end of this period.
- **Resurgence of AI (1980s):** Expert systems became popular.
- **Improvements (1990s):**
- **Big Data & Deep Learning (2000s):** Advancements in neural networks led to the rise of **deep learning**, and significant progress was made in computer vision.
- **AI Breakthroughs and Ethics:** AI became integral in many industries, with growing concerns over AI ethics and societal impacts. The **Nobel Prize in 2024** was awarded for foundational discoveries enabling machine learning with artificial neural networks.

**Definitions:**

- **Artificial Intelligence (AI):** Aims to **simulate human-like intelligent behaviour and critical thinking**. It is the **ability of a machine to imitate intelligent human behaviour**.
- **Machine Learning (ML):** A **sub-set of AI that enables computers to learn from data, identify patterns, and make predictions or decisions without explicit programming** (e.g., statistical methods). Learning improves through experience/data.
- **Deep Learning (DL):** An **application of ML that uses deep neural nets with multiple layers to train a complex model and learn automatically from data**.

**Types of AI:**

- **Knowledge-based AI:** Models human knowledge through input and formalisation of expert knowledge, using a large set of complex rules imitating human intelligence. Similar to early expert systems.
- **Data-driven AI:** Learns patterns in large amounts of data and uses these for predictions, utilising machine learning (and deep learning).
- **Symbolic AI:** Includes expert systems, knowledge bases, and reasoning/logic.
- **Natural Language Processing (NLP):** Focuses on text generation, question answering, context extraction, etc..
- **Vision:** Includes image recognition and computer vision, often using deep learning.
- **Speech:** Encompasses speech-to-text and text-to-speech technologies.

**What is Learning (in ML):** Learning involves memorising, learning facts through exploration, improving skills through practice, and organising new knowledge into general representations. Learning systems acquire data and information from examples and use them to perform better in the future. It is a purposeful process leading to behaviour change based on experience. In ML, behaviour refers to predictions, decisions, actions, and experience refers to data from a learning algorithm.

**Inductive and Deductive Reasoning:**

- **Inductive reasoning:** Derives a **general principle from a number of observations**. ML often falls into this category when learning patterns from data.
- **Deductive reasoning:** Derives at a **logical conclusion given the premises are correct**. Using a trained model or a rule-based system to make assumptions about a specific instance is an example of deduction.

**Why Machine Learning?** ML algorithms can learn to solve tasks independently, improve with data, process large datasets ("big data"), find complex patterns, and even achieve "superhuman" performance.

**Machine Learning and Robotics (Robot Learning):** Combines ML with robotics for the acquisition of new skills (sensorimotor), locomotion, grasping, object categorisation, interactive skills, and adaptation to the environment.

**Machine Learning Input-Output:** ML models learn a mapping from inputs (images, features, graphs, time sequences) to outputs (diagnosis, segmented images, robot movement, etc.).

**White-box vs. Black-box Models:** Conventional (non-ML) image classification often uses white-box models with good interpretability but can be difficult to design and rigid. ML-based image classification uses learned models (often neural networks) with less interpretability ("black box") but are easier to design and can achieve better performance with sufficient data.

**Generalization:** A central problem in ML where the learned model must learn the underlying pattern from training data and **generalise to new, unseen data**.

- **Underfitting:** Model is too simplistic and fails to capture underlying patterns.
- **Overfitting:** Model learns noise and random fluctuations, becoming too specific to the training data and not generalising well.

**Neural Networks:** Inspired by the human brain's network of neurons.

- **Artificial Neurons:** Interconnected units that receive input, combine it with weights and an internal state, and produce an output based on an **activation function**. Activation functions must often be differentiable and nonlinear in deep networks.
- **Learning methods:** Involve adjusting connection weights, adding/deleting connections or neurons, and modifying activation functions.
- **Deep Neural Networks (DNN):** Neural networks with multiple hidden layers ("depth") used for complex data.
- **Advantages:** Flexible, can approximate any function, state-of-the-art in many areas.
- **Disadvantages:** Require large data, lack easy inspection ("black box"), limited reproducibility, data demanding.

**Types of Machine Learning:**

- **Supervised Learning:** Training data with known input and output values (labeled data). The goal is to learn a function that maps inputs to outputs and generalises. Categories include:
    - **Classification:** Dividing data into discrete classes (categorial output). Examples in medicine include breast cancer detection, diabetic retinopathy detection, epileptic seizure detection. Methods include logistic regression, support vector machines, k-nearest neighbour, decision trees, and random forests.
    - **Regression:** Learning the relationship between variables with a continuous output. Examples in medicine include drug dosage optimisation, healthcare cost prediction, disease risk assessment. Methods include linear regression, polynomial regression, decision trees, and random forests.
- **Unsupervised Learning:** Training data with known input but unknown target values (unlabeled data). The task is to find intrinsic structure and patterns. Categories include:
    - **Clustering:** Partitioning data into groups based on similarity.
    - **Compression/Density Fitting:**.
- **Reinforcement Learning:** An agent learns to take actions in an environment to maximise a reward. It involves an agent, environment, state, action, policy, and reward. Often formalised by a **Markov Decision Process (MDP)** where the future state depends only on the current state (**Markov Property**).
    - **Limitations:** Difficult to define good reward functions (sparse, unavailable, faulty leading to reward hacking). Requires large amounts of interaction data and has challenges with convergence.
    - **Inverse Reinforcement Learning (IRL):** Infers the reward function based on observed expert behaviour instead of being given one.
    - **Demonstration Learning (Imitation Learning):** Learns a policy by directly mimicking expert demonstrations.

**Summary of AI Fundamentals:** Machine learning is a subset of AI, and deep learning is a subset of ML. Effective AI development requires careful data analysis, representation learning, model updating, and ensuring generalisation to new data. Deep neural networks need large, high-quality datasets, which can be challenging to obtain in medicine.