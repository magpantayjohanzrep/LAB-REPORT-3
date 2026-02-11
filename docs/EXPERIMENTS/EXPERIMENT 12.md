# EXPERIMENT 12 - PCM ENCODING 🎙️

# OVERVIEW 🔍
- As digital transmission systems increasingly replace analog systems in commercial telecommunications, understanding Pulse Code Modulation (PCM) is essential for technical professionals in the industry. PCM is a fundamental process that converts analog message signals into a serial stream of 0s and 1s through a procedure known as encoding. This process involves sampling the analog signal’s voltage at regular intervals, comparing each sample to a set of reference quantization levels, and generating a corresponding binary number for the closest level. These binary numbers are then outputted one bit at a time in serial form. Key factors in PCM performance include the encoder's clock frequency, which must be at least twice the message frequency to avoid aliasing—and quantization error, which occurs when the original sample value is lost because it does not perfectly match a quantization level.

# OBJECTIVES 📝

- The primary objective of this experiment is to introduce students to digital transmission systems using the Emona Telecoms-Trainer 101. Specifically, the experiment aims to have students use the PCM Encoder module to convert various inputs—including a fixed DC voltage, a variable DC voltage, and a continuously changing signal—into PCM data. Through this process, students will verify the practical operation of PCM encoding and investigate the nature of quantization error. Additionally, the experiment is designed to familiarize students with the technical aspects of PCM data frames, such as identifying the most and least significant bits and understanding the role of Frame Synchronization (FS) signals.

# Material and Component Used ⚙️
- Emona Telecoms-Trainer 101 (plus power-pack)
- Dual Channel 20MHz Oscilloscope
- three Emona Telecoms-Trainer 101 oscilloscope leads
- assorted Emona Telecoms-Trainer 101 patch leads

# SUMMARY OF FINDINGS AND RESULTS 🔬
 
# PART A - An introduction to PCM encoding using a static DC voltage 📌

# Circuit Diagram and Output Waveform ⚡
![figure2](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/97829c0bc25915b375acdccf597fc150f3b03566/docs/images/Part%20A%20-%20Figure%202.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/772f456bfe2e588203f102769e9f2b0a49cb0dd7/docs/images/624566663_1668685001211763_2944551902201522530_n.jpg)


- In this experiment, we observed the conversion of analog signals into digital data using the Emona Telecoms-Trainer 101 PCM Encoder by monitoring the PCM data output on Channel 2 and the Frame Synchronization (FS) signal on Channel 1. We noted that the blue waveform represents the 8-bit serial data stream generated at a clock rate of approximately 8.264 kHz, where each pulse corresponds to a logic level that forms a binary word for a specific voltage sample.
  
- The bursts of data are clearly separated, indicating that the encoder is sampling the input at regular intervals and shifting out the bits in a serial sequence. Regarding the timing, we identified the yellow FS signal as a critical reference marker with a frequency of 1.041 kHz, which goes high during the output of the least significant bit (bit-0). By observing the alignment of the two channels, we confirmed that for every pulse of the FS signal, there is a corresponding frame of 8 bits, verifying that the encoder is correctly converting the analog input into a standard 8-bit digital format where the most significant bit is transmitted first.

# FIGURE 2 CONFIGURED INTO FIGURE 5 ⚡

![figure5](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/6cb72659c281397ff591307a74b302d58d8e677a/docs/images/Screenshot%202026-02-11%20120937.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/98a5c047a98939927d3714978ef304595e47ba11/docs/images/626603235_2155268715225936_7414223903331983057_n.jpg)

- We observed the setup shown in Figure 5, which illustrates the connection of the PCM Encoder’s output to Channel 2 of the oscilloscope while keeping the Frame Synchronization (FS) signal on Channel 1. We noted that the oscilloscope display now presents 10 bits of the PCM data output, where the first 8 bits constitute a single complete frame and the remaining two bits represent te start of the subsequent frame.
  
- This visual arrangement allowed us to confirm the serial nature of the transmission, with each 8-bit word representing the digitized value of the 0V DC input. By comparing the data stream on Channel 2 with the FS pulses on Channel 1, we were able to identify the boundaries of the frames and distinguish between the most significant bit (bit-7) sent first and the least significant bit (bit-0) sent last.

# PART B - PCM encoding of a variable DC voltage 📌

![figure 7](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/00433e12932fbfdfbb3bb262013883b40a26a9e5/docs/images/Screenshot%202026-02-11%20121709.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/1fb2221d28be025cecc647de906c0a016ac728d6/docs/images/623303505_2647580948940246_5781088008166550589_n.jpg)

- In this part of the experiment, we examined the setup corresponding to Figure 7, where the PCM Encoder’s input was connected to the Ground (0V) terminal of the Variable DCV module. By observing the oscilloscope, we were able to see the specific 8-bit binary pattern that the encoder generates when the input voltage is exactly zero. We noted that even with a steady 0V input, the encoder continuously produces a serial bitstream in every frame, which serves as the digital reference for a null analog signal.
- 
- This step was essential because it allowed us to record the "zero-level" bit pattern, which we later used as a baseline to compare how the binary output changes when positive or negative voltages are applied. Additionally, we verified that the Frame Synchronization pulse remained correctly aligned with the end of the 8-bit word, confirming stable operation of the encoder’s internal timing during a constant input state.

