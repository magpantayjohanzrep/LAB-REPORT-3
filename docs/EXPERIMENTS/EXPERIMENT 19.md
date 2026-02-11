# EXPERIMENT 19 - DSSS modulation and demodulation 🔢

# OVERVIEW 🔍
- In this experiment, we explored Direct Sequence Spread Spectrum (DSSS), which acts as a variation of the Double Sideband Suppressed Carrier (DSBSC) modulation scheme. Unlike standard DSBSC that uses a simple sinusoidal carrier, DSSS employs a pulse train known as a Pseudo-Noise (PN) sequence. Since a pulse train theoretically consists of an infinite number of sinewaves, DSSS is effectively the DSBSC modulation of a theoretically infinite number of carrier signals. We learned that this technique spreads the message information across many sidebands, making the signal difficult to deliberately jam or detect. To recover the message, we utilized a product detector, which requires a local carrier that is perfectly synchronized with the transmitter's PN sequence. Throughout the procedure, we used the Emona Telecoms-Trainer 101 to model the DSSS generation and demodulation process.

# OBJECTIVES 📝
- The main objective of this laboratory exercise is to explore the principles of Direct Sequence Spread Spectrum (DSSS) by modeling its modulation and demodulation processes. Specifically, we aim to understand how a pulse train, or Pseudo-Noise (PN) sequence, can be used as a carrier to spread a message signal across a wide range of frequencies, effectively creating a DSBSC signal with an infinite number of sidebands. Another key goal is to implement a product detector using a multiplier and a low-pass filter to successfully recover the original message. By "stealing" the PN sequence from the transmitter to use as a synchronized local carrier, we seek to demonstrate the necessity of phase and frequency synchronization in DSSS communication. Finally, we intend to gain hands-on experience with the Emona Telecoms-Trainer 101 to visualize these signals on an oscilloscope and observe how DSSS can provide a level of security and resistance to interference.

# Material and Component Used ⚙️
- Emona Telecoms-Trainer 101 (plus power-pack)
- Dual Channel 20MHz Oscilloscope
- three Emona Telecoms-Trainer 101 oscilloscope leads
- assorted Emona Telecoms-Trainer 101 patch leads

# SUMMARY OF FINDINGS AND RESULTS 🔬

# PART A - Generating a DSSS signal using a simple message 📌

![figure1](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/Screenshot%202026-02-11%20185506.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/624621293_1635680821211669_1149074799025148892_n.jpg)

- For the setup illustrated in Figure 1, we connected the message source and the sequence generator to the multiplier module to generate the DSSS signal. When viewing the output on the oscilloscope, we observed a complex waveform that possessed a distinct envelope matching the 2kHz sine wave message. The interior of this envelope appeared to be "filled in" with high-frequency rectangular pulses, which resulted from the pseudo-noise sequence acting as the carrier. Essentially, we observed that the amplitude of the high-speed PN sequence rose and fell in perfect synchronization with the message signal, creating a waveform that visually represented the spreading of the message across the carrier's bandwidth.

# PART B - Generating a DSSS signal using speech 📌

![figure3](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/Screenshot%202026-02-11%20185520.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/625968241_834298766300365_7125975519194501454_n.jpg)

- For the setup corresponding to Figure 3, we observed the output waveform when the message signal was changed to a speech signal (or dynamic source). We observed that the waveform continued to exhibit the high-frequency "filled-in" appearance characteristic of the pseudo-noise carrier, but the constant envelope seen in the previous step was replaced by a rapidly fluctuating envelope. We observed that this envelope followed the amplitude variations of the speech pattern, rising and falling with the volume of the voice. Furthermore, we observed that during pauses in speech, the output signal dropped to zero (or very near zero), which effectively demonstrated the suppressed-carrier nature of the DSSS modulation where no power is transmitted without a message.

# PART C - Using the product detector to recover message 📌

![figure4](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/Screenshot%202026-02-11%20185528.png)

- For the setup shown in Figure 4, we examined the output of the demodulation stage on the oscilloscope. We observed that the waveform appeared as a clean sinusoidal wave with a frequency of approximately 2kHz. We observed that this output signal closely matched the shape and frequency of the original message signal generated at the start of the experiment. This indicated that the product detector, synchronized with the local "stolen" PN sequence, had successfully despread the wideband signal and recovered the original baseband information.

