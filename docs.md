# FuncBolon💉

FuncBolon - это функциональный язык программирования, основанный на языке F#. Вот краткое руководство по работе с некоторыми из основных конструкций FuncBolon:

## Типы данных

В языке 💉FuncBolon💉 на момент версии 0.01 существуют следующие типы данны:

* `int` - целочисленный тип

```
hormone testosterone_mg_weekly = 1000
hormone negative_int_test = -567
```

* `boolean` - логический тип

```
hormone is_injecting_hgh = true
hormone has_completed_doping_test = false
```

* `string` - строковый тип

```
hormone favourite_excercise = "bench press"
hormone empty_string_test = ""
```

* `list` - список из любых типов данных

```
hormone list_test = [5,-2,56,true,"dummy"]
```

в FuncBolon динамическая типизация → парсер сам определит используемый тип данных и отдаст его интерпретатору

## Лямбда-выражения (анонимные функции): ключевое слово `injection`

Ключевое слово `injection`  используется для определения лямбда-выражения, то есть анонимной функции.

```
injection (pa,ra,me,ters) {expression}
```

Выражение — это тело функции, последнее выражение которого создает возвращаемое значение. Ниже приведены примеры допустимых лямбда-выражений:

```
injection (x) {x + 1}
injection (a,b,c) {a*b*c}
injection (x,y,gdffgh) {x}
```

Лямбды часто используются c короткими выражениями, когда не хочется определять функцию только для этого выражения. Это особенно часто встречается в операциях со списками.

## Переменные

Ключевое слово `hormone` используется для привязки имени к значению или функции.

Простейшая форма `hormone` выражения привязывает имя к простому значению, как показано ниже.

```
hormone x = 5
hormone x = false
hormone x = "dummy"
```

Также можно привязывать выражения 

```
hormone x =  ((((5+3)-4)*6)/3)
```

И функции

```
hormone fun = injection (x,y,gdffgh) {x}
```

## Операторы

В исходном коде языка FuncBolon💉💉💉 допустимые операторы выглядят следующим образом:

```
let buildinFuncArgs = function
    | "||" -> 2 // логическое ИЛИ 
    | "&&" -> 2 // логическое И
    | "<|" -> 2 // прибавление правой строки к левой строке
    | "?" -> 2 // лексикографическое сравнение двух строк
    | "!" -> 1 // логическое НЕ
    | "+" -> 2 // арифметическое сложение двух чисел
    | "-" -> 2 // арифметическое вычитание двух чисел
    | "*" -> 2 // арифметическое умножение двух чисел
    | "/" -> 2 // арифметическое целочисленное деление двух чисел
    | "==" -> 2 // оператор сравнения двух чисел (равно)
    | ">" -> 2 // оператор сравнения двух чисел (больше)
    | ">=" -> 2 // оператор сравнения двух чисел (больше или равно)
    | "<" -> 2 // оператор сравнения двух чисел (меньше)
    | "<=" -> 2 // оператор сравнения двух чисел (меньше или равно)
    | "&" -> 2 // конкатенация двух списков
    | "$" -> 1 // первый элемент списка
    | "#" -> 1 // хвост списка (всё, кроме первого элемента)
    | "-=-" -> 2 // сравнение двух списков поэлементно
```

## Условные выражения: if...{}...{}

Выражение `if...{}...{}` выполняет различные ветви кода, а также вычисляет другое значение в зависимости от логического выражения.

### Синтаксис

```
if (boolean-expression) {expression1} {expression2}
```

Для пояснения будем использовать следующий пример:

```
if (!(("dumm" <| "y") ? "dummy")) {
    true
}
{
    false
}
```

Данная конструкция используется для условного выполнения кода. На входе выражение в скобках обязательно должно возвращать тип `boolean`. Если вернулось выражение, равно `true`, то будет выполнен код в первых скобах, иначе - во вторых

`if...{}...{}` можно вкладывать друг в друга - код будет выполяться последовательно

## Аппликация (применение выражений)

В языке 💉FuncBolon💉 для применения выражений используется ключевое слово `execute`

### Синтаксис

Базовый синтаксис применения выражения к набору параметров pa,ra,me,ters будет выглядеть следующим образом:

```
execute hormone/injection pa,ra,me,ters
```

где hormone/injection - это либо название переменной, либо лямбда

### Пример 1

```
execute injection (x,y,z) {((x+y)/z)} 5,5,(1+1)
```

В данном примере вычисляется выражение (x+y)/z, где вместо x,y,z будут подставлены 5,5,(1+1) соответственно

### Пример 2

```
hormone fun = injection (x,y,z) {((x+y)/z)}
execute fun  5,5,(1+1)
```

В данном примере вычисляется то же выражение с теми же переменными, что и в первом примере, но вместо лямбы используется функция