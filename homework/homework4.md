# Урок 4. Функции
* Задача 1.
``` 
Напишите программу, которая бесконечно запрашивает целые числа с консоли. 
Программа завершается при вводе символа ‘q’ или при вводе числа, сумма цифр которого чётная.
```
```
while (true)
{
    Console.Write("Введите целое число или 'q' для завершения: ");
    string? input = Console.ReadLine();
    if (input == "q")
    {
        Console.WriteLine("Завершение программы");
        return; // Выход из метода Main
    }

    else if (int.TryParse(input, out int number))
    {
        int sum = 0;
        while (number > 0)
        {
            sum = sum + number % 10;
            number = number / 10;
        }
        if (sum % 2 == 0)
        {
            Console.WriteLine("Завершение программы");
            return; // Выход из метода Main
        }
    }
    else
    {
        Console.Write("Ввод не корректен!");
    }
}
```
* Задача 2. 
```
Задайте массив заполненный случайными трёхзначными числами. 
Напишите программу, которая покажет количество чётных чисел в массиве.
```
```
int[] CreateArrayRndInt(int size, int min, int max)
{
    int[] array = new int[size];
    Random rnd = new Random();

    for (int i = 0; i < size; i++)
    {
        array[i] = rnd.Next(min, max);
    }

    return array;
}

void EvenPrintArray(int[] array)
{
    Console.Write("[ ");
    for (int i = 0; i < array.Length; i++)
    {
        if (array[i] % 2 == 0)
        {
            Console.Write($"{array[i]} ");
        }
    }
    Console.Write("]");
}    

int[] arr = CreateArrayRndInt(10, 100, 999);

EvenPrintArray(arr);
```
* Задача 3.
```
Напишите программу, которая перевернёт одномерный массив 
(первый элемент станет последним, второй – предпоследним и т.д.)
```
```
int[] CreateArrayRndInt(int size, int min, int max)
{
    int[] array = new int[size];
    Random rnd = new Random();

    for (int i = 0; i < size; i++)
    {
        array[i] = rnd.Next(min, max);
    }

    return array;
}

void ReversePrintArray(int[] array)
{
    int n = array.Length;
    Console.Write("[ ");
    for (int i = 0; i < n; i++)
    {
        Console.Write(array[i] + " ");
    }
    Console.Write("] => [ ");
    for (int j = 0; j < n; j++)
    {
        Console.Write(array[n - j - 1] + " ");
    }
    Console.Write("]");
}

int[] arr = CreateArrayRndInt(10, 10, 100);

ReversePrintArray(arr);
```