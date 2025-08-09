


# Lecture Overviews: Intent Detection and Feedback

**Lecture 1 – Foundations of Human-Machine Interfaces (HMI):**  
We begin by exploring the human desire to interact with machines—like reaching for a mug of coffee with a prosthetic hand. This lecture introduces the complexity behind seemingly simple tasks, covering anatomical terminology, muscle groups, and the concept of intent detection, all foundational to designing assistive robotic systems that can sense, understand, and respond.

**Lecture 2 – Eigenvalues and Eigenvectors in EMG Analysis:**  
Delving into the mathematical core, we explore how **eigenvalues** and **eigenvectors** help interpret EMG data. We learn how transformations like PCA reduce high-dimensional EMG signals into meaningful features, helping machines distinguish between different user intentions through patterns in muscle activity.

**Lecture 3 – Signal Processing Basics:**  
Here, we shift focus to cleaning the noisy EMG signals. You learn where to place sensors, how to sample EMG efficiently, and how to filter and preprocess signals using techniques like median filters. This prepares us for accurate feature extraction and classification in future steps.

**Lecture 4 – Sensor Fusion and Data Transmission:**  
We integrate multiple data streams (like EMG and IMU) and tackle practical questions like transmission bandwidth, synchronization, and buffering. You discover how to manage data bottlenecks and align signals in time—a crucial step in building responsive systems that won’t lag or misinterpret user commands.

**Lecture 5 – Advanced Sensing and Modalities (FMG, TMG):**  
Here we broaden our toolkit by exploring **Force Myography (FMG)** and **Tactile Myography (TMG)**. These methods offer alternatives to EMG by measuring pressure changes. We also dive into posture tracking with IMUs, addressing issues like drift and how to minimize it through sensor placement and calibration.

**Lecture 6 – Quaternions and Rotation Representation:**  
In this mathematically rich lecture, we tackle the problem of representing 3D rotations using **quaternions** and **dual quaternions**, comparing them with rotation matrices and Euler angles. These tools are key to interpreting orientation from IMU data and enabling precise motion control in robotics.

**Lecture 7 – Intention Detection Pipeline:**  
We revisit the full prosthetic control pipeline: from raw sensor data to intent classification. You learn how preprocessing, feature extraction, and classification form a chain, with each step feeding into the next to detect user intent in real time and guide robotic movement.

**Lecture 8 – Classification Techniques:**  
Now it’s time to make decisions. We explore how to classify muscle signals using models like **Decision Trees**, **k-NN**, **SVM**, and **Neural Networks**. These tools interpret extracted features and predict intended actions, transforming raw data into meaningful control signals.

**Lecture 9 – Feedback Modalities and Closing the Loop:**  
No action is complete without feedback. We explore visual, haptic, auditory, and thermal feedback systems that enable users to sense how the prosthetic is interacting with the world. This "closing of the loop" ensures safer, more natural interactions.

**Lecture 10 – Grasp Classification with EMG and Machine Learning:**  
Our journey culminates in a practical task: using machine learning to classify different types of grasps based on EMG data. We integrate everything learned—from signal acquisition to feature extraction and classification—into a system that can recognize and assist complex hand functions.



# Glossary: Keywords and Lecture References

## A
- **Agonist-Antagonist Pair** – Lecture 1
- **Amplitude Modulation** – Lecture 6
- **Artificial Limbs / Prosthetics** – Lectures 1, 10

## B
- **Biceps Brachii** – Lecture 1
- **Biological Signal** – Lecture 4
- **Brachialis** – Lecture 1
- **Brachioradialis** – Lecture 1

## C
- **Classifier (LDA, SVM, kNN, NN)** – Lecture 10
- **Confusion Matrix** – Lecture 10
- **Cross-Validation** – Lecture 10

## D
- **Deltoideus** – Lecture 1

## E
- **Electromyography (EMG)** – Lectures 1, 4, 6, 10
- **Electrode Displacement** – Lecture 10
- **EMG Features (MAV, RMS, WL, etc.)** – Lecture 10
- **Extensor Digitorum** – Lecture 1

## F
- **Feature Extraction** – Lectures 4, 10
- **Flexor Digitorum Superficialis** – Lecture 1
- **Fourier Transform (FFT)** – Lecture 10

## G
- **Grasp Planning** – Lecture 1
- **Grasp Classification** – Lecture 10

## H
- **Human-Machine Interface (HMI)** – Lectures 1, 4, 6

## I
- **Intent Detection** – Lectures 1, 4, 10
- **Inter-Subject Variability** – Lecture 10
- **Intra-Subject Variability** – Lecture 10

## L
- **Linear Discriminant Analysis (LDA)** – Lecture 10

## M
- **Machine Learning** – Lectures 4, 10
- **Mean Absolute Value (MAV)** – Lecture 10
- **Mean Frequency (MNF)** – Lecture 10
- **Median Frequency (MDF)** – Lecture 10
- **Movement Planning** – Lecture 1
- **Muscle Fatigue** – Lecture 10
- **Myoelectric Control** – Lectures 1, 4

## N
- **Neural Network (NN)** – Lecture 10
- **Noise in EMG** – Lectures 6, 10

