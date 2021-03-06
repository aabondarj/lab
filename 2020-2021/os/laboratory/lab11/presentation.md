---
## Front matter
lang: ru-RU
title: Лабораторная работа №11
author: |
	Бондарь Алексей Олегович НПМбд-01-20\inst{1}
institute: |
	\inst{1}RUDN University, Moscow, Russian Federation
	
date:  10 мая, 2021, Москва, Россия

## Formatting
toc: false
slide_level: 2
theme: metropolis
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true
---

# Цель работы

Изучить основы программирования в оболочке ОС UNIX/Linux. Научиться писать небольшие командные файлы.



# Выполнение лабораторной работы

Для начала я изучил команды архивации, используя команды «man
zip», «man bzip2», «man tar».(рис. -@fig:001) , (рис. -@fig:002) , (рис. -@fig:003) , (рис. -@fig:004)

![Просмотр](image/1.png){ #fig:001 width=70% }

## Выполнение лабораторной работы

Синтаксис команды zip для архивации файла:
zip [опции] [имя файла.zip] [файлы или папки, которые будем архивировать]
Синтаксис команды zip для разархивации/распаковки файла: unzip [опции] [файл_архива.zip] [файлы] -x [исключить] -d [папка]

![man zip](image/2.png){ #fig:002 width=50% }

## Выполнение лабораторной работы

Синтаксис команды bzip2 для архивации файла:
bzip2 [опции] [имена файлов]
Синтаксис команды bzip2 для разархивации/распаковки файла:
bunzip2 [опции] [архивы.bz2]

![man bzip2](image/3.png){ #fig:003 width=50% }

## Выполнение лабораторной работы

Синтаксис команды tar для архивации файла:
tar [опции] [архив.tar] [файлы_для_архивации]
Синтаксис команды tar для разархивации/распаковки файла:
tar [опции] [архив.tar]

![man tar](image/4.png){ #fig:004 width=50% }

## Выполнение лабораторной работы

Далее я создал файл, в котором буду писать первый скрипт, и открыл
его в редакторе emacs, используя клавиши «Ctrl-x» и «Ctrl-f» (команды
«touch backup.sh» и «emacs &»).(рис. -@fig:005)

![Создание файла backup.sh](image/5.png){ #fig:005 width=70% }

## Выполнение лабораторной работы

После написал скрипт, который при запуске будет делать резервную копию самого себя (то есть файла, в котором содержится его исходный код) в другую директорию backup в вашем домашнем каталоге. При этом файл должен архивироваться одним из архиваторов на выбор zip, bzip2 или tar (рис. -@fig:006). При написании скрипта использовал архиватор bzip2.

![Создание файла](image/6.png){ #fig:006 width=70% }

## Выполнение лабораторной работы

Проверил работу скрипта (команда «./backup.sh»), предварительно добавив для него право на выполнение (команда «chmod +x *.sh»). Проверил, появился ли каталог backup/, перейдя в него (команда «cd backup/»), посмотрела его содержимое (команда «ls») и просмотрел содержимое архива (команда «bunzip2 -c backup.sh.bz2») (рис. -@fig:007) и (рис. -@fig:008). Скрипт работает корректно.

![Проверка](image/7.png){ #fig:007 width=70% }

## Выполнение лабораторной работы

 
![Разархивирование](image/8.png){ #fig:008 width=70% }

## Выполнение лабораторной работы

Создал файл, в котором буду писать второй скрипт, и открыл его в редакторе emacs, используя клавиши «Ctrl-x» и «Ctrl-f» (команды «touch prog2.sh» и «emacs &»).(рис. -@fig:009)

![Создание файла](image/9.png){ #fig:009 width=70% }

## Выполнение лабораторной работы

Написал пример командного файла, обрабатывающего любое произвольное число аргументов командной строки, в том числе превышающее десять. Например, скрипт может последовательно распечатывать значения всех переданных аргументов.(рис. -@fig:010)

![Пример командного файла](image/10.png){ #fig:010 width=70% }

## Выполнение лабораторной работы

Проверил работу написанного скрипта (команды «./prog2.sh 0 1 2 3 4» и «./prog2.sh 0 1 2 3 4 5 6 7 8 9 10 11»), предварительно добавив для него право на выполнение (команда «chmod +x *.sh»). Вводил аргументы, количество которых меньше 10 и больше 10.(рис. -@fig:011)

## Выполнение лабораторной работы

![Проверка](image/11.png){ #fig:011 width=70% }

## Выполнение лабораторной работы

Создал файл, в котором буду писать третий скрипт, и открыл его в редакторе emacs, используя клавиши «Ctrl-x» и «Ctrl-f» (команды «touch progls.sh» и «emacs &»).(рис. -@fig:012)

![Создание файла](image/12.png){ #fig:012 width=70% }

## Выполнение лабораторной работы

Написал командный файл − аналог команды ls (без использования самой этой команды и команды dir). Он должен выдавать информациюо нужном каталоге и выводить информацию о возможностях доступа к файлам этого каталога.(рис. -@fig:013)

## Выполнение лабораторной работы

![Пример командного файла](image/13.png){ #fig:013 width=70% }

## Выполнение лабораторной работы

Далее проверил работу скрипта (команда «./progls.sh ~»), предварительно добавив для него право на выполнение (команда «chmod +x *.sh») (рис. -@fig:014).
Скрипт работает корректно.

## Выполнение лабораторной работы

![Проверка](image/14.png){ #fig:014 width=70% }

## Выполнение лабораторной работы

Для четвертого скрипта также создал файл (команда «touchformat.sh») и открыл его в редакторе emacs, используя клавиши «Ctrl-x» и «Ctrl-f» (команда «emacs &»).(рис. -@fig:015)

![Создание файла](image/15.png){ #fig:015 width=70% }

## Выполнение лабораторной работы

Написал командный файл, который получает в качестве аргумента командной строки формат файла (.txt, .doc, .jpg, .pdf и т.д.) и вычисляет количество таких файлов в указанной директории. Путь к директории также передаётся в виде аргумента командной строки (рис. -@fig:016)

## Выполнение лабораторной работы

![Пример командного файла](image/16.png){ #fig:016 width=70% }

## Выполнение лабораторной работы

Проверил работу написанного скрипта (команда «./format.sh ~ pdf sh txt doc»), предварительно добавив для него право на выполнение (команда «chmod +x *.sh»), а также создав дополнительные файлы с разными расширениями (команда «touch file.pdf file1.doc file2.doc») (рис. -@fig:017).
Скрипт работает корректно.

## Выполнение лабораторной работы

![Проверка](image/17.png){ #fig:017 width=70% }


## Выводы

В ходе выполнения данной лабораторной работы я изучил основы программирования  в  оболочке  ОС UNIX/Linuxи  научился писать небольшие командные файлы.

