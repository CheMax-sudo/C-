# Семинар 7. Рекурсия
* Задание 1. 
```
Задайте значение N. Напишите программу, которая выведет
все натуральные числа в промежутке от 1 до N.
Указание
Использовать рекурсию. Не использовать цикл.
Пример
N=5 => 1 2 3 4 5
```
```
void PrintNaturalNumbers(int num)
{
     if (num == 0) return;
     PrintNaturalNumbers(num - 1); // Вызывает функцию PrintNaturalNumbers с аргументом меньшим на 1
     Console.Write($"{num} ");
     // PrintNaturalNumbers(num - 1); // Хвостовое исполнение, вызов осуществляется после вывода в консоль результата
}                                    // тем самым выводится от num до 1.

Console.WriteLine("Введите натуральное число: ");
int number = Convert.ToInt32(Console.ReadLine());

PrintNaturalNumbers(number); 
```
* Задание 2.
```
Напишите программу, которая будет принимать на вход число и
возвращать сумму его цифр.
Указание
Использовать рекурсию.
Пример
123 => 6
63 => 9
```
```
int SummaDigits(int num) //123, 12, 1, 0
{
    if (num == 0) return 0; //

    return num%10 + SummaDigits(num/10); //123, 12, 1
    // 1%10=1+12%10=2,123%10=3, 1+2+3+0=6
}

Console.Write(SummaDigits(123));
```
* Задание 3.
```
Считать строку с консоли, содержащую латинские буквы.
Вывести на экран согласные буквы этой строки.
Указание
Использовать рекурсию. Не использовать цикл.

Пример:
“hello” => h l l
“World” => W r l d
“Hello world!” => H l l w r l d
```
```
Console.WriteLine("Введите строку содержающую латинские буквы: ");
string text = Console.ReadLine();
Console.WriteLine();
PrintConsonants(text);

void PrintConsonants(string txt, int index = 0)
{
    if (index == txt.Length)
    {
        return;
    }
    string vowels = "aeiouy";
    if (char.IsAsciiLetter(txt[index]) && !vowels.Contains(txt[index]))
    {
        Console.Write($"{txt[index]}");
    }
    PrintConsonants(txt, index + 1);
}
```