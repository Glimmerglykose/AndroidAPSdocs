# Freestyle Libre 2

Система Freestyle Libre 2 может автоматически сообщать об опасных уровнях глюкозы в крови. Сенсор Libre2 каждую минуту отправляет текущие значения гликемии на принимающее устройство (ридер или смартфон). При необходимости приемник инициирует оповещение. С помощью модифицированного приложения LibreLink и приложения xDrip+ можно непрерывно получать данные ГК на смартфон.

Сенсор может быть откалиброван в диапазоне от -40 мг/дл до +20 мг/дл (-2,2 ммоль/л до +1,1 ммоль/л) для корректировки различий между замерами глюкометра и показаниями с сенсора.

Показания ГК можно также получать с помощью трансмиттера BT, как, например для Libre1.

Важное примечание: Не работает с американской версией сенсоров Freestyle 2! Версия США подключается только к ридеру, а не к телефону.

## Шаг 1: Создайте собственное модифицированное приложение Librelink

По юридическим причинам установка так называемого патча должна быть произведена самостоятельно. Используйте поисковые системы для поиска соответствующих ссылок. Есть в основном два варианта: рекомендуемое оригинальное исправленное приложение блокирует любой интернет-трафик, чтобы избежать отслеживания. Другой вариант поддерживает LibreView, который может понадобиться вашему врачу.

Вместо оригинального приложения следует установить модифицированное. Следующий сенсор, запущенный с его помощью, будет передавать по Bluetooth текущие значения гликемии в приложение xDrip +, работающее на смартфоне.

Важно: чтобы избежать возможных проблем, при первой установке/деинсталляции оригинального приложения может помочь использование смартфона с поддержкой NFC. NFC должен быть включен. Это не требует дополнительной энергии. Затем установите модифицированное приложение.

Исправленное приложение можно определить с помощью уведомления об авторизации в основном режиме. Служба проверки прав доступа в основном режиме повышает стабильность соединения по сравнению с исходным приложением, которое не использует эту службу.

```{image} ../images/Libre2_ForegroundServiceNotification.png
:alt: "LibreLink \u0421\u043B\u0443\u0436\u0431\u0430 \u043F\u0435\u0440\u0435\u0434\
:  \u043D\u0435\u0433\u043E \u043F\u043B\u0430\u043D\u0430 (\u043E\u0441\u043D\u043E\
:  \u0432\u043D\u043E\u0439 \u0440\u0435\u0436\u0438\u043C)"
```

Другими индикаторами может быть логотип Linux penguin с тремя точками меню-> Info или шрифт модифицированного приложения. Эти критерии являются необязательными в зависимости от того, какой источник приложения вы выбрали.

```{eval-rst}
.. изображение:: ../images/LibreLinkPatchedCheck.
  :alt: Проверка шрифтов LibreLink
```

Убедитесь, что активирована NFC, включите разрешение на память и геолокацию для модифицированного приложения, включите автоматическое время и часовой пояс и задайте хотя бы одно оповещение в этом приложении.

Теперь запустите датчик Libre2 при помощи модифицированного приложения, просто сканируя сенсор. Убедитесь, что заданы все параметры.

Обязательные параметры для успешного запуска сенсора:

- NFC включен/BT включен
- включено разрешение на память и геолокацию
- Включена служба определения местоположения
- автоматическое определение времени и часового пояса
- задать хотя бы одно оповещение в модифицированном приложении

Обратите внимание, что служба определения расположения является центральным параметром. Это не разрешение на доступ к геолокации в приложении, которое также должно быть активировано!

```{eval-rst}
.. изображение:: ../images/Libre2_AppPermissionsAndLocation.png
  :alt: LibrreLink-разрешение на доступ к памяти и расположению

```

```{eval-rst}
.. изображение:: ../images/Libre2_DateTimeAlarms.png
  :alt: автоматическое определение времени и часового пояса + настройки оповещений
```

