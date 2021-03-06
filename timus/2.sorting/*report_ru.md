# Сортировка

## Шпион

|||
| :---                | :---              |
| Ограничение времени | 0.25 секунд       |
| Ограничение памяти  | 64Mb              |
| Ввод                | стандартный ввод  |
| Вывод               | стандартный вывод |

Спецслужбы обнаружили действующего иностранного агента. Шпиона то есть. Установили
наблюдение и выяснили, что каждую неделю он через Интернет посылает кому-то странные
нечитаемые тексты. Чтобы выяснить, к какой информации получил доступ шпион, требуется
расшифровать информацию. Сотрудники спецслужб проникли в квартиру разведчика, изучили
шифрующее устройство и выяснили принцип его работы.

На вход устройства подается строка текста S<sub>1</sub> = s<sub>1</sub>s<sub>2</sub>
...s<sub>N</sub>.Получив ее, устройство строит все циклические перестановки этой строки,
то есть S<sub>2</sub> = s<sub>2</sub>s<sub>3</sub>...s<sub>N</sub>s<sub>1</sub>, ...,
S<sub>N</sub> = s<sub>N</sub>s<sub>1</sub>s<sub>2</sub>...s<sub>N-1</sub>. Затем множество
строк S<sub>1</sub>, S<sub>2</sub>, ..., S<sub>N</sub> сортируется лексикографически по
возрастанию. И в этом порядке строчки выписываются в столбец, одна под другой. Получается
таблица размером `N × N`. В какой-то строке K этой таблицы находится исходное слово. Номер
этой строки вместе с последним столбцом устройство и выдает на выход.

Например, если исходное слово S<sub>1</sub> = abracadabra, то таблица имеет такой вид:

-   aabracadabr = S<sub>11</sub>
-   abraabracad = S<sub>8</sub>
-   abracadabra = S<sub>1</sub>
-   acadabraabr = S<sub>4</sub>
-   adabraabrac = S<sub>6</sub>
-   braabracada = S<sub>9</sub>
-   bracadabraa = S<sub>2</sub>
-   cadabraabra = S<sub>5</sub>
-   dabraabraca = S<sub>7</sub>
-   raabracadab = S<sub>10</sub>
-   racadabraab = S<sub>3</sub>

И результатом работы устройства является число `3` и строка rdarcaaaabb.

Это все, что известно про шифрующее устройство. А вот дешифрующего устройства не нашли.
Но поскольку заведомо известно, что декодировать информацию можно (а иначе зачем же ее
передавать?), Вам предложили помочь в борьбе с хищениями секретов и придумать алгоритм
для дешифровки сообщений. А заодно и реализовать дешифратор.

#### Формат ввода

В первой и второй строках находятся соответственно целое число и строка, возвращаемые 
шифратором. Длина строки и число не превосходят `100000`. Строка содержит лишь следующие
символы: `a-z`, `A-Z`, символ подчеркивания. Других символов в строке нет. Лексикографический
порядок на множестве слов задается таким порядком символов:

``` cpp
ABCDEFGHIJKLMNOPQRSTUVWXYZ_abcdefghijklmnopqrstuvwxyz
```

Символы здесь выписаны в порядке возрастания.

#### Формат вывода

Выведите декодированное сообщение в единственной строке.

#### Пример

``` cpp
IN                                          OUT

3                                           abracadabra
rdarcaaaabb
```

## В Стране Дураков

|||
| :---                | :---              |
| Ограничение времени | 1 секунда         |
| Ограничение памяти  | 64Mb              |
| Ввод                | стандартный ввод  |
| Вывод               | стандартный вывод |

Главный бульдог-полицейский Страны Дураков решил ввести ограничение скоростного режима на
автомобильной трассе, ведущей от Поля Чудес к пруду Черепахи Тортиллы. Для этого он заказал
у Папы Карло n знаков ограничения скорости. Папа Карло слабо разбирался в дорожном движении
и поэтому изготовил знаки с разными ограничениями на скорость: `49 км/ч`, `34 км/ч`, 
`42 км/ч`, и т.д. Всего получилось `k` различных ограничений: `n_1` знаков с одним ограничением,
`n2` знаков со вторым ограничением, и т.д. (`n_1 + … + n_k = n`)

Бульдог-полицейский ничуть не расстроился, получив такие знаки, напротив, он решил извлечь
из этого экономическую выгоду. Дело в том, что по Правилам дорожного движения Страны Дураков
ограничение на скорость действует вплоть до следующего знака. Если на знаке написано число
`60`, это означает, что участок от данного знака до следующего нужно проехать ровно со
скоростью `60` километров в час — не больше и не меньше. Бульдог распорядился расставить
знаки так, чтобы обогатившимся на Поле Чудес автолюбителям во время своего движения по
трассе приходилось как можно больше раз менять скорость. Для этого нужно расставить имеющиеся
знаки в правильном порядке. Если Вы поможете бульдогу это сделать, то он готов будет
поделиться с Вами частью своих доходов.

#### Формат ввода

В первой строке дано число `k` — количество различных типов знаков с ограничением скорости
(`1 ≤ k ≤ 10000`). Во второй строке через пробел перечислены целые положительные числа
`n_1`, …, `n_k`. Сумма всех ni не превосходит `10000`.

#### Формат вывода

Выведите `n` целых чисел в пределах от `1` до `k` — порядок, в котором нужно расставить по
трассе имеющиеся знаки. Вне зависимости от того, какой знак стоит первым, считается, что,
проезжая его, водитель меняет скорость, так как до этого ограничения не действовали. Если
задача имеет несколько решений, выведите любое.

#### Пример

``` cpp
IN                                          OUT

2                                           1 2 1 2
2 2
```