## P
- **Phalanges** – Lecture 1
- **Pronation/Supination** – Lecture 1
- **Proprioception** – Lecture 2 (implied)
- **Preprocessing** – Lectures 4, 10

## R
- **RMS (Root Mean Square)** – Lecture 10
- **Rubber Hand Illusion** – Lecture 1

## S
- **sEMG (Surface EMG)** – Lectures 4, 10
- **Scapula / Clavicula** – Lecture 1
- **Slope Sign Changes (SSC)** – Lecture 10
- **Support Vector Machine (SVM)** – Lecture 10

## T
- **Triceps Brachii** – Lecture 1
- **Trajectory Planning** – Lecture 1
- **Time-Domain Features** – Lecture 10
- **Time-Frequency Features** – Lecture 10
- **Trapezius** – Lecture 1

## U
- **Ulna / Radius / Humerus** – Lecture 1
- **Upper Limb Deficiency** – Lecture 1

## W
- **Waveform Length (WL)** – Lecture 10
- **Wavelet Transform** – Lecture 10
- **Wrist Flexion/Extension** – Lecture 1

## Z
- **Zero Crossing (ZC)** – Lecture 10



# Lecture 1: Introduction to Intent Detection and Somatosensory Feedback

## 1. Course Overview
- Title: **Intent Detection and Somatosensory Feedback**
- Focus: **Human-Machine Interfaces (HMIs)** in **Rehabilitation** and **Assistive Robotics**
- Instructors: **Claudio Castellini**, **Sabine Thürauf**

## 2. EMG Patterns
- EMG = **Electromyography**
- Used to detect **muscle activity patterns**
- Applications in **myoelectric control**
- Reference image: EMG patterns for **two distinct actions**

## 3. Rubber Hand Illusion
- Phenomenon: **Visual-tactile integration**
- Citation: *Botvinick & Cohen, 1998* – "Rubber hands ‘feel’ touch that eyes see"

## 4. Our Journey: "I want to drink!"
### Steps involved in robotic intent execution:
1. **Find the mug**
2. **Track the mug**
3. **Trajectory planning**
4. **Move hand** to mug
5. **Grasp planning**
6. **Open hand**
7. **Orient hand**
8. **Close hand**
9. **Adjust grip force**
10. **Move mug to mouth**
11. **Drink**

- Actions are enabled by **internal planning** and **external feedback**

## 5. Human-Machine Interfaces for the Disabled
### Major Components:
- **Sensors**
- **Stimulators**
- **Preprocessing** (ADC, Filtering)
- **Feature Extraction**
- **Intent Detection**
- **Stimuli Generation**
- **Machine Learning**
- Interface between **user**, **device**, and **world**

