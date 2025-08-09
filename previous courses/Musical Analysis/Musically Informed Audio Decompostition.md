

https://chatgpt.com/c/67803846-92b8-8005-850e-8ea5ce75cb64



- 2 pages without references; do **not** copy text or figures from the book
 - only the most important points covered in the main section
	- motivation of the problem
	- most important technical details
- feedback on the book chapter and lecture



![[Screenshot from 2025-01-09 21-21-33.png]]

## Introduction


- audio signal is mixture of different sounds from different sources inducing noise. We are concerned here with source separation.
- extracting the different kinds of instruments from a single recording sample.
- very difficult problem because the sound sources are highly correlated. Sometimes theres an assumption that mulutple channels or aduio sources are used.
- different musical properties related to various instruments and voice is exploited to make this process easier.
- three specific ways of decomposing audio
	- section 1 - seperation of precussive and harmonic sounds
	- section 2 - extracting melody with the help of notes from fundermental frequency (predominant frequeny, salience representation, instantaneuos frequency, harmonic summation)
	- seciton 3 - non max factorization for notewise seperation


## Main Sections

### Harmonic Percussive Sound Separation
We have two kinds of sounds, Harmonics: which are responsible for melodies and chords these sustain over time, and can be seen as horizontal lines on a decomposed spectogram analysis. On the other hand, Percussive sounds are single ticks that are localised in time they don't have pitch and they have a vertical line.
HPSS can be consider vague because its difficult to tell what is percussive and harmnonic sometimes .In this process from the spectogram representaiton we oncsider the hortizontal and vertical lines sperately with the help of filtering. Creating a time frequeny-mask from these spectrogram they are applied to the orginal specrogram and with the help of inverse STFT harmonic and percussive sources are obtain.
- horizontal-vertical spectogram decomposition
	- taking the signal x and decomposing it such that x = x h +x p .
	- 1. computing the STFT on the signal
	- X (n, k) := N−1 ∑ r=0 x(r +nH)w(r) exp(−2πikr/N),
	- and taking the power spectrogram Y(n,k) := |X (n, k)| 2
	- 2. when applying median filtering, we can look at as harmonics are outliers against frequency, and percussives are outliers against time. the filtering here removes the outliers respectively by applying it on the both directions respectively. By applying Median in a certain way it has this property that is pushes out the outlier values which we are trying to achieve here. with this we now obtain two filtered spectrograms Y˜ h and Y˜ p
	- 3 Binary and soft masking - the upper are not used directly instead they are used to generate another two masks. There are two methodes,
		- for binary masking, for each point, values for the mask are set as either zero or one if the filtered percussive value is greater the that of harmonics or vice versa
		- for soft masking, we consider relative weighing when comparing the spectorgram values
	- the masked filter is multipied with original spectogram to obtain the harmonic, and percussive spectogram
	- 4. Now we apply the two masks directly on the original STFT to obtain xh and xp
	- 5. the STFTS are converted back into the time domain with the inverse STFT
- Signal re construction from the modified STFT: the problem is the MSTFT may not represent a valid STFT of any signal. During the reconstruction phase this mabye because of introducing information from neighbouring frames So we try to minimise the differences between the MSTFT and STFT. With the distance measure Δ(XMod​,X0​) to quantify difference between both signals with find the x signal which is as close as possible to Xmod given as:
		x∗(r)=∑n​w(r−nH)2∑n​w(r−nH)vn​(r−nH)​
	
Application:
HPS has several applicaitons, in context to the desired instrument for instance, piano or drum. it can be useful for enhancing chroma based feature: chroma features are focussed on small pitchwise subbands. eliminating the noise from filtering percussive can make the process easier. Similarly for onset detection percussive we can take advantage to enahance the vertical time frequeny patterns.

### Melody Extraction
- "a melody is a linear expression of musical tones pressing a particular musical idea." This appears coherent and pleasing to listeners ears.
- melody is the leading composition with higher notes appearing in the foreground, other artifacts are in the background with sometimes as lower notes
- audio decomposition, such that we extract the frequency that correspond to the main melody.
- We analyse the frequency corresponding to the notes pitches to determine the frequency trajectory [1] with that we are interested in the f0 values for the leads instrument/ voice subjected to melody
- This is a challenging task due to overlapping frequencies of various kinds, as well as attributing the f0 frequency to the correct source of interest.
- Overview of the process for melody extraction:
	- refined frequeny estimation to get improved log frequeny spectrogram. and using harmonics summation to get a salience representation to extract predominent melody. with the f0 trajectory we get the melody and accompinied track.
