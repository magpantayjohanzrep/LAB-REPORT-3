# EXPERIMENT 17 - Binary Shift Keying1️⃣0️⃣

# OVERVIEW 🔍
- Binary Phase Shift Keying (BPSK) is a digital modulation technique that serves as a robust alternative to Amplitude Shift Keying (ASK) and Frequency Shift Keying (FSK). Rather than altering the amplitude or frequency of the carrier, BPSK utilizes the logic 1s and 0s of a digital data stream to switch the carrier between two phases, specifically shifting the phase by $180^{\circ}$ whenever the logic level changes. Close observation reveals that the BPSK signal's envelope mimics the shape of the message, indicating that it is effectively a Double-Sideband Suppressed Carrier (DSBSC) signal. Consequently, BPSK generation and recovery can be achieved using conventional DSBSC modulation and demodulation methods. Although it may be more complex to implement than ASK or FSK, BPSK is often the preferred system because it offers superior performance in terms of noise immunity, resulting in fewer errors at the receiver

# OBJECTIVES 📝
- The primary objective of this experiment is to use the Emona Telecoms-Trainer 101 to generate a BPSK signal by implementing its mathematical model using a Multiplier module and a Sequence Generator to model the digital data. Students will then aim to recover the digital data using a product detector (consisting of a Multiplier and Low-pass filter) and observe the distortion present in the demodulated signal. Furthermore, the experiment seeks to demonstrate how to restore the recovered data to a clean digital signal using a comparator circuit. Finally, if the optional activity is conducted, students will model a noisy channel to observe the effects of noise on the BPSK signal and the system's ability to withstand it

# Material and Component Used ⚙️
- Emona Telecoms-Trainer 101 (plus power-pack)
- Dual Channel 20MHz Oscilloscope
- three Emona Telecoms-Trainer 101 oscilloscope leads
- assorted Emona Telecoms-Trainer 101 patch leads
- one set of headphones (stereo)

# SUMMARY OF FINDINGS AND RESULTS 🔬

# PART A - Generating a BPSK signal📌

![figure2](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/fe3ee1f379fc277de696db5f19074e57d2feb14e/docs/images/EXPERIMENT17/Screenshot%202026-02-11%20172838.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/fe3ee1f379fc277de696db5f19074e57d2feb14e/docs/images/EXPERIMENT17/623300799_1484518543469138_391521807117921879_n.jpg)

- We observed that the output waveform is a Binary Phase Shift Keying (BPSK) signal where the carrier wave maintains a constant frequency and amplitude but undergoes abrupt changes in phase. Specifically, we observed that whenever the digital data stream transitions between logic levels, the phase of the carrier signal shifts by exactly $180^{\circ}$. We also observed that this transition is visually distinct; for instance, where the signal is traveling towards a positive peak, the change in logic level causes it to immediately reverse direction and head back toward the negative peak.

# PART B - Demodulating a BPSK signal using a product detector📌

![figure4](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/fe3ee1f379fc277de696db5f19074e57d2feb14e/docs/images/EXPERIMENT17/Screenshot%202026-02-11%20172849.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/fe3ee1f379fc277de696db5f19074e57d2feb14e/docs/images/EXPERIMENT17/623413814_1382185869837925_5727128073387598535_n.jpg)

- We observed that the output waveform is the demodulated baseband signal, which represents the recovered digital data. We observed that the waveform follows the logic pattern of the message, alternating between voltage levels to represent bits. We observed that the signal pulses are not perfectly square but exhibit rounded corners and sloping transitions. We observed that this distortion gives the waveform a "smoothed" appearance, indicating that the high-frequency components have been filtered out during the demodulation process.

# PART C - Restoring the recovered data using a comparator📌

![figure6](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/fe3ee1f379fc277de696db5f19074e57d2feb14e/docs/images/EXPERIMENT17/Screenshot%202026-02-11%20172901.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/fe3ee1f379fc277de696db5f19074e57d2feb14e/docs/images/EXPERIMENT17/625065639_1965563804839729_6973336613526538446_n.jpg)

