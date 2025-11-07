---
## Front matter
lang: ru-RU
title: Лабораторная работа №10
subtitle: Управление модулями ядра Linux
author:
  - Яковлева Дарья Сергеевна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 04 ноября 2025

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цель работы

## Цель

Получить навыки работы с модулями ядра Linux:
* просмотр устройств и связанных модулей;
* загрузка и выгрузка модулей;
* просмотр информации о модулях;
* обновление версии ядра.

# Выполнение лабораторной работы

## Инвентаризация устройств

![Вывод lspci -k](image/01.jpg){ width=70% }

## Проверка и загрузка модуля ext4

![Загрузка и проверка модуля ext4](image/02.jpg){ width=70% }

## Информация о модуле ext4

![Информация о модуле ext4](image/03.jpg){ width=70% }

## Выгрузка модуля

![Выгрузка ext4 и ошибка при удалении xfs](image/04.jpg){ width=70% }

## Модули с параметрами (Bluetooth)

![Загрузка bluetooth](image/05.jpg){ width=70% }

## Параметры Bluetooth

![Информация о модуле bluetooth](image/06.jpg){ width=70% }

## Обновление

![Обновление пакетов и ядра](image/08.jpg){ width=70% }

## Проверка новой версии ядра

![Проверка версии ядра после перезагрузки](image/09.jpg){ width=70% }

# Контрольные вопросы

## Команды

* текущая версия ядра — `uname -r`;
* загруженные модули — `lsmod`;
* загрузка / выгрузка — `modprobe`, `modprobe -r`;
* параметры модуля — `modinfo`.


# Вывод

Были получены практические навыки работы с модулями ядра Linux:

* определение устройств и связанных модулей;
* загрузка и выгрузка модулей;
* просмотр параметров модулей;
* обновление ядра.