# Analysis of Tuneable Low-Pass Filter Settings ⚙️

# Tuneable Low - Pass Filter module; Gain control about middle of its travel 📌
# Tuneable Low - Pass Filter module; Cut-off Frequency to fully anti-clockwise 📌
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/623949072_1555488282414397_2676018891423388704_n.jpg)

- In this position, we observed that the filter's cut-off frequency was set to its minimum value. We observed that the output waveform disappeared or became a flat line, as the filter bandwidth was too narrow to allow the 2kHz message signal to pass through.

# Tuneable Low - Pass Filter module; Gain control about middle of its travel 📌
# Tuneable Low - Pass Filter module; Cut-off Frequency clockwise 📌
![adjusted figure 4](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/623454000_2112119502887310_7245169626294734797_n.jpg)

- As we turned the frequency control clockwise, we observed that the filter's bandwidth increased. This setting allowed the 2kHz message frequency to pass to the output while still filtering out the high-frequency components from the multiplication process, resulting in the visible recovery of the sine wave.

# FIGURE 4 CONFIGURED INTO FIGURE 7 ⚡

![figure7](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/Screenshot%202026-02-11%20185608.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/624546590_1987451531985581_3700905301448067781_n.jpg)

- For the waveform presented in Figure 7, we observed the output of the demodulator on the oscilloscope. We observed that the signal appeared as a low-amplitude, irregular waveform resembling random noise, rather than a clean, periodic wave. We observed that there was no discernible message signal or recognizable pattern within this output. This confirmed that when the local Pseudo-Noise sequence does not match the transmitter's sequence, the product detector is unable to despread the signal, leaving the message buried within the noise-like carrier.

# PART D - DSSS and deliberate interference (jamming)📌

![figure8](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/Screenshot%202026-02-11%20185618.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/628297805_1201732302149561_6785245225388990560_n.jpg)

- For the setup described in Figure 8, we observed the output waveform after introducing an interference (or jamming) signal into the transmission channel. We observed that despite the presence of significant noise/interference in the channel, the output of the demodulator was a clearly recognizable sine wave that matched the original message frequency. We observed that the waveform was slightly "fuzzier" or contained more noise compared to the ideal conditions, but the message integrity was maintained. This observation highlighted the "processing gain" of the DSSS system, showing that it could successfully suppress the interference and recover the original information.

# FIGURE 8 CONFIGURED INTO FIGURE 10 ⚡

![figure10](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/Screenshot%202026-02-11%20185628.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/623819437_2668372463528753_3585021732391406614_n.jpg)

- For the waveform displayed in Figure 10, we examined the output of the demodulator when a second DSSS signal was added to the channel to simulate a Code Division Multiple Access (CDMA) environment. We observed that the oscilloscope showed a clearly recognizable sine wave, which corresponded to the target message we were trying to recover. We observed that although the waveform appeared slightly "fuzzy" or noisy due to the interference from the second user sharing the channel, the desired signal was successfully extracted. This confirmed that by using the correct, synchronized Pseudo-Noise sequence, we could isolate the specific message even in the presence of other DSSS transmissions.

# FIGURE 10 CONFIGURED INTO FIGURE 11 ⚡

![figure11](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/Screenshot%202026-02-11%20185637.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/a3279bb17875e9efb1793c5d72e61c7abbbe62e4/docs/images/EXPERIMENT%2019/625673497_1449250566711224_1627005964756315453_n.jpg)

- For the waveform displayed in Figure 11, we observed the output of the demodulator when attempting to recover the message from an unwanted or non-synchronized DSSS signal (simulating the rejection of a different user in a CDMA system). We observed that the distinct sine wave message was no longer present, and the output appeared as a low-level, irregular waveform resembling random noise. We observed that this confirmed the selectivity of the system, as the product detector was unable to despread the signal using the mismatched Pseudo-Noise sequence, effectively treating the unwanted transmission as background noise.

# PART A TO D QUESTIONS 📝

Question 1: What feature of the Multiplier module's output suggests that it's basically a DSBSC signal?

- Answer: The output waveform exhibits envelopes that follow the shape of the message signal, but the carrier itself is suppressed. Specifically, the DSSS signal’s amplitude rises and falls in sync with the message, similar to a standard Double Sideband Suppressed Carrier (DSBSC) signal, but filled with high-frequency pulses (the PN sequence) instead of a simple sine wave.

