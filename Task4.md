# Язык автоматов
## Синтаксиc состояния сериализованный объект
+ *id* -- целое число
+ Допустимое ли состояние? -- bool
+ обзателен массив перехода ( переход в виде пары):
  + first: условие перехода
  + second: куда переходит

***Итого:*** Состояние: {1, false, [{'2', 3}, {'3', 1}]} -- по номеру 1, недопускающее, по символу '2' переходит в состояние 3, по символу '3' в себя.
## Весь язык
Весь язык состоит из строки:
+ *{id}* начального состояния -- целое число
+ описание состояний, склееных в одну строку

## Примеры
### Четность кол-ва символов
Автомат определяет чётность количества символов в непустом слове над алфавитом **{a,b}**
+ **{1}{1, false, [{'a', 2}, {'b', 2}]}{2, false, [{'a', 3}, {'b', 3}]}{3, true, [{'a', 2}, {'b', 2}]}**

### Четность двоичного положительного числа
+ **{1}{1, false, [{'0', 1}, {'1', 2}]}{2, false, [{'0', 3}, {'1', 2}]}{3, true, [{'0', 3}, {'1', 2}]}**

### Проверка, что в слове над *{a,b}* чередуются символы 
+ **{1}{1, false, [{'a', 2}, {'b', 3}]}{2, true, [{'a', 4}, {'b', 3}]}{3, true, [{'a', 2}, {'b', 4}]}{4, false, [{'a', 4}, {'b', 4}]}**