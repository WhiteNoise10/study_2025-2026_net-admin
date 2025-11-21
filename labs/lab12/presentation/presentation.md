---
## Front matter
lang: ru-RU
title: Отчёт по лабораторной работе №12
subtitle: Настройки сети в Linux
author:
  - Яковлева Дарья Сергеевна
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 20 ноября 2025

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

Получить навыки настройки сетевых параметров и управления сетевыми соединениями в Linux.

# Выполнение лабораторной работы

## Получение полномочий администратора

![Переход к root](image/1.jpg){ width=70% }

## Просмотр состояния интерфейсов

![Информация ip -s link](image/2.jpg){ width=70% }

## Таблица маршрутов

![Маршруты](image/3.jpg){ width=70% }

## IP-адреса интерфейсов

![Адреса интерфейсов](image/4.jpg){ width=70% }

## Список соединений

![Список соединений](image/5.jpg){ width=70% }

## Создание профиля dhcp

![Создание dhcp](image/6.jpg){ width=70% }

## Создание профиля static

![Создание static](image/7.jpg){ width=70% }

## Модификация static

![Изменение параметров](image/8.jpg){ width=70% }

## Дополнительные DNS и IP-адреса

![Модификация DNS и адресов](image/9.jpg){ width=70% }

## Профиль static

![nmtui static](image/10.jpg){ width=70% }

## Профиль dhcp

![nmtui dhcp](image/11.jpg){ width=70% }

## Профиль enp0s3

![nmtui enp0s3](image/12.jpg){ width=70% }

## static в GUI

![GUI static](image/13.jpg){ width=70% }

## dhcp в GUI

![GUI dhcp](image/14.jpg){ width=70% }

## enp0s3 в GUI

![GUI enp0s3](image/15.jpg){ width=70% }

# Контрольные вопросы

## Основные ответы

* Статус устройств: `nmcli device status`
* Служба сети: `NetworkManager`
* Имя устройства: `/etc/hostname`
* Изменение имени: `hostnamectl set-hostname`

## Основные ответы

* Локальное разрешение имён: `/etc/hosts`
* Маршруты: `ip route show`
* Статус NetworkManager: `systemctl status NetworkManager`
* Изменение IP:  
  `nmcli connection modify <имя> ipv4.addresses <адрес>`

# Итоги работы

## Вывод

Получены навыки:

* просмотра статуса интерфейсов и маршрутов  
* добавления IP-адресов  
* работы с профилями nmcli и nmtui  
* изменения параметров сети  

Практически освоены методы управления сетевыми настройками Linux.
