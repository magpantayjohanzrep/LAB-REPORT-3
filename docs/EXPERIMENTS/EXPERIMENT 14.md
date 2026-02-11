# EXPERIMENT 14 - Bandwidth Limiting and restoring digital signals 📉

# OVERVIEW 🔍
-  In the classical communications model, information is transmitted from a sender to a receiver through a specific channel, such as coaxial cables, optical fibers, or free-space airwaves. Regardless of the medium, all channels possess a finite bandwidth that allows a specific range of frequencies to pass while attenuating others, effectively acting as a filter . Since digital signals are composed of a fundamental sine wave and multiple harmonics, a channel with insufficient bandwidth will attenuate or lose these components, leading to signal distortion and changes in the pulse shape. Furthermore, a bandwidth-limited channel can shift the phase of sine waves by varying amounts, making it difficult for digital receivers like PCM decoders to accurately interpret logic levels. This distortion ultimately results in misinterpreted codes and incorrect voltage generation, which manifests as "noise" in the recovered message.

# OBJECTIVES 📝
- The primary objective of this experiment is to use the Emona Telecoms-Trainer 101 to establish a functional PCM communications system and investigate the impact of channel limitations. Specifically, the experiment aims to model bandwidth limiting by introducing a low-pass filter into the channel and observing how this affects the integrity of PCM data. Students will use an oscilloscope to visually monitor signal changes and listen to the effects on the recovered message to understand how bandwidth constraints degrade performance. Additionally, the experiment seeks to demonstrate the use of a comparator for restoring digital signals while identifying the inherent limitations of such restoration methods. Finally, the study explores how increasing the transmission bit rate can produce similar negative effects on signal quality as reducing the channel's bandwidth.

# Material and Component Used ⚙️
- Emona Telecoms-Trainer 101 (plus power-pack)
- Dual Channel 20MHz Oscilloscope
- three Emona Telecoms-Trainer 101 oscilloscope leads
- assorted Emona Telecoms-Trainer 101 patch leads
- one set of headphones (stereo)

# SUMMARY OF FINDINGS AND RESULTS 🔬

# PART A - The effects of bandwidth limiting on PCM decoding 📌

![figure3](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/Screenshot%202026-02-11%20135743.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/623867351_4174964919420050_8152293009720767833_n.jpg)

- We observed a clear demonstration of the distortion introduced by a bandwidth-limited channel on a digital signal. The upper waveform represents the ideal digital signal at the channel's input, characterized by sharp, near-instantaneous transitions between logic high and logic low states, forming clean square pulses.

- In strong contrast, we observed that the lower waveform, which shows the signal at the channel's output, has lost its sharp edges and appears significantly "rounded." The transitions between logic levels are no longer vertical but have become sloping rise and fall times. We observed that this distortion occurs because the channel, acting as a low-pass filter, has a finite bandwidth and attenuates the high-frequency harmonics that are essential for defining the sharp corners of the original square wave. This resulting "smeared" pulse shape visually confirms how we observed bandwidth limitations degrading a digital signal, which can make it difficult for a receiver to accurately interpret the intended logic levels.

# FIGURE 3 CONFIGURED INTO FIGURE 5 ⚡

![figure5](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/Screenshot%202026-02-11%20135751.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/624535853_1172342345114674_4722083362218335825_n.jpg)

- We observed that passing the distorted, rounded signal through the Comparator resulted in a new output waveform that regained the characteristics of a digital signal. We observed that the Comparator successfully "squared up" the incoming signal, producing an output with sharp, vertical rising and falling edges, effectively removing the rounding caused by the channel's limited bandwidth.

- However, we also observed a significant discrepancy in timing. Although the shape was restored, the new output waveform was phase-shifted (delayed in time) relative to the original source signal. This confirmed to us that while the Comparator can restore the pulse shape, it cannot correct the time delay introduced by the channel's filtering effect.

# PART B - The effects of bandwidth limiting on digital signal's shape 📌

![figure7](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/Screenshot%202026-02-11%20135801.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/624950630_1552807402443655_3414360807485823360_n.jpg)

- Based on the oscilloscope display presented in Figure 7, **we observed** two distinct waveforms. **We observed** that the upper waveform represents the original digital signal, characterized by sharp, vertical transitions defining clear logic high and logic low states.

