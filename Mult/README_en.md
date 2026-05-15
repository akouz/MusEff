# Multiplyers

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