Question 2: Why is the DSSS signal so large when it's supposed to be small and indistinguishable from noise?

- Answer: In this experiment, the DSSS signal is generated at a large amplitude to make it visible on the oscilloscope for educational purposes. In a real-world application, the spreading of energy across a wide bandwidth would reduce the power spectral density to below the noise floor, but here it is kept high to allow for easy observation and analysis.

Question 3: Why isn't there any signal out of the DSSS modulator when you're not talking, etc?

- Answer: This is because DSSS is a suppressed-carrier modulation scheme. Without a message signal input (amplitude of zero), the multiplication process results in an output of zero. Therefore, no power is transmitted when there is no information (speech) to modulate.

Question 4:  What does the signal out of the low-pass filter look like?

- Answer: The signal out of the low-pass filter looks like the original message signal (a 2kHz sine wave). This indicates that the low-pass filter successfully removed the high-frequency components generated by the multiplier, leaving only the recovered baseband message.

Question 5: Why does using the wrong PN sequence for the local carrier cause the product detector's output to look like this

- Answer:  DSSS demodulation requires the receiver's local PN sequence to be identical and perfectly synchronized with the transmitter's PN sequence. The product detector multiplies the incoming signal by the local sequence. If the sequences match, the phase reversals are removed ("despreading"), leaving the original message to pass through the filter. If the sequences are wrong or out of sync, the multiplication produces a signal that is still random and "spread" over a wide frequency range. The Low Pass Filter (LPF) rejects this high-frequency energy, resulting in no recovered message at the output (just low-level noise). This feature provides security (Code Division Multiple Access - CDMA).

Question 6: Why doesn't the jamming signal interfere with the recovery of the message?

- Answer: This is due to the Processing Gain of the DSSS system. In the receiver, the incoming signal (which contains both the Desired Message and the Interference/Jammer) is multiplied by the local PN sequence.
This multiplication despreads the Desired Message (bringing it back to its original low frequency) but spreads the Interference (scattering its energy across a wide bandwidth). The Low Pass Filter then easily passes the Desired Message (which is now low frequency) while blocking the majority of the Interference (which is now high frequency). This allows the system to recover the message even if the jamming signal is strong.

# Reflection/Learning Summary 💡

- Through the completion of Experiment 19, I have gained a comprehensive understanding of Direct Sequence Spread Spectrum (DSSS) and its practical implementation in modern communication systems. The experiment successfully bridged the gap between theoretical concepts and physical application by using the Emona Telecoms-Trainer 101 to model the entire modulation and demodulation chain.

- One of the most significant takeaways was visualizing how DSSS functions as a specialized form of Double Sideband Suppressed Carrier (DSBSC) modulation. By observing the "filled-in" envelopes on the oscilloscope, I was able to see firsthand how the high-frequency Pseudo-Noise (PN) sequence acts as a carrier, effectively spreading the message signal across a wide bandwidth. This visualization clarified why DSSS signals can often appear as background noise to unauthorized receivers, highlighting the inherent security and low-probability-of-intercept (LPI) characteristics of this technology.

- The experiment also underscored the critical importance of synchronization in spread spectrum communications. The failure to recover the message when using a mismatched or "wrong" PN sequence (as seen in Part C) provided a powerful demonstration of how Code Division Multiple Access (CDMA) works. It became clear that without the exact, synchronized "key" (the local PN sequence), the transmitted information remains inaccessible, buried within what appears to be random noise. This reinforced the concept of selectivity, where multiple users can share the same frequency band without interfering with one another, provided they use orthogonal codes.

- Furthermore, the sections on jamming and interference were particularly enlightening. Observing the "processing gain" in action—where the system successfully recovered the original sine wave message despite the presence of a strong interference signal—demonstrated the robustness of DSSS. It was fascinating to see how the multiplication process at the receiver simultaneously despreads the desired signal (concentrating its energy) while spreading the jamming signal (diluting its energy), allowing the low-pass filter to easily separate the two.

- In conclusion, this laboratory exercise provided a solid foundation in the mechanics of spread spectrum technology. I now have a practical appreciation for how DSSS achieves secure, interference-resistant communication, principles that are foundational to many modern wireless standards like GPS, Wi-Fi, and 3G cellular networks. The hands-on manipulation of the multiplier, sequence generator, and filters made the abstract mathematics of spread spectrum tangible and easier to grasp.