- In the final stage of the experiment, we observed that the output waveform is a restored digital signal that has been "cleaned up" by the comparator circuit. We observed that this waveform takes the shape of a sharp, binary square wave, which is produced when the comparator evaluates the distorted demodulated signal against a specific reference level. We observed that the specific characteristics of this output, such as the pulse width and overall shape, are directly influenced by the DC voltage level provided by the Variable DCV module. Additionally, we observed that while the signal is restored to a clean digital state, it may still exhibit a phase shift relative to the original source signal.

# PART A TO C QUESTIONS 📝

Question 1: What happens to the BPSK signal on the data stream's logic transitions?

- Answer: We observed that when a change in the logic level occurs in the data stream, the BPSK signal's phase changes by $180^{\circ}$. For instance, if the signal is moving toward a positive peak at the moment of transition, it will reverse direction and head toward a negative peak, or vice versa.

Question 2: What feature of the BPSK signal suggests that it's a DSBSC signal?

- Answer: We observed that alternating halves of the BPSK signal’s envelopes share the same shape as the message. This characteristic indicates that BPSK is essentially a form of double-sideband suppressed carrier (DSBSC) modulation. 

Question 3: What feature of the BPSK signal suggests that it's a DSBSC signal?

- Answer: While the manual does not explicitly state the technical reason (such as propagation delay or filter bandwidth), it instructs the student to compare the signals and note that the recovered version is a distorted representation of the original data stream.
  
Question 4: What feature of the BPSK signal suggests that it's a DSBSC signal?

- Answer: We observed that a comparator circuit is used to "clean up" or restore distorted digital signals. By comparing the distorted signal against a reference level, the comparator converts it back into a sharp binary waveform.

Question 5: What feature of the BPSK signal suggests that it's a DSBSC signal?

- Answer: We observed that varying the DC voltage on the comparator's input changes the threshold at which the circuit switches between logic high and low. This adjustment allows the user to manipulate the pulse width of the restored digital signal to match the original source, despite any phase shifts.

# Reflection/Learning Summary 💡

# Conceptual Understanding of BPSK:

- The core learning centered on how BPSK functions as a digital modulation technique. Unlike ASK (amplitude) or FSK (frequency), BPSK relies on phase transitions to represent digital data. A fundamental takeaway was the observation of the 180° phase shift; we observed that at every logic transition in the data stream, the carrier wave reverses its direction. This visual evidence solidified the concept that phase can be used as an efficient carrier of binary information.

# The Relationship Between BPSK and DSBSC:

- One of the most insightful aspects of the experiment was identifying BPSK as a specific form of Double-Sideband Suppressed Carrier (DSBSC) modulation. We observed that the signal's envelopes mirror the shape of the original message, which explained why we could use standard DSBSC demodulation tools—specifically a product detector—to recover the data. This connection highlighted the versatility of analog communication modules in digital applications.

# Practical Challenges in Signal Recovery:

- The transition from Part B to Part C highlighted the practical realities of telecommunications. We observed that simply demodulating a signal through a low-pass filter does not yield a perfect digital copy; instead, the result is a distorted, "smoothed" waveform due to the filtering of high-frequency components. This underscored the necessity of a Restoration stage in digital receivers.

# The Critical Role of the Comparator:

- The experiment successfully demonstrated the utility of a comparator as a decision-making tool in digital systems. We learned that by setting a specific reference voltage using the Variable DCV module, we could "clean up" the distorted signal back into a sharp square wave. We observed that this reference level is crucial, as it directly determines the pulse width and accuracy of the restored data relative to the original source.

# System Performance and Noise Immunity

- Reflecting on the preliminary discussion, the experiment reinforced why BPSK is a preferred modulation scheme in modern systems. Despite being more complex to implement than ASK or FSK, its superior noise immunity and lower error rates make it the most robust choice for high-reliability communications. This theoretical advantage was practically supported by observing how effectively the comparator could reconstruct the signal even after it had been smoothed by the demodulation process.
