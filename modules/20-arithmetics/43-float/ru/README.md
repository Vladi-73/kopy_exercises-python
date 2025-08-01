В математике есть разные типы чисел. Например:

- Натуральные — целые положительные числа: 1, 2, 3 и т.д.
- Рациональные — дробные числа, которые можно представить в виде деления, например: 0.5, 1.75, 3.14.

С точки зрения математики — всё просто. Но с точки зрения компьютера между этими типами чисел — настоящая пропасть. Попробуйте мысленно решить: Сколько будет `0.2` + `0.1`? Очевидно, `0.3`. А вот что скажет Python:

```python
print(0.2 + 0.1)  # => 0.30000000000000004
```

❗Вместо привычных 0.3 мы получаем 0.30000000000000004.

## Почему так происходит?

Это не ошибка Python. Такое поведение можно наблюдать и в JavaScript, и в C++, и в большинстве языков программирования.

Причина в устройстве компьютера. Компьютер работает с ограниченной памятью, а рациональные числа — бесконечно точные. Между 0.1 и 0.2 можно поместить бесконечно много других чисел. Но компьютер не может хранить бесконечность. Он приближает число, стараясь уместить его в доступное количество бит.

Такие приближённые значения называются числами с плавающей точкой (floating point numbers). Хранение и вычисления с ними подчиняются строгим правилам. Эти правила описаны в специальном стандарте IEEE 754 — именно на него ориентируются большинство языков программирования.

## Когда появляются такие числа

Числа с плавающей точкой появляются в программах чаще, чем может показаться. Вот основные случаи:

- Когда вы явно пишете дробное число — например, 0.1, 2.5, 3.14.
- Когда выполняете деление — даже если делите два целых числа:

```python
print(1 / 2)  # => 0.5
print(2 / 3)  # => 0.6666666666666666
```

Даже если результат кажется "красивым", внутри он всё равно представлен в виде приближённого значения. Некоторые дроби, такие как 1 / 3, вообще не могут быть точно представлены в двоичной системе, поэтому их точность всегда ограничена.

## Что нужно запомнить

- Операции с числами с плавающей точкой не всегда точны. Это нормально. Это не баг, а особенность архитектуры.
- Точность можно контролировать. Например, с помощью округления или сравнения чисел с заданной погрешностью.
- Будьте осторожны, если работаете с деньгами, точными измерениями или научными расчётами — в таких случаях лучше использовать специальные типы данных, которые обеспечивают контроль над точностью.
