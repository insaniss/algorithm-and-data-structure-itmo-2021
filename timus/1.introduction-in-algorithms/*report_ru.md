# Введение в алгоритмы

## Куча камней

|||
| :---                | :---              |
| Ограничение времени | 1 секунда         |
| Ограничение памяти  | 64Mb              |
| Ввод                | стандартный ввод  |
| Вывод               | стандартный вывод |

У вас есть несколько камней известного веса `w_1`, ..., `w_n`. Напишите программу,
которая распределит камни в две кучи так, что разность весов этих двух куч будет
минимальной.

#### Формат ввода

Ввод содержит количество камней `n` (`1 ≤ n ≤ 20`) и веса камней `w_1`, ..., `w_n` 
(`1 ≤ w_i ≤ 100 000`) — целые, разделённые пробельными символами.

#### Формат вывода

Ваша программа должна вывести одно число — минимальную разность весов двух куч.

#### Пример

``` cpp
IN                                          OUT

5                                           3
5 8 13 27 14
```

## Гиперпереход

|||
| :---                | :---              |
| Ограничение времени | 1 секунда         |
| Ограничение памяти  | 64Mb              |
| Ввод                | стандартный ввод  |
| Вывод               | стандартный вывод |

Гиперпереход, открытый ещё в начале `XXI`-го века, и сейчас остаётся основным способом
перемещения на расстояния до сотен тысяч парсеков. Но совсем недавно физиками открыто
новое явление. Оказывается, длительностью альфа-фазы перехода можно легко управлять.
Корабль, находящийся в альфа-фазе перехода, накапливает гравитационный потенциал. Чем
больше накопленный гравитационный потенциал корабля, тем меньше энергии потребуется ему
на прыжок сквозь пространство. Ваша цель — написать программу, которая позволит кораблю
за счёт выбора времени начала альфа-фазы и её длительности накопить максимальный
гравитационный потенциал.

В самой грубой модели грави-интенсивность — это последовательность целых чисел `p_i`. Будем
считать, что если альфа-фаза началась в момент `i` и закончилась в момент `j`, то накопленный
в течение альфа-фазы потенциал — это сумма всех чисел, стоящих в последовательности на местах
от `i` до `j`.

#### Формат ввода

В первой строке входа записано целое число `N` — длина последовательности, отвечающей за
грави-интенсивность (`0 ≤ N ≤ 60000`). Далее идут `N` строк, в каждой записано целое число
`p_i` (`−30000 ≤ p_i ≤ 30000`).

#### Формат вывода

Максимальный гравитационный потенциал, который может накопить корабль в альфа-фазе прыжка.
Считается, что потенциал корабля в начальный момент времени равен нулю.

#### Пример 1

``` cpp
IN                                          OUT

10                                          187
31
-41
59
26
-53
58
97
-93
-23
84
```

#### Пример 2

``` cpp
IN                                          OUT
3                                           0
-1
-5
-6
```