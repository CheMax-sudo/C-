* Задача 1. 
```
Напишите программу, которая принимает
на вход число и проверяет, кратно ли оно
одновременно 7 и 23
```
```
Console.Write("Введите целое число: ");
int num = Convert.ToInt32(Console.ReadLine());
if (num % 7 == 0 && num % 23 == 0)
{
  Console.Write($"Число {num} кратно 7 и 23");   
}
else
{
    Console.Write($"Число {num} не кратно 7 и 23"); 
}
```
* Задача 2.
```
Напишите программу, которая принимает
на вход координаты точки (X и Y), причём X ≠ 0 и Y ≠
0 и выдаёт номер координатной четверти плоскости,
в которой находится эта точка.
```
```
Console.Write("Введите координат x: ");
int x = Convert.ToInt32(Console.ReadLine());
Console.Write("Введите координат y: ");
int y = Convert.ToInt32(Console.ReadLine());

if (x != 0 && y != 0)
{
    if (x > 0 && y > 0) Console.Write("Координатная четверть №1"); 
    else if (x < 0 && y > 0) Console.Write("Координатная четверть №2");
    else if (x <= 0 && y > 0) Console.Write("Координатная четверть №3");
    else if (x > 0 && y < 0) Console.Write("Координатная четверть №4");
}
else
{
    Console.Write("Точка находится на оси координат");
}

Console.Write("Введите координаты точки X и Y через пробел:");string[] coordinates = Console.ReadLine().Split(' '); // Функция принимает ввод через пробел.
int x = Convert.ToInt32(coordinates[0]);
int y = Convert.ToInt32(coordinates[1]);
```
* Задача 3.
```
Напишите программу, которая принимает на вход целое число 
из отрезка [10, 99] и показывает наибольшую цифру числа.
```
```
Console.Write("Введите число от 10 до 99: ");
int num = Convert.ToInt32(Console.ReadLine());


if (num >= 10 && num <= 99)
{
     int firstNum = num / 10;
     int secondNum = num % 10;
     if (firstNum > secondNum) Console.Write("Наибольшее число: "+firstNum); 
     else if (firstNum < secondNum) Console.Write("Наибольшее число: "+secondNum);
     else if (firstNum == secondNum) Console.Write("Числа равны");
}
else
{
    Console.Write("Введите коректное число!");
}
```
* Задача 4.
```
Напишите программу, которая на вход
принимает натуральное число N, а на выходе
показывает его цифры через запятую.
```
```
Console.Write("Введите натуральное число N: ");
int numN = Convert.ToInt32(Console.ReadLine());
int currentDigit;

if (numN < 10)
{
    Console.WriteLine(numN);
}
else
{
    while (numN > 0)
    {
        currentDigit = numN % 10;
        numN = numN / 10;

        if (numN > 0)
        {
            Console.Write(currentDigit + ",");
        }
        else
        {
            Console.WriteLine(currentDigit);
        }
    }
}
```

