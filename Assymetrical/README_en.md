# Asymmetrical distortion

If a sinusoidal signal is distorted using an asymmetric transfer function (ATF), the output spectrum will contain both even and odd harmonics. Almost any single-ended amplifier stage has an ATF. This could be a vacuum tube stage, a field-effect transistor stage, or a bipolar transistor stage. An ATF can also be created in a stage that doesn't amplify the signal, for example, using a diode.

## 1. Biased diode

In a simplest diode clipper circuit (Fig.1), let's apply a positive bias of 400 mV to a standard 1N4148 silicon diode. The diode will then slightly conduct and introduce asymmetric distortion starting from the lowest input signal levels. Up to a certain point, the distortion will be directly proportional to the input signal.

![Fig.1](https://github.com/akouz/MusEff/blob/main/Assymetrical/Diode_1.png)

Fig.1

With a signal of 380 mV p-p, distortion reaches 10%

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_10.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_10_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.2

If we double the amplitude of the input signal, the distortion will increase slightly less than twice.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_18.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_18_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.3

As the amplitude further doubles, the increase in distortion begins to lag noticeably. At this point, a negative voltage appears in the output signal. With negative output voltage the diode is completely off and does not contribute to total distortion.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_26.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_26_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.4

We double the input voltage again, and now its swing exceeds 3 V. The negative half-wave in the output signal becomes dominant, and the increase in distortion has noticeably slowed.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_33.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_33_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.5

At a 6V p-p input voltage, the increase in distortion almost ceased. Meanwhile, the output signal dynamics more or less continued to follow the input signal dynamics.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_37.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_37_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.6

If you need to limit the output signal dynamics, you can connect another diode, such as a 1N4148, in antiparallel to the first diode. This looks like a standard two-diode clipper, but unlike the standard setup, it is biased with a 400 mV DC.

At low input voltages, the second diode is off and has no effect, so Figs. 2 - 4 remain valid. However, at some point, the amplitude of the negative half-wave becomes sufficient for the second diode to turn on. Consequently, instead of Figs. 5 and 6, the output will look like Figs. 7 and 8.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_29.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_29_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.7

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_33-2.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_33-2_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.8

The transfer function and its first derivative for such a clipper are shown in Fig. 9. The offset is set to 500 mV to position it approximately in the middle of the falling edge of the derivative at zero input signal. This will result in small-signal distortion that is closest to that produced by a parabolic transfer function.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/Diodes_transfer_func.png" width="70%"></td>
  </tr>
</table>
Fig.9

## 2. JFET amplifier stage

Let's compare two JFET connection schemes, conventional and cascode.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/JFET_cascode.png" width="70%"></td>
  </tr>
</table>
Fig.10

The transfer functions of these cascades, as well as their derivatives, are shown in Fig. 11. The derivative of the cascode transfer function is more linear. This means that the cascode transfer function itself is closer to parabolic. Therefore, both circuits will produce the same second harmonic, while the cascode circuit will produce fewer higher harmonics.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/JFET_cascode_transfer.png" width="70%"></td>
  </tr>
</table>
Fig.11

This can be verified by applying a sinusoidal signal to the input of both stages and comparing the resulting spectra. The DC bias on the gates of both stages is -2.3 V.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/JFET_cascode_Vout.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/JFET_cascode_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.12

Comparing these spectra at 10% distortion with the spectra of the diode cascade Fig. 2, it is easy to see that JFETs produce much fewer higher harmonics, especially the cascode stage.

## 3. Multiplier

A [parabolic transfer function](https://github.com/akouz/MusEff/blob/main/Mult/README_en.md) is easily obtained by multiplying the signal by itself. However, analog multiplier chips are expensive. A simple analog multiplier can be built using a Gilbert cell. Precision isn't required, and four-quadrant multiplication isn't necessary, so the circuit can be simplified to its utmost:

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/Gilb_sch.png" width="70%"></td>
  </tr>
</table>
Fig.13

The output signals and their spectra are shown in Fig. 14. A signal of double frequency is present at the collector of Q1.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/Gilb_out.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/Gilb_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.14

A multiplier can also be built using a transconductance amplifier. This idea was embodied by Robert Moog in his all-solid-state Lab Series amplifiers in the late 1970s. Using a [multiplier](https://aionfx.com/app/files/schematics/Lab_Series_L5_L7_L9_L11_schematic.pdf)  based on the CA3080/CA3280/CA3094 produced a [sound comparable to that of tube amplifiers](https://www.youtube.com/watch?v=JzR54nKKtJQ). Aion subsequently released a [preamp]((https://aionfx.com/project/l5-preamp/) similar to the Lab Series L5 preamplifier. The multiplier used is the LM13700.

## 4. Differential cascade

A differential stage offers another way to obtain a transfer function similar to a parabolic one. To do this, simply apply a constant bias to one of the transistors in idle mode, as shown in Fig. 15. The resulting transfer function and its first derivative at R3 = 33 kOhm, as well as the spectrum at 10% output distortion, are also shown there.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/DiffAmp.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/DiffAmp_deriv.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/DiffAmp_FFT_at_THD_10.png" width="70%"></td>
  </tr>
</table>
Fig.15

It's easy to see that the resulting spectrum more closely resembles the "diode" spectrum in Fig. 2 than the spectrum of a multiplier or the JFET spectrum in Fig. 12.

Fig. 16 shows the output signal waveforms and corresponding spectra.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/DiffAmp_Vout.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/DiffAmp_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.16
