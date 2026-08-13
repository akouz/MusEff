# RangeMaster

Практическая реализация овердрайва, аналогичного [Dallas Rangemaster](https://github.com/akouz/MusEff/blob/main/Assymetrical/README.md#5-dallas-rangemaster).

![Fig 1](https://raw.githubusercontent.com/akouz/MusEff/refs/heads/main/RangeMaster/RangeMaster_rev_1_2.png)

Переключатель SW1 типа ON-OFF-ON позволяет менять частоту среза ФВЧ на входе искажающего каскада Q1. Регулятор тембра RV2 примерно такой же как у Big Muff Pi. 

Переключатель SW2 типа ON-OFF-ON введен для имитации свойств оригинального Dallas Rangemaster. Если перед входом стоит какая-то педаль, то SW2 ни на что не влияет. Он работает тогда, когда гитара включена на вход примочки напрямую. В крайних положениях SW2 конденсаторы C20 и C21 взаимодействуют с индуктивностью гитарного датчика и создают резонанс. Эффект получается примерно такой же, как если бы между гитарой и примочкой была включена квакушка с фиксированным положением педали.

Примеры звучания. TONE в положении 12:00, SW1 в нижнем (по схеме) положении.

[GAIN в положении 9:00](https://github.com/akouz/MusEff/raw/refs/heads/main/RangeMaster/RM_1_2_Gain_9.mp3)

[GAIN в положении 15:00](https://github.com/akouz/MusEff/raw/refs/heads/main/RangeMaster/RM_1_2_Gain_15.mp3)



