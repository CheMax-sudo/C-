# Функции и массивы
* Задание 1.
```
Задайте одномерный массив, заполненный случайными
числами. Определите количество простых чисел в этом
массиве.
Примеры
[1 3 4 19 3] => 2
[4 3 4 1 9 5 21 13] => 3
```
```
int[] CreateArrayRndInt(int size, int min, int max) // Метод создаёт массив с рандомными элементами.
{
    int[] array = new int[size];
    Random rnd = new Random();

    for (int i = 0; i < size; i++)
    {
        array[i] = rnd.Next(min, max);
    }

    return array;
}

void PrintArray(int[] array) // Метод выводит массив в консоль
{
    Console.Write("[");
    for (int i = 0; i < array.Length - 1; i++)
    {
        if (i < array.Length - 1)
            Console.Write($"{array[i]}, ");
        else
            Console.Write($"{array[i]}");
    }
    Console.Write("]");
}

int CountPrimeNumbers(int[] array) // Метод нахождения количества чисел
{
    int count = 0;
    for (int i = 0; i < array.Length; i++)
    {
        if(IsPrime(array[i]))
        {
            count++;
        }

    }

    return count;
}

bool IsPrime(int num) // Метод нахождения простых чисел 
{
    for (int i = 2; i < Math.Sqrt(num); i++) // Функция квадратный корень числа num
    {
       if (num % i == 0) 
       {
        return false; 
       }    
    }
    return true;
}

int[] arr = CreateArrayRndInt(10, 1, 100);
PrintArray(arr);

int countPrime = CountPrimeNumbers(arr);
Console.Write(" => "+countPrime);
```
* Задание 2.
```
Задайте массив из N случайных целых чисел (N вводится с клавиатуры).
Найдите количество чисел, которые оканчиваются на 1 и
делятся нацело на 7.
Пример:
[1 5 11 21 81 4 0 91 2 3] => 2
```
```
int[] CreateArrayRndInt(int size, int min, int max) // Метод создаёт массив с рандомными элементами.
{
    int[] array = new int[size];
    Random rnd = new Random();

    for (int i = 0; i < size; i++)
    {
        array[i] = rnd.Next(min, max);
    }
    
    return array;
}

void PrintArray(int[] array) // Метод выводит в консоль массив
{
    Console.Write("[");
    for (int i = 0; i < array.Length; i++)
    {
        if (i < array.Length - 1)
            Console.Write($"{array[i]}, ");
        else
            Console.Write($"{array[i]}");
    }
    Console.Write("]");
}

int CountNumsLastDevB(int[] array, int aLast, int bDev) // Метод который находит количество чисел, которые оканчиваются на 1 и делятся нацело на 7.
{
    int count = 0;
   
    for (int i = 0; i < array.Length; i++)
    {
       if (array[i]%10 == aLast && array[i]%bDev == 0) 
       {
        count++;
      
       }    
    }
    return count;
}

int[] arr = CreateArrayRndInt(30, 1, 100);
PrintArray(arr);

int result = CountNumsLastDevB(arr, 1, 7);
Console.Write(" => " + result);
```
