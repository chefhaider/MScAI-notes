## Lecture 1: Introduction – Human-Machine Interfaces (HMIs) in Rehabilitation and Assistive Robotics

### 1. Course Overview

- Focus on **robots in medicine**: assistive, prosthetic, and rehabilitation devices
- Key use-cases:
  - **Prosthetic control**
  - **Exoskeletons** and **exo-suits**
  - **VR avatars**, **teleoperation**, and **daily-life aids**



### 2. Motivation

- Problem: **Controlling assistive devices** is often difficult
- Cause: **Loss of limb function** or **motor control**
- Goal: Design **smart Human-Machine Interfaces (HMIs)** to:
  - Detect **user intent**
  - Deliver **feedback** to the user



### 3. What is a Human-Machine Interface (HMI)?

- A **system or channel** that enables **interaction between human and machine**
- Two key functionalities:
  - **Feedforward**: Converts **human-generated signals** into control commands
  - **Feedback**: Converts **environmental/robot signals** into **bodily stimuli**



### 4. Examples of HMIs

- **Wheelbarrow handle**
- **Car cockpit**
- **Smartphone touchscreen and OS**



### 5. Characteristics of an Ideal HMI

1. **Reliability** – precise, timely, and exclusive control
2. **Dexterity** – full access to **degrees of freedom (DoFs)**
3. **Ease of Use** – intuitive, low learning curve
4. **Flexibility** – works for novices and experts, minimal calibration



### 6. HMI Design for Disabled Users

- Standard HMIs rely on **arms/hands/fingers**
- Disabled users need:
  - Replacement of **control commands** with **intent signals**
  - Replacement of **force feedback** with **somatosensory feedback**
  - Use of **custom sockets** instead of mechanical joysticks



### 7. HMI Architecture (Functional Diagram)

**Key components**:

- **Sensors** and **stimulators**
- **Preprocessing** (ADC, filtering, fusion)
- **Feature extraction**
- **Intent detection**
- **Stimuli generation**
- **Machine Learning layer**
- Interfaces between:
  - **User**
  - **HMI**
  - **Device**
  - **World**



### 8. Terminology

- **Intent Detection** (Feedforward path):
  - Recognize user’s intent from **biosignals** and map it to **robot commands**

- **Somatosensory Feedback** (Feedback path):
  - Convert **robot/environment feedback** into **bodily sensations**

- **Bidirectional HMI**:
  - Combines **intent detection** + **feedback**
  - Should be:
    - **Unobtrusive**
    - **Real-time**
    - **Reliable**
    - **Dexterous**
    - **Low-power**



### 9. Basic Anatomy for HMIs

#### a. Anatomical Directions and Planes

- **Anterior/Posterior**, **Medial/Lateral**
- Planes: **Sagittal**, **Frontal**, **Transverse**

#### b. Skeleton of the Upper Limb

- 30 bones in upper limb
- **Scapula**, **Clavicle**, **Humerus**, **Radius**, **Ulna**, **Carpals**, **Metacarpals**, **Phalanges**

- **Joints**:
  - MCP (Metacarpophalangeal)
  - PIP (Proximal Interphalangeal)
  - DIP (Distal Interphalangeal)

#### c. Movements

- **Flexion / Extension**
- **Abduction / Adduction**
- **Rotation**
- **Supination / Pronation**

#### d. Muscles

- **Shoulder**:
  - M. Trapezius
  - M. Deltoideus

- **Upper Arm**:
  - M. Biceps (elbow flexion)
  - M. Triceps (elbow extension)
  - Antagonist/Agonist → **co-contraction**

- **Forearm**:
  - M. Flexor Digitorum Superficialis
  - M. Extensor Digitorum
  - M. Brachioradialis
  - M. Pronator Teres

- **Hand**:
  - M. Flexor Pollicis Brevis
  - M. Abductor Pollicis Brevis
  - Interossei muscles (Palmar and Dorsal)



### 10. Upper Limb Deficiencies

- Various types of **amputations**
- Challenges in **intent detection** due to:
  - Absence of limb
  - Lack of feedback
  - Non-standard signal sources



### 11. Summary

