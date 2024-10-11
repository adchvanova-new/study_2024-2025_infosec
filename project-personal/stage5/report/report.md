---
## Front matter
title: "Отчет по 5 этапу индивидуального проекта"
subtitle: "Основы информационной безопасности"
author: " Чванова Ангелина Дмитриевна, НПИбд02-21"

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

Научиться использовать Burp Suite.

# Теоретическое введение

Burp Suite представляет собой набор мощных инструментов безопасности веб-приложений, которые демонстрируют реальные возможности злоумышленника, проникающего в веб-приложения. Эти инструменты позволяют сканировать, анализировать и использовать веб-приложения с помощью ручных и автоматических методов. Интеграция интерфейсов этих инструментов обеспечивает полную платформу атаки для обмена информацией между одним или несколькими инструментами, что делает Burp Suite очень эффективной и простой в использовании платформой для атаки веб-приложений.

# Выполнение лабораторной работы

Запускаем локальный сервер, на котором необходимо открыть веб-приложение DVWA для тестирования инструмента Burp Suite (рис. [-@fig:001]).

![Запуск локального сервера](image/1.jpg){#fig:001 width=70%}

Запускаем инструмент Burp Suite (рис. [-@fig:002]).

![Запуск приложения](image/2.jpg){#fig:002 width=70%}

Открываем сетевые настройки браузера для подготовки к работе (рис. [-@fig:003]).

![Сетевые настройки браузера](image/3.jpg){#fig:003 width=70%}

Изменение настроек сервера для работы с proxy и захватом данных с помощью Burp Suite (рис. [-@fig:004]).

![Настройки сервера](image/4.jpg){#fig:004 width=70%}

Изменяем настройки Proxy инструмента Burp Suite (рис. [-@fig:005]).

![Настройки Burp Suite](image/5.jpg){#fig:005 width=70%}

Устанавливаем значение "Intercept is on" во вкладке Proxy (рис. [-@fig:006]).

![Настройки Proxy](image/6.jpg){#fig:006 width=70%}

Чтобы Burp Suite исправно работал с локальным сервером, необходимо установить параметр `network_allow_hijacking_loacalhost` на `true` (рис. [-@fig:007]).

![Настройки параметров](image/7.jpg){#fig:007 width=70%}

При входе в браузер на DVWA, во вкладки Proxy появляется захваченный запрос. Нажимаем "Forward", чтобы загрузить страницу (рис. [-@fig:008]).

![Получаемые запросы сервера](image/8.jpg){#fig:008 width=70%}

Загружаем страницу авторизации, текст запроса поменялся (рис. [-@fig:009]).

![Страница авторизации](image/9.jpg){#fig:009 width=70%}

История запросов хранится во вкладке Target (рис. [-@fig:010]).

![История запросов](image/10.jpg){#fig:010 width=70%}

Попробуем ввести неправильные, случайные данные в веб-приложении и нажмем `Login`. В запросе увидим строку, в которой отображаются введенные нами данные, то есть поле для ввода (рис. [-@fig:011]).

![Ввод случайных данных](image/11.jpg){#fig:011 width=70%}

Этот запрос так же можно найти во вкладке Target, там же жмем правой кнопкой мыши на хост нужного запроса, и далее нажимаем "Send to Intruder" (рис. [-@fig:012]).

![POST-запрос с вводом пароля и логина](image/12.jpg){#fig:012 width=70%}

На вкладке Intruder видим значения по умолчанию у типа атаки и наш запрос (рис. [-@fig:013]).

![Вкладка Intruder](image/13.jpg){#fig:013 width=70%}

Изменяем значение типа атаки на Cluster bomb и проставляем специальные символы у тех данных в форме для ввода, которые будем пробивать, то есть у имени пользователя и пароля (рис. [-@fig:014]).

![Изменение типа атаки](image/14.jpg){#fig:014 width=70%}

Так как мы отметили 2 параметра для подбора, то нам необходимо 2 списка со значениями для подбора. Заполняем первый список в `Payload setting` (рис. [-@fig:015]).

![Первый Simple list](image/15.jpg){#fig:015 width=70%}

Заполняем значениями второй список. В строке request count видим нужное количество запросов, чтобы проверить все возможные пары пользователь-пароль (рис. [-@fig:016]).

![Второй Simple list](image/16.jpg){#fig:016 width=70%}

Запускаем атаку и начинаем подбор (рис. [-@fig:017]).

![Запуск атаки](image/17.jpg){#fig:017 width=70%}

При открытии результата каждого post-запроса можно увидеть полученный get-запрос, в нем видно, куда нас перенаправило после выполнения ввода пары пользователь-пароль. В представленном случае с подбором пары admin-admin нас перенаправило на login.php, это значит, что пара не подходит (рис. [-@fig:018]).

![Результат запроса](image/18.jpg){#fig:018 width=70%}

Проверим результат пары admin-password во вкладке Response, теперь нас перенаправляет на страницу index.php, значит пара должна быть верной (рис. [-@fig:019]).

![Результат запроса](image/19.jpg){#fig:019 width=70%}

Дополнительная проверка с использованием Repeater, нажимаем на нужный нам запрос правой кнопкой мыши и жмем "Send to Repeater" (рис. [-@fig:020]).

![Дополнительная проверка результата](image/20.jpg){#fig:020 width=70%}

Переходим во вкладку "Repeater" (рис. [-@fig:021]).

![Вкладка Repeater](image/21.jpg){#fig:021 width=70%}

Нажимаем "send", получаем в Response в результат перенаправление на index.php (рис. [-@fig:022]).

![Окно Response](image/22.jpg){#fig:022 width=70%}

После нажатия на `Follow redirection`, получим нескомпилированный html код в окне Response (рис. [-@fig:023]).

![Изменение в окне Response](image/23.jpg){#fig:023 width=70%}

Далее в подокне Render получим то, как выглядит полученная страница (рис. [-@fig:024]).

![Полученная страница](image/24.jpg){#fig:024 width=70%}

# Выводы

При выполнении лабораторной работы научилась использовать инструмент Burp Suite.

# Список литературы{.unnumbered}

[1] Документация по Virtual Box: https://www.virtualbox.org/wiki/Documentation

[2] Парасрам, Ш. Kali Linux: Тестирование на проникновение и безопасность : Для профессионалов. Kali Linux / Ш. Парасрам, А. Замм, Т. Хериянто, и др. – Санкт-Петербург : Питер, 2022. – 448 сс
