# Series connection of cascades and the influence of feedback

As we've already established, a single vacuum tube or JFET stage has a transfer function close to parabolic. Unlike a purely parabolic function, which only produces the first and second harmonics when a sine wave is applied to the output, vacuum tube and JFET stages have a small number of higher harmonics.

What happens when two stages are connected in series? To avoid clouding the picture with the weak higher harmonics of real stages, let's consider two stages with ideal parabolic (i.e., quadratic) transfer functions. We'll invert and slightly boost the output signal of the first stage, which will more or less correspond to two output stages of vacuum tube guitar preamplifiers, such as the JCM800 and others.

Without any particular reference to specific values, the output signal spectra at a moderate THD level of 10% will look something like this:

![Fig.1](https://github.com/akouz/MusEff/blob/main/Two_stages_and_FBK/Fig_1.png)

Fig.1

The first stage's THD was 8.6%, and after the second stage, the THD increased only slightly, to 10%. This is because, due to inversion, the second stage's nonlinearity counteracts and compensates for the first stage's nonlinearity. However, by itself, in a single operation and all other things being equal, the second stage would introduce much more distortion than 10%.

The first stage, with its parabolic transfer characteristic (red line), as expected, will only add the second harmonic to the output signal. However, after the second stage (green line), the output signal will contain harmonics from the first to the fourth, but nothing else. In other words, two series-connected stages with parabolic or very close-to-parabolic transfer characteristics will enrich a weak signal with harmonics up to the fourth, but will not add unpleasant-sounding high harmonics, or will add very little of them.

It's quite obvious that this fact explains the notorious "warm tube sound." Until severe clipping occurs, tube stages add almost no higher harmonics to the signal, but they do enrich the sound with low harmonics that aren't jarring. To avoid ruining the resulting effect, all other stages should not introduce significant distortion.

And what is the effect of negative feedback (NFB)? At first glance, the answer seems obvious: there should be fewer harmonics at the output. However, this is incorrect. After all, we're considering distorting amplifiers. Therefore, we should compare a stage without NFB and a stage with NFB with the same amount of output distortion.

Let's place a mixer at the input of a stage with a parabolic transfer characteristic. We'll feed the inverted signal from the output of this stage to one input of the mixer, and the input signal to the other. Since the output signal amplitude will decrease due to negative feedback, we increase the input signal amplitude to a level such that the first harmonic in the output signal spectrum maintains the same amplitude. The result is shown in Fig. 2.

![Fig.2](https://github.com/akouz/MusEff/blob/main/Two_stages_and_FBK/Fig_2.png)

Fig.2

At the same time, the THD at the stage's output decreased slightly, from 8.6% to 6.1%, but the signal spectrum changed radically. In addition to the second harmonic, the negative feedback stage added all the higher harmonics to the output spectrum.

This was obviously the reason why VOX firmly promised that its amplifiers would not use negative feedback. As is well known, The Beatles played on VOX amplifiers. In light of the above, this does not seem coincidental.
