# 🎙️ Speech Production Modelling using Linear Predictive Coding (LPC)

This repository demonstrates vowel synthesis and analysis using **Linear Predictive Coding (LPC)** in MATLAB.  
The project models how human vowels are produced by combining a **source–filter model** of speech:  
- the *excitation source* (voiced periodic impulse train), and  
- the *vocal-tract filter* (approximated by LPC coefficients).  

> 🧠 This was implemented as part of MSc coursework on Speech & Audio Processing (University of Surrey, 2025).

---

## 🧩 Overview

### 🔹 Objectives
- Load and inspect recorded male and female vowel sounds (`/æ/` – “had”, `/iː/` – “heed”).  
- Extract 100 ms **quasi-stationary** segments for analysis.  
- Compute **LPC coefficients** to estimate the vocal-tract filter.  
- Compare the **FFT magnitude spectrum** with the **LPC spectral envelope**.  
- Estimate **formant frequencies (F₁–F₃)** from LPC poles.  
- Perform **pitch estimation** using the Normalised Correlation Function (NCF).  
- Re-synthesise vowels using a periodic impulse-train excitation filtered through the LPC model.  
- Evaluate model sensitivity to **order** and **segment length**.

---

## 🧮 Signal-Processing Pipeline
Audio input (.wav)
↓
Pre-processing & Quasi-stationary Segmentation
↓
LPC Analysis (Autocorrelation Method)
↓
FFT vs LPC Envelope Comparison
↓
Formant Estimation (from LPC Poles)
↓
Pitch Estimation (NCF)
↓
Speech Synthesis using Impulse-Train Excitation
↓
Spectral & Perceptual Evaluation

---

## 📂 Repository Structure

speech-production-lpc/
│
├── SCRIPT_1_Analysis_Estimation.m       # Quasi-stationary analysis, LPC, formant & pitch estimation
├── SCRIPT_2_Synthesis_Evaluation.m      # Excitation, synthesis, order/segment evaluation
├── data/                                # Input vowel recordings (not distributed publicly)
├── audio_output/                        # Synthesised speech samples
├── figures/                             # All generated plots (2.1 – 6.2)
├── README.md
└── LICENSE

---

## 🧾 Key Results

### 🗣️ Waveform & Spectrograms
| Male /æ/ | Female /iː/ |
|:--:|:--:|
| ![](figures/Figure_2_1_Waveforms.png) | ![](figures/Figure_2_2_Spectrograms.png) |

### 🔍 FFT vs LPC Envelopes
| Male (p = 29) | Female (p = 25) |
|:--:|:--:|
| ![](figures/Figure_3_1_Male_FFT_LPC.png) | ![](figures/Figure_3_2_Female_FFT_LPC.png) |

### 🔊 Synthesised Speech
| Male Synth | Female Synth |
|:--:|:--:|
| ![](figures/Figure_5_1_SynthSpectrograms.png) | ![](figures/Figure_6_1_OrderSensitivity.png) |

Formant estimation confirmed expected ranges for English vowels:  
- **Male /æ/** → F₁ ≈ 730 Hz, F₂ ≈ 1220 Hz, F₃ ≈ 2520 Hz  
- **Female /iː/** → F₁ ≈ 310 Hz, F₂ ≈ 2320 Hz, F₃ ≈ 3120 Hz  

Pitch estimation produced mean **F₀ ≈ 105 Hz (male)** and **F₀ ≈ 224 Hz (female)**.  
Both values are physiologically consistent with typical human vocal ranges.

---

## 🧠 Concepts Highlighted
- Quasi-stationary assumption in speech analysis  
- All-pole filter modelling of the vocal tract  
- LPC coefficient estimation using the autocorrelation method  
- Pitch detection via NCF (autocorrelation)  
- Spectral envelope vs. harmonic detail interpretation  
- Formant extraction from complex poles  
- Trade-off between LPC order and spectral fidelity  

---

## ⚙️ Requirements
- MATLAB R2023a or newer  
- Signal Processing Toolbox  
- Optional: Audio Toolbox for playback (`sound()`)

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/<yourusername>/speech-production-lpc.git
   cd speech-production-lpc
   ```

2.	Open MATLAB and set this folder as your working directory.
3.	Run the scripts in order:

   run("SCRIPT_1_Analysis_Estimation.m");
   run("SCRIPT_2_Synthesis_Evaluation.m");

4.	All figures and synthesised audio will be saved in /figures and /audio_output.

📚 References
	•	L. R. Rabiner & R. W. Schafer, Theory and Applications of Digital Speech Processing, Pearson, 2011.
	•	J. D. Markel & A. H. Gray, Linear Prediction of Speech, Springer, 1976.
	•	T. F. Quatieri, Discrete-Time Speech Signal Processing, Prentice Hall, 2002.
	•	MathWorks Documentation, LPC Function￼.

   


