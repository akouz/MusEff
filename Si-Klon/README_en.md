# Si-Klon Overdrive

A revised and improved version of the iconic Klon Centaur overdrive.

<img width="1319" height="808" alt="Si-Klon_rev_1_2" src="https://github.com/user-attachments/assets/16860769-c3db-42a8-91a6-49638c2c8ea3" />

Specifically, an inherent flaw of the original device and all its clones has been corrected: when the GAIN control is at its minimum setting, the input op-amp is overloaded by a capacitive load, resulting in a monstrous sound. In my circuit, this is corrected by introducing resistor R12. Furthermore, the power supply has been simplified and improved; it can withstand polarity reversal and overvoltage up to 45V.

The main improvement is the use of a [biased silicon clipper](https://github.com/akouz/MusEff/blob/main/Clippers/README_en.md#offset-clippers) instead of a germanium one. The germanium clipper was retained so that it's easy to verify that the silicon one sounds at least as good. By adjusting resistors R29...R32, you can adjust the bias and tailor the sound to your taste. Using resistors of 1 MOhm or less will produce a softer sound than the germanium clipper.

The effect was assembled in a 1590B enclosure. The sound is essentially the same as other Centaur clones.

![Assembled](https://github.com/user-attachments/assets/f8226d31-8c0b-4815-bb12-9386cac3a84c)
