https://chatgpt.com/c/67803846-92b8-8005-850e-8ea5ce75cb64

### chroma
is known as the 12 distict pitch classes


### octave
is a musical interval between two pitches where the higher pitch has a frequency that is **twice** the frequency of the lower pitch.


### fundamental frequency
is known as the smallest frequeny available for a specfic pitch from an ocatve
The **fundamental frequency** is the **lowest frequency** of a periodic waveform or sound. It is the primary tone that you perceive when you hear a musical note or sound, and it determines the pitch of that sound.
- **Overtones** are higher frequencies that are integer multiples of the fundamental frequency. They contribute to the timbre of the sound.
- The first overtone is typically one octave above the fundamental. So, if the **fundamental** is **A4 (440 Hz)**, the **first overtone** is **A5 (880 Hz)**, which is one octave higher.


### chroma-based features:
the strenght of the pitch class present in the signal
- A chroma vector represents the intensity of each of these 12 pitch classes at a given time.
- Typically visualized as a 12-dimensional vector or spectrogram over time.
In the context of **chroma-based features**, the term **strength** refers to the **intensity** or **energy** associated with each pitch class (the 12 chromatic notes) at a specific point in time. This strength indicates how much of that particular pitch class is present in the sound, but it is not directly tied to any specific physical quantity like amplitude or decibels. Rather, it is more of an abstract representation of the relative presence of pitches within the signal.
1. **Strength as Energy**:
    
    - The strength of a chroma feature reflects the **amount of energy** or **power** in a particular pitch class. For example, if there's a strong C note in the audio at a given moment, the strength for the C chroma component would be higher.
    - This energy is typically computed by aggregating the spectral content of the audio signal within the frequency range corresponding to each pitch class.


### Timber
is the characteristic of a sound that leads to distinguished sound  despite having the same loudness and pitch. the reason why different instruments having the same of these both characteristics sounds the same. it is effected by the following
- **Harmonic Content**: The presence and relative intensity of overtones (higher frequency components) alongside the fundamental frequency contribute to timbre.
- **Envelope**: The shape of a sound over time—its attack, decay, sustain, and release (ADSR)—affects how the sound is perceived.
- **Resonance**: How an instrument or sound source amplifies certain frequencies.
- **Transient Characteristics**: The initial part of a sound (e.g., the "pluck" of a string or "blow" of a wind instrument) also defines timbre.

### Vibrato:
A slight, rapid variation in pitch, like a "wobble," often used by singers or instrumentalists to make the sound more expressive.
    
## Glissando:
A smooth slide between two notes, like running a finger along the strings of a harp or sliding on a piano's keys.