- Overview of **IDF use-cases**
- Defined **Human-Machine Interfaces**
- Introduced concepts of **intent detection** and **feedback**
- Covered **basic anatomy** relevant to interface design





## Lecture 2: Intent Detection – Overview, Definitions, Biosignals

### 1. What is Intent Detection?

- **Assumption**: The participant can produce **voluntary muscle activity**
- **Goal**: Gather signals representing muscle activity for robotic control
- **Myocontrol**: Control based on **direct muscle activity**
  - Ideal: _"user wants → device acts"_
  - Realistic: _"user does something → device acts accordingly"_

- **Examples**:
  - **Amputees** show remarkable **residual muscle activity**
    - **Quantitative**: Intensity of activation
    - **Qualitative**: Type of action
  - **Stroke patients**: Signals differ, but still **correlate to intent**
  - Use **surface EMG (sEMG)** → pattern recognition → control actions

### 2. Practical Systems (Myocontrol)

- **Simple setup**: 2 sEMG sensors, 1 DoF control
- **Typical example (trans-radial amputee)**:
  - $$ v_{\text{open}} \propto \text{EMG}_{\text{Extensor Digitorum}} $$
  - $$ v_{\text{close}} \propto \text{EMG}_{\text{Flexor Digitorum Superficialis}} $$
- **Low DoF systems** can be highly functional

### 3. Philosophical vs. Operational View of Intent

- **Challenge**: Defining "intent" philosophically
- **Operational solution**:
  - _Signals_ contain info to anticipate future actions
  - Define a **mapping function** from signal → action
    - $$ f(\text{signal}) = \text{action} $$

### 4. The Problem of Ground Truth

- **Key Question**: How to associate signal patterns with correct labels?
- **Labeling issues**:
  - Data collection & **semantics** depend on the **user**
  - **Amputees**: No sensors for ground truth
  - **Stroke patients**: Feedback is unreliable or incorrect

- **Solutions**:
  - Ask user or **induce actions**
  - Use **stimulus-response protocols**
  - Iterative corrections over time

### 5. Experimental Protocol (Castellini et al. 2009)

- **Three methods** for EMG collection from amputees:
  1. **Imitating** experimenter's hand
  2. **Bilateral symmetry**
  3. **Mirror feedback**

- Evaluate:
  - How **rich** is EMG data?
  - Which method yields **best results**?

### 6. Offline vs. Online Intent Detection

#### **Offline Detection**
- Protocol: User performs action once
- Model: Trained on part of data, tested on rest
- User exits experiment
- Issue: Poor correlation with **real-world performance**

#### **Online Detection**
- User remains in loop
- Continuous model updates with new data
- More **realistic and adaptive**

#### **Takeaway**:
> Offline intent detection is **almost a waste of time**

### 7. Summary of Intent Detection Workflow

1. **User wants** to perform action at specific time
2. **Muscle activation** generates signal
3. Signal is **measured**
4. Signal is **classified/regressed**
5. Action or **configuration label** is assigned



## Lecture 3: Electromyography (EMG)

### 1. What is EMG?

- **Electromyography (EMG)**: Measures **electrical signals** generated by muscle contractions
- **Surface EMG (sEMG)**:
  - **Non-invasive**
  - Measures signals through electrodes placed on the **skin**
  - Oscillating signal related to **muscle contraction**
  - **Bandwidth**: 15–450 Hz
  - **Amplitude**: 1 µV – 10 mV

### 2. Practical Output of sEMG

- sEMG signal is:
  - **Noisy**
  - Subject to **crosstalk** from nearby muscles
  - Requires **processing** before use in control systems

### 3. Processing Surface EMG

There are two main strategies:

#### a. Averaged-Rectified Values (ARVs)

- **Temporal features** (not spectral)
- Monotonically related to **muscle contraction intensity**

Two main methods:
1. Compute **RMS** over a time window:
   $$ \text{RMS} = \sqrt{\frac{1}{N} \sum_{i=1}^N x_i^2} $$
2. **Rectify** signal (absolute value), then apply **low-pass filter**:
   $$ \text{ARV} = \frac{1}{N} \sum_{i=1}^{N} |x_i| $$

#### b. Window-Based Feature Extraction

- Extract **multiple features** from a sliding window of raw signal
- Most common: **Hudgins Features** (4 features/channel)