# PART C - Quantisation 📌

- we observed the PCM encoder transitioning from processing static DC levels to digitizing a continuously changing analog signal, such as a low-frequency sine wave. In this scenario, the 8-bit binary patterns on the oscilloscope would no longer remain stationary; instead, they would constantly change in real-time as the encoder samples the varying voltages of the input signal at the 8kHz clock rate.
-
- We saw that the serial bitstream update every frame to reflect the signal’s instantaneous amplitude, allowing us to witness the practical application of sampling theory and the effects of quantization. By comparing the original analog waveform to the resulting digital data, we could analyze how the system handles dynamic signals and identify the presence of quantization error, which occurs when the analog sample is rounded to the nearest of the 256 available digital levels.

# PART D - PCM encoding of continuously changing voltages 📌

![figure9](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/0736c826b157d696e70cec49b1573d8d6c8806e9/docs/images/Screenshot%202026-02-11%20122853.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/1fb2221d28be025cecc647de906c0a016ac728d6/docs/images/622709763_1626555225189111_2405934674823063849_n.jpg)

- In this part of the experiment, we observed the operation of the PCM Encoder while using the Variable DCV module to change the input voltage level. By observing the oscilloscope, we noted how the 8-bit serial data pattern on Channel 2 updated in response to different analog DC inputs. Using the Frame Synchronization (FS) signal as a steady trigger, we were able to clearly identify the individual bits within each frame and watch them shift between high and low states as the quantization levels changed.
- 
- We verified that the encoder successfully translates specific analog voltages into unique binary sequences, allowing us to confirm the direct relationship between the input signal’s amplitude and the resulting digital PCM output. This process demonstrated how the system precisely maps continuous voltages to discrete 8-bit digital values.

# DISCUSSION 📌

# PART A QUESTIONS 📝

- Question 1: Indicate on your drawing the start and end of the frame.

Answer: A frame starts with the most significant bit (bit-7) and ends with the least significant bit (bit-0). The Frame Synchronization (FS) signal goes high specifically when bit-0 is being outputted, marking the end of the 8-bit frame.

- Question 2: Indicate on your drawing the start and end of each bit.

Answer: Each bit's duration is determined by one cycle of the 8kHz digital clock signal. You should mark the divisions on your PCM data trace according to the clock pulses.

- Question 3: Indicate on your drawing which bit is bit-0 and which is bit-7.

Answer: Bit-7 (the most significant bit) is the first bit transmitted in the frame. Bit-0 (the least significant bit) is the final bit of the 8-bit sequence and aligns with the high pulse of the FS signal.

- Question 4: What is the binary number that the PCM Encoder module is outputting?

Answer: This depends on your observation of the oscilloscope's Channel 2. For a 0V input, you should record the sequence of 8 bits (high = 1, low = 0) starting from bit-7 to bit-0.

- Question 5: Why does the code change even though the input voltage is steady?

Answer: Although not explicitly detailed in the text provided, in practical circuits, minor changes or "flickering" in the least significant bits can occur due to quantization error or thermal noise. If the steady input voltage sits exactly between two quantization levels, the encoder may alternate between the two closest digital representations.

- Question 6: Why does the PCM Encoder module output this code for 0V DC and not 0000000?

Answer: The PCM encoder used (a codec chip) maps the input range of -2V to +2V to 256 quantization levels (0 to 255 in binary). In such systems, 0V is typically assigned a middle value (like 10000000 or 01111111) rather than all zeros, as "00000000" usually represents the most negative voltage in the range (-2V).

# PART B QUESTIONS 📝

- Question 7: What happens to the variable DCV modules output?

Answer: When we adjust the control knob on the Variable DCV module, the output voltage changes proportionally to the physical rotation of the dial. If we turn the knob clockwise, the DC output voltage becomes more positive, and if we turn it counter-clockwise, the voltage becomes more negative. This output serves as the analog input for the PCM Encoder. In the context of our experiment, we observed that this voltage level is represented as a flat horizontal line on Channel 1 of the oscilloscope, shifting up or down on the vertical axis as the knob is adjusted. This shifting voltage is what determines the specific 8-bit binary pattern being generated by the encoder at any given moment.

- Question 8: In what way does the binary number that the pcm encoder module outputs change?

Answer: The binary number changes by switching individual bits between high (logic 1) and low (logic 0) states to match the corresponding quantization level. As the input voltage increases, the binary value increments (the pattern of 1s and 0s represents a higher numerical value); as the voltage decreases, the binary value decrements.

- Question 9: What happens to the DCV module’s output?

Answer: The output of the DCV module is a steady DC voltage that is sent to the PCM Encoder’s input. When the knob is turned clockwise, the output voltage becomes more positive; when turned counter-clockwise, it becomes more negative. This output is also monitored on Channel 1 of the oscilloscope to provide a visual reference of the analog level being encoded.

