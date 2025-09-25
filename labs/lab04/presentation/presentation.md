---
## Front matter
lang: ru-RU
title: Отчёт по лабораторной работе №4
subtitle: Работа с программными пакетами
author:
  - Яковлева Дарья Сергеевна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 13 сентября 2025

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

Получить навыки работы с репозиториями и менеджерами пакетов в Linux.

# Выполнение лабораторной работы

## Работа с репозиториями

![Содержимое файла rocky.repo](image/01.png){ #fig:001 width=70% }

## Поиск и установка пакетов

![Поиск пакетов по слову user](image/02.png){ #fig:002 width=70% }

## Поиск и установка пакетов

![Информация о пакете nmap](image/03.png){ #fig:003 width=70% }

## Установка и удаление пакетов

![Установка nmap](image/04.png){ #fig:004 width=70% }

## Установка и удаление пакетов

![Удаление nmap](image/05.png){ #fig:005 width=70% }

## Работа с группами пакетов

![Список и информация о группах пакетов](image/07.png){ #fig:006 width=70% }

## Работа с группами пакетов

![Удаление группы и восстановление из истории](image/08.png){ #fig:007 width=70% }

## Использование rpm (lynx)

![Загрузка пакета lynx](image/10.png){ #fig:009 width=70% }

## Использование rpm (lynx)

![Установка и проверка lynx](image/11.png){ #fig:010 width=70% }

## Изучение документации (lynx)

![Список файлов пакета lynx](image/12.png){ #fig:011 width=70% }

## Изучение документации (lynx)

![Документация пакета lynx](image/13.png){ #fig:012 width=70% }

## Запуск и удаление lynx

![Запуск браузера lynx](image/15.png){ #fig:013 width=70% }

## Запуск и удаление lynx

![Удаление lynx](image/16.png){ #fig:014 width=70% }

## Использование rpm (dnsmasq)

![Установка и проверка dnsmasq](image/17.png){ #fig:015 width=70% }

## Использование rpm (dnsmasq)

![Информация о пакете dnsmasq](image/18.png){ #fig:016 width=70% }

## Документация и конфигурация dnsmasq

![Список файлов и документации dnsmasq](image/19.png){ #fig:017 width=70% }

## Документация и конфигурация dnsmasq

![Руководство dnsmasq](image/20.png){ #fig:018 width=70% }

## Документация и конфигурация dnsmasq

![Конфигурация и скрипты dnsmasq](image/21.png){ #fig:019 width=70% }

# Контрольные вопросы

## Основные команды

* `rpm -qf /usr/sbin/useradd` — поиск пакета по файлу  
* `dnf group list`, `dnf group info` — работа с группами  
* `rpm -Uvh package.rpm` — установка rpm из файла  
* `rpm -qp --scripts package.rpm` — просмотр скриптов  
* `rpm -qd package_name` — документация пакета  
* `rpm -qf /path/to/file` — поиск пакета по файлу  

# Итоги работы

## Вывод

В ходе работы были изучены команды `dnf` и `rpm`.  
Выполнены операции поиска, установки, удаления и анализа пакетов,  
а также работа с группами пакетов и документацией.
