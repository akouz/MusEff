# 1, 2 or 3 stages?

Let's take the simplest JFET amplifier stage without negative feedback:


Such stages have been well-studied; their transfer characteristic is close to a parabolic function. With relatively low overdrive (up to approximately 15% THD), they produce a good sound, reminiscent of a vacuum tube stage. This is because such a stage produces primarily the second harmonic; higher harmonics in the output spectrum decay quickly.

![Fig.1](https://raw.githubusercontent.com/akouz/MusEff/refs/heads/main/1_2_3_stages/JFET_stage.png)

What happens if two stages are connected in series? What happens if three stages are connected in series?

The simple answer "there will be more distortion" is incorrect. After all, we adjust the input signal so that the output distortion is the same in all variations, with, say, a THD of 10%. And we adjust the output signal amplitude so that the first harmonic of the spectrum is 0 dB. Therefore, the amount of distortion is the same, so what's the difference?

A conventional single-transistor common-source amplifier stage inverts the signal. If two such stages are connected in series, the distortion of the first stage will (partially) compensate for the distortion of the second stage. Consequently, to achieve the same level of distortion, the input signal level will have to be increased. The signal amplitude at the output of the last stage will increase. Since the stages have the same supply voltage, the transition from soft to hard clipping will occur earlier, with a lower input signal amplitude. Thus, two stages connected in series will produce a harder, more "fuzzy" sound.

Of course, much depends on the gain of the output stage. If it has high gain, then with 10% distortion at its output, the contribution of the first stage to distortion will be small. In this case, two stages will perform almost identically to a single stage. However, if the gain of the second stage is low, or if there is a divider (i.e., an attenuator) at its input, the "hardening" effect will become noticeable.

The three-stage option only makes sense if the second (i.e., intermediate) stage introduces little or no distortion. In this case, the distortions of the first and third stages are additive, and the desired 10% output distortion will appear at a lower output signal level. This means that the overdrive will later enter hard clipping mode caused by supply voltage limit. It will produce soft distortion with minimal higher harmonics over a larger portion of the transfer characteristic. The transition from soft to hard distortion and back will be smoother and less audible.

This reasoning is supported by simulations in Spice.

Output signals at 10% output distortion:

![Fig.2](https://raw.githubusercontent.com/akouz/MusEff/refs/heads/main/1_2_3_stages/Output_when_THD_10.png)

The red curve is the signal at the first stage output in the 2- and 3-stage configurations. Its output signal is used for both the 2- and 3-stage configurations. Distortion at the first stage output is approximately 3%, and the amplitude is approximately one-third of the output amplitude.

It's easy to see that at 10% distortion, the output signal amplitude of the three-stage overdrive is almost half that of the two-stage overdrive, as predicted.

When the input signal amplitude doubles, the two-stage overdrive enters hard clipping, the single-stage overdrive balances on the edge, and the three-stage overdrive still has some headroom.

![Fig.3](https://raw.githubusercontent.com/akouz/MusEff/refs/heads/main/1_2_3_stages/Output_when_Vin_x2.png)

Distortion at transition to hard clipping:

Vin mVpp        1-st    2-st    3-st
---------------------------------------
50              10%     10%     10%
100             16%     19%     20%
200             28%     33%     26%
400             37%     41%     37%


