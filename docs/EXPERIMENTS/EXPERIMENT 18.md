# EXPERIMENT 18 - Quadrature Phase Shift Keying 📉

# OVERVIEW 🔍
- Quadrature Phase Shift Keying (QPSK) is a digital modulation scheme and a variation of Binary Phase Shift Keying (BPSK) that transmits two bits of digital information at a time rather than a single bit. The fundamental operation involves splitting the incoming digital data stream into pairs consisting of odd and even bits. These separated streams are used to simultaneously modulate two carriers of the same frequency that are phase-shifted by $90^{\circ}$ relative to each other, creating two independent BPSK signals known as $PSK_I$ and $PSK_Q$ . These signals are then summed for transmission, allowing them to occupy the same portion of the radio-frequency spectrum. The significant advantage of this method is spectral efficiency; by converting a series of bits into bit-pairs, the effective data bit-rate is halved, which means the RF spectrum required to transmit QPSK is half that required for BPSK, ultimately making room for more users on the channel. Although the signals are mixed, the $90^{\circ}$ phase separation allows the receiver to isolate and recover the original data using phase discrimination.

# OBJECTIVES 📝
- The objective of this laboratory exercise is to practically implement and analyze a QPSK communication system using the Emona Telecoms-Trainer 101. Specifically, the experiment aims to demonstrate how to generate a QPSK signal by utilizing a bit-splitter and dual multipliers to combine two orthogonal BPSK signals. Through the use of an oscilloscope, the goal is to observe the phase transitions and signal characteristics of the modulated output. Additionally, the experiment seeks to investigate the demodulation process, focusing on how phase discrimination and product detection can be used to isolate and recover the original bit streams from the combined signal by aligning the local carrier phase.

# Material and Component Used ⚙️
- Emona Telecoms-Trainer 101 (plus power-pack)
- Dual Channel 20MHz Oscilloscope
- three Emona Telecoms-Trainer 101 oscilloscope leads
- assorted Emona Telecoms-Trainer 101 patch leads

  # SUMMARY OF FINDINGS AND RESULTS 🔬

  # PART A - Generating a QPSK signal📌
  
  ![figure3](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/27118e7fa8df5363927b5813d0c003bc93f0f231/docs/images/EXPERIMENT%2018/Screenshot%202026-02-11%20174931.png)
  ![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/27118e7fa8df5363927b5813d0c003bc93f0f231/docs/images/EXPERIMENT%2018/623801918_765240059961326_7190651243551776803_n.jpg)

  - Based on the visual characteristics of the output waveform in Figure 3, we observed the distinct timing relationship between the input serial data and the separated parallel data stream. We observed that the digital pulses in the lower trace have a duration that is exactly twice the width of the pulses in the upper trace, which represents the original sequence. This indicates that the bit rate has been effectively halved, confirming the successful operation of the serial-to-parallel conversion where the high-speed data stream is split into its odd or even components.

 # FIGURE 3 CONFIGURED INTO FIGURE 5 ⚡
 
 ![figure5](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/27118e7fa8df5363927b5813d0c003bc93f0f231/docs/images/EXPERIMENT%2018/Screenshot%202026-02-11%20174943.png)
 ![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/27118e7fa8df5363927b5813d0c003bc93f0f231/docs/images/EXPERIMENT%2018/624453087_1489483552807546_6176452857448765539_n.jpg)

-

 # FIGURE 5 CONFIGURED INTO FIGURE 7 ⚡
 
![figure7](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/27118e7fa8df5363927b5813d0c003bc93f0f231/docs/images/EXPERIMENT%2018/Screenshot%202026-02-11%20174951.png)
![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/27118e7fa8df5363927b5813d0c003bc93f0f231/docs/images/EXPERIMENT%2018/624587561_1228083155494947_7497082085793426272_n.jpg)

-

 # FIGURE 7 CONFIGURED INTO FIGURE 9 ⚡

 ![figure9](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/27118e7fa8df5363927b5813d0c003bc93f0f231/docs/images/EXPERIMENT%2018/Screenshot%202026-02-11%20175000.png)
 ![output](https://github.com/magpantayjohanzrep/LAB-REPORT-3/blob/27118e7fa8df5363927b5813d0c003bc93f0f231/docs/images/EXPERIMENT%2018/624710721_1958072621782462_6162527207769454123_n.jpg)

 - 



 
  