- Question 10: What happens to the binary number that the PCM encoder module is outputting?

Answer: The binary number represents the digital "map" of the analog voltage. If the input is steady, the binary number remains a fixed 8-bit pattern (though it may flicker slightly due to quantization uncertainty). If the input voltage changes, the bits within the 8-bit frame update in real-time to represent the new voltage level.

- Question 11: Based on the information in Table 1, what is the maximum allowable amplitude for an AC signal on the PCM encoder module’s input?

Answer: According to the PCM Encoder specifications (referenced in the manual's technical notes and Table 1), the encoder is designed to handle an input range of -2V to +2V. Therefore, the maximum allowable peak-to-peak amplitude for an AC signal is 4Vpp (or a peak amplitude of 2V). Exceeding this range would cause the signal to be "clipped" as the encoder cannot generate a binary value higher than 11111111 or lower than 00000000

# PART C QUESTIONS 📝

- Question 12: Whats the name for the difference between a sampled voltage and its closes quantisation level?

Answer: The term for the difference between a sampled analog voltage and its closest quantization level is quantization error (sometimes also called quantization noise).This error occurs because an analog signal is continuous and can have an infinite number of values, whereas a digital system like our 8-bit PCM encoder can only represent $2^8 = 256$ discrete levels. When a sample falls between two levels, the encoder "rounds" it to the nearest one, creating this small discrepancy.

- Question 13: Calculate the difference between the quantisation levels in the PCM encoder module by subtracting the values in table 1 and dividing the number by 256

Answer: Based on the PCM Encoder module specifications (Range: -2V to +2V) and the 8-bit resolution (256 levels):

* **Total Voltage Range (V_max - V_min):** 2V - (-2V) = 4V
* **Number of Levels:** 256
* **Formula:** Range / 256

**Calculation:**
$$\frac{4\text{V}}{256} = 0.015625\text{V}$$

**Result:**
The difference between quantization levels is **0.015625V** or **15.625 mV**.

# PART D QUESTIONS 📝

- Question 14: To reduce quantisation error it's better to have

Answer: More quantization levels between plus or minus 2V. Quantization error is essentially the "rounding error" that occurs during the analog-to-digital conversion process. By increasing the number of levels (increasing the bit resolution), the vertical distance between each discrete step—known as the step size—becomes smaller. When the steps are smaller, the digital representation can sit much closer to the actual analog voltage, resulting in a more accurate reproduction of the original signal. In contrast, fewer levels create larger "jumps" between values, leading to a coarser approximation and higher error.

- Question 15: Why does the PCM DATA change continuously?

Answer:  The PCM data changes continuously because the encoder is performing real-time digitization of a dynamic analog input signal, such as a sine wave. Since an AC signal’s voltage level is constantly rising or falling over time, the encoder captures a different instantaneous voltage at every sampling interval—which, in this system, occurs 8,000 times per second. Each of these unique voltage "snapshots" must be mapped to a specific 8-bit binary word; therefore, as the input amplitude fluctuates, the resulting bitstream must update just as rapidly to accurately track the signal's shape. On an oscilloscope, this high-speed transition between different binary values creates the appearance of "flickering" or "dancing" bits, as each successive frame transmitted represents a new numerical value corresponding to a different point on the analog waveform.

# Reflection/Learning Summary 💡

- The experiment on PCM Encoding provided a comprehensive look into the transition from analog signals to digital bitstreams, highlighting the essential role of Pulse Code Modulation in modern telecommunications. Through the use of the Emona Telecoms-Trainer 101, we successfully demonstrated how a continuous analog voltage is transformed into a discrete 8-bit serial data stream. A primary takeaway was the importance of the Frame Synchronization (FS) signal, which serves as a critical timing reference to identify the boundaries of each 8-bit frame. We observed that the most significant bit (bit-7) is transmitted first, while the least significant bit (bit-0) coincides with the FS pulse, ensuring that the receiver can accurately reconstruct the intended numerical value of each sample.

- Our investigation into quantization revealed the inherent limitations of digital representation. By calculating the step size, we determined that each of the 256 available quantization levels represents a specific voltage increment of approximately 15.625 mV within the -2V to +2V range. This explained the "flickering" bits observed during static DC tests, where minor noise or voltage fluctuations caused the encoder to oscillate between adjacent levels. This phenomenon, known as quantization error, underscored the fact that digital conversion is an approximation; to achieve higher fidelity and reduce this "rounding" noise, a system must utilize more quantization levels, which requires a higher bit-depth.

- Furthermore, the experiment illustrated the dynamic nature of digital data when processing time-varying signals. When a sine wave was introduced, the PCM data no longer remained stationary but updated 8,000 times per second to track the signal's changing amplitude. This real-time tracking demonstrated the practical application of sampling theory, where the output bitstream effectively "dances" to mirror the analog input. Ultimately, the lab successfully verified that the accuracy of a PCM system is fundamentally dependent on the balance between its sampling frequency and the number of available quantization levels, providing a solid foundation for understanding digital data transmission.















