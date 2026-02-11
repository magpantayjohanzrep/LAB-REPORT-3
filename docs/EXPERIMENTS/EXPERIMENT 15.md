# EXPERIMENT 15 - Amplitude Shift Keying 📡

# OVERVIEW 🔍
- In modern telecommunications, sharing a communication channel—whether it be copper wire, optical fiber, or free space, is essential to allow multiple users to transmit simultaneously. One primary method for achieving this is Frequency Division Multiplexing (FDM), which assigns users exclusive access to specific portions of the radio frequency spectrum by superimposing messages onto a carrier signal. When digital data is multiplexed using Amplitude Modulation (AM) techniques, the process is known as Amplitude Shift Keying (ASK), also referred to as on-off keying or continuous wave modulation. This experiment explores ASK, where the digital signal's logic levels determine the presence or absence of the carrier. While ASK is advantageous because it can be demodulated with a simple envelope detector, it is highly susceptible to channel noise, which can distort the signal's envelope and lead to bit errors at the receiver.

# OBJECTIVES 📝
- The primary objective of this experiment is to model the generation and demodulation of an Amplitude Shift Keying (ASK) signal using the Emona Telecoms-Trainer 101. Specifically, students will learn to generate an ASK signal by employing a switching method, where a Sequence Generator module models digital data to control the connection of a carrier signal to the channel. Another objective is to implement and examine the performance of a simple envelope detector,consisting of a rectifier and a tunable low-pass filter—to recover the original digital message from the ASK signal. Throughout the process, students will observe the inherent distortions in the recovered signal caused by the demodulation process and finally utilize a comparator module to "clean up" and fully restore the digital data.

  # Material and Component Used ⚙️
- Emona Telecoms-Trainer 101 (plus power-pack)
- Dual Channel 20MHz Oscilloscope
- three Emona Telecoms-Trainer 101 oscilloscope leads
- assorted Emona Telecoms-Trainer 101 patch leads

# SUMMARY OF FINDINGS AND RESULTS 🔬

# PART A - Generating an ASK signal📌

![figure 2](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/6efe23ce395849a691283cc10ebaf0dbfa5bb351/docs/images/EXPERIMENT%2015/Screenshot%202026-02-11%20161712.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/6efe23ce395849a691283cc10ebaf0dbfa5bb351/docs/images/EXPERIMENT%2015/623454000_1257655846282746_6746462022658991401_n.jpg)

- Based on the output waveform of Figure 2, we observed an Amplitude Shift Keying (ASK) signal generated using the switching method. We observed that the waveform consists of a sinusoidal carrier wave that is pulsed on and off in direct synchronization with the digital message signal. Specifically, we observed that when the digital data is at a Logic 1 (High) level, the carrier signal is present with a constant amplitude. Conversely, we observed that when the digital data drops to a Logic 0 (Low) level, the carrier signal is completely cut off, resulting in a flat line at zero volts. Finally, we observed that the transitions between the "on" and "off" states are sharp and instantaneous, corresponding directly to the rising and falling edges of the control signal.

# FIGURE 2 CONFIGURED INTO FIGURE 4⚡

![figure4](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/6efe23ce395849a691283cc10ebaf0dbfa5bb351/docs/images/EXPERIMENT%2015/Screenshot%202026-02-11%20161727.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/6efe23ce395849a691283cc10ebaf0dbfa5bb351/docs/images/EXPERIMENT%2015/627580820_904049942116350_8436175128694713757_n.jpg)

- In this part of the experiment, we observed the generation of an Amplitude Shift Keying (ASK) signal using a lower frequency carrier. We observed that the output waveform appears as a series of "bursts" of a sinusoidal wave separated by flat intervals of zero voltage. Specifically, we observed that the analog switch allows the 2kHz sine wave to pass through to the output only when the control signal is High (Logic 1), creating the "mark" state. Conversely, we observed that when the control signal is Low (Logic 0), the switch opens and the output drops to zero, creating the "space" state. Effectively, we observed that the digital sequence gates the sine wave, resulting in a signal where the presence of oscillations represents digital ones and the absence represents digital zeros.

# PART B - Demodulationg an ASK signal using an envelope detector📌

![figure6](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/6efe23ce395849a691283cc10ebaf0dbfa5bb351/docs/images/EXPERIMENT%2015/Screenshot%202026-02-11%20161738.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/6efe23ce395849a691283cc10ebaf0dbfa5bb351/docs/images/EXPERIMENT%2015/623806101_2194062554334983_7082148570229413541_n.jpg)

- In this stage of the experiment, we observed the recovered message signal at the output of the envelope detector (rectifier and low-pass filter). We observed that the waveform reconstructs the basic shape of the original digital sequence, clearly showing high and low voltage states corresponding to the presence and absence of the carrier. However, we observed that the signal is not a perfect square wave; instead, it exhibits distinct rounded corners and sloping edges during the transitions, caused by the charging and discharging time constants of the low-pass filter. Additionally, we observed small ripples remaining on the peaks of the signal, representing trace amounts of the carrier frequency that passed through the filter.

# PART C - Restoring the recovered digital signal using a comparator📌