### 4. Hudgins Features

Within a time window:

- **MAV (Mean Absolute Value)**:
  $$ \text{MAV} = \frac{1}{N} \sum_{i=1}^{N} |x_i| $$

- **ZC (Zero Crossings)**: Counts number of sign changes

- **SSC (Slope Sign Changes)**: Counts changes in slope sign

- **WL (Waveform Length)**:
  $$ \text{WL} = \sum_{i=1}^{N-1} |x_{i+1} - x_i| $$

- These features help detect different **muscle activities** and improve **classification accuracy**

### 5. Advanced Processing (not covered in detail)

- **High-Density EMG (HD-EMG)** decomposition into individual **Motor Unit Action Potentials (MUAPs)**

- Very informative but **computationally expensive**

### 6. Key Takeaways

- **sEMG** is a rich signal source for **intent detection**
- Must be **preprocessed** and **interpreted**
- Common processing involves:
  - **ARV/RMS methods**
  - **Windowed feature extraction** like **Hudgins features**
- Enables **myoelectric control** of prostheses and devices

-

## Lecture 4: Motion Tracking (Optical, IMU-Based)

### 1. Introduction

- Motion tracking can **reveal user intent** by observing their movements.
- **Intent detection** can be inferred from **body motion**, **gaze direction**, or **scene understanding**.
- Multiple modalities:
  - **Optical tracking**
  - **Gaze tracking**
  - **Inertial Measurement Units (IMUs)**



### 2. Optical Motion Tracking (OMT)

- Tracks user movement using **cameras**.
- Methods:
  - **Standard cameras** (visible light)
  - **Specialized systems** (laser, infrared, structured light)
- Types:
  - **Active markers**
  - **Passive markers**
  - **Markerless systems** (hard problem, needs computer vision)

#### Limitations:
- Requires **bulky equipment**
- **Not feasible** for daily-life prosthetics
- Best suited for **clinical settings** and **research labs**

#### Utility:
- Measures **compensatory movements**
- Supports **functional recovery assessments**



### 3. Scene Understanding via Optical Tracking

- Idea: Track the **scene** around the user, not just the user.
- Use **AR glasses** to:
  - Recognize nearby objects
  - Choose an object based on **proximity to prosthesis**
  - Decide between:
    - **Autonomous grasp**
    - **Volitional (sEMG-based) grasp**

#### Challenges:
- **Computer vision** problems: illumination, occlusion, perspective
- Needs to be **wearable**, **real-time**, **affordable**



### 4. Gaze Tracking

- Detect **eye movement** using **infrared cameras**
- Reveals **visual attention** and **movement targets**

#### Insights:
- **Users don’t look at their limbs** while moving (due to proprioception)
- They focus on **targets** (objects to grasp, places to move)

#### Applications:
- **Rehabilitation robotics**:
  - Good performance = looking at targets
  - Poor control = watching prosthesis instead



### 5. Inertial Measurement Units (IMUs)

- Miniature devices integrating:
  - **Accelerometer**
  - **Gyroscope**
  - **Magnetometer**

- Provides:
  - **Orientation** relative to **gravity vector**
  - **Motion and posture data**

#### Benefits:
- Small, **wearable**
- Used in:
  - **Direct kinematics**
  - **Posture detection**
  - **Body motion estimation**

#### Examples:
- **DLR BodyRig**
- **Corehab Riablo**



### 6. Summary

- **Motion tracking** helps infer intent through:
  - **Body movement**
  - **Eye movement**
  - **Scene interaction**
- Technologies include:
  - **Optical systems**
  - **Gaze tracking**
  - **IMUs**
- Each has trade-offs in:
  - **Feasibility**
  - **Wearability**
  - **Real-time capability**
  - **Cost**



## Lecture 5: Pressure Sensing (FMG, TMG)

### 1. Introduction

- An alternative to EMG-based intent detection is measuring **muscle deformation**.
- Muscle contraction leads to:
  - **Shape changes** in muscles
  - Detectable **pressure changes** on skin/body surface
- Pressure sensing can be:
  - **Easy to implement**
  - **Cost-effective**
  - **Robust to noise and sweat**



