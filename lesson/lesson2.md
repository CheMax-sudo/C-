* Задание 1.
```
Напишите программу, которая принимает на
вход трёхзначное число и удаляет вторую
цифру этого числа.
Примеры
a = 256 => 26
a = 891 => 81
```
```
Console.Write("Введите трёхзначное целое число: ");
int num = Convert.ToInt32(Console.ReadLine());
if (num > 99 && num < 1000)
{
    int secondNum = num/100;
    int firstNum = num % 10; //456 % 10 = 450 + 6 = 6
    Console.Write(secondNum+""+firstNum);
}else
{
Console.Write("Ошибка ввода");
}
```
* Задание 2.
```
Напишите программу, которая принимает на вход
трёхзначное число и возводит вторую цифру этого
числа в степень, равную третьей цифре.
Примеры
487 => 8^7 = 2 097 152
254 => 5^4 = 625
617 => 1
```
```
Console.Write("Введите трёхзначное целое число: ");
int num = Convert.ToInt32(Console.ReadLine());
if (num > 99 && num < 1000)
{
    int firstNum = num / 10 % 10;
    int lastNum = num % 10;
    int result = firstNum;

    for (int i = 0; i < lastNum - 1; i++)
    {
        result *= firstNum;
    }
    Console.WriteLine(result);
}
else
{
    Console.Write("Ошибка ввода");
}
```
* Задание 3.
```
Напишите программу, которая будет принимать на
вход два числа и выводить, является ли первое число
кратным второму. Если первое число некратно
второму, то программа выводит остаток от деления.
Примеры
14, 5 => нет, 4
16, 8 => да
4, 3 => нет, 1
```
```
Console.Write("Введите первое целое число: ");
int num = Convert.ToInt32(Console.ReadLine());
Console.Write("Введите второе целое число: ");
int num_two = Convert.ToInt32(Console.ReadLine());
if (num > 0 && num < 100 && num_two > 0 && num_two < 100)
{
    int result = num % num_two;
    if (result == 0)
    {
        Console.WriteLine("Да");
    }
    else
    {
        Console.Write($"Нет, {result}");
    }

}
else
{
    Console.Write("Ошибка ввода!");
}
```
* Задание 4.
```
Напишите программу, которая выводит третье с
конца цифру заданного числа или сообщает, что
третьей цифры нет.
456 => 6
7812 => 1
91 => Третьей цифры нет
```
```
Console.Write("Введите трёхзначное целое число: ");
int num = Convert.ToInt32(Console.ReadLine());
int result;

if (num > 99 || num < -99)
{
    while (num > 999 || num <-999) //Подключается цикл для того чтобы уменьшить разрядность числа
    {
        num = num / 10; //Переносит разрядность (точку) на две позиции вперёд! 
    }
    result = num % 10; //Находит остаток от деления пример 456 % 10 = 450 + 6 = 6
    Console.WriteLine("Третья цифра с лева: "+result);
}
else
{
    Console.Write("Третьей цифры нет");
}
```
