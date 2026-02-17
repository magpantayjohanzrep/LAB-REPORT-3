# LAB-REPORT-3 📡0️⃣1️⃣
Digital communication systems play a vital role in modern technology by enabling the reliable transmission of information over long distances. Unlike analog communication, digital communication represents information using binary signals (0s and 1s), which makes the system more resistant to noise, distortion, and interference. To transmit digital data efficiently, different modulation techniques are used to convert binary information into signals that can travel through a communication channel.

Among the fundamental digital modulation techniques are Amplitude Shift Keying (ASK), Frequency Shift Keying (FSK), Binary Phase Shift Keying (BPSK), and Quadrature Phase Shift Keying (QPSK). Each method modifies a specific parameter of the carrier signal—amplitude, frequency, or phase—to represent digital data. ASK varies the amplitude, FSK changes the frequency, BPSK shifts the phase by 180 degrees, and QPSK uses multiple phase shifts to transmit more bits per symbol. These techniques demonstrate different approaches to achieving reliable and bandwidth-efficient data transmission.

In addition to modulation methods, Pulse Code Modulation (PCM) is an essential digital encoding technique used to convert analog signals into digital form. PCM involves sampling, quantization, and encoding, allowing analog information such as voice signals to be transmitted through digital systems. Together, PCM and digital modulation techniques form the foundation of modern communication systems, including wireless networks, satellite communication, digital broadcasting, and telecommunications.

This experiment aims to study and understand the principles, signal characteristics, and practical applications of these digital modulation and encoding techniques, highlighting their importance in advanced communication systems.


# Pulse Code Modulation 🎤
![PCM](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/be6eb0218358f5eccf086a1b135af2d62681e13e/docs/images/PICS%20FOR%20READme/PCM.png)

- Pulse Code Modulation (PCM) is a digital communication technique used to convert analog signals into digital form for transmission and storage. It involves three main steps: sampling, quantization, and encoding. In the transmitter section, the analog message signal is first passed through a low-pass filter to remove unwanted high-frequency components, then sampled at regular intervals. The sampled values are quantized into discrete levels and converted into binary code by the encoder. The digital signal is then transmitted through the communication channel. At the receiver section, the signal is regenerated, decoded, and passed through a reconstruction filter to recover the original analog signal. PCM is widely used in digital audio systems, telecommunications, and computer networks because it provides high signal quality and strong resistance to noise and interference.

# Amplitude Shift Keying 0️⃣1️⃣ ➜ 📶 ➜ 📡
![ASK](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/be6eb0218358f5eccf086a1b135af2d62681e13e/docs/images/PICS%20FOR%20READme/ask.jpg)

- Amplitude Shift Keying (ASK) is a type of digital modulation technique in which the amplitude of a carrier signal is varied according to the digital input data while the frequency and phase remain constant. In this method, a binary “1” is represented by transmitting a carrier signal with a certain amplitude, while a binary “0” is represented by reducing or completely removing the carrier signal. ASK is one of the simplest forms of digital modulation and is widely used in low-data-rate communication systems such as optical fiber communication, remote controls, and RFID systems. The diagram shows how the digital bit sequence controls the presence or absence of the carrier wave, resulting in the ASK modulated signal. This modulation technique demonstrates how digital information can be transmitted using changes in signal amplitude.

# Frequency Shift Keying 0️⃣1️⃣ ➜ 📈📉 ➜ 📡
![FSK](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/be6eb0218358f5eccf086a1b135af2d62681e13e/docs/images/PICS%20FOR%20READme/fsk.jpg)

- Frequency Shift Keying (FSK) is a digital modulation technique in which the frequency of the carrier signal is changed according to the binary input signal, while the amplitude and phase remain constant. In this technique, one frequency represents binary “1” and another frequency represents binary “0”. This allows digital data to be transmitted by switching between two different carrier frequencies. FSK is commonly used in applications such as radio communication, modems, telemetry, and wireless systems because it is more resistant to noise compared to amplitude-based modulation techniques. The diagram illustrates how the digital bitstream selects between a high-frequency and low-frequency carrier wave, producing the FSK modulated output signal.

# Binary Shift Keying 0️⃣1️⃣ ➜ 🔄 ➜ 📡 
![BSK](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/be6eb0218358f5eccf086a1b135af2d62681e13e/docs/images/PICS%20FOR%20READme/bsk.jpg)

- Binary Shift Keying (BSK), also known as Binary Phase Shift Keying (BPSK), is a digital modulation technique in which the phase of the carrier signal is changed according to the binary input data, while the amplitude and frequency remain constant. In this method, binary “1” and binary “0” are represented by two different phases of the carrier signal, typically separated by 180 degrees. This phase shift allows digital data to be transmitted efficiently and with better noise immunity compared to ASK. BPSK is widely used in satellite communication, wireless communication, and digital data transmission systems because of its reliability and simplicity. The diagram shows how the phase of the carrier signal changes depending on the digital input signal, resulting in the BPSK modulated waveform.

# Quadrature Phase Shift Keying 00 01 10 11 ➜ 🔄↗️↘️ ➜ 📡
![QPKS](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/be6eb0218358f5eccf086a1b135af2d62681e13e/docs/images/PICS%20FOR%20READme/qpsk.png)

- Quadrature Phase Shift Keying (QPSK) is an advanced digital modulation technique that uses four different phase shifts of the carrier signal to represent digital data. Unlike BPSK, which transmits one bit per symbol, QPSK transmits two bits per symbol, making it more efficient in terms of bandwidth usage. Each phase shift represents a unique pair of binary digits, allowing faster data transmission without increasing the bandwidth. QPSK is widely used in modern communication systems such as wireless networks, satellite communication, and digital television because of its high efficiency and strong resistance to noise. The diagram demonstrates how different phase shifts of the carrier signal correspond to different combinations of binary input data.


