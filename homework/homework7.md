* Задача 1
```
Вывод натуральных чисел в промежутке от M до N
Описание: Напишите программу, которая выведет все натуральные числа в
промежутке от M до N. Используйте рекурсию и не используйте циклы.
Пример:
● Вход: M = 1, N = 5
● Выход: 1, 2, 3, 4, 5
● Вход: M = 4, N = 8
● Выход: 4, 5, 6, 7, 8
```
```
Console.Write("Введите число М: ");
int mNum = Convert.ToInt32(Console.ReadLine());
Console.Write("Введите число N: ");
int nNum = Convert.ToInt32(Console.ReadLine());

void NaturalsDigitsMtoN(int mNum, int nNum)
{
    if(nNum == mNum-1) return;
    NaturalsDigitsMtoN(mNum, nNum - 1);
    Console.Write($"{nNum} ");
}
NaturalsDigitsMtoN(mNum, nNum);
```
* Задача 2
```
Функция Аккермана
Описание: Напишите программу для вычисления функции Аккермана с помощью
рекурсии. Даны два неотрицательных числа m и n.
Пример:
● Вход: m = 2, n = 3
● Выход: A(m, n) = 29
● Вход: m = 1, n = 4
● Выход: A(m, n) = 7
```
```
int Ackermann(int mNum, int nNum)
{
    if (mNum == 0) return nNum + 1;
    else if (mNum > 0 && nNum == 0) return Ackermann(mNum - 1, 1);
    else if (mNum > 0 && nNum > 0) return Ackermann(mNum - 1, Ackermann(mNum, nNum - 1));
    return 0;
}
Console.Write("Введите M: ");
int nNum = Convert.ToInt32(Console.ReadLine());
Console.Write("Введите N: ");
int mNum = Convert.ToInt32(Console.ReadLine());
// Вычисляем функцию Аккермана
int result = Ackermann(mNum, nNum);
// Выводим результат
Console.WriteLine($"A({mNum}, {nNum}) = {result}");
```
* Задача 3
```
Вывод элементов массива в обратном порядке
Описание: Задайте произвольный массив. Выведите его элементы, начиная с конца.
Используйте рекурсию и не используйте циклы.
Пример:
● Вход: {1, 2, 3, 4, 5}
● Выход: 5, 4, 3, 2, 1
● Вход: {10, 20, 30, 40}
● Выход: 40, 30, 20, 10
```
```
void PrintArrayReverse(int[] array, int index)
{
    if (index < 0) return; // Базовый случай: если индекс меньше 0, прекращаем рекурсию             
    Console.Write(array[index]);
    if (index > 0) Console.Write(", ");
    PrintArrayReverse(array, index - 1);
}

int[] array = { 1, 2, 3, 4, 5 };
Console.WriteLine("Массив в обратном порядке:");
PrintArrayReverse(array, array.Length - 1);
```