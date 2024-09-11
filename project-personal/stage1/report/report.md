---
## Front matter
title: "Отчёт по индивидуальному проекту Этап №1


Информационная безопасность"
subtitle: "Настройка рабочего пространства и конфигурация операционной системы на виртуальную машину"
author: "Чванова Ангелина Дмитриевна, НПИбд-02-21"

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
papersize: a4
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
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
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

Настроить рабочее пространство для индивидульного проекта, приобрести практические навыки
установки операционной системы на виртуальную машину и настройки минимально необходимых для дальнейшей работы сервисов.



# Теоретическое введение

**Kali Linux** — это дистрибутив операционной системы Linux, предназначенный для специалистов по информационной безопасности. Он позволяет выполнять расширенное тестирование на проникновение, находить системные уязвимости и устранять возможные лазейки для взломщиков.

Особенности Kali Linux:

1. Основан на дистрибутиве Debian. Унаследовал от него структуру и систему управления пакетами, принципы свободного программного обеспечения.

2. Полностью бесплатен.

3. Исходный код доступен для просмотра и изменения. Это позволяет настроить систему под нужды, вплоть до изменения ядра.

4. Поддерживает широкий спектр устройств, включая USB и беспроводные адаптеры.

5. Совместим с популярными одноплатными компьютерами, такими как Raspberry Pi и BeagleBone Black.

Применение Kali Linux:

1. Специалисты по цифровой криминалистике и судебные эксперты. Применяют Kali Linux для анализа и исследования данных.

2. Пентестеры и специалисты по кибербезопасности. Используют Kali Linux для проверки систем на уязвимости, оценки безопасности сетей и приложений, моделирования атак и тестирования защиты от потенциальных угроз.

# Выполнение 

## Установка и конфигурация операционной системы на виртуальную машину

### Virtual Box

![Общие настройки](image/6.png){ #fig:001 width=70% height=70% }

![Размер пямяти и число процессоров](image/7.png){ #fig:002 width=70% height=70% }

![Виртуальный жесткий диск](image/8.png){ #fig:003 width=70% height=70% }

![Итог настроек](image/9.png){ #fig:004 width=70% height=70% }

![Окно настройки установки: выбор языка](image/10.png){ #fig:005 width=70% height=70% }

![Окно настройки установки образа ОС](image/11.png){ #fig:006 width=70% height=70% }

![Окно настройки установки: Раздел диска](image/12.png){ #fig:007 width=70% height=70% }

![Окно настройки установки: Раздел диска](image/13.png){ #fig:008 width=70% height=70% }

![Окно настройки установки: Раздел диска](image/14.png){ #fig:009 width=70% height=70% }

![Окно настройки установки: Раздел диска](image/15.png){ #fig:010 width=70% height=70% }

![Окно настройки установки: Раздел диска](image/16.png){ #fig:011 width=70% height=70% }

![Установка](image/17.png){ #fig:012 width=70% height=70% }

![Загрузчик GRUB](image/18.png){ #fig:013 width=70% height=70% }

![Вход в систему](image/19.png){ #fig:014 width=70% height=70% }


# Вывод

Были настроено рабочее пространство для индивидуального проекта, приобретены практические навыки установки операционной системы на виртуальную машину и настройки минимально необходимых для дальнейшей работы сервисов.



# Список литературы. Библиография

[1] Документация по Virtual Box: https://www.virtualbox.org/wiki/Documentation