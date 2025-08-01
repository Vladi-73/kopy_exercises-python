
В этом уроке разберем, какие параметры существуют, чем они отличаются и в каких случаях их применять.

**Аргументы** — это данные, которые передаются в вызов функции. Они бывают двух типов:

Первый тип — **позиционные аргументы**. Они передаются в том же порядке, в котором определены параметры функции:

```python
# (text, length)
truncate('My Text', 3)
```

Второй тип — **именованные аргументы**. Они передаются не просто как значения, а как пара «имя=значение». Поэтому их можно передавать в любом порядке:

```python
# Аргументы переданы в другом порядке
truncate(length=3, text='My Text')
```

Если внимательно посмотреть на два примера выше, то можно понять, что это две одинаковые функции.

Теперь разберемся, в каких случаях нужно применять эти типы аргументов.

Выбор типа параметра зависит от того, кто вызывает функцию.

Есть две причины использовать именованные аргументы:

* Они повышают читаемость, так как сразу видно имена

* Можно не указывать все промежуточные параметры, которые нам сейчас не нужны

Последнее полезно, если у функции много необязательных параметров. Посмотрим на примере:

```python
def print_params(a=1, b=2, c=3, d=4):
    print(a, b, c, d)

# Нужно передать только d, но приходится передавать все
f(1, 2, 3, 8)

# Именованные аргументы позволяют передавать только d
# Для остальных аргументов используются значения по умолчанию
f(d=8)
```

Именованные аргументы можно передавать одновременно с позиционными. Тогда позиционные должны идти в самом начале:

```python
# Передаем только a (позиционно) и d (как именованный)
f(3, d=3)
```
