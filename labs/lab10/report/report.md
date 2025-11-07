---
## Front matter
title: "Отчёт по лабораторной работе №10"
subtitle: "Основы работы с модулями ядра операционной системы"
author: "Яковлева Дарья Сергеевна"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Получить навыки работы с утилитами управления модулями ядра операционной системы.

# Выполнение лабораторной работы

# Выполнение лабораторной работы

## Управление модулями ядра из командной строки

### Инвентаризация устройств и связанных модулей

Получаю root-доступ и вывожу список контроллеров с привязками драйверов (`lspci -k`).  
Обнаружено, что видеокарта VMware SVGA II использует модуль `vmwgfx`, сетевой адаптер Intel — `e1000`, гостевые службы VirtualBox — `vboxguest`, аудио-контроллер Intel — `snd_intel8x0`, USB-контроллеры используют `ohci_pci` и `ehci_pci`, а SATA-контроллер работает через `ahci`.  

![Вывод lspci -k](image/01.jpg){ #fig:001 width=70% }

### Просмотр загруженных модулей и загрузка ext4

Смотрю список загруженных модулей (`lsmod | sort`).  
Проверяю наличие файловой системы ext4 — модуль отсутствует. Загружаю модуль, затем повторно проверяю список модулей: появляется `ext4` и его зависимости `mbcache` и `jbd2`.

![Загрузка и проверка модуля ext4](image/02.jpg){ #fig:002 width=70% }

### Информация о модуле ext4

Вывожу информацию о модуле (`modinfo ext4`).  
Отмечаю следующие данные:

- `filename` — путь к файлу модуля в системе;
- `license` — лицензия GPL;
- `description` — модуль файловой системы ext4;
- `depends` — зависимости `jbd2`, `mbcache`;
- `vermagic` — версия ядра, с которой совместим модуль;
- `signature` и `signer` — цифровая подпись модуля.

Параметров у модуля нет.

![Информация о модуле ext4](image/03.jpg){ #fig:003 width=70% }

### Выгрузка модулей ext4 и xfs

Пытаюсь выгрузить ext4. Команда выполняется только после нескольких повторов, так как модуль может быть занят.  
Пробую выгрузить `xfs`, но система сообщает ошибку — модуль используется и выгрузить его невозможно.

![Выгрузка ext4 и ошибка при удалении xfs](image/04.jpg){ #fig:004 width=70% }

## Загрузка модулей с параметрами (Bluetooth)

Проверяю наличие Bluetooth-модулей — отсутствуют.  
Загружаю модуль Bluetooth и повторно проверяю — появляется `bluetooth` и связанный `rfkill`.

![Загрузка и проверка bluetooth](image/05.jpg){ #fig:005 width=70% }

Смотрю информацию о модуле. У него есть параметры, которые можно передавать при загрузке:

- `disable_esco` — отключение eSCO-соединений;
- `disable_ertm` — отключение режима ERTM (enhanced retransmission);
- `enable_ecred` — включение режима enhanced credit flow control.

![modinfo bluetooth](image/06.jpg){ #fig:006 width=70% }

После проверки выгружаю модуль.

## Обновление ядра системы

Проверяю текущую версию ядра.  
Смотрю доступные версии пакетов ядра в репозиториях — присутствует более новая версия.

![Проверка версии ядра и доступных пакетов](image/07.jpg){ #fig:007 width=70% }

Выполняю обновление ядра и обновление всей системы.  
В процессе система сообщает, что зависимости разрешены и обновление завершено.

![Обновление пакетов и ядра](image/08.jpg){ #fig:008 width=70% }

После перезагрузки проверяю текущую версию ядра и системную информацию — загружено новое ядро.

![Проверка версии ядра после перезагрузки](image/09.jpg){ #fig:009 width=70% }

# Контрольные вопросы

1. **Какая команда показывает текущую версию ядра, которая используется на вашей системе?**  
   Используется команда `uname -r`.

2. **Как можно посмотреть более подробную информацию о текущей версии ядра операционной системы?**  
   Подробные сведения выводит команда `hostnamectl`.

3. **Какая команда показывает список загруженных модулей ядра?**  
   Для просмотра используется `lsmod`.

4. **Какая команда позволяет определять параметры модуля ядра?**  
   Информацию выводит команда `modinfo <имя_модуля>`.

5. **Как выгрузить модуль ядра?**  
   Для удаления используется `modprobe -r <имя_модуля>`.

6. **Что делать, если появляется сообщение об ошибке при попытке выгрузить модуль ядра?**  
   Это значит, что модуль используется. Нужно остановить процессы или службы, которые его используют, или завершить работу файловой системы/устройства, связанного с модулем.

7. **Как определить, какие параметры модуля ядра поддерживаются?**  
   Параметры отображаются в выводе `modinfo`, в секции `parm:`.

8. **Как установить новую версию ядра?**  
   Выполняется обновление системы и пакета ядра с помощью `dnf update kernel`, затем перезагрузка и выбор нового ядра при старте системы.

# Заключение

В ходе лабораторной работы были освоены основные приёмы работы с модулями ядра в Linux. Рассмотрены способы определения загруженных модулей, их загрузки и выгрузки, а также изучения параметров модулей через `modinfo`. Было проведено управление модулями ext4 и bluetooth, выявлены их зависимости и поддерживаемые параметры. Также выполнено обновление ядра операционной системы, что позволило получить навыки работы с пакетным менеджером и настройкой загрузки новой версии ядра. Полученные знания позволяют гибко управлять функциональностью ядра и диагностировать работу оборудования на уровне модулей.
