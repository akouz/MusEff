# Overdrive with HF-clipper

A clipper circuit featuring high-frequency (HF) signal injection is described [here](https://github.com/akouz/MusEff/blob/main/Clippers/README_en.md#clippers-with-high-frequency-signal-admixture). Clipper D3 is a dual Schottky diode. 
An HF triangular-wave generator operating at a frequency of at least 100 kHz is built around op-amp U3A. A second-order passive low-pass filter R13,C16,R16,C17 with a cutoff frequency 
of 7 kHz suppresses the HF component in the output signal to a level suitable for the proper operation of op-amp U2B. Final HF suppression is achieved via the tone control circuit R19,R22,C22.

Switch XS1 allows for comparing the sound with and without the HF signal injection. Without the HF injection, the effect sounds like a fairly common relatively soft overdrive based on Schottky diodes, 
with a hint of "fizz" in the tone. When the HF injection is engaged, the fizz disappears completely, and the sound clears up, taking on the characteristics of a tube overdrive.

<img width="1108" height="693" alt="ODplus_rev_1_2" src="https://github.com/user-attachments/assets/99573e5f-9179-4027-9f2f-36132f91d037" />