- In contrast, when examining the lower output waveform, **we observed** significant signal degradation. Specifically, **we observed** that the sharp edges present in the input signal were lost, replaced by sloped rise and fall times that gave the pulses a heavily rounded appearance. Furthermore, **we observed** a noticeable time delay (phase shift) between the start of the transitions in the upper original signal and the corresponding transitions in the lower output signal.

# When Cutoff Frequency is anti-fully clockwise ✂️

![figure8](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/Screenshot%202026-02-11%20135832.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/623282225_3790322834610887_6878593146518579966_n.jpg)

- Based on the oscilloscope display presented in Figure 8, we observed two distinct waveforms. We observed that the upper waveform, representing the original source signal, displayed sharp, definite transitions between logic high and logic low states. We observed that the lower waveform, representing the output of the comparator, also displayed sharp, vertical rising and falling edges, indicating that the rectangular pulse shape had been re-established. However, we distinctly observed a noticeable time interval (time delay or phase shift) between the edges of the upper source signal and the corresponding edges of the lower output signal.

- When the Cut-off Frequency adjust knob on the Tuneable Low-pass Filter module is turned fully anti-clockwise, the filter's bandwidth is set to its narrowest possible setting.
This results in the aggressive filtering (attenuation) of nearly all high-frequency harmonics from the input digital signal, allowing only the fundamental frequency and perhaps a few very low harmonics to pass. Consequently, the output signal becomes severely distorted, losing all its sharp corners and appearing highly rounded, resembling a sine wave or a triangular wave rather than a square wave. This setting also typically introduces the maximum amount of signal attenuation (loss of amplitude) and the largest phase shift (time delay) through the channel.

![figure9](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/Screenshot%202026-02-11%20135843.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/623940191_1089611129960527_8950423111742464396_n.jpg)

-Based on the oscilloscope display presented in Figure 9, we observed two distinct waveforms representing a high-frequency digital transmission. We observed that the upper waveform displayed the input digital signal, characterized by rapid, narrow rectangular pulses with sharp transitions between logic states.

-In contrast, when examining the lower waveform representing the channel output, we observed severe signal distortion. We observed that the sharp, rectangular shape of the input pulses was completely lost, replaced by a highly rounded signal that resembled a sine wave more than a digital pulse train. Furthermore, we observed significant attenuation, where the output signal often failed to reach the full logic high or logic low voltage levels of the input signal because the input pulses were switching too rapidly for the channel to fully respond.


# Eye Diagrams 👁️

![Fig 1: Eye Diagram](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/Screenshot%202026-02-11%20135902.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/625774341_881121241558732_2846130380463338105_n.jpg)

- Based on the conceptual block diagram presented in Figure 1, we observed a visual representation of the fundamental communications model. We observed that the system is composed of three primary distinct blocks connected in series: a Transmitter, a Channel, and a Receiver. Furthermore, within the central "Channel" block, we specifically observed a graphical illustration along with text explicitly labeling it as "bandwidth limited," visually defining the channel's role as a filter that restricts frequency passage between the source and the destination.

# PART C - Restoring digital signals 📌

![figure11](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/Screenshot%202026-02-11%20135928.png)

# When the Variable DCV module's Variable DC control is set to about middle of its travel📌
![DCVmiddle](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/623791796_747505751415286_7777259145517777575_n.jpg)

# When the Variable DCV module's Variable DC control is set to fully clockwise 📌
![DCVfully](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/622631205_1272677248101406_2491296174545313081_n.jpg)

# When the Variable DCV module's Variable DC control is set to fully anti-clockwise 📌
![DCVAnti](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/625810893_1537561760834263_2915498082717427290_n.jpg)

- Based on the three distinct oscilloscope displays presented in Figure 11, we observed in each case an upper waveform representing a noisy, distorted analog input signal, and a corresponding lower waveform representing a clean, restored digital output signal with sharp vertical transitions. We specifically observed that the width (duration) of the logic high and logic low pulses in the lower output waveform varied significantly depending on the setting of the comparator's threshold voltage.

# Explanation of Variable DCV Control Settings:

# Variable DC control set to about middle of its travel  📌
- When the control was set to the middle, we observed that the reference voltage was set roughly at the midpoint of the noisy signal's vertical swing. Because the input signal spent approximately half its time above this midpoint and half below it, the resulting restored digital output was a near-symmetrical square wave with roughly equal durations for the logic high and logic low states.

#  Variable DC control set fully clockwise 📌
- When the control was turned fully clockwise, we observed that the reference voltage was raised to a very high level, near the peaks of the noisy input signal. Since the input signal only briefly crossed above this high threshold, the resulting output waveform consisted of very narrow logic high pulses separated by long periods of logic low.

# Variable DC control set fully anti-clockwise 📌
- When the control was turned fully anti-clockwise, we observed that the reference voltage was lowered to a very low level, near the bottom troughs of the noisy input signal. Since the input signal stayed above this low threshold for the majority of the time, the resulting output waveform consisted of very wide logic high pulses separated by brief drops to logic low.

# FIGURE 11 CONFIGURED INTO FIGURE 13 ⚡

![figure13](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/Screenshot%202026-02-11%20135935.png)

# When the Tuneable Low-pass Filter Module's Cut-off Frequency Adjust is set to fully anti-clockwise 📌
![CFanti](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/623306366_1229417288621312_6960208515197105755_n.jpg)

# When the Tuneable Low-pass Filter Module's Cut-off Frequency Adjust is set to fully clockwise 📌
![CFfully](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a8bf5a0495dd75cec54b6a672c9a139d5f342e32/docs/images/EXPERIMENT14/623107384_875161035155604_3121497194071811563_n.jpg)

- Based on the two oscilloscope displays presented side-by-side in Figure 13, we observed the relationship between an incoming signal from the channel (upper traces) and the subsequent decoded digital output signal (lower traces) under two distinct filter conditions. In both displays, we observed that the PCM decoder was attempting to reconstruct a clean digital pulse train (lower traces) from the analog input signal it received (upper traces).

# Explanation of Tuneable Low-pass Filter Settings:

# Cut-off Frequency Adjust set to fully anti-clockwise 📌
- In this configuration, we observed the effects of the narrowest bandwidth setting. The filter aggressively attenuated high frequencies, causing the input signal (upper trace) to become heavily rounded and distorted. Because of this significant distortion, the PCM decoder struggled to precisely determine the transition points between logic levels. Consequently, we observed that the recovered digital output signal (lower trace) exhibited irregularities, such as varying pulse widths or jitter, indicating potential errors in data recovery.

# Cut-off Frequency Adjust set to fully clockwise  📌
- In this configuration, we observed the effects of the widest bandwidth setting. The filter allowed a broad range of frequencies to pass, resulting in an input signal (upper trace) that retained much sharper edges and possessed better definition. Because the input signal was clear, the PCM decoder could accurately interpret the logic states. Therefore, we observed a clean, stable, and accurate recovered digital output signal (lower trace) with regular, well-defined pulses.

# PART A TO C QUESTIONS 📝

- Question 1: Why does bandwidth limiting of the channel cause the PCM Decoder module to output incorrect voltages as well as the correct one?

 Answer: Bandwidth limiting acts as a filter that attenuates (reduces) and phase-shifts the harmonics that make up the digital signal pulses . This distortion changes the shape of the pulses, making them rounded or "smeared" rather than sharp square waves. As a result, the PCM Decoder struggles to accurately interpret the logic levels (distinguishing 1s from 0s). When the decoder misinterprets a code, it generates an incorrect voltage value instead of the correct sample voltage.

- Question 2: If this were a communications system transmitting speech, what would these errors sound like when the message is reconstructed?

  Answer: These errors would manifest as "noise" in the recovered speech. The incorrect voltages generated by the misread codes would create audible distortion, making the speech sound garbled or static-filled.

- Question 3: What two things are happening to cause the digital signal to change shape?

Answer: 
- Attenuation of Harmonics: The channel filters out or reduces the amplitude of the higher-frequency harmonics that are essential for defining the sharp edges of the square wave.
- Phase Shifting: The channel shifts the phase of the signal's sine wave components by varying amounts, further distorting the alignment of the components that form the pulse.
- Question 4: What other change to your communication system distorts the digital signal in the same way as increasing its bit-rate?

  Answer: Reducing the channel's bandwidth distorts the digital signal in the same way as increasing the bit-rate. As observed in the experiment, trying to push more data through an existing channel (increasing the bit rate) has the same basic effect as narrowing the bandwidth, leading to signal distortion .