![figure8](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/6efe23ce395849a691283cc10ebaf0dbfa5bb351/docs/images/EXPERIMENT%2015/Screenshot%202026-02-11%20161752.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/6efe23ce395849a691283cc10ebaf0dbfa5bb351/docs/images/EXPERIMENT%2015/626403040_2087680398748574_8687578634923162613_n.jpg)

- In this final stage of the experiment, we observed the output waveform after passing the filtered signal through the Comparator module. We observed that the Comparator has successfully "squared up" the distorted signal, restoring it to a clean digital format. Specifically, we observed that the rounded edges and amplitude ripples previously seen in the envelope detector stage have been completely eliminated, resulting in sharp, vertical transitions between voltage levels. We observed that this output is a rectangular pulse train that closely matches the original digital message, confirming that the digital data has been fully recovered and cleaned of noise.

# PART A TO C QUESTIONS 📝

Question 1: What is the relationship between the digital signal and the presence of the carrier in the ASK signal?

- Answer: The relationship is that the digital signal acts as a switch for the carrier. When the digital signal is at a Logic-1 (high), the carrier signal is present (on). When the digital signal is at a Logic-0 (low), the carrier signal is absent (off).

Question 2: What is the ASK signal's voltage when the digital signal is logic-0?

- Answer: When the digital signal is at logic-0, the ASK signal's voltage is zero volts (0V). This creates the "off" state in the on-off keying modulation.

Question 3: What feature of the ASK signal suggests that it's an AM signal?

- Answer: The feature suggesting it is an AM (Amplitude Modulation) signal is that the ASK signal's upper and lower limits (the envelopes) trace the same shape as the modulating digital data stream. Essentially, the amplitude of the carrier changes in direct response to the message signal, which is the definition of AM.

Question 4: Why is the recovered digital signal not a perfect copy of the original?

- Answer: The recovered signal is not perfect because the envelope detector (rectifier and low-pass filter) introduces distortion. The low-pass filter's charging and discharging time constants cause the "square" edges of the digital pulses to become rounded and sloped. Additionally, some ripple from the carrier frequency may still remain on the signal.

Question 5: What can be used to "clean-up" the recovered digital signal?

- Answer: A Comparator module can be used to clean up the recovered digital signal. It squares up the rounded edges and removes amplitude variations, restoring the signal to a clean digital format.

Question 6: How does the comparator turn the slow rising voltages of the recovered signal into sharp transitions?

- Answer:
  
- The comparator achieves sharp transitions by utilizing its incredibly high open-loop voltage gain to force its output into saturation the instant the input signal crosses a specific reference threshold. Instead of linearly amplifying the slow rising slope of the recovered signal, the comparator acts as a binary switch: it constantly compares the incoming voltage against a fixed reference level (often zero or a midpoint voltage).

- As the slowly rising input voltage climbs, it eventually exceeds this reference level. At that precise moment, the comparator's high gain amplifies even the tiniest difference between the input and the reference, causing the output to immediately snap to its maximum positive voltage (Logic High). Conversely, when the input falls below the reference, the output instantly snaps to its minimum voltage (Logic Low). This rapid switching effectively ignores the gradual slope of the input, replacing the slow rise and fall times with near-vertical, sharp edges, thus restoring the clean "square" shape of the original digital data.

# Reflection/Learning Summary 💡

# Understanding the Mechanics of ASK Generation

- Through this experiment, I learned that Amplitude Shift Keying (ASK) is fundamentally a digital application of Amplitude Modulation (AM). The generation process using the "switching method" was particularly insightful. It demonstrated that complex modulation doesn't always require complex circuitry; a simple analog switch controlled by a digital sequence is sufficient to gate a carrier frequency. Observing the waveform confirm that Logic 1 corresponds to the presence of the carrier (Mark) and Logic 0 corresponds to its absence (Space) solidified my understanding of how binary data is physically represented in an analog medium.

# The Reality of Signal Demodulation

- One of the most critical takeaways from this experiment was the realization that demodulation is rarely perfect in the initial stage. While the envelope detector (rectifier + low-pass filter) successfully recovered the general shape of the digital data, the output was significantly distorted compared to the original input. I observed that the "square" pulses became rounded with sloping edges due to the capacitor's charging and discharging time constants. This practical observation highlighted the trade-off in analog electronics: the filter removes the high-frequency carrier but inevitably slows down the transition speed of the digital data.

# The Critical Role of Signal Restoration

- The final stage of the experiment demonstrated the necessity of signal conditioning in digital communications. I learned that a "messy" analog signal (the output of the envelope detector) is often unusable for precise digital logic until it is cleaned up. The use of the Comparator module was a key learning moment; understanding how its high open-loop gain forces the output to "snap" between saturation levels based on a reference threshold explained how we can recover sharp, vertical transitions from a sluggish, rounded input. This process of "squaring up" the signal is essential for preventing bit errors in real-world telecommunications.

- Experiment 15 provided a complete picture of a communication system's lifecycle: Modulation $\rightarrow$ Demodulation $\rightarrow$ Restoration. It bridged the gap between the theoretical concept of "sending 1s and 0s" and the physical reality of voltage levels, carrier frequencies, and noise management. The experiment proved that while ASK is susceptible to noise and distortion during simple envelope detection, these issues can be effectively managed with proper post-processing using a comparator.






