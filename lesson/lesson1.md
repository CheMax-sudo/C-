* Задание 1.
```
Напишите программу, которая на вход
принимает два целых числа и проверяет,
является ли первое число квадратом второго.
a = 25, b = 5 => да
a = 2, b = 10 => нет
a = 9, b = -3 => да
a = -3, b = 9 => нет
```
```Console.Write("Введите первое число: ");
int num1 = Convert.ToInt32(Console.ReadLine());
Console.Write("Введите второе число: ");
int num2 = Convert.ToInt32(Console.ReadLine());

if(num1 == num2 * num2)
{
    Console.WriteLine("Первое число является квадратом второго");
}
else
{
    Console.WriteLine("Первое число не является квадратом второго");
}
```

* Задание 2.
```
Напишите программу, которая на вход принимает
целое число N, а на выходе показывает все целые
числа в промежутке от -N до N.
Примеры
4 => -4, -3, -2, -1, 0, 1, 2, 3, 4
2 => -2, -1, 0, 1, 2
```
```
Console.Write("Введите целое положительное число: ");
int num = Convert.ToInt32(Console.ReadLine());
if (num > 0)
{
      for (int i = -num; i <= num; i++)
      {
            Console.Write(i + " ");
      }
}
else
{
      Console.WriteLine("Нужно вводить положительное число!");
}
```
* Задание 3.
```
Напишите программу, которая принимает на вход
трёхзначное целое число и на выходе показывает сумму
первой и последней цифры этого числа.
456 => 10
782 => 9
918 => 17
```
```
Console.Write("Введите трёхзначное целое число: ");
int num = Convert.ToInt32(Console.ReadLine());
if (num > 99 && num < 1000)
{
    int secondNum = num/100;
    int firstNum = num % 10;
    int result = secondNum+firstNum;
    Console.Write($"Сумма первой и последней цифры = {result}");
}else
{
Console.Write("Ошибка ввода");
}
```

