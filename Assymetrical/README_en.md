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

