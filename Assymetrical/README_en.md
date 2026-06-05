# Asymmetrical distortion

If a sinusoidal signal is distorted using an asymmetric transfer function (ATF), the output spectrum will contain both even and odd harmonics. Almost any single-ended amplifier stage has an ATF. This could be a vacuum tube stage, a field-effect transistor stage, or a bipolar transistor stage. An ATF can also be created in a stage that doesn't amplify the signal, for example, using a diode.

## 1. Biased diode

In a simplest diode clipper circuit (Fig.1), let's apply a positive bias of 400 mV to a standard 1N4148 silicon diode. The diode will then slightly conduct and introduce asymmetric distortion starting from the lowest input signal levels. Up to a certain point, the distortion will be directly proportional to the input signal.

![Fig.1](https://github.com/akouz/MusEff/blob/main/Assymetrical/Diode_1.png)

Fig.1
