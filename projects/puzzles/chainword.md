---
title: Чайнворд — Haskell 2018
---

Чайнворд
========

Описание
--------

Чайнворд — это разновидность кроссворда, где слова составляют единую цепочку.
Каждое следующее слово начинается с последней буквы предыдущего слова.

![Спиральное расположение.](images/chainword_spiral.jpg){:width="40%"}
![Расположение лабиринтом.](images/chainword_maze.jpg){:width="40%"}

Минимальные требования (базовая часть)
--------------------------------------

Базовая реализация проекта, в которой должны разбираться все участники, должна включать:

- интерфейс для разгадывания чайнворда (чайнворд + описания слов);
- загрузку головоломки из файла.

Расширенный интерфейс (индивидуальная часть)
--------------------------------------------

Расширенный интерфейс должен добавлять хотя бы 2 различные возможности к базовому интерфейсу.
Ниже перечислены возможные варианты расширения интерфейса, однако этим списком они не ограничены:

- показ верно угаданных слов;
- меню генерации чайнворда:
  - словарь;
  - сложность (например, количество слов);
  - вариант расположения (например, спираль, змейкой, лабиринтом, и т.д.)
- подсказки (показать одну букву);
- таймер решения головоломки;
- просмотр таблицы рекордов;
- интерфейс сохранения/загрузки игр;
- альтернативные способы отображения чайнворда (многоугольники, круги, спирали и пр.);
- редактор головоломок;
- и т.д.

Генерация головоломок (индивидуальная часть)
--------------------------------------------

Генератор головоломок должен:

- использовать для генерации как минимум два параметра из трёх:
  - словари;
  - схемы расположения цепочки слов;
  - уровни сложности.
- по возможности, предоставлять равномерное распределение вероятности попадания слова из словаря в головоломку.

Выбор из нескольких заранее подготовленных головоломок не считается генерацией.

Работа с базой данных (индивидуальная часть)
--------------------------------------------

Модуль для работы с базой данных должен предоставлять хотя бы 2 различных возможности:

- таблица рекордов;
- сохранения игровых сессий;
- база головоломок;
- и т.д.

