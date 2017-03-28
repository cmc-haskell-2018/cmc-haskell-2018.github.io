<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css">

## Программирование на языке Haskell

Haskell — это чистый функциональный язык программирования общего назначения.

В рамках этого курса Вы познакомитесь с его основами и научитесь создавать полноценные функциональные приложения!

### Лекции

Все лекции доступны для просмотра [на YouTube](https://www.youtube.com/playlist?list=PLov3NSwpY86cfkfXyVroSZkHemxoAdnrd):

- Лекция 1
    1. [<i class="fa fa-lg fa-youtube-play"></i> Функции высшего порядка.](https://youtu.be/jNQVa5INdDk)
    2. [<i class="fa fa-lg fa-youtube-play"></i> Свойства полиморфных функций.](https://youtu.be/41x5ZihxpOI)
- Лекция 2
    1. [<i class="fa fa-lg fa-youtube-play"></i> Ленивые вычисления.](https://youtu.be/MUfncxhDZK0)
    2. [<i class="fa fa-lg fa-youtube-play"></i> Функции над списками. Свёртки.](https://youtu.be/AwiOOkzZB_o)
- Лекция 3
    1. [<i class="fa fa-lg fa-youtube-play"></i> Алгебраические типы данных.](https://youtu.be/A9XX9Wv0faY)
    2. [<i class="fa fa-lg fa-youtube-play"></i> Классы типов.](https://youtu.be/efwK257k47o)
    3. [<i class="fa fa-lg fa-youtube-play"></i> Функторы.](https://youtu.be/k0nltRK0MUE)
- Лекция 4
    1. [<i class="fa fa-lg fa-youtube-play"></i> Моноиды.](https://youtu.be/C0uRL-CMk1Q)
    2. [<i class="fa fa-lg fa-youtube-play"></i> Моноидная свёртка.](https://youtu.be/JOYh5ngQzxU)
- Лекция 5
    1. [<i class="fa fa-lg fa-youtube-play"></i> Аппликативные функторы.](https://youtu.be/ckp60IxNH9s)
- Лекция 6
    1. [<i class="fa fa-lg fa-lock"></i> Обход структур.](https://youtu.be/ckp60IxNH9s)
- Лекция 7
    1. [<i class="fa fa-lg fa-lock"></i> Альтернативы.](https://youtu.be/ckp60IxNH9s)
- Лекция 8
    1. [<i class="fa fa-lg fa-lock"></i> Монады.](https://youtu.be/ckp60IxNH9s)
- Новые лекции уже на подходе!

### Практические задания

Сроки этапов сдачи практического задания на Haskell:

- Базовая (общая) часть:
    - **28 марта** — основные типы и функции (только сигнатуры);
    - **4 апреля** — реализация основных функций;
    - **11 апреля** — рабочее приложение.
- Индивидуальная часть:
    - **25 апреля** — основные типы и функции (только сигнатуры);
    - **9 мая** — завершённый функционал.

Методические указания и варианты доступны на [странице практических заданий](projects/README#практические-задания).

### Оценка

Оценка по практикуму зависит от набранного за семестр суммарного количества баллов.
Баллы начисляются за:

- работу в семестре на семинарах;
- выполнение практического задания на Лиспе;
- выполнение практического задания на Haskell.

Все результаты будут внесены в таблицу
[<i class="fa fa-lg fa-table"></i> Лисп и Haskell 2017](https://docs.google.com/spreadsheets/d/1uvXnqGwpSHLpRe5zZwvSFipsWZkbvU9HE3U6E-vTjH4/edit?usp=sharing).

### Haskell Platform

Для работы с Haskell в этом семестре рекомендуется [установить Haskell Platform](https://www.haskell.org/platform/) с официального сайта языка.
На сайте есть инструкции по установке для каждой платформы (Linux, macOS, Windows). Haskell Platform содержит следующие инструменты:

- компилятор GHC;
- система сборки Cabal;
- [утилита Stack](http://docs.haskellstack.org/) для разработки проектов;
- стандартные и часто-используемые библиотеки.

#### Интерпретатор GHCi

Для работы с небольшими программами рекомендуется использовать интерпретатор GHCi.
Чтобы запустить его наберите команду `ghci`. Здесь вы можете определять функции, типы и играться с данными:

```
>>> type Offset = Float
>>> let offsets = [0, 200 ..]
>>> take 10 offsets
[0,200,400,600,800,1000,1200,1400,1600,1800]
>>> :t take
take :: Int -> [a] -> [a]
```

Чтобы загрузить типы и функции из файла, используйте команду `:load`:

```
>>> :load /path/to/your/file.hs
```

Если вы работаете с проектом Stack, используйте `stack ghci` из корня проекта, чтобы автоматически
подгрузить все модули этого проекта. Например, для проекта [`demo-galaxies`](https://github.com/cmc-haskell-2017/demo-galaxies):

```
cd demo-galaxies
stack ghci
>>> massCenter [Particle 1 (0, 0) (0, 0), Particle 2 (3, 3) (0, 0)]
(2.0,2.0)
```

### Контакты

Вопросы по лекциям?
Проблема с выполнением практического задания?
Просто хочется обсудить Haskell или функциональное программирование?
**Пишите!**

Общие группы:

- [<i class="fa fa-lg fa-envelope"></i> cmc-haskell-2017@googlegroups.com](https://groups.google.com/d/forum/cmc-haskell-2017) — список рассылки курса;
- [<i class="fa fa-lg fa-telegram"></i> Haskell 2017](https://telegram.me/joinchat/AAAAAAz6vbLO35c7VmG7pQ) — группа в Telegram;
- [<i class="fa fa-lg fa-github"></i> cmc-haskell-2017](https://github.com/cmc-haskell-2017) — материалы курса и практические задания.

Контакты преподавателя:

- [<i class="fa fa-lg fa-envelope"></i> nickolay.kudasov@gmail.com](mailto:nickolay.kudasov@gmail.com);
- [<i class="fa fa-lg fa-telegram"></i> fizruk31337](http://t.me/fizruk31337);
- [<i class="fa fa-lg fa-github"></i> fizruk](https://github.com/fizruk).
