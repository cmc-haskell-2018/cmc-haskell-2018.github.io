<link rel="stylesheet" href="//maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css">

## Программирование на языке Haskell

Haskell — это чистый функциональный язык программирования общего назначения.

В рамках этого курса Вы познакомитесь с его основами и научитесь создавать полноценные функциональные приложения!

### Материалы курса

Данный курс состоит из видео-лекций, семинаров и семестрового практического задания.

#### Лекции

Все лекции доступны для просмотра [на YouTube](https://www.youtube.com/playlist?list=PLov3NSwpY86cfkfXyVroSZkHemxoAdnrd):

- [<i class="fa fa-fw fa-lg fa-youtube-play"></i> Функции высшего порядка.](https://youtu.be/jNQVa5INdDk)
- [<i class="fa fa-fw fa-lg fa-youtube-play"></i> Свойства полиморфных функций.](https://youtu.be/41x5ZihxpOI)
- [<i class="fa fa-fw fa-lg fa-youtube-play"></i> Ленивые вычисления.](https://youtu.be/MUfncxhDZK0)
- [<i class="fa fa-fw fa-lg fa-youtube-play"></i> Функции над списками. Свёртки.](https://youtu.be/AwiOOkzZB_o)
- [<i class="fa fa-fw fa-lg fa-youtube-play"></i> Алгебраические типы данных.](https://youtu.be/A9XX9Wv0faY)
- [<i class="fa fa-fw fa-lg fa-youtube-play"></i> Классы типов.](https://youtu.be/efwK257k47o)
- [<i class="fa fa-fw fa-lg fa-youtube-play"></i> Функторы.](https://youtu.be/k0nltRK0MUE)
- [<i class="fa fa-fw fa-lg fa-youtube-play"></i> Моноиды.](https://youtu.be/C0uRL-CMk1Q)
- [<i class="fa fa-fw fa-lg fa-youtube-play"></i> Моноидная свёртка.](https://youtu.be/JOYh5ngQzxU)
- [<i class="fa fa-fw fa-lg fa-youtube-play"></i> Аппликативные функторы.](https://youtu.be/ckp60IxNH9s)

#### Семинары

Материалы семинаров доступны в
[репозитории <i class="fa fa-lg fa-github"></i> cmc-haskell-2018/seminars](https://github.com/cmc-haskell-2018/seminars).

#### Практическое задание

Предварительные сроки этапов сдачи практического задания на Haskell:

- Базовая (общая) часть:
    - **13 марта** — основные типы и функции (только сигнатуры);
    - **20 марта** — реализация основных функций;
    - **3 апреля** — рабочее приложение.
- Индивидуальная часть:
    - **17 апреля** — основные типы и функции (только сигнатуры);
    - **1 мая** — завершённый функционал.

Методические указания и варианты доступны на [странице практических заданий](projects/README#практические-задания).

### Оценка

Оценка по практикуму зависит от набранного за семестр суммарного количества баллов.
Баллы начисляются за:

- работу в семестре на семинарах;
- выполнение практического задания на Haskell.

Все результаты будут внесены в таблицу
[<i class="fa fa-lg fa-table"></i> Haskell 2018](https://docs.google.com/spreadsheets/d/1mkxvczZbjOfz7QAGA1r8LThVHCGTIJjwv2AHcllYKQ8/edit?usp=sharing).

### Haskell Platform

Для работы с Haskell в этом семестре рекомендуется [установить Haskell Platform](https://www.haskell.org/platform/) с официального сайта языка.
На сайте есть инструкции по установке для каждой платформы (Linux, macOS, Windows). Haskell Platform содержит следующие инструменты:

- компилятор GHC (версии 8.2.2);
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
подгрузить все модули этого проекта.

Например, для [<i class="fa fa-lg fa-github"></i> проекта `demo-galaxies`](https://github.com/cmc-haskell-2017/demo-galaxies):

```
cd demo-galaxies
stack ghci
>>> massCenter [Particle 1 (0, 0) (0, 0), Particle 2 (3, 3) (0, 0)]
(2.0,2.0)
```

### Дополнительные материалы

Недостаточно материалов в курсе? Хочется знать больше?
Ниже несколько источников знаний о Haskell, которые я рекомендую!
(если есть такая возможность, читайте материалы на английском языке)

- [Learn You a Haskell](http://learnyouahaskell.com/) —
  это позитивно и понятно изложенный материал, начиная с самых основ
  и заканчивая введением в интересные вещи.
- [Haskell Wikibook](https://en.wikibooks.org/wiki/Haskell) —
  нечто среднее между справочником и туториалом по языку Haskell.
  В книге содержатся статьи по базовым и продвинутым темам,
  включая структуры данных, теорию типов и статьи о производительности программ
  на Haskell.
- [Haskell Weekly](https://haskellweekly.news/) —
  еженедельная сводка новостей про то, что происходит в сообществе:
  здесь вы можете узнать о том, что нового происходит с языком,
  где он применяется, а также о ближайших событиях и даже вакансиях.
- [ruHaskell.org](https://ruhaskell.org) —
  сайт русскоязычного сообщества Haskell.
- [Functional pearls](https://wiki.haskell.org/Research_papers/Functional_pearls) —
  некоторые исключительно элегантные функциональные решения различных практических
  проблем, с использованием Haskell.

Существует также несколько книг и учебников о Haskell (как на английском, так и на русском).
Однако, по разным причинам, я не могу порекомендовать какую-либо из них.

### Контакты

Вопросы по лекциям?
Проблема с выполнением практического задания?
Просто хочется обсудить Haskell или функциональное программирование?
**Пишите!**

Общие группы:

- [<i class="fa fa-lg fa-envelope"></i> cmc-haskell-2018@googlegroups.com](https://groups.google.com/d/forum/cmc-haskell-2018) — список рассылки курса;
- [<i class="fa fa-lg fa-telegram"></i> Haskell 2018](https://telegram.me/joinchat/B8HofBJKpCsEI0YH78_XFw) — группа в Telegram;
- [<i class="fa fa-lg fa-github"></i> cmc-haskell-2018](https://github.com/cmc-haskell-2018) — материалы курса и практические задания.

Контакты преподавателя:

- [<i class="fa fa-lg fa-envelope"></i> nickolay.kudasov@gmail.com](mailto:nickolay.kudasov@gmail.com);
- [<i class="fa fa-lg fa-telegram"></i> fizruk31337](http://t.me/fizruk31337);
- [<i class="fa fa-lg fa-github"></i> fizruk](https://github.com/fizruk).
