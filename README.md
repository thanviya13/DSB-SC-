# DSBSC


EX NO: 2	DSB-SC-AM MODULATOR AND DEMODULATOR

AIM:

To write a program to perform DSBSC modulation and demodulation using SCI LAB and study its spectral characteristics

EQUIPMENTS REQUIRED

•	Computer with i3 Processor
•	SCI LAB

Note: Keep all the switch faults in off position

Algorithm:

1.	Define Parameters:
•	Fs: Sampling frequency.
•	T: Duration of the signal.
•	Fc: Carrier frequency.
•	Fm: Frequency of the message signal.
•	Amplitude: Maximum amplitude of the message signal.
2.	Generate Signals:
•	Message Signal: A sinusoidal signal that will be modulated.
•	Carrier Signal: A high-frequency sinusoidal signal used for modulation.
3.	DSBSC Modulation:
•	Modulated Signal: Multiply the message signal by the carrier signal to produce the DSBSC signal.
4.	DSBSC Demodulation:
•	Multiplication: Multiply the modulated signal by the carrier signal to get the product of the message signal with itself (i.e., the original message signal plus high-frequency components).
•	Low-pass Filtering: Apply a Butterworth low-pass filter to remove the high- frequency components and recover the original message signal.
5.	Visualization:
Plot the message signal, carrier signal, DSBSC modulated signal, and the recovered signal after demodulation.
PROCEDURE

•	Refer Algorithms and write code for the experiment.
•	Open SCILAB in System
•	Type your code in New Editor
•	Save the file
 
•	Execute the code
•	If any Error, correct it in code and execute again
•	Verify the generated waveform using Tabulation and Model Waveform

Model Waveform

<img width="703" height="679" alt="image" src="https://github.com/user-attachments/assets/e7c7c7f8-ccf2-41ac-b1f3-325989941a6f" />

Program
```
import numpy as np
import matplotlib.pyplot as plt
Ac = 122.6
fc = 1000
Am = 61.3
fm = 500
fs = 70000
t = np.arange(0, 2/fm, 1/fs)
Wm = 2 * np.pi * fm
Wc = 2 * np.pi * fc
Em = Am * np.sin(Wm * t)
Ec = Ac * np.sin(Wc * t)
Edsbsc = ((Am / 2) * np.cos((Wc - Wm) * t)) - ((Am / 2) * np.cos((Wc + Wm) * t))
plt.figure(figsize=(10, 6))
plt.subplot(3, 1, 1)
plt.plot(t, Em)
plt.grid()
plt.subplot(3, 1, 2)
plt.plot(t, Ec)

plt.grid()
plt.subplot(3, 1, 3)
plt.plot(t, Edsbsc)
plt.grid()
plt.tight_layout()
plt.show()
```
Output Graph


<img width="582" height="411" alt="Screenshot 2025-11-27 114203" src="https://github.com/user-attachments/assets/c6277ac3-db18-4d87-b856-f57d083798c5" />




Tablular Column


<img width="607" height="880" alt="Screenshot 2025-11-27 114055" src="https://github.com/user-attachments/assets/be034fd7-d545-4c98-9e6a-89c7c09a0cd4" />


Result


<img width="481" height="929" alt="image" src="https://github.com/user-attachments/assets/b2c4bf3a-7c79-4ed4-ae5b-bf15e14b019f" />