- Question 5: Although the restored digital signal is almost identical to the original digital signal, there is a difference. Can you see what it is?

Answer: Yes, the restored signal is phase-shifted (delayed in time) compared to the original digital signal . While the comparator restores the sharp edges and pulse shape, it cannot correct the time delay caused by the channel's filtering effect.

- Question 6: Can this difference be ignored? Why?
  
Answer: It depends on the application, but generally, a constant phase shift (time delay) can often be ignored or compensated for in asynchronous systems where only the data integrity matters, not the absolute timing relative to the source clock. However, in synchronous systems where timing is critical for sampling, this delay could cause synchronization errors if not accounted for. The manual notes that the channel shifts phases by different amounts, which complicates interpretation

- Question 7: Why do some DC voltages cause the comparator to output the wrong information?

Answer: The comparator outputs the wrong information because its reference threshold (set by the DC voltage) is either too high or too low relative to the incoming signal's amplitude. If the threshold is set too high (near the signal's peak), the signal only briefly crosses it, resulting in pulses that are too narrow. If set too low (near the signal's trough), the signal stays above it too long, resulting in pulses that are too wide. This incorrect pulse width distorts the information carried by the digital signal.

- Question 8: Why does the comparator begin to output the wrong information when this control is turned for enough?

Answer: When the control is turned far enough (fully clockwise or anti-clockwise), the reference voltage moves completely outside the range of the input signal's voltage swing. If the reference voltage is higher than the signal's maximum peak or lower than its minimum trough, the comparator will stop switching altogether, outputting a constant logic level (either always Low or always High) instead of the digital data stream. This results in a complete loss of information.

# Reflection/Learning Summary 💡

# The Physical Reality of Digital Signals
- This experiment provided a crucial insight into the difference between ideal theoretical models and physical reality. While we often visualize digital signals as perfect square waves with instantaneous transitions, I learned that in the real world, they are composed of a fundamental sine wave and infinite harmonics. The channel acts as a filter, and because no physical channel has infinite bandwidth, some high-frequency harmonics are always lost. This experiment visually demonstrated that a "digital" signal is effectively analog while it is traveling through a medium, subject to the same laws of physics (attenuation and phase shifting) as any other wave.

# The Critical Relationship Between Bandwidth and Bit Rate

- One of the most significant takeaways was the reciprocal relationship between channel bandwidth and transmission speed.
- Reducing Bandwidth: We observed that narrowing the channel (turning the filter anti-clockwise) "smeared" the pulses, leading to inter-symbol interference.
- Increasing Bit Rate: We observed that increasing the data speed produced the exact same distortion as reducing the bandwidth.
Reflection: This confirms that "bandwidth" is not an absolute value but is relative to the speed of the data being sent. This explains why we cannot simply "turn up the speed" on existing internet cables without upgrading the physical infrastructure to handle wider bandwidths.

# The Limits of Signal Restoration

- The experiment demonstrated the power and limitations of digital regeneration. Using the Comparator, we were able to take a messy, rounded sine-like wave and turn it back into a sharp square wave. This explains why digital communication is generally more robust than analog—we can "clean up" the signal at the receiver.

- However, I learned that restoration is not perfect. The Phase Shift (Time Delay) introduced by the channel’s filtering could not be corrected by the comparator. This highlights that while we can recover the shape (logic levels), maintaining the correct timing (synchronization) is a separate and equally difficult engineering challenge.

# The Importance of Threshold Voltage (Decision Levels)

- The manipulation of the Variable DC control taught me the importance of the "decision threshold" in a receiver.

- If the threshold is not perfectly centered, the recovered pulse widths become distorted (too wide or too narrow).

- If the threshold drifts too far (fully clockwise/anti-clockwise), data is completely lost.
Reflection: In a real-world system, this emphasizes the need for stable reference voltages and automatic gain control (AGC) to ensure the receiver is always "looking" at the center of the incoming signal to avoid bit errors.





