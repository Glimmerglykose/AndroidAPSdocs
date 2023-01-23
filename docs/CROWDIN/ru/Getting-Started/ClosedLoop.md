# Что такое система замкнутого цикла?

% изображение:../images/autopilot.png
% :alt: AAPS-как автопилот

Искусственная поджелудочная железа замкнутой системы сочетает в себе различные компоненты чтобы облегчить управление диабетом.
В своей книге " Automated Insulin Delivery \<<https://www.artificialpancreasbook.com/>>\` _ Dana M. Lewis, одна из основателей движения ИПЖ с открытым исходным кодом, назвала алгоритм системы "автопилот для диабета" \<<https://www.artificialpancreasbook.com/3.-getting-started-with-your-aps>>\` \_. Что это означает?

**Автопилот в самолете**

Автопилот не выполняет всю работу и не дает возможности пилоту спать в течение всего полета. Он облегчает работу пилотов. Он освобождает их от бремени постоянного наблюдения за самолетом и ходом полета. Это позволяет пилоту сосредоточиться на мониторинге воздушного пространства и управлении функциями автопилота.

Автопилот получает сигналы от различных датчиков, компьютер оценивает их наряду со спецификациями пилота, а затем вносит необходимые корректировки. Пилоту больше не нужно беспокоиться о постоянных корректировках.

\*\* Система замкнутого цикла * \*

То же самое относится и к и системе искусственной поджелудочной железы. Она не делает всю работу, вы все равно должны контролировать свой диабет. Система замкнутого цикла объединяет данные датчиков мониторинга с такими параметрами управления диабетом, как скорость базала, коэффициент чувствительности к инсулину и углеводный коэффициент. Исходя из этого, она рассчитывает предложения по лечению и выполняет постоянные небольшие корректировки, чтобы держать диабет в целевом диапазоне и избавить вас от этой заботы. Это оставляет больше времени для жизни "рядом с" диабетом.

Так же, как никто не хочет попасть на самолет, которым управляет только автопилот без контроля человека, система замкнутого цикла помогает нам в управлении диабетом, но всегда нуждается в нашей поддержке! \*\* Даже в режиме замкнутого цикла нельзя просто взять и забыть про свой диабет! \*\*

Точно так же, как автопилот зависит от показателей датчиков, а также от параметров, задаваемых летчиками, система замкнутой петли требует соответствующих вводных данных, таких как скорость базала, чувствительность к инсулину ISF и углеводный коэффициент, чтобы успешно обеспечить поддержку вашего организма.

## Замкнутые системы ИПЖ с открытым исходным кодом

В настоящее время существует три основных замкнутых системы с открытым исходным кодом:

### AndroidAPS (AAPS)

AndroidAPS подробно описан в этой документации \<./WhatisAndroidAPS.html> \` \_. Он использует смартфон Android для вычислений и контроля инсулиновой помпы. Он создан в тесном взаимодействии с OpenAPS (т.е. у них общие алгоритмы).

Совместимые \` помпы \<../Hardware/pumps.md> \` \_:

- [DanaR](../Configuration/DanaR-Insulin-Pump.md) / [DanaRS & Dana-i](../Configuration/DanaRS-Insulin-Pump.html)

- Accu-Chek Combo \<../Конфигуратор/Accu-Chek-Combo-Pump.html> \` \_

[Accu-Chek Insight](../Конфигуратор/Accu-Chek-Insight-Pump.html)
\* [Diaconn G8](../Configuration/DiaconnG8.md)
\* [Omnipod Eros](../Конфигуратор/OmnipodEros.html)
\* некоторые старые помпы [Medtronic](../Конфигуратор/MedtronicPump.html)

### OpenAPS

\` OpenAPS \<<https://openaps.readthedocs.io>>\` \_-это первая закольцованная система с открытым исходным кодом. Она использует мини-компьютер, Raspberry Pi или Intel Edison.

Совместимые помпы:

- некоторые старые помпы Medtronic

### Петля iOS

\` Петля для iOS \<<https://loopkit.github.io/loopdocs/>>\` \_-это замкнутая система Loop для Apple iPhone.

Совместимые помпы:

- Omnompod Eros
- некоторые старые помпы Medtronic