Сенсор запоминает устройство, с которого он был запущен. Только это устройство может получать оповещения в будущем.

Первая установка соединения с сенсором имеет решающее значение. Приложение LibreLink пытается установить беспроводное соединение с сенсором каждые 30 секунд. Если один или несколько обязательных параметров отсутствуют, их надо скорректировать. У вас нет ограничений по времени для этого. Сенсор постоянно пытается установить соединение. Даже если это длится несколько часов. Будьте терпеливы и попробуйте разные настройки, прежде чем даже подумать о замене сенсора.

Красный восклицательный знак ("!) в левом верхнем углу стартового экрана LibreLink означает, что нет соединения или какая-то другая настройка не позволяет LibreLink издавать оповещения. Проверьте, включен ли звук и отключены ли все виды блокировок уведомлений от приложений. Когда восклицательный знак исчезнет, соединение будет установлено и значения гликемии отправятся на смартфон. Это должно произойти не более чем через 5 минут.

```{eval-rst}
.. изображение:: ../images/Libre2_ExclamationMark.png
  :alt: LibreLink нет соединения
```

Если восклицательный знак остается или вы получите сообщение об ошибке, это может иметь несколько причин:

- Служба определения местоположения Android не предоставлена - включите ее в системных настройках
- автоматическое время и часовой пояс не заданы - измените настройки

-активировать сигналы -по крайней мере однин из трех сигналов в LibreLink
\- Bluetooth выключен - включите
\- звук заблокирован
\- уведомления приложений заблокированы
\- неактивные уведомления на экране заблокированы
\- у вас неисправный сенсор Libre 2 из партии K + 8 цифр. Вы найдете этот номер на желтой упаковке Эти сенсоры должны быть заменены, поскольку они не работают с bluetooth.

Перезапуск телефона помогает, возможно, придется перезапустить несколько раз. Как только соединение будет установлено, красный восклицательный знак исчезнет и самый важный этап - сопряжение - пройден. Может случиться так, что в зависимости от системных настроек восклицательный знак остается, но данные идут. В обоих случаях нет причин беспокоиться. Сенсор и телефон теперь сопряжены, каждую минуту передаются данные ГК.

```{eval-rst}
.. изображение:: ../images/Libre2_Connected.png
  :alt: Соединение LibreLink установлено
```

Иногда может помочь очистка кэша bluetooth и/или сброс всех сетевых соединений через меню системы. Это удалит все подключенные устройства и возможно восстановит правильное соединение. Эта процедура безопасна, так как запущенный сенсор запоминается модифицированным приложением LibreLink. Ничего дополнительного не нужно делать. Просто подождите подключения к сенсору.

После успешного подключения при необходимости можно изменить настройки смартфона. Это не рекомендуется, но вы можете захотеть экономить энергию. Служба определения местоположения может быть отключена, громкость установлена на ноль, сигналы снова отключены. Данные сахара крови в любом случае передаются.

Однако, при запуске следующего сенсора, все параметры должны быть установлены снова!

Замечание: чтобы включить соединение, приложению требуются обязательные настройки, установленные в течение часа после разогрева,. В течение 14-дневного периода работы они не нужны. В большинстве случаев при проблемах с запуском сенсора было выключена служба определения местоположения. На Android это необходимо для правильной работы Bluetooth. См. документацию Google Android.

В течение 14 дней для сканирования при работе с приложением LibreLink можно использовать параллельно один или несколько смартфонов с NFC (не ридер!). Для этого действия нет ограничений по времени. Можно начать работу еще с одним телефоном, например, на пятый или любой другой день. Второй телефон (телефоны) может передавать значения сахара крови в Abbott Cloud (LibreView). LibreView может генерировать отчеты для специалистов. Есть много родителей, которым это необходимо.

Обратите внимание, что оригинальное модифицированное приложение **не имеет никакого подключения к Интернету**, чтобы избежать отслеживания.

Однако существует вариант этого приложения с включенным доступом в Интернет для поддержки LibreView. Имейте в виду, что в этом случае ваши данные передаются в облако. Но ваша цепочка отчетов и diadoc полностью поддерживается. С помощью этого варианта можно также перенести оповещения сенсора на другое устройство, которое не запускало сенсор. Подробно о том, как это сделать, можно найти поиском google на немецких диабетических форумах.

## Шаг 2: Установите и настройте приложение xDrip+

Значения гликемии передаются на смартфон приложением xDrip+.

- Если это еще не сделано, загрузите xdrip и установите одну из последних ночных сборок отсюда [https://github.com/NightscoutFoundation/xDrip/releases](https://github.com/NightscoutFoundation/xDrip/releases).
- В xDrip+ выберите "Libre2 (пропатченное приложение)" в качестве источника данных
- При необходимости введите "BgReading:d, xdrip libr_receiver:v" в разделе Менее распространенные настройки -> Extra Logging Settings-> Extra tags for logging. Это позволит записывать сообщения об ошибках для устранения неисправностей.

В xdrip перейдите в настройки > совместимость программ >локальная трансляция данных и выберите Включить (ON).
В xdrip+ перейдите в настройки > совместимость программ > принимать назначения (Accept treatments) и выберите ВЫКЛ (OFF).
\* для включения приема ГК с xdrip (версия AAPS 2.5.x и выше) установите [Settings > Interapp Settings > Identify Receiver "info.nightscout.androidaps"](../Configuration/xdrip#identify-receiver)
Если хотите, чтобы AndroidAPS мог калибровать показания гликемии, в xdrip + перейдите в настройки > совместимость приложений > принимать калибровки (Accept calibrations) и выберите ВКЛ (ON).  Возможно вы также захотите рассмотреть варианты калибровки в настройках > менее распространенные параметры > дополнительные параметры калибровки.

```{eval-rst}
.. изображение:: ../images/Libre2_Tags.png
  :alt: xDrip+ LibreLink журналы
```

## Шаг 3: Запустить сенсор

В xDrip+ запустите датчик с помощью "Start Sensor" и "not today".

На самом деле это физически не запустит сенсор Libre2 и не начнет взаимодействие с ним. Это просто для того, чтобы указать xDrip+, что новый сенсор начал передавать уровень ГК. Если доступно, введите два замера крови для начальной калибровки. Теперь значения глюкозы крови должны отображаться в xDrip+ каждые 5 минут. Пропущенные значения, например из-за того, что вы были слишком далеко от вашего телефона, не будут восстановлены.

После смены сенсора xDrip+ автоматически определит новый и удалит все данные калибровки. После активации измерьте ГК и сделайте первоначальную калибровку.

## Шаг 4: Настройка AndroidAPS (для работы в замкнутом/незамкнутом цикле)

- В AndroidAPS перейдите в Config Builder > BG Source и проверьте 'xDrip+'

Если AAPS не получает значения ГК с телефона в режиме авиаперелета пользуйтесь функцией Идентифицировать приемник на странице настроек [xDrip+](../Configuration/xdrip#identify-receiver).

До настоящего времени, используя Libre 2 в качестве источника данных ГК, невозможно активировать «Включить SMB всегда» и «Включить SMB после углеводов» в алгоритме SMB. Значения BG Libre 2 недостаточно ровные, чтобы использовать их безопасно. Подробнее см. в `Выравнивание данных мониторинга <../Usage/Smoothing-Blood-Glucose-Data-in-xDrip.md>`.

## Опыт и устранение неполадок

### Связь

Способность к сопряжению исключительная. За исключением мобильных телефонов Huawei, все современные смартфоны, по-видимому, работают хорошо. Повторное подключение в случае потери связи проходит отлично. Связь может прерваться, если мобильный телефон находится в кармане напротив сенсора или на улице. Когда я работаю в саду, я ношу телефон на одной стороне тела с датчиком. В помещениях, где активно присутствуют устройства Bluettooth, нет никаких проблем. Если возникают проблемы с подключением, проверьте другой телефон. Также может помочь установка сенсора антенной BT вниз. При установке сенсора прорезь на аппликаторе должна быть направлена вниз.

### Сглаживание данных и необработанные данные

Технически, текущее значение сахара в крови передается на xDrip + каждую минуту. Фильтруется средневзвешенное сглаженное значение за последние 25 минут. Это обязательно для цикла. Кривые выглядят гладкими, и результаты работы цикла великолепны. Необработаные значения, на которых основаны оповещения, имеют несколько больший разборос, но в конечном счете соответствуют показателям ридера. Кроме того, необработанные значения могут отображаться на графике xDrip+ для того, чтобы имелась возможность своевременно реагировать на быстрые изменения. Переключитесь на Менее распространенные Настройки > Расширенные настройки для Libre2 > "показывать необработанные значения" и "показывать Информацию с сенсора". После этого "необработанные" значения будут дополнительно отображается в виде небольших белых точек и в меню системы будет доступна дополнительная информация о сенсоре.

Необработанные данные очень полезны при быстрых изменениях ГК. Даже если точки идут вразброс, для принятия решений по терапии тенденция видна гораздо лучше, чем при сглаживании.

```{eval-rst}
.. изображение:: ../images/Libre2_RawValues.png
  :alt: xDrip + дополнительные параметры Libre 2 & необработанные данные
```

### Время работы сенсора

Рабочее время сенсора фиксируется на 14 дней. 12 дополнительных часов Либре1 больше не существует. xDrip + показывает дополнительную информацию о сенсоре после включения дополнительных параметров для Libre2 > "show Sensors Infos" в системном меню, такую например, как время запуска сенсора. Оставшееся время работы сенсора можно также увидеть в модифицированном приложении LibreLink. Либо в главном окне в виде оставшихся дней работы, либо в виде времени начала работы датчика в трехточечных меню-> Справка-> Протокол событий в разделе "Новый датчик найден".

```{eval-rst}
.. изображение:: ../images/Libre2_Starttime.png
  :alt: Libre 2 время запуска
```

### Новый сенсор

Замена сенсора происходит на лету: установите новый сенсор незадолго до активации. Как только xDrip + перестает получать больше данных от старого сенсора, запустите новый при помощи модифицированного приложения. Через час новые значения должны автоматически отображаться в xDrip+.

В противном случае проверьте настройки телефона и перейдите к первоначальному запуску. У вас нет ограничения по времени. Постарайтесь найти правильные настройки. Нет необходимости сразу же менять сенсор пока не перепробованы разные комбинации. Датчики надежны, постарайтесь установить надежное соединение. Не торопитесь. В большинстве случаев вы можете случайно изменить один параметр, который вызывет новые проблемы.

При успехе выберите "стоп сенсор" и "только удалить калибровки" в xDrip. xDrip + сможет понять, что новый сенсор получает данные об уровне сахара в крови, а старые калибровки больше не действительны и поэтому должны быть удалены. Никакого реального взаимодействия с сенсором Libre2 при этом не происходит!  Запускать сенсор в xDrip не требуется+.

```{eval-rst}
.. изображение:: ./images/Libre2_GapNewSensor.png
  :alt: xDrip + пропущенные данные при замене сенсора Libre 2
```

### Калибровка

Вы можете калибровать Libre2 со смещением -40 мг/дл до +20 мг/dL \[-2,2 ммоль/л до +1,1 ммоль/л\] (intercept). Наклон графика не может быть изменен, поскольку Libre2 гораздо точнее по сравнению с Libe1. Проверяйте глюкометром как можно раньше после установки нового сенсора. Известно, что при измерении глюкометром могут возникнуть большие расхождения. Для верности, калибруйте каждые 24-48 часов. Значения точны до конца срока работы сенсора и не имеют такого разброса как в Libre1. Однако, если сенсор и близко не показывает верные значения, это не изменится. В этом случае сенсор следует немедленно заменить.

### Верификация

Сенсоры Libre2 способны выполнять самопроверку для обнаружения неверных значений. Как только сенсор смещается на руке или слегка приподнимается, данные могут начать колебаться. После этого датчик Libre2 отключится по соображениям безопасности. К сожалению, при сканировании при помощи приложения, проводятся дополнительные проверки. Приложение может отключить сенсор, даже если он исправен. В настоящее время внутренний тест слишком жесткий. Я полностью прекратил сканирование и с тех пор сбоев не было.

### Пересечение часового пояса

В других часовых поясах \<../Usage/Timezone-traveling.md>\`\_ есть две стратегии для работы алгоритма:

Либо

1. оставить время смартфона без изменений и сдвинуть базальный профиль (смартфон в режиме полета) или
2. удалить историю помпы и изменить время смартфона на местное время.

Метод 1. очень хорош, если вам не нужно тут же устанавливать новый датчик Libre2. При наличии сомнений выберите метод 2, особенно если поездка занимает больше времени. Если вы запускаете новый сенсор, часовой пояс должен быть установлен на автоматическую смену, поэтому метод 1. будет нарушен. Пожалуйста, проверьте это заранее, вы можете столкнуться с проблемами.

### Опыт

В целом это одна из самых маленьких систем мониторинга ГК на рынке. Маленькая, не нуждается в трансмиттере, выдает точные значения без отклонений. После приблизительно 12 часов работы в фазе подстройки с отклонениями до 30 мг/дл (1,7 ммольl/л), отклонения не превышают 10 мд/дл (0,6 ммоль/л). Наилучшие результаты на внутренней части верха руки, другие места применяйте с осторожностью! Нет необходимости устанавливать новый сенсор заранее для привыкания. Это помешает внутреннему механизму сглаживания.

В ремя от времени случаются плохие сенсоры, у которых имеются расхождения с показаниями ГК. Они не изменяются. Их следует немедленно заменить.

Если датчик сдвинется немного на коже или каким-то образом поднимется это может привести к плохим результатам. Если нить сенсора немного вышла из ткани, это приведет к неверным результатам. Скорее всего вы увидите скачущие данные в xDrip +. Или к изменению значений ГК. В этом случае немедленно замените сенсор! Т.к. результаты неточны.

## Использование трансмиттера блутус and OOP

Трансмиттер bluetooth может применяться в Libre2 с новейшими версиями приложения xDrip+ и приложением OOP для Libre2. Данные ГК будут поступать каждые 5 минут, так же как и с Libre1. Для получения описания обратитесь к сайту miaomiao. Аналогично и с устройством Bubble и в будущем с другими трансмиттерами. Blucon должен работать, но еще не тестировался.

Старые устройства Либре1 не могут использоваться с программами для Libre2. Их следует заменить на более новые или обновить им прошивку для правильной работы. К сожалению, MM1 с новейшей прошивкой пока не работает - в настоящее время идет поиск причин.

Алгоритм Libre2 генерирует те же значения ГК, что и оригинальное считывающее устройство или приложение LibreLink при NFC сканировании. AAPS с Libre2 производит 25 минутное сглаживание, чтобы избежать отдельных скачков. Алгоритм программы генерирует данные каждые 5 минут со сглаживанием по среднему значению за последние 5 минут. Поэтому значения ГК не выглядят гладкими, а совпадают с показаниями оригинального устройства считывания и быстрее следуют "реальным". Если вы хотите пользоваться алгоритмом OOP, включите все настройки сглаживания в xDrip+.

Трансмиттер Droplet работает также и с Libre2, но использует интернет-сервис. Дополнительную информацию можно найти в FB или поискать в поисковой системе. ММ2 с приложением "tomato" также использует интернет-сервис. Для получения данных гликемии на обоих устройствах необходимо иметь хорошую связь с интернетом.

Даже если алгоритм модифицированного приложения LibreLink не вызывает нареканий, могут существовать причины использования Bluetooth-передатчика:

- значения ГК совпадают с ридером
- Libre2 может работать 14,5 дней как и Libre1
- Полностью поддерживается восьмичасовое обратное наполнение данными.
- значения ГК доступны в течение часа прогрева при запуске нового датчика

Замечание: Передатчик может работать параллельно с приложением LibreLink. Он не нарушает его работу.

Замечание #2: Процедура OOP пока не может калиброваться. Это изменится в будущем.

## Наилучшие методы калибровки Libre 2

To get the best results when calibrating a libre 2 sensor there are some “rules” you should follow.
They apply independently of the software combination (e.g. patched libre-app, oop2, …) that is used to handle the libre 2 values.

1. The most important rule is to only calibrate the sensor when you have a flat bg level for at least 15 minutes. The delta between the last three readings should not exceed 10 mg/dl (over 15min not between each reading). As the libre 2 does not measure your blood glucose level but your flesh glucose level there is some time lag especially when bg level is rising or falling. This time lag can lead to way too large calibration offsets in unfavourable situations even if the bg level rise / fall is not that much. So whenever possible avoid to calibrate on rising or falling edges.  -> If you have to add a calibration when you do not have a flat bg level (e.g. when starting a new sensor) it is recommended to remove that calibration(s) as soon as possible and add a new one when in flat bg levels.
2. Actually this one is automatically taken into account when following rule 1 but to be sure: When doing comparison measurements your bg level should also be flat for about 15min. Do not compare when rising or falling. Important: You still shall do blood glucose measurements whenever you desire, just don’t use the results for calibration when rising or falling!
3. As calibrating the sensor in flat levels is a very good starting point it is also strongly recommended to calibrate the sensor only within your desired target range like 70 mg/dl to 160 mg/dl. The libre 2 is not optimized to work over a huge range like 50 mg/dl to 350 mg/dl (at least not in a linear manner), so try to only calibrate when within your desired range. -> Simply accept that values outside your calibration range will not perfectly match blood glucose levels.
4. Do not calibrate too often. Calibrating the sensor very often mostly leads to worse results. When the sensor delivers good results in flat conditions just don’t add any new calibration as it does not have any -useful- effect. It should be sufficient to recheck the status every 3-5 days (of course also in flat conditions).
5. Avoid calibration when not required. This might sound silly but it is not recommended to add a new calibration if the blood glucose to flesh glucose level difference is only ±10 mg/dl (e.g. blood glucose level: 95, Libre sensor 100 -> do NOT add the 9l, blood glucose level: 95, Libre sensor 115 -> add the 95 to be taken into account for the calibration)

Some general  notes:
After activating a new sensor and at the sensor’s end of life it does make sense to do comparison measurements more often than 3-5 days as stated in rule nr. 4. For new and old sensors it is more likely that the raw values change and a re-calibration is required.
From time to time it happens that a sensor does not provide valid values. Most likely the sensor value is way to low compared to the actual blood glucose level (e.g. sensor: 50 mg/dl, bg: 130 mg/dl) even after calibrating. If this is the case the sensor cannot be calibrated to report useful results. E.g. when using the patched libre app one can add an offset of maximal +20 mg/dl. When it happens to you that the sensor does provides way too low values, don’t hesitate to replace it as it will not get better.
Even if it might be a defective sensor, when seeing sensors that do provide way too low values very often, try to use different areas to place your sensor. Even in the official area (upper arm) there might be some locations where the sensors just do not provide valid values. This is some kind of trial end error to find areas that work for you.