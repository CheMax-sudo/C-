# Функции для создания и вывод массивов.
* int Генератор случайных чисел в одномерный массив
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
```
* int Выводит в консоль одномерный массив
```
void PrintArray(int[] array)
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
```
* int Генератор случайных чисел в двумерный массив
```
int[,] CreateMatrixRndInt(int rowCount, int intColums, int min, int max)
{
    int[,] matrix = new int[rowCount, intColums]; //3x4
    Random rnd = new Random();

    for (int j = 0; j < matrix.GetLength(1); j++)
    {
        for (int i = 0; i < matrix.GetLength(0); i++)
        {
            matrix[i, j] = rnd.Next(min, max);
        }
    }
    return matrix;
}
```
* int Выводит в консоль двумерный массив
```
void PrintMatrix(int[,] matrix)
{

    for (int i = 0; i < matrix.GetLength(0); i++)
    {
        for (int j = 0; j < matrix.GetLength(1); j++)
        {
            Console.Write($"{matrix[i,j], 4} ");
        }
        Console.WriteLine();
    }
}
```
* char Генератор случайных символов в одномерный массив
```
char[] CreateArrayRndChar(int length)
{
    string symbols = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
    char[] arr = new char[length];
    Random r = new Random();

    for (int i = 0; i < arr.Length; i++)
    {
            arr[i] = symbols[r.Next(symbols.Length)];
    }
    return arr;
}
```
* char Выводит в консоль одномерный массив
```
void PrintArray(char[] array)
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
```
* char Генератор случайных символов в двумерный массив
```
char[,] CreateMatrixRndChar(int rowCount, int intColums)
{
    string symbols = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
    char[,] matrix = new char[rowCount, intColums]; //3x4
    Random rnd = new Random();

    for (int j = 0; j < matrix.GetLength(1); j++)
    {
        for (int i = 0; i < matrix.GetLength(0); i++)
        {
            matrix[i, j] = symbols[rnd.Next(symbols.Length)];
        }
    }
    return matrix;
}
```
* char Выводит в консоль двумерный массив
```
void PrintMatrix(char[,] matrix)
{

    for (int i = 0; i < matrix.GetLength(0); i++)
    {
        for (int j = 0; j < matrix.GetLength(1); j++)
        {
            Console.Write($"{matrix[i, j],4} ");
        }
        Console.WriteLine();
    }
}
```
* Строка из двумерного массива. Перебирает элементы двумерного массива и добавляет в строку.
```
string CreateStringToArray2d(char[,] matrix)
{
    string result = "";
    for (int i = 0; i < matrix.GetLength(0); i++)
    {
        for (int j = 0; j < matrix.GetLength(1); j++)
        {
            result+= matrix[i, j];
        }
    }
    return result;
}  
```