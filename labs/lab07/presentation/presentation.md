---
## Front matter
lang: ru-RU
title: Отчёт по лабораторной работе №7
subtitle: Управление журналами событий в системе
author:
  - Яковлева Дарья Сергеевна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 1 октября 2025

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

Получить навыки работы с журналами мониторинга различных событий в системе.

# Выполнение лабораторной работы

## Мониторинг системных событий

![Ошибка аутентификации при su](image/01.png){ #fig:001 width=70% }

## Мониторинг системных событий

![Сообщение logger hello](image/02.png){ #fig:002 width=70% }

## Мониторинг системных событий

![Просмотр /var/log/secure](image/03.png){ #fig:003 width=70% }

## Изменение правил rsyslog.conf

![Установка и запуск Apache](image/04.png){ #fig:004 width=70% }

## Изменение правил rsyslog.conf

![Просмотр error_log Apache](image/05.png){ #fig:005 width=70% }

## Изменение правил rsyslog.conf

![Настройка ErrorLog в httpd.conf](image/06.png){ #fig:006 width=70% }

## Изменение правил rsyslog.conf

![Правило rsyslog для httpd](image/07.png){ #fig:007 width=70% }

## Изменение правил rsyslog.conf

![Создание debug.conf](image/08.png){ #fig:008 width=70% }

## Изменение правил rsyslog.conf

![Сообщение Daemon Debug Message](image/09.png){ #fig:009 width=70% }

## Использование journalctl

![Просмотр журнала journalctl](image/10.png){ #fig:010 width=70% }

## Использование journalctl

![Вывод без пейджера](image/11.png){ #fig:011 width=70% }

## Использование journalctl

![Режим реального времени](image/12.png){ #fig:012 width=70% }

## Использование journalctl

![Фильтрация журнала](image/13.png){ #fig:013 width=70% }

## Использование journalctl

![UID=0](image/14.png){ #fig:014 width=70% }

## Использование journalctl

![Последние 20 строк](image/15.png){ #fig:015 width=70% }

## Использование journalctl

![Сообщения об ошибках](image/16.png){ #fig:016 width=70% }

## Использование journalctl

![Со вчерашнего дня](image/17.png){ #fig:017 width=70% }

## Использование journalctl

![Ошибки со вчерашнего дня](image/18.png){ #fig:018 width=70% }

## Использование journalctl

![Подробный вывод verbose](image/19.png){ #fig:019 width=70% }

## Использование journalctl

![Журнал sshd](image/20.png){ #fig:020 width=70% }

## Постоянный журнал journald

![Создание каталога journald](image/21.png){ #fig:021 width=70% }

## Постоянный журнал journald

![Активация journald](image/22.png){ #fig:022 width=70% }

# Контрольные вопросы

## Конфигурация rsyslog

* Основной файл — `/etc/rsyslog.conf`  
* Файлы правил — `/etc/rsyslog.d/`
* Журнал аутентификации - `/var/log/secure`

## Ротация журналов

* По умолчанию — раз в неделю  
* Хранение — 4 недели (`logrotate`)

## journalctl

* Режим реального времени: `journalctl -f`  
* Сообщения PID 1 с 9:00 до 15:00:  
  `journalctl _PID=1 --since "09:00" --until "15:00"`  
* После перезагрузки: `journalctl -b`

# Итоги работы

## Вывод

Были приобретены навыки мониторинга системных журналов и настройки регистрации событий в Linux:  
работа с `tail`, настройка `rsyslog`, использование `logger`, исследование логов при помощи `journalctl` и настройка постоянного хранения с помощью `journald`.
