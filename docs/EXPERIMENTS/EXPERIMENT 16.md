# EXPERIMENT 16 - Frequency Shift Keying 📈

# OVERVIEW 🔍
- Frequency Shift Keying (FSK), also commonly referred to as Binary Frequency Shift Keying (BFSK), is a frequency modulation (FM) scheme utilized to transmit digital data by superimposing a message onto a carrier signal.  In this modulation technique, the signal switches between two distinct frequencies to represent binary data: a "space frequency" typically lower than the nominal carrier frequency which corresponds to logic-0s, and a "mark frequency" usually higher than the nominal carrier which corresponds to logic-1s. A significant advantage of FSK is its relative immunity to noise compared to amplitude modulation schemes; because noise manifests as variations in amplitude, it can be removed by a limiter circuit in FM/FSK receivers without adversely affecting the recovered message. While FSK generation is commonly handled by Voltage-Controlled Oscillators (VCOs) and standard FM demodulators, this experiment explores an alternative demodulation method where a selective filter isolates one of the signal's sinewaves, allowing the data to be recovered through an envelope detector as if it were an Amplitude Shift Keying (ASK) signal.

# OBJECTIVES 📝
- The primary objective of this experiment is to use the Emona Telecoms-Trainer 101 to implement the Voltage-Controlled Oscillator (VCO) method of generating an FSK signal, using a Sequence Generator module to model the digital message data. Students will then attempt to recover this data by using a tuneable low-pass filter to isolate one of the sinewaves within the FSK signal and demodulating it using an envelope detector. Finally, the experiment aims to demonstrate how to observe the distortion in the demodulated FSK signal and use a comparator circuit to restore the recovered waveform back into clean digital data.
  
# Material and Component Used ⚙️
- Emona Telecoms-Trainer 101 (plus power-pack)
- Dual Channel 20MHz Oscilloscope
- three Emona Telecoms-Trainer 101 oscilloscope leads
- assorted Emona Telecoms-Trainer 101 patch leads
- one set of headphones (stereo)

# SUMMARY OF FINDINGS AND RESULTS 🔬

# PART A - Generating an FSK signal 📌

![figure2](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/071e10a7843115a709f1757c3a0caf11475bcf30/docs/images/EXPERIMENT%2016/Screenshot%202026-02-11%20165247.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/071e10a7843115a709f1757c3a0caf11475bcf30/docs/images/EXPERIMENT%2016/624994668_885647537691900_7747651454698658371_n.jpg)

- Based on the output waveform associated with Figure 2, we observed a continuous sinusoidal signal that maintains a constant peak-to-peak amplitude throughout the display. We observed that the distinguishing feature of the waveform is the distinct variation in its frequency, which alternates between two specific states. We observed sections where the waveform cycles are compressed and dense, indicating a higher frequency, and other sections where the cycles are wider and more spread out, indicating a lower frequency. We observed that these frequency shifts occur abruptly, representing the toggling between the specific 'mark' and 'space' frequencies.

# PART B - Demodulating an FSK signal using filtering and an envelope detector 📌

![figure4](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/071e10a7843115a709f1757c3a0caf11475bcf30/docs/images/EXPERIMENT%2016/Screenshot%202026-02-11%20165258.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/071e10a7843115a709f1757c3a0caf11475bcf30/docs/images/EXPERIMENT%2016/625901104_1968354280784169_2272952905970689858_n.jpg)

- Based on the output waveform associated with Figure 4, we observed that the signal is no longer a continuous constant-amplitude sine wave. We observed that the waveform consists of intermittent bursts of a sinusoidal signal separated by periods where the signal amplitude drops to nearly zero. We observed that this creates a distinct "on-off" pattern, where the sine wave is present and visible during specific intervals and effectively absent during others, resembling an Amplitude Shift Keying (ASK) signal structure.

# FIGURE 4 CONFIGURED INTO FIGURE 7 ⚡

![figure7](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/071e10a7843115a709f1757c3a0caf11475bcf30/docs/images/EXPERIMENT%2016/Screenshot%202026-02-11%20165309.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/071e10a7843115a709f1757c3a0caf11475bcf30/docs/images/EXPERIMENT%2016/623296562_1897090331171135_1409318416958428915_n.jpg)

- Based on the output waveform associated with Figure 7, we observed a baseband signal that approximates the shape of a digital square wave but exhibits distinct rounding and smoothing effects. We observed that the waveform does not have sharp, vertical transitions; instead, it displays sloping rising and falling edges, characteristic of the charging and discharging effects found in envelope detection. We observed that the signal successfully alternates between high and low voltage levels, corresponding to the detected presence or absence of the carrier bursts, effectively recovering the envelope of the signal.