#### Instantaneous Frequency Estimation
- Instantaneous frequency is a process to refine the frequency for melody extraction. The method of dividing the signal to its time and frequency components via STFT is no viable because its grid size may not capture slight in change pitch such as for vibrato, and glissando. This method refines frequency estimates by analyzing the phase information of the STFT. Phase represents the position of a wave within its cycle. By measuring how the phase changes between consecutive time frames, the instantaneous frequency is calculated as the rate of this change.
	- The phase at time n−1n-1n−1 and nnn is ϕ(n−1,k)\phi(n-1, k)ϕ(n−1,k) and ϕ(n,k)\phi(n, k)ϕ(n,k). The phase difference between these two time points is Δϕ=ϕ(n,k)−ϕ(n−1,k)\Delta \phi = \phi(n, k) - \phi(n-1, k)Δϕ=ϕ(n,k)−ϕ(n−1,k).
	- FIF​(k,n)=ΔtΔϕ​
	- This calculation allows finer frequency resolution beyond the STFT's fixed grid.
#### Salience Representation
- Salience representation helps in increasing the accuracy by refining the log-frequency spectrogram. It may not be appropriate to arrange frequeny bins in logarithmic scale. The log frequency is refined by grouping the coeffiecents that corresponds to the same frequeny bin. Which results in a better representation for the frequncies.
- IF provides more precise frequency bins. The refined frequency estimates are used to update the bin slices improving frequency resolution.
- we can enhance the spectogram by considering both fundamental frequency and f0 estimation
- Harmonic Summation: harmonic summation allows the spectrogram values at the harmonic positions.
- Log Frequency Harmonic Summation: in the log frequency domain, harmonic relations are additive instead of multiplicative so the summation needs to be adjusted accordingly
- the results is a salience representation: Z=Y~IFLF​
#### Informed Fundamental Frequency (F0) Tracking
- to identify the main melody from the salience representation. 
- consider Z(n,b) indicates the likelihood of a frequency bin bbb at time frame nnn.
	- framewise maximum tracking: selecting frequency bin with maximum (n,b) at each time frame n  ηmax​(n)=argb∈[1:B]max​Z(n,b)
	- limitations: catures non melody compenents and produces outliers and discontinuities.
- for the limitations we can use transition likely hood matrix to introdude smoothness.
- - T(b,c): Likelihood of transitioning from bin bbb at frame nnn to bin ccc at frame n+1n+1n+1.
- T(b,c)=11+∣b−c∣T(b, c) = \frac{1}{1 + |b - c|}T(b,c)=1+∣b−c∣1​
- we can wincorporate some music knowldge to improve the f0 tracking.
	- define regions in time frequency plain based on the musical score. and only allow f0 tracking in these regions
	- manual adjustments in the based on the score if a note is missing
#### Applications
- identifying melody throgh qureing via humming. the database stores all the extracted melodies from which the queried melody is compared. a perfect f0 trajectory may not be required for this. one can do this via mid level representation and tolerate local extraction errors.
- automated generation of karaoke version for a given song. This requires melody separation from the music. Melody extraction algorithim is applied, two stfts are derived from masking techniques from which we can obtain the desired signal.

### NMF-Based Audio Decomposition
Decomposing audio into note-wise events from original signals which allows new ways of editing audio.
The idea behind Non negative matrix factorisation is that a matrix V with non negative entries can be factorised to two components W and H (which should only contain non-negative entries as well). Which are easier to understand and more accessible for original processing than the original matrix. This is difficult to compute so instead we go for approximation.
#### non negative matrix factorisation
We aim to decompose the Matric V with spectral vectors in a magnitude spectrogram with DImensions K and N to its consitutes W a non negative matrix of basis or template vectors. and Non-negative matrix H of activations and coefficients. The goal with NMF is to minimize the distance between V and W.H since we are approximating.
**Euclidean distance** can be used to quantify the measure between V and WH to acheive the best factorisation
∥V−W⋅H∥2=k=1∑K​n=1∑N​(Vkn​−(W⋅H)kn​)2
**Gradient descent** can be used to iteratively minimise the euclidean distance between V and W.H by adjsting W and H step by step
Gradient of HHH:
∂ϕW∂Hρν=2((WTWH)ρν−(WTV)ρν)\frac{\partial \phi_W}{\partial H_{\rho\nu}} = 2 \left( (W^T W H)_{\rho\nu} - (W^T V)_{\rho\nu} \right)∂Hρν​∂ϕW​​=2((WTWH)ρν​−(WTV)ρν​)
Gradient of WWW:
∂ϕH∂Wkr=2((WHHT)kr−(VHT)kr)\frac{\partial \phi_H}{\partial W_{kr}} = 2 \left( (W H H^T)_{kr} - (V H^T)_{kr} \right)∂Wkr​∂ϕH​​=2((WHHT)kr​−(VHT)kr​)
**Multiplicative update rules** are used since it is essential that the values of W and H remain non-negative.
Update for HHH:
Hρν(ℓ+1)=Hρν(ℓ)⋅(WTV)ρν(WTWH(ℓ))ρνH_{\rho\nu}^{(\ell+1)} = H_{\rho\nu}^{(\ell)} \cdot \frac{(W^T V)_{\rho\nu}}{(W^T W H^{(\ell)})_{\rho\nu}}Hρν(ℓ+1)​=Hρν(ℓ)​⋅(WTWH(ℓ))ρν​(WTV)ρν​​
Update for WWW:
Wkr(ℓ+1)=Wkr(ℓ)⋅(VHT)kr(W(ℓ)H(ℓ)HT)krW_{kr}^{(\ell+1)} = W_{kr}^{(\ell)} \cdot \frac{(V H^T)_{kr}}{(W^{(\ell)} H^{(\ell)} H^T)_{kr}}Wkr(ℓ+1)​=Wkr(ℓ)​⋅(W(ℓ)H(ℓ)HT)kr​(VHT)kr​​