### 2. Force Myography (FMG)

- Detects **muscle deformation** using **pressure sensors**
- Sensors are placed inside a **semi-rigid housing** (e.g., socket, bracelet)

#### Signal Origin:
- Muscle contraction → bulging → pressure on the housing → **sensor signal**

#### Advantages:
- **Not affected** by muscle fatigue
- **Unaffected** by skin conditions like sweat
- Uses **cheap, low-power electronics**
- Suitable for **wearable devices**

#### Signal Properties:
- Related to:
  - **Force output**
  - **Posture**
  - **Type of movement**



### 3. High-Density FMG

- Uses a **large array** of pressure sensors
- Allows:
  - **Higher spatial resolution**
  - Better **pattern recognition**
  - More accurate **classification of intent**



### 4. Tactile Myography (TMG)

- A specialized form of FMG using **dense tactile sensors**
- Measures **detailed spatial pressure distributions**
- Capable of capturing:
  - **Fine-grained hand gestures**
  - **Individual finger movements**



### 5. Signal Processing in FMG/TMG

- Similar to EMG:
  - **Feature extraction** from time windows
  - Apply **machine learning** for classification/regression
- Signal can be processed to:
  - Detect **grip force**
  - Recognize **hand posture**
  - Trigger **prosthetic control**



### 6. Applications

- FMG/TMG can be used in:
  - **Prosthetic hand control**
  - **Exoskeleton interfaces**
  - **Rehabilitation robotics**

#### Example Systems:
- **Residual Kinetic Imaging (RKI)**
  - Detects pressure from muscle bulges
  - Applied in **prosthetic sockets**



### 7. Summary

- **FMG** and **TMG** are robust alternatives to **EMG**.
- Detect **muscle deformation** via pressure, not electric signals.
- Offer:
  - **Simplicity**
  - **Low cost**
  - **High reliability**
- Can be integrated into **wearable sockets** and **assistive devices**
- Enables **myocontrol** via **non-electrical sensing**



## Lecture 6: Stimulation and Feedback

### 1. Introduction

- **Somatosensory feedback**: Converts external signals into **bodily stimuli**
- Essential for:
  - **Realistic control**
  - **Closed-loop systems**
  - **Perception of the environment**

- Complements **intent detection** (feedforward path)
- Together, they form a **bidirectional HMI**



### 2. Types of Feedback

#### a. Modalities of Feedback

- **Haptic feedback** (touch, force)
- **Electrotactile stimulation**
- **Vibrotactile stimulation**
- **Mechanotactile stimulation**
- **Thermal stimulation**

#### b. Key Criteria for Feedback Systems

- **Intensity**: How strong is the stimulus?
- **Latency**: How fast is the stimulus applied?
- **Resolution**: How many distinguishable levels?
- **Spatial coverage**: Area of skin or body affected
- **Power consumption**: Must be low for wearable use
- **User acceptability**: Comfort, safety, intrusiveness



### 3. Electrical Stimulation

- Based on delivering **current pulses** to the skin
- Types:
  - **Transcutaneous Electrical Nerve Stimulation (TENS)**
  - **Functional Electrical Stimulation (FES)**

#### Features:
- Stimulates **nerves or muscles**
- Evokes:
  - **Tactile sensations**
  - **Muscle contractions**

#### Signal properties:
- Pulse waveform:
  - **Biphasic** or **monophasic**
- Parameters:
  - **Amplitude**: in mA
  - **Pulse width**: in µs
  - **Frequency**: in Hz



### 4. Vibrotactile Stimulation

- Uses small **vibrating motors** (e.g., eccentric rotating mass)
- Evokes a sense of **contact or motion**
- Commonly used due to:
  - **Simplicity**
  - **Low cost**
  - **Wearability**

#### Limitations:
- Low **spatial resolution**
- Perceptual thresholds vary between users



### 5. Mechanotactile Feedback

- Delivers **physical pressure** or **force**
- Examples:
  - **Motor-driven actuators**
  - **Inflatable bladders**
  - **Skin stretch mechanisms**

- Benefits:
  - **Natural perception**
  - **Continuous feedback**

- Limitations:
  - **Complex mechanics**
  - **Higher power consumption**



