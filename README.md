# SSB

EXP NO: 3	SSB-SC-AM MODULATION using SCILAB

AIM:

To write a program to perform SSBSC modulation and demodulation using SCI LAB and study its spectral characteristics

EQUIPMENTS REQUIRED

•	Computer with i3 Processor

•	SCI LAB

Note: Keep all the switch faults in off position


Algorithm
1.	Define Parameters:
•	Fs: Sampling frequency.
•	T: Duration of the signal.
•	Fc: Carrier frequency.
•	Fm: Frequency of the message signal.
•	Amplitude: Maximum amplitude of the message signal.
2.	Generate Signals:
•	Message Signal: The baseband signal that will be modulated.
•	Carrier Signal: A high-frequency signal used for modulation.
•	Analytic Signal: Constructed using the Hilbert transform to get the in-phase and quadrature components.
3.	SSBSC Modulation:
•	Modulated Signal: Create the SSBSC signal using the in-phase and quadrature components, modulated by the carrier.
4.	SSBSC Demodulation:
•	Mixing: Multiply the SSBSC signal with the carrier to retrieve the message signal.
•	Low-pass Filtering: Apply a low-pass filter to remove high-frequency components and recover the original message signal.
5.	Visualization:
•	Plot the message signal, carrier signal, SSBSC modulated signal, and the recovered signal after demodulation.


PROCEDURE

•	Refer Algorithms and write code for the experiment.
•	Open SCILAB in System
•	Type your code in New Editor
•	Save the file
 
•	Execute the code
•	If any Error, correct it in code and execute again
•	Verify the generated waveform using Tabulation and Model Waveform

Model Waveform

<img width="704" height="178" alt="image" src="https://github.com/user-attachments/assets/32ee29b3-0d95-4192-9762-972d50c05c90" />
<img width="706" height="167" alt="image" src="https://github.com/user-attachments/assets/bff0d8fd-d679-444e-af37-0b34585853c1" />

Program
```
ac=39;                // Carrier amplitude
Am=19.5;              // Message amplitude
fc=7300;             // Carrier frequency
fm=730;              // Message frequency
fs=95000;            // Sampling frequency
t=0:1/fs:2/fm;       // Time base for two message cycles

wc=2*3.14*fc;        // Carrier angular frequency
wm=2*3.14*fm;        // Message angular frequency

// Message signal
e1=(Am*sin(wm*t));
subplot(4,1,1);
plot(t,e1);
xgrid;

// Carrier signal
e2=(ac*sin(wc*t));
subplot(4,1,2);
plot(t,e2);
xgrid;

// --- Sideband Components ---
sbsc1=(Am/2.*cos(wc*t-wm*t))-(Am/2.*cos(wc*t+wm*t));
sbsc2=(Am/2.*cos(wc*t-wm*t))+(Am/2.*cos(wc*t+wm*t));

// Combination 1 (USB + LSB together => DSB-SC)
e3=(sbsc2)+(sbsc1);
subplot(4,1,3);
plot(t,e3);
xgrid;

// Combination 2 (USB - LSB => isolates one sideband → SSB-SC)
e4=(sbsc2)-(sbsc1);
subplot(4,1,4);
plot(t,e4);

xgrid;
```

OUTPUT WAVEFORM

<img width="765" height="726" alt="image" src="https://github.com/user-attachments/assets/5da769b8-815e-42fd-8af9-09a47b22b361" />


TABULATION

<img width="827" height="655" alt="image" src="https://github.com/user-attachments/assets/c0ed6584-f09a-4d05-a30e-19ec360e46ae" />


RESULT:

Thus, the SSB-SC-AM Modulation and Demodulation is experimentally done and the output is verified.