The NMF process alternates between updating W and H iteratively using the mulitplicative update rules until convergence.
Algorithim
- Initialize W(0)W^{(0)}W(0) and H(0)H^{(0)}H(0) randomly or using some heuristic.
- Update H(ℓ+1)H^{(\ell+1)}H(ℓ+1): H(ℓ+1)=H(ℓ)⋅(W(ℓ))TV(W(ℓ))TW(ℓ)H(ℓ)H^{(\ell+1)} = H^{(\ell)} \cdot \frac{(W^{(\ell)})^T V}{(W^{(\ell)})^T W^{(\ell)} H^{(\ell)}}H(ℓ+1)=H(ℓ)⋅(W(ℓ))TW(ℓ)H(ℓ)(W(ℓ))TV​
- Update W(ℓ+1)W^{(\ell+1)}W(ℓ+1): W(ℓ+1)=W(ℓ)⋅V(H(ℓ+1))TW(ℓ)H(ℓ+1)(H(ℓ+1))TW^{(\ell+1)} = W^{(\ell)} \cdot \frac{V (H^{(\ell+1)})^T}{W^{(\ell)} H^{(\ell+1)} (H^{(\ell+1)})^T}W(ℓ+1)=W(ℓ)⋅W(ℓ)H(ℓ+1)(H(ℓ+1))TV(H(ℓ+1))T​
- Repeat steps 2 and 3 until convergence
#### Spectrogram Factorisation 
Now NMF can be applied to and audio recording to extract its individual notes as following:
we take the magnitude of the STFT
V:=∣X∣T and decompose it into W and H
to imporve results, contraints are imposed on W and H
- **Harmonic Templates:** For instruments like pianos, templates can enforce harmonic structures (energy around the fundamental frequency and its harmonics).
    - For pitch ppp with fundamental frequency Fpitch(p)F_\text{pitch}(p)Fpitch​(p), set harmonic positions h⋅Fpitch(p)h \cdot F_\text{pitch}(p)h⋅Fpitch​(p) (h=1,2,3,…h = 1, 2, 3, \dotsh=1,2,3,…) to nonzero values.
- This ensures that the harmonic structure is preserved and refined during learning.

**Score-Informed Constraints**
If prior knowledge, such as a musical score, is available:

1. **Set RRR:** Use the number of distinct pitches in the score to set the rank RRR.
2. **Align Time:** Use synchronized score information to constrain activations HHH. For instance, allow only specific time intervals for activation entries.

To include **note onsets** (percussive components):

1. **Add Onset Templates:** Introduce extra templates for each pitch to model note onsets.
2. **Temporal Constraints:** Restrict activation of onset templates to short time intervals around predicted onset times.
- Onset templates capture broadband energy, leaving harmonic templates cleaner and more focused.

#### Audio Decomposition
**NMF based Audio Decomposition** divides an audio signal into components based on musical score, mapping the coefficients to specific note events. 

In **Separation Process Using Spectral Masking**, audio components are separated by using spectral masking. It separates the audio into different note groups, like the left and right hand of a piano, by creating soft masks based on the NMF results. These masks help preserve important spectral details and reduce artifacts.

with **Notewise Audio Processing**  the goal is to break down an audio recording into individual note events from a score. Each note event is isolated and processed separately using masking techniques, and the residual (leftover) signal is calculated to assess the quality of the decomposition.

In **Audio Editing** , using the score-informed decomposition, users can edit an audio recording interactively. For example, they can modify notes (change pitch, duration, or volume) within the score, and these changes are reflected in the audio. This allows for easy manipulation of musical recordings based on score alterations.

## Reference
8.2 Melody Extraction 439 [1]

## Feedback




