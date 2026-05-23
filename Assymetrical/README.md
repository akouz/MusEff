# Несимметричные искажения

Если синусоидальный сигнал исказить при помощи несимметричной передаточной функции (НПФ), то в выходном спектре будут присутствовать и четные, и нечетные гармоники. Практически любой однотактный усилительный каскад обладает НПФ. Это может быть ламповый каскад, каскад на полевом или на биполярном транзисторе.  Кроме этого, НПФ можно получить в  каскаде не усиливающем сигнал, например, при помощи диода.

## 1. Диод со смещением

В простейшей схеме диодного клиппера Fig.1 подадим на обычный кремниевый диод 1N4148 положительное смещение 400 мВ. Диод при этом немного приоткроется и станет вносить несимметричные искажения начиная с самых малых уровней входного сигнала. До какого-то уровня искажения будут прямо пропорциональны входному сигналу. 

![Fig.1](https://github.com/akouz/MusEff/blob/main/Assymetrical/Diode_1.png)

Fig.1

При сигнале с двойной амплитудой 380 мВ искажения достигнут 10%.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_10.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_10_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.2

Если мы удвоим амплитуду входного сигнала, то искажения возрастут чуть менее чем вдвое.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_18.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_18_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.3

При дальнейшем удвоении амплитуды рост искажений начнет уже заметно отставать. На этом шаге в выходном сигнале появилось отрицательное напряжение, при котором диод полностью закрыт и не вносит искажений.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_26.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_26_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.4

Еще раз удвоим входное напряжение, теперь его размах превышает 3 В. Отрицательная полуволна в выходном сигнале становится доминирующей, а рост искажений заметно замедлился.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_33.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_33_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.5

При входном напряжении двойной амплитудой 6 В рост искажений почти прекратился. При этом динамика выходного сигнала более-менее продолжает следовать динамике входного сигнала.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_37.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/THD_37_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.6

Если требуется ограничить динамику выходного сигнала, то можно встречно-параллельно первому диоду подключить еще один диод, например, такой же 1N4148. Получится самый обычный клиппер на двух диодах, но в отличие от стандартного включения на него подано постоянное смещение 400 мВ.

При малых входных напряжениях второй диод закрыт и не оказывает влияния, поэтому Fig.2 - Fig.4 остаются в силе. Но в какой-то момент амлитуда отрицательной полуволны становится достаточной, чтобы второй диод открылся. Соответственно, вместо Fig.5 и Fig.6 на выходе получится то, что изображено на Fig.7 и Fig.8.

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

Передаточная функция и ее первая производная для такого клиппера показана на Fig.9. Смещение задано 500 мВ, чтобы при нулевом входном сигнале оказаться примерно в середине падающго фронта производной. При этом малосигнальные искажения будут ближе всего к искажениям, создаваемым параболической передаточной функцией. 

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/Diodes_transfer_func.png" width="70%"></td>
  </tr>
</table>
Fig.9

## 2. Усилительный каскад на JFET

Сравним две схемы включения JFET, обычную и каскодную. 

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/JFET_cascode.png" width="70%"></td>
  </tr>
</table>
Fig.10

Передаточные функции этих каскадов, а также их производные показаны на Fig.11. Производная передаточной функции каскода более линейна. Это значит, что сама передаточная функция каскода ближе к параболической. Поэтому обе схемы дадут вторую гармонику одинаковой величины, а более высоких гармоник в каскодной схеме будет меньше. 

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/JFET_cascode_transfer.png" width="70%"></td>
  </tr>
</table>
Fig.11

В этом можно убедиться, подав на вход обоих каскадов синусоидальный сигнал и сравнив получившиеся спектры. Постоянное смещение на затворах обоих каскадов равно -2.3 В.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/JFET_cascode_Vout.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/JFET_cascode_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.12

Сравнивая эти спектры при 10% искажениях со спектрами диодного каскада Fig.2, легко убедиться, что JFET производят гораздо меньше высших гармоник, особенно при каскодном включении.

## 3. Умножитель

Квадратичную передаточную функцию легко получить если умножить сигнал сам на себя. Однако микросхемы аналоговых умножителей дОроги. Простой аналоговый умножитель можно собрать на ячейке Гилберта. Точность не требуется, четырехквадрантное умножение тоже ни к чему, поэтому схему можно предельно упростить:

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/Gilb_sch.png" width="70%"></td>
  </tr>
</table>
Fig.13

Выходные сигналы и их спектры преставлены на Fig.14. На коллекторе Q1 присутствует сигнал удвоенной частоты.

<table style="width: 100%;">
  <tr>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/Gilb_out.png" width="70%"></td>
    <td><img src="https://github.com/akouz/MusEff/blob/main/Assymetrical/Gilb_FFT.png" width="70%"></td>
  </tr>
</table>
Fig.14

Умножитель можно также сделать на основе транскондукторного усилителя. Эта идея была воплощена Р.Мугом в линейке полностью полупроводниковых усилителей Lab Series в конце 70-х. Использование умножителя на основе LM3280 позволяло получать звучание, не уступающее ламповым усилителям. Впоследствии фирма Aion выпустила [примочку](https://aionfx.com/project/l5-preamp/), аналогичнную предусилителю Lab Series L5. В качестве умножителя использован LM13700.
