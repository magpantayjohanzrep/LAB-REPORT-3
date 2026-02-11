# EXPERIMENT 11 - Sampling and Reconstruction 🎙️

# OVERVIEW 🔍
- In this experiment, we explored the fundamental process of converting analog signals into digital formats, which is essential because digital transmission is rapidly replacing analog systems due to its better resistance to noise. We learned that this conversion starts with sampling, where the analog message's voltage is measured at regular intervals. We examined two specific types of sampling: "natural" sampling, where the sample amplitude follows the signal changes during the sampling pulse, and "sample-and-hold," where the voltage is held constant for the duration of the sample. The theory also highlights that to get the original message back from these slices, we can mathematically model the sampled signal as the multiplication of the message and the sampling signal, which results in many frequency components. Consequently, reconstructing the original message simply requires passing the sampled signal through a low-pass filter to isolate the message frequency. We also touched on the concept of aliasing, which distorts the signal if the sampling frequency isn't high enough—specifically, it needs to be higher than the Nyquist Sample Rate (twice the message frequency) to avoid overlapping frequencies.

# OBJECTIVES 📝
- The primary objective of this lab was to use the Emona Telecoms-Trainer 101 to practically demonstrate sampling and reconstruction techniques. Specifically, we aimed to set up and observe waveforms for both natural sampling and sample-and-hold schemes to understand their differences. We also planned to observe the effects of sampling on a real speech signal to see how it translates to practical applications. Another key goal was to successfully reconstruct the original message from the sampled output using a tunable low-pass filter. Finally, we intended to investigate the phenomenon of aliasing by manually varying the sampling frequency with a VCO module, allowing us to identify the minimum sampling rate required before distortion occurs and comparing it to the theoretical Nyquist rate.

- # Material and Component Used ⚙️
- Emona Telecoms-Trainer 101 (plus power-pack)
- Dual Channel 20MHz Oscilloscope
- two Emona Telecoms-Trainer 101 oscilloscope leads
- assorted Emona Telecoms-Trainer 101 patch leads

# SUMMARY OF FINDINGS AND RESULTS 🔬

# PART A - Sampling a simple message 📌

![figure2](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/b613f340f31a3eea3dbeb572909984bdbd6e6768/docs/images/EXPERIMENT%2011/Screenshot%202026-02-11%20212044.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/b613f340f31a3eea3dbeb572909984bdbd6e6768/docs/images/EXPERIMENT%2011/614860401_1221579643272475_685553800845256331_n.jpg)

- Based on the output waveform derived from the setup in Figure 2, we observed that the signal consisted of a train of pulses rather than a continuous wave. Specifically, we noticed that the amplitude of these pulses was not constant; instead, the tops of the pulses varied in height, perfectly tracing the envelope of the original sine wave message signal. We also observed that in the intervals between the pulses, the voltage level dropped completely to zero. This confirms that the waveform represents "natural sampling," where the signal is effectively gated—passing through only when the sampling pulse is active and returning to zero when the switch is open.

# FIGURE 2 CONFIGURED INTO FIGURE 4 ⚡

![figure4](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/b613f340f31a3eea3dbeb572909984bdbd6e6768/docs/images/EXPERIMENT%2011/Screenshot%202026-02-11%20212101.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/b613f340f31a3eea3dbeb572909984bdbd6e6768/docs/images/EXPERIMENT%2011/616090604_2593112594418248_7989708581507017289_n.jpg)

-  For the output waveform associated with Figure 4, we observed that the signal appeared as a series of distinct rectangular pulses with flat tops, resembling a staircase or a bar chart. We noticed that instead of varying continuously, the voltage level of each pulse was held constant for the duration of the sample, capturing a snapshot of the signal at that instant. We observed that these flat-topped steps collectively traced the envelope of the original message signal, but with a stepped, rather than smooth, transition between samples.

# PART B - Sampling speech 📌

![figure 6](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/b613f340f31a3eea3dbeb572909984bdbd6e6768/docs/images/EXPERIMENT%2011/Screenshot%202026-02-11%20212114.png)

OUTPUT WHEN THERE IS VOICE PRESENT 🗣️
![talking](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/b613f340f31a3eea3dbeb572909984bdbd6e6768/docs/images/EXPERIMENT%2011/613359913_3352716808209545_8959600306505742229_n.jpg)

- When voice was present: We observed that the output consisted of a continuous stream of pulses where the heights of the pulses changed rapidly and irregularly. These fluctuations in amplitude appeared to follow the complex and unpredictable patterns of the human voice, creating a dynamic pulse train that reflected the real-time speech input.