### 6. Other Feedback Types

#### a. Thermal Feedback

- Stimulates **temperature receptors**
- Still under research; limited use in prosthetics

#### b. Auditory Feedback

- Provides **sound cues**
- Useful for **non-intrusive alerts**
- But **not directly somatosensory**



### 7. Applications in Prosthetics

- Feedback can encode:
  - **Grip force**
  - **Contact detection**
  - **Slip events**
  - **Hand posture**

- Improves:
  - **User confidence**
  - **Object manipulation**
  - **Embodiment and ownership**



### 8. Feedback Coding Strategies

- **Amplitude modulation (AM)**:
  $$ \text{Stimulus Intensity} \propto \text{Input Signal Amplitude} $$

- **Pulse width modulation (PWM)**:
  $$ \text{Pulse Width} \propto \text{Input Signal Level} $$

- **Pulse frequency modulation (PFM)**:
  $$ \text{Pulse Frequency} \propto \text{Input Signal Rate} $$

- **Spatial coding**:
  - Different locations correspond to different types of feedback



### 9. Summary

- Feedback is essential for **closed-loop control**
- Modalities include:
  - **Electrical, vibrotactile, mechanotactile, thermal**
- Systems must be:
  - **Low-latency**, **wearable**, **comfortable**, **interpretable**
- Signal encoding uses:
  - **AM, PWM, PFM, spatial strategies**
- Enhances prosthetic **functionality** and **embodiment**



## Lecture 7: Signal Processing for Intent Detection

### 1. Introduction

- **Signal processing** is crucial to convert raw biosignals into meaningful features.
- Enables **machine learning models** to classify or regress **user intent**.
- Applies to signals such as:
  - **sEMG**
  - **FMG**
  - **IMU**
  - **EIT**
  - **Ultrasound**



### 2. General Processing Pipeline

1. **Signal acquisition**
2. **Preprocessing**
3. **Windowing**
4. **Feature extraction**
5. **Feature selection / dimensionality reduction**
6. **Classification / regression**



### 3. Preprocessing

- **Filtering**:
  - Remove **noise** and **artifacts**
  - Common filters:
    - **Band-pass filter** for sEMG (e.g., 20–450 Hz)
    - **Notch filter** at 50/60 Hz to remove powerline interference

- **Normalization**:
  - Standardize signal amplitude
  - Methods:
    - Max value normalization:
      $$ x_{\text{norm}} = \frac{x}{\max(x)} $$
    - Z-score:
      $$ x_{\text{norm}} = \frac{x - \mu}{\sigma} $$

- **Smoothing**:
  - Moving average, RMS windows



### 4. Windowing

- Signals are **segmented** into overlapping time windows
- Typical window length: **100–300 ms**
- Window overlap: **50–75%**

Purpose:
- Capture **temporal dynamics**
- Maintain **real-time responsiveness**



### 5. Feature Extraction

- Extract **quantitative descriptors** from each window
- Depends on signal type

#### For sEMG:

- **Time-domain features**:
  - Mean Absolute Value (MAV):
    $$ \text{MAV} = \frac{1}{N} \sum_{i=1}^N |x_i| $$
  - Root Mean Square (RMS):
    $$ \text{RMS} = \sqrt{\frac{1}{N} \sum_{i=1}^N x_i^2} $$
  - Zero Crossings (ZC), Slope Sign Changes (SSC), Waveform Length (WL)

- **Frequency-domain features**:
  - Mean Frequency (MNF)
  - Median Frequency (MDF)
  - Power Spectral Density (PSD)

- **Time-frequency domain**:
  - Short-time Fourier Transform (STFT)
  - Wavelet Transform



### 6. Feature Selection & Dimensionality Reduction

- Removes **redundant or irrelevant** features
- Improves:
  - **Model performance**
  - **Computational efficiency**

#### Techniques:

- **Principal Component Analysis (PCA)**
- **Linear Discriminant Analysis (LDA)**
- **Sequential Feature Selection**
- **Mutual Information**, **ReliefF**



### 7. Classification & Regression

- Goal: Map extracted features to **intended actions or continuous outputs**

#### Classification (discrete actions):

