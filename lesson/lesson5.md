# Двумерные массивы.
* Задание 1.
```
Задайте двумерный массив. Найдите элементы, у которых оба
индекса чётные, и замените эти элементы на их квадраты.
Пример:
2 3 4 3    4 3 4  3  
4 3 4 1 => 4 3 4  2 
2 9 5 4    2 9 25 4
```
```
int[,] CreateMatrixRndInt(int rowCount, int intColums, int min, int max) // Метод создаёт двумерный массив с рандомными элементами.
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

void PrintMatrix(int[,] matrix) // Метод выводит массив в консоль
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

void ElemEvenIndexesToSquare(int[,] matrix) // Метод ищет чётные элементы двуммерного массива и меняет на их квадраты
{
    for (int i = 0; i < matrix.GetLength(0); i+=2)
    {
        for (int j = 0; j < matrix.GetLength(1); j+=2)
        {
            //if(i%2 == 0 && j%2 == 0)
            //{
                matrix[i,j]*=matrix[i,j];
            //}
        }
    }
}

int[,] array2d = CreateMatrixRndInt(3, 4, 1, 10);
PrintMatrix(array2d);

Console.WriteLine();

ElemEvenIndexesToSquare(array2d);
PrintMatrix(array2d);
```
* Задание 2. 
```
Задайте двумерный массив. Найдите сумму элементов,
находящихся на главной диагонали (с индексами (0,0); (1;1) и
т.д.
Пример
2 3 4 3
4 3 4 1 => 2 + 3 + 5 = 10
2 9 5 4
```
```
int[,] CreateMatrixRndInt(int rowCount, int intColums, int min, int max) // Метод создаёт двумерный массив с рандомными элементами.
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

void PrintMatrix(int[,] matrix) // Метод выводит массив в консоль
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

int SumMainDiagonal(int[,] matrix) // Метод находит сумму элементов на главной диагонали
{
    int sum = 0;
    int minSize = matrix.GetLength(0);
    // if (matrix.GetLength(1) < minSize)
    // {
    //     minSize = matrix.GetLength(1);
    // }

    for (int i = 0; i < matrix.GetLength(0) && i < matrix.GetLength(1); i++)
    {
        sum = sum + matrix[i, i];
    }
    return sum;
}

int[,] arr = CreateMatrixRndInt(4, 4, 1, 10);

PrintMatrix(arr);
Console.WriteLine();
int sum = SumMainDiagonal(arr);
Console.Write(sum);
```
* Задание 3. Совместная работа
```
Задайте двумерный массив из целых чисел. Сформируйте новый
одномерный массив, состоящий из средних арифметических
значений по строкам двумерного массива.
Пример
2 3 4 3
4 3 4 1 => [3 3 5]
2 9 5 4
```
```
int[,] CreateMatrixRndInt(int rowCount, int intColums, int min, int max) // Метод создаёт двумерный массив с рандомными элементами.
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

void PrintMatrix(int[,] matrix) // Метод выводит массив в консоль
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

double[] GetAvergeArrayRows(int[,] matrix) // Метод находит из средних арифметических значений по строкам двумерного массива
{   
    double[] array = new double[matrix.GetLength(0)];
        
    for (int i = 0; i < matrix.GetLength(0); i++) //Rows
    {
        int sum = 0;

        for (int j = 0; j < matrix.GetLength(1); j++) //Columns
        {
            sum += matrix[i, j];
        }
        array[i] = (double)sum / matrix.GetLength(1);
    }
    return array;
}

void PrintArray(double[] array) // Метод выводит массив в консоль
{
    Console.Write("[");
    for (int i = 0; i < array.Length; i++)
    {
        if (i < array.Length-1)
            Console.Write($"{array[i]}, ");
        else
            Console.Write($"{array[i]}");
    }
    Console.Write("]");
}


int[,] array2d = CreateMatrixRndInt(3, 4, 1, 11);
PrintMatrix(array2d);

double[] arr = GetAvergeArrayRows(array2d);
PrintArray(arr);
```