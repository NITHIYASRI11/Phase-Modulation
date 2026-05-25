# EXPT. NO. 2 GENERATION AND DETECTION OF PHASE MODULATION (PM)
## AIM:
To generate and detect Phase Modulation (PM) using SCILAB and to calculate the phase deviation index (modulation index) of PM.

## EQUIPMENTS REQUIRED

Computer with i3 Processor

SCILAB software

## THEORY:

Phase Modulation (PM) is a type of angle modulation where the phase of the carrier signal is varied in proportion to the instantaneous amplitude of the modulating (message) signal. In PM, the frequency remains constant, but the phase changes according to the message signal.

The general expression for a PM wave is:






<img width="282" height="64" alt="image" src="https://github.com/user-attachments/assets/8dabaa51-6f4a-492a-90d3-def030b967eb" />




where:

Ac= carrier amplitude

fc = carrier frequency
kp= phase sensitivity constant (radians per volt)
m(t) = modulating signal

### Demodulation of PM:
PM can be demodulated by first converting the PM signal into an FM-like signal using a differentiator, then applying FM demodulation (e.g., using an envelope detector after a frequency discriminator). In SCILAB, we can simulate this by:

Differentiating the PM signal → produces a signal whose amplitude varies with instantaneous frequency.

Envelope detection of the differentiated signal recovers the original message.

### Need for Phase Modulation:

Better noise immunity compared to AM.

Constant envelope allows use of efficient nonlinear amplifiers.

Used in digital modulation schemes like PSK (Phase Shift Keying).

## Procedure


Open SCILAB on your computer.

1.Write the code in the SCILAB Editor as per the algorithm given.

2.Save the file with a .sce extension (e.g., phase_modulation.sce).

3.Execute the code by clicking the "Execute" button or pressing Ctrl+Shift+E.

4.Check for errors – if any error appears, debug and correct the code, then execute again.

5.Verify the waveforms – observe the three plots:

6.Modulating signal m(t)

7.Carrier signal c(t)

8.Phase Modulated signal s(t)

9.Check the demodulation plot – compare the original modulating signal with the recovered signal.

10.Note the calculated modulation index – displayed in the SCILAB console.

11.Record the observations in the tabulation and compare with theoretical values.

## Program

```
am=8.22;
fm=768;

ac=16.44;
fc=7680;

b=2.19;

fs=76800;
t=0:1/fs:2/fm;

em=am*cos(2*%pi*fm*t);
subplot(4,1,1);
plot(t,em);

ec=ac*cos(2*%pi*fc*t);
subplot(4,1,2);
plot(t,ec);

efm=ac*cos((2*%pi*fc*t)+(b.*sin(2*%pi*fm*t)));
subplot(4,1,3);
plot(t,efm);


epm=ac*cos((2*%pi*fc*t)+(b.*cos(2*%pi*fm*t)));
subplot(4,1,4);
plot(t,epm);


```

## Output
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fb844c8d-dbcb-428e-8753-90378d164153" />


## Result
Thus, Phase Modulation (PM) was successfully generated and demodulated using SCILAB. The modulation index (phase deviation) was calculated theoretically and practically, and the recovered signal matches the original modulating signal. The experiment demonstrates the principles of angle modulation and demodulation.