## 6. Basic Terminology
### a. Anatomical Position & Orientation
- Reference: [Lumen Learning](https://courses.lumenlearning.com/ap1x94x1)

### b. Anatomy: Shoulder
- Forms the **pectoral girdle**
- Consists of:
  - **Scapula** (shoulder blade)
  - **Clavicula** (collar bone)

### c. Anatomy: Upper Limb Bones
- **Humerus**, **Radius**, **Ulna**, **Carpals**, **Metacarpals**, **Phalanges**

### d. Movements Relative to the Body
- **Flexion/Extension**
- **Abduction/Adduction**
- **Pronation/Supination**

### e. Musculature
#### Shoulder Muscles:
- **M. Trapezius**
- **M. Deltoideus**

#### Upper Arm:
- **M. Biceps Brachii**
- **M. Triceps Brachii**
- **M. Brachialis**

#### Lower Arm (Forearm or Antebrachium):
- **M. Flexor Digitorum Superficialis**
- **M. Extensor Digitorum**
- **M. Brachioradialis**
- **M. Pronator Teres**

### Functional Muscle Roles:
- **Flexors**: Actuate **wrist/finger flexion**
- **Extensors**: Actuate **wrist/finger extension**
- Work in **agonist-antagonist pairs**
- Control **stiffness** and **positioning**

#### Hand Muscles (Complex):
- **M. Flexor Pollicis Brevis**
- **M. Abductor Pollicis Brevis**
- **M. Palmar/Dorsal Interossei**

## 7. Types of Upper Limb Deficiency
- **Amputations** – classified by **level of limb loss**
- References:
  - [Physio-Pedia](https://www.physio-pedia.com/Principles_of_Amputation)
  - [Nova Scotia Health](https://www.cdha.nshealth.ca/amputee-rehabilitation-musculoskeletal-program/patient-family-information/upper-limb-amputations)

## 8. Key Insight / Take-Home Message
- Even **simple-looking tasks** like drinking coffee involve **complex multi-step processes**
- Emphasizes need for:
  - **Robust feedback**
  - **Accurate intent detection**
  - **Reliable execution in prosthetic systems**


# Lecture 2: Eigenvalues, Eigenvectors and PCA

## 1. Context: Human-Machine Interfaces (HMI)
- HMIs for prosthetic control rely heavily on **feature extraction** and **dimensionality reduction**
- EMG data contains multiple **channels** and **complex patterns**
- PCA helps in understanding and visualizing this data effectively



## 2. Eigenvalues & Eigenvectors: Basics
- Given a **square matrix** \( A \), an **eigenvector** \( v \) satisfies:

  $$
  A \cdot v = \lambda \cdot v
  $$

  where:
  - \( \lambda \) = **eigenvalue**
  - \( v \) = **eigenvector**

- **Eigenvectors** point in a direction that is **scaled** (not rotated) by the transformation
- **Orientation** of eigenvectors remains the same under transformation
- A matrix is **diagonalizable** if it can be written as:

  $$
  A = V \cdot D \cdot V^{-1}
  $$

  where:
  - \( V \) = matrix of eigenvectors
  - \( D \) = diagonal matrix of eigenvalues



## 3. Covariance Matrix
- To compute **PCA**, first center the data:
  
  $$
  X_{\text{centered}} = X - \mu
  $$

- Compute **covariance matrix** \( C \):

  $$
  C = \frac{1}{n-1} X_{\text{centered}}^T X_{\text{centered}}
  $$

  - \( C \) is **symmetric** and **orthogonal**



## 4. Normalization
- Data is often **normalized** before PCA:
  - **Centering**: Subtract the mean
  - **Scaling**: Ensure variance is 1

- Normalization ensures:
  - **Equal importance** of all features
  - **Unbiased PCA** outcome



## 5. Principal Component Analysis (PCA)
- PCA transforms the data into a new basis with:
  - **Maximized variance along each axis**
  - **Orthogonal principal components**

- Key steps:
  1. Center the data
  2. Compute **covariance matrix**
  3. Extract **eigenvectors** and **eigenvalues**
  4. Project data onto top \( k \) eigenvectors

- Projection:

  $$
  X_{\text{projected}} = X_{\text{centered}} \cdot V_k
  $$

  - \( V_k \): matrix of top \( k \) eigenvectors



## 6. PCA as a Quadratic Form
- The variance explained by each component is proportional to its **eigenvalue**:

  $$
  \text{Var}(v_i) = \lambda_i
  $$

- The **first principal component** has the **highest variance**



## 7. Visual Explanation (Optional)
- **Unit sphere** gets transformed into an **ellipse** during PCA
- Axes of ellipse = **principal components**
- Lengths = **square roots of eigenvalues**



## 8. Summary
- **Eigenvalues** and **eigenvectors** are fundamental for understanding **data structure**
- **PCA** helps in:
  - **Noise reduction**
  - **Dimensionality reduction**
  - **Visualization**
- Used in **feature extraction** in intent detection systems


## Lecture 2: Intent Detection – Overview, Definitions, Biosignals

### 1. What is Intent Detection?

- **Assumption**: The user can produce **voluntary muscle activity**
- **Goal**: Acquire signals that reflect this activity to control devices
- Known as **myocontrol**
  - Ideal: "User wants → Device acts"
  - Practical: "User does something → Device acts accordingly"

- **Examples**:
  - **Amputees**: Strong residual EMG activity (quantitative & qualitative)
  - **Stroke patients**: Altered but still usable signals



### 2. Myocontrol in Practice

- Simple example: 2 sEMG sensors controlling 1 DoF
  - Open hand:
    $$ v_{\text{open}} \propto \text{EMG}_{\text{Extensor Digitorum}} $$
  - Close hand:
    $$ v_{\text{close}} \propto \text{EMG}_{\text{Flexor Digitorum Superficialis}} $$

- Such low DoF systems are surprisingly **functional**.



### 3. Philosophical vs Operational Intent

- Philosophical definitions are **difficult to formalize**
- **Operational view**:
  - Detect signals that **predict** future action
  - Use a **mapping function**:
    $$ f(\text{signal}) = \text{action} $$



### 4. Problem of Ground Truth

- Central issue: How to **label biosignals** correctly?
- Especially problematic in:
  - **Amputees** (no ground truth motion)
  - **Stroke** (motion not always intentional)

- **Strategies**:
  - Ask user
  - Use **stimulus-response** protocols
  - Collect data during **imitation**, **mirror feedback**, **bilateral symmetry**



### 5. Experiment Example (Castellini et al. 2009)

- Three ways to elicit EMG in amputees:
  1. Imitating another person
  2. Performing movements on intact side (bilateral symmetry)
  3. Mirror feedback from screen

- Goal: Compare **richness** of EMG signals & **classification performance**



### 6. Offline vs Online Intent Detection

#### Offline

- Collect data → Train model → Test
- User not in the loop
- Does not reflect real-life use

#### Online

- User interacts during control
- Model adapts during interaction
- Reflects **real-world constraints and learning**

> Conclusion: **Offline detection is insufficient alone**



### 7. General Intent Detection Pipeline

1. User **intends** to perform an action
2. Body generates **measurable signals**
3. Signals are **captured**
4. Signals are **processed**
5. Label (discrete or continuous) is predicted

#### Classification:

- Output is a **discrete label**:
  $$ \text{Signal} \rightarrow \text{Features} \rightarrow \text{Classifier} \rightarrow \text{Label} $$

#### Regression:

- Output is a **continuous value**:
  $$ \text{Signal} \rightarrow \text{Features} \rightarrow \text{Regressor} \rightarrow \text{Output Values} $$



### 8. Summary

- Intent detection uses **biosignals** to infer motor commands
- Depends on:
  - **Reliable sensors**
  - **Ground truth labels**
  - **Adaptive models**
- Online detection and **user-in-the-loop** systems are more representative of real applications



### References

- Castellini et al., *Fine detection of grasp force and posture by amputees via surface EMG*, J. Physiol., 2009
- Jiang et al., *Is Accurate Mapping of EMG Signals on Kinematics Needed for Myoelectric Control?*, IEEE TNSRE, 2014


# Lecture 3: EMG Processing & Feature Extraction

## 1. Recap of EMG Acquisition

### a. EMG Signal Characteristics
- **Electromyography (EMG)** records **electrical activity** from muscles
- Origin: **Motor Unit Action Potentials (MUAPs)**
- Signal is **stochastic**, **non-stationary**, and **low amplitude** (0–10 mV before amplification)
- Frequency range: **10–500 Hz**, dominant energy in **50–150 Hz**

### b. EMG Acquisition Workflow
1. **Electrode placement**
2. **Amplification**
3. **Filtering**
4. **Sampling**
5. **Analog-to-Digital Conversion (ADC)**

### c. Sampling Theorem
- To capture a signal without aliasing:
  $$
  f_s \geq 2 f_{\text{max}}
  $$

## 2. Preprocessing of EMG

### a. Filtering
- Remove **motion artifacts** (below 20 Hz)
- Remove **power line interference** (50/60 Hz notch)
- **Band-pass filters** typically between 20–450 Hz

### b. Rectification
- Convert signal to **absolute values** (positive)
  - Full-wave rectification: $|x(t)|$

### c. Smoothing
- Using **moving average filters** or **low-pass filters**
- Example:
  $$
  \text{MA}(t) = \frac{1}{N} \sum_{i=0}^{N-1} x(t-i)
  $$

## 3. EMG Feature Extraction

### a. Time-Domain Features (most common)
- **Mean Absolute Value (MAV)**:
  $$
  \text{MAV} = \frac{1}{N} \sum_{i=1}^{N} |x_i|
  $$
- **Zero Crossings (ZC)**: number of sign changes (crosses zero)
- **Slope Sign Changes (SSC)**: number of changes in slope direction
- **Waveform Length (WL)**:
  $$
  \text{WL} = \sum_{i=1}^{N-1} |x_{i+1} - x_i|
  $$
- **Willison Amplitude (WAMP)**:
  - Counts amplitude differences above a threshold:
    $$
    \text{WAMP} = \sum_{i=1}^{N-1} f(|x_{i+1} - x_i| > \text{threshold})
    $$

### b. Frequency-Domain Features
- **Mean Frequency (MNF)** and **Median Frequency (MDF)**
- Obtained via **Fast Fourier Transform (FFT)**
- **Power Spectral Density (PSD)** estimation

### c. Time-Frequency Features
- **Wavelet Transform (WT)**
- Combines **time** and **frequency** localization

### d. Feature Vector
- Concatenation of features from **multiple channels**
- Used as input to **classifiers** (e.g., SVM, LDA, Neural Networks)

## 4. Signal Segmentation

### a. Windowing
- EMG is analyzed in **windows/frames**
- Typical window length: **100–300 ms**
- Overlap: **25–50%** for smoother transitions

### b. Trade-offs
- **Smaller windows**: more responsive, but noisier
- **Larger windows**: smoother, but higher latency

## 5. Summary

- EMG requires **filtering, rectification**, and **smoothing** before features are extracted.
- **Time-domain features** are widely used due to **simplicity** and **low computational cost**
- **Frequency** and **time-frequency** features offer more detailed analysis
- Feature extraction enables **machine learning-based classification** of **user intent**




# Lecture 4: Features from sEMG and Classification

## 1. Introduction
- Focus: **Extracting features from surface EMG (sEMG)** and applying **classification** for **intent detection**
- Importance: Features must be **repeatable**, **discriminative**, and **computationally efficient**

## 2. sEMG Signal Properties
- sEMG is **stochastic**, **non-stationary**, and affected by:
  - **Muscle fatigue**
  - **Electrode displacement**
  - **Noise**

## 3. sEMG Signal Preprocessing
### Common Steps:
1. **Filtering** (bandpass filter, typically 20–450 Hz)
2. **Rectification** (taking the **absolute value** of signal)
3. **Smoothing** (e.g., **moving average filter**)

## 4. Feature Extraction
### Time-Domain (TD) Features:
- **Mean Absolute Value (MAV):**
  $$ \text{MAV} = \frac{1}{N} \sum_{n=1}^{N} |x_n| $$

- **Root Mean Square (RMS):**
  $$ \text{RMS} = \sqrt{\frac{1}{N} \sum_{n=1}^{N} x_n^2} $$

- **Waveform Length (WL):**
  $$ \text{WL} = \sum_{n=1}^{N-1} |x_{n+1} - x_n| $$

- **Zero Crossing (ZC):** Counts the number of times the signal crosses zero, with a threshold.

- **Slope Sign Changes (SSC):** Measures complexity via changes in the slope.

- **Willison Amplitude (WAMP):**
  - Counts how many times the difference between consecutive samples exceeds a threshold.

### Frequency-Domain (FD) Features:
- **Mean Frequency (MNF):**
  $$ \text{MNF} = \frac{\sum_{j=1}^{M} f_j P_j}{\sum_{j=1}^{M} P_j} $$

- **Median Frequency (MDF):**
  $$ \sum_{j=1}^{k} P_j = \sum_{j=k+1}^{M} P_j $$
  where $P_j$ is the power at frequency bin $j$

- **Fourier Transform** used to convert sEMG into frequency domain.

### Time-Frequency Features:
- **Wavelet Transform**
  - Useful for analyzing **non-stationary** signals.
  - **Discrete Wavelet Transform (DWT)** breaks signal into approximation and detail coefficients.

## 5. Feature Selection
- **Why?** Reduce dimensionality, increase generalization.
- Techniques:
  - **Sequential Forward Selection (SFS)**
  - **Sequential Backward Selection (SBS)**
  - **Principal Component Analysis (PCA)**

## 6. Classification Algorithms
- **Linear Discriminant Analysis (LDA)**
  - Assumes Gaussian distributions with equal covariance
  - Computationally efficient and widely used

- **Support Vector Machines (SVM)**
  - Maximizes the margin between classes
  - Can handle non-linearly separable data using **kernels**

- **k-Nearest Neighbors (k-NN)**
  - Instance-based learning; sensitive to feature scaling

- **Neural Networks**
  - Can model complex, non-linear relationships
  - Require large amounts of data

## 7. Evaluation Metrics
- **Accuracy**: Proportion of correct predictions
- **Precision, Recall, F1-Score**: Useful in **imbalanced datasets**
- **Confusion Matrix**: Breaks down true/false positives/negatives

## 8. Cross-Validation
- Ensures model generalizability
- Common strategy: **k-fold cross-validation**

## 9. Take-Home Message
- Choosing the **right features** and **classifier** is crucial for accurate intent detection.
- Feature extraction and selection are **application-specific** and require **domain knowledge**.

# Lecture 5: EMG and Signal Processing

## 1. Electromyography (EMG)

### Definition
- **Electromyography (EMG)**: Measurement of **muscle electrical activity**
- Captures the **summed electrical potentials** of muscle fibers during contraction
- Used in **intent detection** for **prosthetic** and **rehabilitative** systems

### Types of EMG
- **Intramuscular EMG**: Fine-wire or needle electrodes inserted into muscle
- **Surface EMG (sEMG)**: Electrodes placed on skin surface

## 2. Motor Unit Action Potentials (MUAPs)
- Muscles are made of **motor units**: one **motor neuron** and the **muscle fibers** it innervates
- Each MU fires in an **all-or-none** fashion
- EMG is a **superposition** of many **MUAPs**

## 3. Raw EMG Signal Characteristics
- **Stochastic** and **non-stationary**
- Contains **noise** and **movement artifacts**
- Needs **preprocessing** for meaningful analysis

## 4. Preprocessing of EMG

### Steps:
1. **Amplification**
2. **Filtering**
   - **High-pass filter**: Removes motion artifacts (typical cutoff: 20–30 Hz)
   - **Low-pass filter**: Smooths signal (typical cutoff: 400–500 Hz)
3. **Rectification**
   - Converts signal to **absolute value**
4. **Smoothing**
   - Example: **Moving Average Filter**

### EMG Preprocessing Chain:

**Raw EMG → Filtering → Rectification → Smoothing**

## 5. Feature Extraction

- Converts EMG into **quantitative representations** for classification or regression
- Operates over **sliding windows** (e.g., 200–300 ms)

### Types of Features:
- **Time-Domain Features (TD):**
  - **Mean Absolute Value (MAV)**:
    $$
    MAV = \frac{1}{N} \sum_{i=1}^{N} |x_i|
    $$
  - **Root Mean Square (RMS)**:
    $$
    RMS = \sqrt{\frac{1}{N} \sum_{i=1}^{N} x_i^2}
    $$
  - **Zero Crossings (ZC)**:
    $$
    ZC = \sum_{i=1}^{N-1} \text{sign}[(x_i \cdot x_{i+1}) < 0]
    $$
  - **Slope Sign Changes (SSC)**:
    $$
    SSC = \sum_{i=2}^{N-1} \text{sign}[(x_i - x_{i-1})(x_i - x_{i+1}) > 0]
    $$
  - **Waveform Length (WL)**:
    $$
    WL = \sum_{i=1}^{N-1} |x_{i+1} - x_i|
    $$

- **Frequency-Domain Features** (via **FFT** or **Wavelet**):
  - **Median Frequency (MF)**
  - **Mean Frequency (MNF)**

## 6. Windowing

- EMG is processed in **overlapping windows**
- Example:
  - **Window length**: 250 ms
  - **Overlap**: 50%

- Trade-off:
  - **Short windows** → low latency, but less information
  - **Long windows** → better features, but more delay

## 7. Summary

- EMG reflects **muscle activation patterns**
- Preprocessing is crucial: **amplification**, **filtering**, **rectification**, **smoothing**
- Feature extraction enables **machine learning** models to detect intent
- Windowing enables **real-time processing**

# Lecture 6: Decoding Muscle Activity with Machine Learning

## 1. Goal
- Learn how to **decode EMG** signals using **machine learning (ML)**
- Understand application in **real-time prosthetic control**

## 2. Problem Overview
- Input: **EMG signals** from forearm muscles
- Output: **Intent classification** (e.g., grasp types, hand movements)
- Challenge: Real-time performance under **noisy, dynamic conditions**

## 3. Typical ML Pipeline for EMG Decoding
### Step-by-step:
1. **Signal Acquisition**
2. **Preprocessing**
   - **Filtering**, **rectification**, **normalization**
3. **Windowing**
   - Divide signal into **overlapping windows** (e.g., 200ms)
4. **Feature Extraction**
   - Time-domain (TD), frequency-domain (FD), time-frequency features
5. **Classification/Regression**
   - Classify movement intent or regress continuous position/velocity
6. **Postprocessing**
   - Smoothing, majority voting

## 4. EMG Features
### Time-Domain (TD) Features:
- **Mean Absolute Value (MAV)**:
  $$ \text{MAV} = \frac{1}{N} \sum_{i=1}^{N} |x_i| $$

- **Waveform Length (WL)**:
  $$ \text{WL} = \sum_{i=1}^{N-1} |x_{i+1} - x_i| $$

- **Zero Crossings (ZC)**: Number of times signal crosses 0

- **Slope Sign Changes (SSC)**: Count of slope direction changes

- **Root Mean Square (RMS)**:
  $$ \text{RMS} = \sqrt{ \frac{1}{N} \sum_{i=1}^{N} x_i^2 } $$

### Frequency-Domain Features:
- **Mean Frequency**, **Median Frequency**
- Require **FFT** computation

## 5. Classifiers
### Common Algorithms:
- **Linear Discriminant Analysis (LDA)**
- **Support Vector Machine (SVM)**
- **K-Nearest Neighbors (KNN)**
- **Random Forests (RF)**
- **Artificial Neural Networks (ANNs)**
- Trade-off between **accuracy**, **latency**, and **computational cost**

## 6. Evaluation Metrics
### Offline:
- **Accuracy**
- **Precision/Recall**
- **Confusion Matrix**
- **Cross-validation**

### Online:
- **Completion Rate**
- **Time to Completion**
- **Number of Corrections**

## 7. Dimensionality Reduction
### Techniques:
- **Principal Component Analysis (PCA)**
- **Linear Discriminant Analysis (LDA)**
- Reduces **feature space** while retaining relevant variance

## 8. Regression-Based Control
- For **proportional control** (not just classification)
- Common algorithms:
  - **Linear Regression**
  - **Multivariate Regression**
  - **Support Vector Regression (SVR)**
  - **Neural Networks**

## 9. Real-Time Control Considerations
- **Delay**
- **Stability**
- **Robustness to noise**
- **Adaptation to user and sensor shifts**

## 10. Summary
- Decoding EMG with ML is a **core task** in intent detection
- Requires **careful feature engineering**, **classifier choice**, and **real-time constraints**
- Key to achieving **natural and intuitive prosthetic control**


# Lecture 7: Machine Learning for Intent Detection

## 1. Review of Pattern Recognition Pipeline
- **Sensor Signals** → **Preprocessing** → **Feature Extraction** → **Classification/Regression** → **Postprocessing**
- Sensors: e.g., **sEMG**, **Force**, **IMU**, etc.

## 2. Machine Learning Objectives
- Train a **model** to map **input features** to **output labels**
- Types:
  - **Classification** (e.g., gesture recognition)
  - **Regression** (e.g., joint angle estimation)

## 3. Feature Vectors and Labels
- Input: **Feature vector** $$ \mathbf{x} \in \mathbb{R}^d $$
- Output:
  - Classification: **Label** $$ y \in \{1, ..., C\} $$
  - Regression: **Continuous value** $$ y \in \mathbb{R}^m $$

## 4. Model Training
- Learn a function: $$ f(\mathbf{x}) = \hat{y} $$
- Minimize a **loss function** over training data

## 5. Loss Functions
- **Classification**:
  - 0/1 Loss: $$ \mathcal{L}(y, \hat{y}) = \begin{cases} 
      0 & y = \hat{y} \\
      1 & y \neq \hat{y}
    \end{cases} $$
  - Cross Entropy:  
    $$ \mathcal{L}(y, \hat{y}) = -\sum_{c=1}^C y_c \log(\hat{y}_c) $$
- **Regression**:
  - Mean Squared Error (MSE):  
    $$ \mathcal{L}(y, \hat{y}) = \frac{1}{n} \sum_{i=1}^n (y_i - \hat{y}_i)^2 $$

## 6. Training and Validation
- **Train set**: Used to learn model parameters
- **Validation set**: Used for hyperparameter tuning
- **Test set**: Final evaluation of generalization

## 7. Common Algorithms
### a. k-Nearest Neighbors (k-NN)
- Memorizes training data
- Prediction based on **majority label of nearest neighbors**

### b. Linear Discriminant Analysis (LDA)
- Projects data for **maximal class separability**
- Assumes **Gaussian distribution** and equal class covariance

### c. Support Vector Machines (SVM)
- Finds **maximal margin hyperplane**
- Can use **kernel trick** for non-linear decision boundaries

### d. Decision Trees / Random Forests
- Trees: Splits data based on feature thresholds
- Forests: **Ensemble** of trees to improve robustness

### e. Neural Networks
- Composed of **layers of interconnected neurons**
- Output: $$ \hat{y} = f(\mathbf{x}; \theta) $$
- Trained via **backpropagation**

## 8. Evaluation Metrics
- **Accuracy**:  
  $$ \text{Accuracy} = \frac{\text{Correct Predictions}}{\text{Total Predictions}} $$
- **Precision**, **Recall**, **F1 Score** (for imbalanced datasets)

## 9. Practical Considerations
- **Overfitting**: High performance on training, low on test
- Use **cross-validation** to improve generalization
- Balance **bias-variance trade-off**

## 10. Take-Home Messages
- Machine learning enables **intent inference** from complex biosignals
- Choice of model depends on:
  - **Data type**
  - **Application**
  - **Required performance**

# Lecture 8: Closing the Loop

## 1. Recap of Prosthesis Grasping a Coffee Cup
- Real-world example:
  - Prosthesis grasps a **coffee cup**
  - Human **wants to grasp** and **drink**
- Needed components:
  - **Sensor-based feedback**
  - **Intent detection**
  - **Shared autonomy**

## 2. Preprocessing
- Converts **raw signals** to **feature vectors**
- Includes:
  - **Amplification**
  - **Filtering**
  - **Analog-to-digital conversion (ADC)**
  - **Rectification**
  - **Windowing**
  - **Smoothing**
- Goal: Obtain a **clean**, **usable signal**

## 3. Feature Extraction
### Types of features:
- **Time-domain** (TD)
- **Frequency-domain** (FD)
- **Time-frequency domain** (TFD)

### Common time-domain features:
- **Mean Absolute Value (MAV)**
  $$
  MAV = \frac{1}{N} \sum_{n=1}^{N} |x_n|
  $$

- **Waveform Length (WL)**
  $$
  WL = \sum_{n=1}^{N-1} |x_{n+1} - x_n|
  $$

- **Zero Crossings (ZC)**:
  Count of sign changes above a **threshold**

- **Slope Sign Changes (SSC)**:
  Count of changes in **slope sign** above a threshold

- **Willison Amplitude (WAMP)**:
  $$
  WAMP = \sum_{n=1}^{N-1} f(|x_{n+1} - x_n| > \text{threshold})
  $$

### Notes:
- **Thresholds** help avoid noise misclassification
- These features are **computationally efficient** and effective for **real-time** systems

## 4. Intent Detection
- Goal: Translate **features** into **actions**
- Typically via **machine learning**:
  - **Classification** (for discrete actions)
  - **Regression** (for continuous control)

### Common classifiers:
- **Linear Discriminant Analysis (LDA)**
- **Support Vector Machines (SVM)**
- **k-Nearest Neighbors (k-NN)**
- **Neural Networks (NN)**
- **Random Forests (RF)**

## 5. Closing the Loop
### Feedback types:
- **Visual** (e.g., screen or mirror)
- **Auditory**
- **Vibrotactile**
- **Electrotactile**
- **Force feedback** (via motors)

### Key Concepts:
- **Open-loop**: No feedback
- **Closed-loop**: Includes **sensor-based** feedback

### Shared Autonomy:
- The system:
  - Recognizes **user intent**
  - Executes **low-level control**
  - Provides **feedback**
- Reduces user effort and increases **usability**

## 6. Summary
- **Preprocessing** → cleans raw signals
- **Feature Extraction** → converts signals to meaningful data
- **Intent Detection** → interprets user intent using ML
- **Closing the Loop** → improves control via **feedback mechanisms**

## 7. Take-Home Message
- A full prosthetic system must:
  - **Interpret intent accurately**
  - **Respond reliably**
  - **Provide informative feedback**
- Enables **naturalistic**, **safe**, and **effective** interaction

# Lecture 9: Deep Learning for Classification and Regression

## 1. Introduction to Deep Learning
- Deep Learning is a **subset of Machine Learning**
- Utilizes **neural networks with multiple layers**
- Good at learning **non-linear relationships**
- Excels in:
  - **Image processing**
  - **Natural language processing**
  - **Sensor-based classification/regression**

## 2. What is a Neural Network?
- **Artificial Neural Networks (ANNs)** are inspired by **biological neurons**
- Consist of:
  - **Input Layer**
  - **Hidden Layers**
  - **Output Layer**
- Each node performs:
  $$ y = f\left(\sum_i w_i x_i + b\right) $$

  Where:
  - \( w_i \): weights
  - \( x_i \): inputs
  - \( b \): bias
  - \( f \): activation function

## 3. Activation Functions
- Introduce **non-linearity**
- Common examples:
  - **Sigmoid**:
    $$ \sigma(x) = \frac{1}{1 + e^{-x}} $$
  - **ReLU (Rectified Linear Unit)**:
    $$ f(x) = \max(0, x) $$
  - **Tanh**:
    $$ \tanh(x) = \frac{e^x - e^{-x}}{e^x + e^{-x}} $$

## 4. Feedforward and Backpropagation
- **Feedforward**: Inputs flow through the network to generate predictions
- **Backpropagation**:
  - Computes gradients of the **loss function**
  - Uses **gradient descent** to update weights:
    $$ w := w - \eta \cdot \frac{\partial L}{\partial w} $$
  Where:
  - \( \eta \): learning rate
  - \( L \): loss function

## 5. Loss Functions
- Measure the **difference between prediction and truth**
- Classification:
  - **Cross Entropy**:
    $$ L = -\sum_{i} y_i \log(\hat{y}_i) $$
- Regression:
  - **Mean Squared Error (MSE)**:
    $$ L = \frac{1}{n} \sum_{i=1}^n (y_i - \hat{y}_i)^2 $$

## 6. Convolutional Neural Networks (CNNs)
- Designed for **spatial data** like images and EMG signals
- Components:
  - **Convolutional layers**
  - **Pooling layers**
  - **Fully connected layers**
- Benefits:
  - **Weight sharing**
  - **Local feature extraction**

## 7. Training a Neural Network
### Steps:
1. **Initialize weights**
2. Perform **forward pass**
3. Compute **loss**
4. Perform **backward pass**
5. **Update weights**
6. Repeat for **multiple epochs**

### Key Hyperparameters:
- **Learning rate**
- **Number of layers**
- **Number of neurons**
- **Batch size**
- **Number of epochs**

## 8. Overfitting and Regularization
- **Overfitting**: Model performs well on training but poorly on test data
- Solutions:
  - **Dropout**
  - **L2 Regularization**:
    $$ L = L_0 + \lambda \sum w^2 $$
  - **Early stopping**

## 9. Evaluation Metrics
- For Classification:
  - **Accuracy**, **Precision**, **Recall**, **F1 Score**
- For Regression:
  - **MSE**, **MAE (Mean Absolute Error)**, **R² Score**

## 10. Applications in Intent Detection
- EMG signal classification
- **Multimodal sensor fusion**
- **Gesture recognition**
- **Prosthetic control**

## 11. Take-Home Messages
- **Deep learning** enables powerful **non-linear modeling**
- Key components: **architecture, activation, loss, training strategy**
- Be wary of **overfitting**
- Evaluate with **appropriate metrics**
- DL is highly useful in **intent detection and somatosensory feedback**

# Lecture 10: Grasp Classification using EMG and Machine Learning

## 1. Introduction
- Goal: Use **surface EMG (sEMG)** to predict **grasp type**.
- Application in **prosthetics** and **robotic arms**.

## 2. Typical Setup
- **sEMG electrodes** placed on forearm
- Data collected during **grasp trials**
- EMG signals are:
  - **Noisy**
  - **Non-stationary**
  - Require **preprocessing and classification**

## 3. Signal Processing Pipeline
### Steps:
1. **Pre-processing** (e.g., filtering)
2. **Feature extraction**
3. **Classifier training**
4. **Evaluation**

## 4. Feature Extraction
- Convert raw EMG signal into **meaningful features**.
- Types:
  - **Time-domain features**
  - **Frequency-domain features**
  - **Time-frequency features**

### Common Time-Domain Features:
- **Mean Absolute Value (MAV)**:
  $$
  \text{MAV} = \frac{1}{N} \sum_{i=1}^{N} |x_i|
  $$

- **Root Mean Square (RMS)**:
  $$
  \text{RMS} = \sqrt{ \frac{1}{N} \sum_{i=1}^{N} x_i^2 }
  $$

- **Waveform Length (WL)**:
  $$
  \text{WL} = \sum_{i=1}^{N-1} |x_{i+1} - x_i|
  $$

- **Zero Crossings (ZC)**:
  - Count of times the signal crosses 0
  - May include a **threshold** to ignore noise

- **Slope Sign Changes (SSC)**:
  - Number of times the slope direction changes

## 5. Frequency-Domain Features
- **Fourier Transform (FFT)** used
- Features like:
  - **Median Frequency (MDF)**
  - **Mean Frequency (MNF)**

## 6. Time-Frequency Features
- **Wavelet Transform**
  - Better suited for **non-stationary** signals like EMG

## 7. Classification
- **Supervised learning** approach:
  - Collect labeled data (e.g., different grasps)
  - Train model
- Common classifiers:
  - **Linear Discriminant Analysis (LDA)**
  - **Support Vector Machine (SVM)**
  - **k-Nearest Neighbors (kNN)**
  - **Neural Networks**

## 8. Evaluation Metrics
- **Confusion matrix**
- **Accuracy**
- **Precision**, **Recall**, **F1-score**
- **Cross-validation** to avoid overfitting

## 9. Challenges
- **Intra-subject variability**
- **Inter-subject variability**
- **Electrode displacement**
- **Muscle fatigue**
- **Signal noise**

## 10. Summary
- **EMG-based grasp classification** is feasible
- Requires careful **signal processing** and **model training**
- Used for **prosthetic control**, **rehabilitation devices**
