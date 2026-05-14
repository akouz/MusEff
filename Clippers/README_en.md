#Clippers

Overdrive and distortion pedals often use clippers made with back-to-back diodes. An example of a simple clipper:

<img width="381" height="181" alt="diodes" src="https://github.com/user-attachments/assets/de00f680-831b-440a-ba8e-14080d3fb426" /> 
Fig. 1

It's well known that different types of diodes produce significantly different sounds: silicon diodes produce a harsh sound with abundant high harmonics, germanium diodes produce a softer tone, somewhat reminiscent of vacuum tube amplifiers, and Schottky diodes fall somewhere in between. However, the nature of these differences remains largely unknown. Extensive research into the I-V characteristics of diodes has eluded them. Understanding why germanium diodes sound different from Schottky and silicon diodes is virtually impossible based solely on the bare I-V characteristics or clipper transfer characteristics.

Interesting phenomena emerge when looking at the first derivative of the transfer characteristics of clippers with different diodes. Things become apparent that are impossible to discern when examining oscillograms.

Here are the transfer characteristics of germanium diode clippers (red and blue lines), plus their derivatives (green lines):

<img width="512" height="383" alt="1N34A_1N270" src="https://github.com/user-attachments/assets/3ef8f0bb-2584-4ae4-8636-138791d0f24a" />

Fig. 2

Here are the transfer characteristics and their derivatives for silicon diodes:

<img width="507" height="486" alt="1N4148_1N4001" src="https://github.com/user-attachments/assets/953d7224-80c3-4989-96e6-4c9e9c57d3c8" />

Fig.3

It's clear that the initial portion of the transfer characteristics of silicon clippers is practically linear, since their first derivative is horizontal. The diodes are off and do not introduce distortion up to a certain threshold voltage. However, beyond this threshold, at voltages above 0.35...0.4 V, the transfer characteristics of silicon clippers become similar to those of germanium clippers. The signal transition between the linear and nonlinear portions of the transfer characteristics causes an unpleasant, raspy sound.

Thus, the essential difference between a "germanium" transfer characteristic and a "silicon" one is that the "germanium" one is nonlinear throughout its entire length, while the "silicon" one combines linear and nonlinear sections. A monotonically nonlinear transfer characteristic produces a soft sound, free of unpleasant overtones ("grit").

Accordingly, the sound of clippers using Schottky diodes remains "silicon-like," as the clipper still has a linear portion in its transfer characteristic, albeit smaller than that of a clipper using conventional silicon diodes. This linear portion can be further reduced by heating the Schottky diodes to 100–120°C. Experiments have shown that the clipper's sound softens and becomes more similar to that of a germanium clipper, but the "silicon wheeze" cannot be completely eliminated.

##Offset clippers

This means that if the silicon diodes in the clipper are "shifted to the left" by applying a small positive bias, the linear sections can be eliminated. The transfer characteristics will be the same as those of germanium clippers, nonlinear throughout. Consequently, they will sound virtually identical. The required bias voltage can be achieved by passing a small current through the reference diode, and the resulting voltage drop is buffered and used as the bias voltage for the clipper. For 1N4148 diodes, the transfer characteristics at reference diode bias currents of 10 µA and 20 µA are as follows:

<img width="494" height="389" alt="1N4148_biased" src="https://github.com/user-attachments/assets/5fb49fee-d8b9-488f-b19d-d0b518f60f0e" />

Fig. 4

As we can see, there are now virtually no differences from germanium clippers. One version of a clipper circuit using biased silicon diodes looks like this:

<img width="256" height="393" alt="Clipper_biased" src="https://github.com/user-attachments/assets/d2e3a353-9987-40f4-8cfc-9a9de3d527b9" />

Fig. 5

Diodes D5 serve as reference diodes, while emitter followers Q1A and Q2B act as buffers. Diode-connected transistors Q1B and Q2A are used for temperature compensation of the emitter followers. The current through the reference diodes is set by resistors R31 and R32. Resistors R29 and R30 ensure that, in quiescent mode, the same current flows through limiter diodes D4 as through reference diodes D5.

An offset clipper can also be built using two op-amps. In this case, the offset can be smoothly adjusted with a trimpot.

<img width="513" height="395" alt="OpAmp_bias" src="https://github.com/user-attachments/assets/711b506a-9da6-444e-b216-dc0ae94e17fe" />

Fig.6

##Clippers with high-frequency signal admixture

There's another way to achieve a smooth clipper transfer characteristic without a linear section. Applying a triangular RF signal with an amplitude corresponding to the bias voltage to the silicon clipper diodes will cause the diodes to slightly conduct. The clipper output signal should then be filtered using a passive low-pass filter. The characteristics of this clipper, using 1N4148 diodes, are as follows:

<img width="505" height="447" alt="1N4148_with RF" src="https://github.com/user-attachments/assets/0118f866-c9ee-40e2-b689-a07d78b60c4b" />

Fig. 7

Artifacts at the beginning of the derivative graph are caused by transient processes in the 3rd order low-pass filter used, as well as by the imperfection of the differentiator used to calculate the derivative.

For clarity, we'll show the characteristics of a clipper using 2N2222 transistors as diodes. The red line is without high-frequency admixture, the green line is with it. As we can see, with the high-frequency admixture, the transfer characteristic has smoothed out and, over a large section, has become described by a quadratic function, since its derivative is linear.

<img width="516" height="394" alt="2N2222_with_without_RF" src="https://github.com/user-attachments/assets/0773ff9a-c0ce-46e1-9006-c7e35b1be2f8" />

Fig.8

Power functions describe the transfer characteristics of triode vacuum tube stages. The distortions they create have a rapidly decaying spectrum. It is well known that squaring transforms a sine wave into a sine wave of double frequency, i.e., it produces only the second harmonic.

Let's take a triangular voltage source with a swing from -1 V to +1 V and a frequency of, say, 200 kHz. We'll mix it 1:1 with the input signal and feed it into an ideal clipper, which will cut off the signal at levels of -1 V and +1 V. We'll pass the output signal through a 2-4th order low-pass filter with a cutoff frequency of 7 kHz.

With a zero input signal, the low-pass filter output will be 0. The triangle is not clipped by the clipper, but is almost completely suppressed by the filter. As the input voltage increases, the triangle vertices will be increasingly clipped by the clipper. The low-pass filter will average the resulting signal, calculating the area of ​​the trapezoids at voltages greater than zero minus the area of ​​the triangles at voltages less than zero. As the input signal increases, the output voltage will increase more and more slowly, and at an input voltage of +2 V, the output voltage will reach +1 V and will not increase any further. As the input voltage decreases below zero, the same processes will occur in reverse; at an input voltage of -2 V, the output voltage will reach -1 V and will not decrease any further.

<img width="479" height="377" alt="transfer" src="https://github.com/user-attachments/assets/8e7f3c32-5f33-432a-a13a-700d7e4045aa" />

Fig.9

The transfer characteristic of the resulting soft clipper in the range from X=-2 V to X=+2 V is described by the formulas

$`X - X^2/4`$ 

for positive voltages and

$`X + X^2/4`$ 

for negative ones.

If a sine wave signal is fed to a soft clipper with such a transfer characteristic, the output distortion will increase more or less proportionally to the input signal:

    0.44% at 200 mV pp
    0.89% at 400 mV pp
    1.88% at 800 mV pp
    4.13% at 1.6 V pp
    10.1% at 3.2 V pp

At 4 V pp, distortion reaches 15%. After this point, more severe clipping begins.