# PART C - Restoring the recovered data using a comparator 📌

![figure8](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/071e10a7843115a709f1757c3a0caf11475bcf30/docs/images/EXPERIMENT%2016/Screenshot%202026-02-11%20165316.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/071e10a7843115a709f1757c3a0caf11475bcf30/docs/images/EXPERIMENT%2016/623291543_1051919297137968_7734246970038140301_n.jpg)

- Based on the output waveform associated with the setup in Figure 8, we observed a clean, rectangular digital signal characterized by sharp, vertical transitions between high and low voltage levels. We observed that the waveform maintains constant flat amplitudes during its high and low states, creating a distinct and stable pulse train structure. We observed that the signal clearly defines binary Logic-1 and Logic-0 states with immediate switching, representing a fully restored digital data stream.

# PART A TO C QUESTIONS 📝

Question 1: What's the name for the VCO output frequency that corresponds with logic-1s in the digital data?

- Answer: Mark frequency. The manual states that the frequency corresponding to logic-1s is called the "mark frequency" and is usually higher than the nominal carrier frequency.

Question 2: What's the name for the VCO output frequency that corresponds with logic-Os in the digital data?

- Answer: Space frequency. The manual states that the frequency corresponding to logic-0s is called the "space frequency" and is usually lower than the nominal carrier frequency.

Question 3: Based on your observations of the FSK signal, which of the two is the higher frequency? Explain your answer.

- Answer: The Mark frequency (corresponding to Logic-1) is the higher frequency. The preliminary discussion establishes that the mark frequency is usually higher than the modulator's nominal carrier frequency, while the space frequency is usually lower. Visually, the waveform sections corresponding to Logic-1s will appear more "compressed" with more cycles, indicating a higher frequency.

Question 4: Which of the FSK signal's two sinewaves is the filter picking out?

- Answer: The lower frequency (Space frequency) sinewave.  The procedure involves using a Tuneable Low-pass Filter (LPF) and adjusting the cut-off until the "higher frequency component of the FSK signal becomes equal to zero". Since a low-pass filter passes frequencies below a certain point and rejects those above it, removing the higher frequency leaves the lower frequency to be "picked out" or passed through.

Question 5: What does the filtered FSK signal look like?

- Answer: It looks like an Amplitude Shift Keying (ASK) signal. The manual explains that when one sinewave is isolated from the FSK signal, the result is effectively an ASK signal. This appears as bursts of a sine wave (during the periods of the "picked out" frequency) separated by periods of zero amplitude (where the rejected frequency used to be).

Question 6: What can be used to "clean-up" the recovered digital signal?  

- Answer: A Comparator. The manual introduces Part C by stating that a comparator is a "useful circuit for restoring distorted digital signals" and is used to "clean-up" the demodulated FSK signal.

Questiion 7: How does the comparator turn the slow rising voltages of the recovered digital signal into sharp transitions?

- Answer: The comparator compares the varying input voltage against a fixed reference voltage (threshold). When the input voltage crosses this threshold level, the comparator's output switches states almost instantaneously (snapping to its maximum positive or negative output). This rapid switching effectively "squares off" the slow rising and falling edges of the distorted signal, restoring them to sharp, vertical digital transitions.

# Reflection/Learning Summary 💡

# The Nature of FSK: 

- I learned that FSK is essentially a "switching" mechanism. By using a Voltage-Controlled Oscillator (VCO), I observed how the carrier wave adapts to the digital input, shifting to a higher "Mark" frequency for Logic-1 and a lower "Space" frequency for Logic-0. This visualized the concept of constant-amplitude but variable-frequency transmission.

# Alternative Demodulation Techniques:

- A significant insight from this lab was that FSK demodulation doesn't strictly require a dedicated FM discriminator. I learned that by using a Tuneable Low-Pass Filter, we can manipulate the FSK signal to behave like an Amplitude Shift Keying (ASK) signal. By filtering out the higher frequency component, we effectively turned the frequency variation into an "presence/absence" (on/off) variation, which allowed us to use simple envelope detection to recover the data.

# Signal Distortion and Restoration:

- The experiment highlighted the reality of analog signal processing. The output from the envelope detector (Figure 7) was not a perfect square wave; it was rounded and "sloppy" due to the charging and discharging nature of the detector components. This demonstrated that raw demodulation often results in distortion.

# The Role of the Comparator:

- I learned that the Comparator is critical for digital data recovery. It acts as a threshold decision-maker, taking the distorted, rounded waveform and converting it back into sharp, vertical digital transitions. This reinforced the concept that digital systems are robust because they can "regenerate" clean signals even after significant analog distortion.