- **Linear Discriminant Analysis (LDA)**
- **Support Vector Machines (SVM)**
- **k-Nearest Neighbors (kNN)**
- **Random Forests**
- **Neural Networks (MLP, CNN, RNN)**

#### Regression (continuous control):

- **Linear regression**
- **Support Vector Regression (SVR)**
- **Gaussian Processes**
- **Neural Networks**



### 8. Training & Testing

- **Supervised learning** requires labeled data
- Data split:
  - **Training set**: to build model
  - **Validation set**: for hyperparameter tuning
  - **Test set**: for final performance evaluation

#### Metrics:

- Classification:
  - **Accuracy**, **Precision**, **Recall**, **F1 Score**
- Regression:
  - **Mean Squared Error (MSE)**:
    $$ \text{MSE} = \frac{1}{N} \sum_{i=1}^N (y_i - \hat{y}_i)^2 $$
  - **R-squared**:
    $$ R^2 = 1 - \frac{\sum (y_i - \hat{y}_i)^2}{\sum (y_i - \bar{y})^2} $$



### 9. Real-Time Considerations

- Algorithms must run **online**
- Ensure:
  - **Low latency**
  - **Minimal delay**
  - **Low computational load**
- Prefer:
  - **Simple features**
  - **Fast classifiers** (e.g., LDA over deep CNN)



### 10. Summary

- Signal processing enables **conversion of raw biosignals to control commands**
- Pipeline includes:
  - Preprocessing → Feature extraction → Classification/Regression
- Feature quality strongly influences **accuracy and responsiveness**
- **Dimensionality reduction** and **real-time constraints** are essential in practical systems


## Lecture 8: Machine Learning for Intent Detection

### 1. Introduction

- **Machine Learning (ML)** is central to **intent detection systems**
- Learns to **map biosignal patterns** to **intended actions**
- Types of problems:
  - **Classification**: Discrete actions (e.g., hand open, close)
  - **Regression**: Continuous outputs (e.g., finger position)



### 2. Supervised Learning Basics

- **Training data**:
  - $$ X = [x_1, x_2, ..., x_N] $$ (input features)
  - $$ Y = [y_1, y_2, ..., y_N] $$ (labels or targets)

- **Goal**: Find a function
  $$ f: X \rightarrow Y $$
  that generalizes well to new data

- Requires:
  - Large, well-labeled dataset
  - High-quality features
  - Proper training/validation/testing split



### 3. Classification Algorithms

- **Linear Discriminant Analysis (LDA)**:
  - Projects data to maximize **class separability**
  - Fast, low-resource, common in **sEMG** systems

- **Support Vector Machines (SVM)**:
  - Maximizes margin between classes
  - Can use **kernel trick** for non-linear boundaries

- **k-Nearest Neighbors (kNN)**:
  - Classifies based on majority vote among k closest points

- **Random Forests**:
  - Ensemble of decision trees
  - Good for **non-linear**, high-dimensional data

- **Neural Networks**:
  - **Multilayer Perceptron (MLP)**: Fully connected layers
  - **Convolutional Neural Networks (CNN)**: For spatial signals like HD-EMG
  - **Recurrent Neural Networks (RNN)**: For temporal dependencies



### 4. Regression Algorithms

- Used for **continuous control signals**

#### Examples:

- **Linear regression**:
  $$ y = w^T x + b $$

- **Support Vector Regression (SVR)**

- **Gaussian Process Regression (GPR)**:
  - Non-parametric, probabilistic model

- **Neural networks for regression**:
  - Trained with loss functions like **MSE**:
    $$ \text{MSE} = \frac{1}{N} \sum_{i=1}^N (y_i - \hat{y}_i)^2 $$



### 5. Model Training

- **Steps**:
  1. Preprocess data (filtering, normalization)
  2. Extract features (e.g., MAV, RMS, ZC)
  3. Split data (train/val/test)
  4. Choose algorithm and hyperparameters
  5. Train and evaluate

- **Cross-validation**: k-fold CV improves generalizability



### 6. Evaluation Metrics

#### Classification:

- **Accuracy**:
  $$ \text{Accuracy} = \frac{\text{Correct Predictions}}{\text{Total Predictions}} $$

- **Precision, Recall, F1 Score**

#### Regression:

