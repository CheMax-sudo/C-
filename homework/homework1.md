* Задание 1
```
Определите, делится ли число на другое
Описание: Напишите метод, который на вход принимает два целых числа и проверяет, делится ли первое число на второе. Если делится, выводите "делится", иначе выводите "не делится".
Пример использования: На входе:
firstNumber: 10
secondNumber: 2
На выходе:
делится
На входе:
firstNumber: 10
secondNumber: 3
На выходе:
не делится
```
```
Console.Write("Введите первое целое число: ");
int firstNumber = Convert.ToInt32(Console.ReadLine());
Console.Write("Введите второе целое число: ");
int secondNumber = Convert.ToInt32(Console.ReadLine());
if (secondNumber == 0)
{
    Console.Write("На ноль делить нельзя!");
}
else
{
    if (firstNumber % secondNumber == 0)
    {
        Console.WriteLine("Делиться!");
    }
    else
    {
        Console.WriteLine("Не делится!");
    }
}
```
* Задание 2
```
Поиск среднего из трех чисел
Описание: Напишите метод, который принимает на вход три числа и возвращает
среднее из этих чисел (то есть не самое большое и не самое маленькое).
Пример использования: На входе:
a: 5
b: 3
c: 8
На выходе:
5
На входе:
a: 1
b: 9
c: 7
На выходе:
7
```
```
Console.Write("Введите первое целое число: ");
int firstN = Convert.ToInt32(Console.ReadLine());
Console.Write("Введите второе целое число: ");
int secondN = Convert.ToInt32(Console.ReadLine());
Console.Write("Введите третье целое число: ");
int thirdN = Convert.ToInt32(Console.ReadLine());
int average = 0;

if (firstN<secondN && secondN<thirdN || firstN>secondN && secondN>thirdN) 
{
average = secondN; 
Console.Write(average);
}
else if (secondN<firstN && firstN<thirdN || secondN>firstN && firstN>thirdN)
    {
    average = firstN;
    Console.Write(firstN);
    }
else if (secondN<thirdN && thirdN<firstN || secondN>thirdN && thirdN>firstN)
        {
        average = thirdN;    
        Console.Write(thirdN);
        } 
else if (average == 0)
{
    Console.Write("Ошибка ввода");
}  
``` 
* Задание 3
```
Определение, является ли число положительным
Описание: Напишите метод, который на вход принимает число и выводит, является ли
оно положительным (больше нуля), отрицательным (меньше нуля) или нулём.
Пример использования: На входе:
number: 7
На выходе:
положительное
На входе:
number: -3
На выходе:
отрицательное
На входе:
number: 0
На выходе:
ноль 
```
```
Console.Write("Введите целое число: ");
int num = Convert.ToInt32(Console.ReadLine());
if (num < 0)
{
    Console.Write($"Число {num} отрицательное!");
}
else if (num > 0)
{
    Console.Write($"Число {num} положительное!");
}
else if (num == 0)
{
    Console.Write($"Число {num} равное нулю!");
}
```
* Задание 4
```
Вывести нечетные числа
Описание: Напишите метод, который на вход принимает число (number), а на выходе
выводит все нечетные числа от 1 до number (включительно), после каждого числа
должен быть знак пробела.
Пример использования: На входе:
number: 5
На выходе:
1 3 5
На входе:
number: 8
На выходе:
1 3 5 7
```
```
Console.Write("Введите целое число: ");
int inNum = Convert.ToInt32(Console.ReadLine());
for (int i = 1; i <= inNum; i++)
{
    int outNum=+i;
    if (outNum%2 == 1) Console.Write(outNum+" ");
}
```