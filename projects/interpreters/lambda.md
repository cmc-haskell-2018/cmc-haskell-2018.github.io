---
title: λ-исчисление — Haskell 2017
---

<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# $$\lambda$$-исчисление

Описание
--------

$$\lambda$$-исчисление (лямбда-исчисление) лежит в основе большинства функциональных языков программирования:
семейства Лиспа (Common Lisp, Scheme, Clojure и др.) и семейства ML (Standard ML, Haskell, Agda и пр.).

$$\lambda$$-исчисление состоит из языка $$\lambda$$-выражений и набора правил преобразования.
Базовые правила построения $$\lambda$$-выражений:

- переменная $$x$$ является $$\lambda$$-выражением;
- если $$e$$ — $$\lambda$$-выражение, а $$x$$ — переменная, то $$(\lambda x.\; e)$$ также $$\lambda$$-выражение (**лямбда-абстракция**);
- если $$e_1$$ и $$e_2$$ — $$\lambda$$-выражения, то $$(e_1\;e_2)$$ также $$\lambda$$-выражение (**аппликация**).

Для удобства работы с $$\lambda$$-выражениями, при записи могут использоваться следующие упрощения:

внешние скобки могут быть опущены
: $$(\lambda x.\; e_1)\;e_2$$;

аппликация считается лево-ассоциативной
: $$e_1\;e_2\;e_3 \equiv ((e_1\;e_2)\;e_3)$$;

тело $$\lambda$$-выражения распространяется вправо насколько возможно
: $$\lambda x.\; e_1\;e_2 \equiv \lambda x.\; (e_1\;e_2)$$;

последовательные $$\lambda$$-абстракции схлопываются в одну
: $$\lambda x.\; \lambda y.\; \lambda z.\; e \equiv \lambda x\;y\;z.\; e$$.

Оператор $$\lambda$$ *связывает* переменную в выражении $$\lambda x.\;e$$. Переменные, подпадающие под какой-либо
оператор $$\lambda$$-абстракции, называются *связанными*. Все прочие переменные называются *свободными*.
Например, переменная $$y$$ свободна в выражении $$\lambda x.\;y\;x$$. Переменная связывается *ближайшим* оператором $$\lambda$$.
Например, единственное вхождение переменной $$x$$ в выражении $$\lambda x.\;y\;(\lambda x.\;x)$$ связано со вторым оператором
$$\lambda$$.

Значение $$\lambda$$-выражения определяется правилами редукции:

$$\alpha$$-**конверсия**
: переименовывание связанных переменных

$$\beta$$-**редукция**
: применение функции к аргументам

$$\eta$$-**конверсия**
: выражает принцип *две функции идентичны, если имеют одинаковый результат на всех входах*

Применение функции к аргументам осуществляется засчёт подстановки выражения-аргумента
вместо связанной переменной в теле $$\lambda$$-выражения:

$$
   \begin{aligned}
     x[x \mapsto e] & \equiv e \\
     y[x \mapsto e] & \equiv y, \text{если $y \neq x$} \\
     (e_1\;e_2) [x \mapsto e] & \equiv (e_1 [x \mapsto e])\;(e_2 [x \mapsto e]) \\
     (\lambda x.\;e_1) [x \mapsto e] & \equiv \lambda x.\;e_1 \\
     (\lambda y.\;e_1) [x \mapsto e] & \equiv \lambda y.\;(e_1 [x \mapsto e]), \text{если $y \neq x$ и $y$ не входит свободно в $e$}
   \end{aligned}
$$

Язык $$\lambda$$-выражений может быть расширен:

- базовыми типами данных (например, числа, булевы значения, строки);
- базовыми контейнерными типами (списки и кортежи);
- встроенными операциями (например, $$+$$, $$-$$, $$\sin$$, $$\cos$$, $$and$$, $$or$$, $$++$$)
- специальными конструкциями (например, $$if \ldots then \ldots else \ldots$$ или $$let \ldots = \ldots in \ldots$$);
- системой типов;
- пользовательские структуры данных;
- и т.д.

Минимальные требования (базовая часть)
--------------------------------------

Базовая реализация проекта, в которой должны разбираться все участники, должна:

- определять структуру данных для синтаксического дерева;
- содержать раздельно парсер и интерпретатор (с любой стратегией редукций);
- предоставлять простую интерактивную среду программирования (REPL).

Расширенный парсер (индивидуальная часть)
-----------------------------------------

Расширенный парсер должен добавлять хотя бы 2 различные возможности к базовому варианту.
Ниже перечислены возможные варианты расширения парсера, однако этим списком они не ограничены:

- разбор расширенного $$\lambda$$-исчисления;
- восстановление после ошибок (например, если пользователь написал запятую (``,``) вместо точки (``.``),
  парсер может запомнить эту ошибку и продолжить разбор программы);
- поддержка пользовательских инфиксных операций с возможностью задать приоритет и ассоциативность;
- и т.д.

Система типов (индивидуальная часть)
------------------------------------

Система типов помогает определить семантику $$\lambda$$-выражений, но также может быть использована
для оптимизаций при интерпретации и генерации кода.

Система типов должна поддерживать хотя бы 2 различные возможности:

- базовые типы (числа, булев тип, строки);
- контейнерные типы (списки, кортежи, суммы);
- параметрический полиморфизм;
- пользовательские типы данных;
- механизм автоматического вывода типа для терма;
- и т.д.

Расширенная интерактивная среда (индивидуальная часть)
------------------------------------------------------

Расширенная интерактивная среда должна добавлять хотя бы 2 различные возможности к базовому интерфейсу.
Ниже перечислены возможные варианты расширения интерактивной среды, однако этим списком они не ограничены:

- команды интерпретатора:
  - показать все возможные варианты редукции терма (одного шага) и выбрать один;
  - показать тип выражения;
  - поменять порядок редукции;
  - перевести терм из/в кодировку Чёрча;
  - загрузить программу из файла;
- интерпретация расширенного $$\lambda$$-исчисления;
- дружелюбные сообщения об ошибках (например, для замкнутых термов при опечатке в имени переменной
  можно предложить имена переменных, отличающихся одной буквой, которые находятся в области видимости);
- и т.д.

Генерация кода (индивидуальная часть)
-------------------------------------

Модуль генерации кода — предпоследний этап компиляции.
Генерация кода может быть реализована многими способами, но чтобы простым
образом получить портируемый компилятор, можно генерировать промежуточный код
на низкоуровневом языке программирования, таком как C или еще ниже, например, LLVM.

Генерация кода должна переводить именованные $$\lambda$$-термы в соответствующие функции
(для этого язык должен быть расширен возможностью именования $$\lambda$$-термов).

Демонстрация генерации кода должна включать в себя программу на любом языке,
использующую сгененированный объектный код при сборке.