- **Mean Squared Error (MSE)**
- **Root Mean Squared Error (RMSE)**
- **R-squared (coefficient of determination)**:
  $$ R^2 = 1 - \frac{\sum (y_i - \hat{y}_i)^2}{\sum (y_i - \bar{y})^2} $$



### 7. Online vs Offline Learning

- **Offline**:
  - Data collected → model trained → deployed
  - Faster, simpler, but not adaptive

- **Online / Incremental**:
  - Model updated as new data arrives
  - Handles **non-stationarity** and **user adaptation**
  - Enables **personalization**



### 8. Real-Time Constraints

- **Latency** must be minimized
- Models must be:
  - **Efficient**
  - **Low-power**
  - **Memory-light**

#### Trade-off:
- Complexity vs speed
  - LDA: fast, interpretable
  - Deep networks: accurate, slower



### 9. Challenges in ML for Intent Detection

- **Data variability**:
  - Between users, sessions, sensors
- **Labeling difficulties**
  - Ground truth is hard to obtain (esp. in amputees, stroke)
- **Generalization**:
  - Models must work across **tasks**, **contexts**, and **users**



### 10. Summary

- ML enables **mapping of biosignals to user intent**
- Choice of algorithm depends on:
  - Task (classification vs regression)
  - Constraints (real-time, power)
  - Data (amount, quality)
- **Feature quality and model efficiency** are critical
- Online learning offers **adaptivity** and **long-term usability**



## Lecture 9: Practical Use Cases and Experimental Protocols

### 1. Introduction

- Real-world systems must transition from **lab prototypes** to **functional assistive devices**
- Requires:
  - Clear **experimental protocols**
  - Robust **data acquisition**
  - **User-centered** validation



### 2. Use Case Categories

#### a. Prosthetic Control

- **Trans-radial amputees**
  - Use **sEMG**, **FMG**, or **ultrasound**
  - Control hand opening/closing, wrist rotation
- Requires training to associate signals with prosthetic **grasp types**

#### b. Exoskeletons

- Support **rehabilitation** (e.g. stroke)
- Must detect **residual movement** and assist accordingly
- Use **EMG**, **IMUs**, or **torque sensors**

#### c. VR/Avatar Control

- sEMG or IMUs to control a **virtual limb**
- Supports:
  - **Phantom limb therapy**
  - **Pre-operative training**
  - **Cognitive rehabilitation**

#### d. Teleoperation

- Signals from human are sent to control a **remote robot**
- Challenges:
  - **Latency**
  - **Feedback delay**
  - **Signal distortion**



### 3. Experimental Protocol Design

- Define:
  - **Target task** (e.g., grasping cup, typing)
  - **Signal modalities**
  - **Sensors placement**
  - **Feedback mechanism**

#### Guidelines:

1. Choose **representative tasks**
2. Ensure **repeatability**
3. Minimize **user fatigue**
4. Define **clear start/stop conditions**
5. Record **ground truth** if possible



### 4. Ground Truth Collection Challenges

- **Amputees**: No natural motion to reference
- **Stroke patients**: Distorted or limited movement

#### Workarounds:

- **Imitation** of therapist
- **Bilateral symmetry** (healthy side as reference)
- **Mirror feedback**
- Use **external motion capture** to label intent



### 5. Data Synchronization

- Synchronize multiple data streams:
  - sEMG
  - Video
  - Motion tracking
  - Force sensors

#### Methods:

- **Timestamps**
- **Trigger pulses**
- **Software synchronization**



### 6. Signal Annotation

- Supervised learning needs labeled data:
  $$ \{(x_i, y_i)\}_{i=1}^N $$

Where:
- $$ x_i $$ = feature vector from biosignal
- $$ y_i $$ = label or output (class or regression target)

#### Annotation options:

- **Manual labeling** (via GUI)
- **Automatic labeling** using:
  - **Cyberglove**
  - **Instrumented objects**
  - **Motion trackers**



### 7. Model Adaptation

- Users may improve over time → signals evolve
- Systems must adapt via:

#### a. **Online learning**:
- Model updated with new data:
  $$ f_t(x) \rightarrow f_{t+1}(x) $$

#### b. **Transfer learning**:
- Adapt pretrained model to new user



