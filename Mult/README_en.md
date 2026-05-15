# Multipliers

From trigonometry we know that squaring the sine function gives a function with double the frequency:

$`sin^2(x) = (1- cos(2x))/2`$          [1]

Since sine and cosine are audibly indistinguishable in sound, for simplicity's sake, squaring a signal doubles its frequency. This is clearly seen in the graph in Fig. 1. By passing a sine wave (green line) through a quadratic transfer function (red parabola), we obtain a signal with double the frequency at the output (purple line).

![Fig.1](https://github.com/akouz/MusEff/blob/main/Mult/fig_1.png)

Fig. 1

It's quite obvious that the output signal is unipolar: all its values ​​are positive, since squaring can only result in a positive result.

If we double the amplitude of the input signal in Figure 2 (yellow line), the amplitude of the unipolar output signal with doubled frequency will quadruple (blue line). This is also obvious.

![Fig.2](https://github.com/akouz/MusEff/blob/main/Mult/fig_2.png)

Fig. 2

Let's switch to the more familiar Spice environment, see Fig. 3. Using a multiplier, we'll square the sine wave of a 500 Hz frequency with an amplitude of 0.5 V (green line) and 1 V (yellow line). The output will be a sine wave with a frequency of 1000 Hz and an amplitude of 0.25 V (purple line) and 1 V (blue line).

![Fig.3](https://github.com/akouz/MusEff/blob/main/Mult/fig_3.png)

Fig. 3

What happens if we mix the input signal with the multiplier's output? To be precise, we'll attenuate the multiplier's output signal by a factor of two. The resulting transfer function is:

$`0.5*X^2 + X`$        [2] 

Fig. 4 shows the results for an input signal with an amplitude of 1 V (green line) and 0.5 V (red line).

![Fig.4](https://github.com/akouz/MusEff/blob/main/Mult/fig_4.png)

Fig. 4

As expected, as the input signal amplitude decreases, distortion decreases proportionally to the amplitude. This occurs because the output signal spectrum contains only the first and second harmonics, and the second harmonic amplitude decreases as the square of the input signal amplitude.

This is clearly visible in the signal spectrum: the dotted line is the output signal spectrum for an input signal of 1 V, and the solid line is the spectrum for an input signal of 0.5 V. As the input signal decreased, the first harmonic decreased by 6 dB, and the second harmonic by 12 dB (see Fig. 5).

![Fig.5](https://github.com/akouz/MusEff/blob/main/Mult/fig_5.png)

Fig. 5

To achieve the same result, it's not necessary to mix the multiplier's output signal with the input signal. Simply apply a constant bias V to the multiplier's input. After some trivial transformations, we obtain the following transfer function:

$`(X + V)*(X + V) = X^2 + 2*V*X + V^2`$          [3]

The constant $`V^2`$ can be discarded, since a constant offset cannot be heard. After this, we obtain the transfer function

$`X^2 + 2*V*X`$          [4] 

which, up to a factor of several, is identical to that discussed above [2]. The input signal level and output volume controls allow for absolutely identical results.

For clarity, this is illustrated in Fig. 6. The input signal with a constant offset (green line), after passing through the right shoulder of the parabolic transfer function, becomes a signal (red line) similar to that shown in Fig. 4.

![Fig.6](https://github.com/akouz/MusEff/blob/main/Mult/fig_6.png)

Fig.6.

Vacuum tube and JFET amplifier stages have transfer characteristics close to parabolic. However, unlike an ideal multiplier, their transfer characteristics reproduce only a small portion of the parabola, as shown in Fig. 7. With the operating point correctly adjusted, they are capable of producing 25% distortion in the parabolic region. However, as the input signal amplitude increases further, the amplifiers begin to severely clip the signal.

![Fig.7](https://github.com/akouz/MusEff/blob/main/Mult/fig_7.png)

Fig.7.

Fig. 8 illustrates the difference between the signal at the output of the multiplier (blue line) and the amplifier outside the parabolic region (red line).

![Fig.8](https://github.com/akouz/MusEff/blob/main/Mult/fig_8.png)

Fig.8.

And if, with an increase in the input signal level, in the spectrum (Fig. 9) of the multiplier output signal, as before, only the first and second harmonics (green line) are present, then in the spectrum of the amplifier signal, after the onset of hard clipping, all higher harmonics (red line) instantly appear.

![Fig.9](https://github.com/akouz/MusEff/blob/main/Mult/fig_9.png)

Fig.9.

However, this doesn't sound all that bad to the ear, since the signal in the parabolic region is already significantly distorted by the second harmonic. And if the amplifier's transfer characteristic isn't quite so parabolic before clipping, the spectrum always contains higher harmonics, so the transition to clipping isn't perceived as abruptly.
