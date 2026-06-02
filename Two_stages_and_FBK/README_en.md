# Series connection of cascades and the influence of feedback

As we've already established, a single vacuum tube or JFET stage has a transfer function close to parabolic. Unlike a purely parabolic function, which only produces the first and second harmonics when a sine wave is applied to the output, vacuum tube and JFET stages have a small number of higher harmonics.

What happens when two stages are connected in series? To avoid clouding the picture with the weak higher harmonics of real stages, let's consider two stages with ideal parabolic (i.e., quadratic) transfer functions. We'll invert and slightly boost the output signal of the first stage, which will more or less correspond to two output stages of vacuum tube guitar preamplifiers, such as the JCM800 and others.

Without any particular reference to specific values, the output signal spectra at a moderate THD level of 10% will look something like this:

![Fig.1](https://github.com/akouz/MusEff/blob/main/Two_stages_and_FBK/Fig_1.png)

Fig.1