### 8. Performance Metrics

#### For classification:

- Accuracy:
  $$ \text{Accuracy} = \frac{\text{TP + TN}}{\text{TP + TN + FP + FN}} $$

- F1 Score:
  $$ \text{F1} = 2 \cdot \frac{\text{Precision} \cdot \text{Recall}}{\text{Precision} + \text{Recall}} $$

#### For regression:

- Mean Squared Error:
  $$ \text{MSE} = \frac{1}{N} \sum_{i=1}^N (y_i - \hat{y}_i)^2 $$



### 9. User Feedback and Usability

- Evaluate:
  - **Comfort**
  - **Learning curve**
  - **Perceived control**
  - **Fatigue**
  - **Cognitive load**

- Methods:
  - **Questionnaires**
  - **Think-aloud protocols**
  - **Observation-based notes**



### 10. Summary

- Practical use requires:
  - Robust **protocols**
  - Accurate **data labeling**
  - **Adaptive models**
- Involves multiple signal types and feedback loops
- Goal is to create **real-time**, **reliable**, and **user-friendly** interfaces



## Lecture 10: State of the Art and Open Challenges

### 1. Introduction

- Despite progress, **assistive robotics** and **intent detection** still face **many limitations**.
- Need for **robust**, **wearable**, and **intuitive** systems in **real-world conditions**.



### 2. State of the Art

#### a. Signal Acquisition

- **sEMG** remains most used for **intent detection**
  - High **temporal resolution**
  - But sensitive to:
    - **Skin condition**
    - **Electrode displacement**
    - **Noise**

- Alternatives:
  - **FMG**: pressure-based, robust to noise
  - **Ultrasound imaging**: high detail, but bulkier
  - **EIT (Electrical Impedance Tomography)**: early-stage, promising

#### b. Feedback Modalities

- Common feedback types:
  - **Vibrotactile**
  - **Electrotactile**
  - **Mechanotactile**

- Integration of **closed-loop feedback** is still rare in **commercial devices**



### 3. Machine Learning Advances

- **Deep learning** offers improved **pattern recognition**
  - Especially CNNs, RNNs for **EMG**, **HD-EMG**

- **Transfer learning** helps in **cross-user generalization**

- **Online adaptive systems** allow continual learning:
  $$ f_t(x) \rightarrow f_{t+1}(x) $$

- **Hybrid models** combining multiple modalities are more robust



### 4. Challenges in Real-World Deployment

#### a. Variability

- **Between-subject variability**
- **Intra-subject variability**:
  - Fatigue
  - Electrode shift
  - Day-to-day changes

#### b. Signal Quality

- Need for **robust preprocessing**:
  - Filtering
  - Normalization:
    $$ x_{\text{norm}} = \frac{x - \mu}{\sigma} $$

#### c. Ground Truth

- Difficult to obtain for:
  - **Amputees**
  - **Stroke patients**
- Requires **manual annotation** or **sensor fusion**



### 5. Usability Concerns

- Devices must be:
  - **Comfortable**
  - **Low-power**
  - **Wearable**
  - **Intuitive**

- Feedback systems must be:
  - **Non-intrusive**
  - **Quickly interpretable**
  - **User-specific**



### 6. Clinical and Ethical Issues

- Integration in **rehabilitation** requires:
  - Clinician collaboration
  - FDA/CE approval
  - Long-term studies

- Ethical concerns:
  - **Data privacy**
  - **Autonomy and control**
  - **Informed consent**



### 7. Future Directions

- **Multimodal intent detection**:
  - Combine sEMG + IMU + vision

- **Sensory substitution**:
  - Provide feedback via alternative senses (e.g., sound, vibration)

- **Personalized adaptive systems**:
  - Self-calibrating, user-specific models

- **AI co-adaptation**:
  - Human and machine learn together

- **Benchmark datasets**:
  - Needed for fair comparison and reproducibility



### 8. Summary

- **Current systems** work well in **controlled settings**, but struggle in real-world use
- Need for:
  - **Robust signals**
  - **Intelligent adaptation**
  - **Comfortable feedback**
  - **Real-time performance**
- Future lies in **hybrid, adaptive, user-centered systems**