OUTPUT WHEN NOT TALKING ON SPEECH MODULE 👄
![silent](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/b613f340f31a3eea3dbeb572909984bdbd6e6768/docs/images/EXPERIMENT%2011/615005219_1575712803746982_4263192660567933253_n.jpg)

- When no voice was present: We observed that the output pulses did not disappear entirely but instead became uniform in height. Without an active speech signal to modulate the amplitude, the waveform settled into a steady, consistent pulse train with a constant peak voltage, representing the sampling of the quiet background or the system's baseline state.

# PART C - Reconstructing a sample message 📌

![figure7](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/b613f340f31a3eea3dbeb572909984bdbd6e6768/docs/images/EXPERIMENT%2011/Screenshot%202026-02-11%20212145.png)

# When the Tuneable Low-pass Filter Module's Cut-off Frequency Adjust is set to fully anti-clockwise 📌
# When the Tuneable Low-pass Filter Module's Gain control  is set to about the middle of its travel 📌

![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/b613f340f31a3eea3dbeb572909984bdbd6e6768/docs/images/EXPERIMENT%2011/615411946_4270178783234461_4006761406369097175_n.jpg)

-  When the Cut-off Frequency was fully anti-clockwise and Gain was at the middle: We observed that the output waveform appeared heavily attenuated or almost non-existent. In this state, we observed that the filter was essentially blocking the message signal along with the sampling noise, resulting in a flat or very low-amplitude line that failed to show the original sine wave.

# When the Tuneable Low-pass Filter Module's Gain control  and Cutoff frequency is varied (FULLY CONSTRUCTED)📌
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/b613f340f31a3eea3dbeb572909984bdbd6e6768/docs/images/EXPERIMENT%2011/611677579_1482733250520112_4740306865986744581_n.jpg)

- When the Gain and Cut-off Frequency were varied (Fully Reconstructed): We observed that as we adjusted the controls, a smooth, continuous sine wave began to emerge on the oscilloscope. Specifically, we observed that by correctly tuning the cut-off frequency, the "staircase" or "pulsed" appearance of the sampled signal was removed, leaving behind a clean reconstruction that closely matched the shape and frequency of the original analog message.

# PART A TO C QUESTIONS 📝

Question 1: What type of sampling is this an example of?

- Answer: This is an example of Natural sampling.

Question 2: What two features of the sampled signal confirm this?

Answer:

- The sample voltages change during the sampling period rather than remaining flat.
- The signal's voltage returns completely to zero volts between the samples.

Question 3: What two features of the sampled signal confirm that the set-up models the sample-and-hold scheme?

Answer: 

- The sample voltages do not change (they remain flat) during the sampling interval.
- There is no space or return-to-zero between the samples; one sample immediately follows the next in a staircase fashion.

Question 4: What’s the name of the distortion that appears when the VCO module’s Frequency Adjust control is turned far enough?

- Answer: The name of the distortion is Aliasing.

Question 5: Given the message is a 2kHz sinewave, what’s the theoretical minimum frequency for the sampling signal?

- Answer: The theoretical minimum frequency is 4kHz (which is calculated as $2 \times 2\text{kHz}$ message frequency).

Question 6: Why is the actual minimum sampling frequency higher than the theoretical minimum that you calculated for Question 5?

- Answer: The actual frequency must be higher because physical filters are not perfect; their rejection of frequencies beyond the cut-off is gradual rather than instantaneous. Therefore, a "guard band" is needed to prevent the filter from failing to reject the lowest frequency aliases.

# Reflection/Learning Summary 💡

- This experiment provided me with a clear, hands-on understanding of the bridge between analog and digital communications. By working with the Emona Telecoms-Trainer 101, I was able to see that sampling isn't just a mathematical concept, but a physical process of "gating" information. Comparing natural sampling and sample-and-hold was particularly eye-opening; I learned that while natural sampling preserves the message’s shape during the pulse, sample-and-hold creates a "staircase" effect that is much more representative of how real-world Analog-to-Digital Converters (ADCs) operate.

- One of the most important takeaways for me was the critical role of the low-pass filter in reconstruction. It was fascinating to see how a series of disjointed pulses or sharp steps could be smoothed back into a clean sine wave just by isolating the correct frequency components. It made the theory of "multiplication in the time domain" much more tangible. I also realized how vital the sampling rate is; observing aliasing firsthand showed me exactly why the Nyquist criteria matters. If we don’t sample fast enough, the original information is lost to distortion that no filter can fix.

- Lastly, applying these concepts to a speech signal made the lab feel relevant to modern technology. Seeing how my own voice modulated the pulse train helped me understand how cell phones and computers process our conversations. Overall, this experiment reinforced the idea that while digital systems are superior for noise resistance, they rely entirely on precise timing and filtering to maintain the integrity of the original analog signal.
