# Урок 5. Массивы.
* Задание 1
```
Поиск максимального элемента в каждой строке
Описание: Задайте двумерный массив целых чисел. Напишите программу, которая
находит максимальный элемент в каждой строке массива и выводит его.
Пример входных данных:
1  3  5  7
2  4  6  8
9 10 11 12
Пример результата:
Максимальный элемент в строке 0: 7
Максимальный элемент в строке 1: 8
Максимальный элемент в строке 2: 12
```
```
// int[,] CreateMatrixRndInt(int rowCount, int intColums, int min, int max)
// {
//     int[,] matrix = new int[rowCount, intColums]; //3x4
//     Random rnd = new Random();

//     for (int j = 0; j < matrix.GetLength(1); j++)
//     {
//         for (int i = 0; i < matrix.GetLength(0); i++)
//         {
//             matrix[i, j] = rnd.Next(min, max);
//         }
//     }
//     return matrix;
// }

// void PrintMatrix(int[,] matrix)
// {

//     for (int i = 0; i < matrix.GetLength(0); i++)
//     {
//         for (int j = 0; j < matrix.GetLength(1); j++)
//         {
//             Console.Write($"{matrix[i, j],4} ");
//         }
//         Console.WriteLine();
//     }
// }

// int[] GetMaxArrayRows(int[,] matrix)
// {   
//     int[] array = new int[matrix.GetLength(0)];
        
//     for (int i = 0; i < matrix.GetLength(0); i++) //Rows
//     {
//         int sum = 0;

//         for (int j = 0; j < matrix.GetLength(1); j++) //Columns
//         {
//             if(sum < matrix[i, j]) sum = matrix[i, j]; 
//         }
//         array[i] = sum;
//     }
//     return array;
// }

// void PrintArray(int[] array)
// {
//     int result;
//     for (int i = 0; i < array.Length; i++)
//     {
//         result = array[i];
//         Console.Write($"Максимальный элемент в строке {i}: {result}");
//         Console.WriteLine();
//     }
// }


// int[,] array2d = CreateMatrixRndInt(3, 4, 1, 11);
// PrintMatrix(array2d);

// int[] arr = GetMaxArrayRows(array2d);
// PrintArray(arr);
```
# Задание 2: Поиск суммы элементов в каждом столбце
```
Описание: Задайте двумерный массив целых чисел. Напишите программу, которая
находит сумму элементов в каждом столбце массива и выводит её.

Пример входных данных:
1   2   3
4   5   6
7   8   9
10  11  12

Пример результата:
Сумма элементов в столбце 0: 22
Сумма элементов в столбце 1: 26
Сумма элементов в столбце 2: 30
```
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

void PrintMatrix(int[,] matrix)
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

int[] GetMaxArrayColumns(int[,] matrix)
{   
    int rows = matrix.GetLength(1);
    int columns = matrix.GetLength(0);
    int[] array = new int[rows];
        
    for (int j = 0; j < rows; j++) 
    {
        int sum = 0;

        for (int i = 0; i < columns; i++)
        {
            sum += matrix[i, j]; 
        }
        array[j] = sum;
    }
    return array;
}

void PrintArray(int[] array)
{
    int result;
    for (int i = 0; i < array.Length; i++)
    {
        result = array[i];
        Console.Write($"Сумма элементов в столбце {i}: {result}");
        Console.WriteLine();
    }
}


int[,] array2d = CreateMatrixRndInt(3, 4, 1, 11);
PrintMatrix(array2d);

int[] arr = GetMaxArrayColumns(array2d);
PrintArray(arr);
```
# Задание 3: Транспонирование двумерного массива
```
Описание: Задайте двумерный массив целых чисел. Напишите программу, которая
транспонирует массив (меняет строки и столбцы местами).

Пример входных данных:
1 2
3 4
5 6

Пример результата:
1 3 5
2 4 6
```
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

void PrintMatrix(int[,] matrix)
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

int[,] GetTransposeMatrix(int[,] matrix)
{   
    int rows = matrix.GetLength(0);
    int columns = matrix.GetLength(1);
    int[,] matrixOut = new int[columns, rows];  //Меняем Строки с столбцами для создания матрицы      
    for (int j = 0; j < columns; j++)           //которая будет отвечать условию задачи.
    {
        for (int i = 0; i < rows; i++)
        {
            matrixOut[j, i] = matrix[i, j];     //Заполняем матрицу materixOut элементами из входящей
        }                                       //матрицы и путём перестановки индексов записываем 
    }                                           //элементы в строки из столбцов.
    return matrixOut;
}

int[,] array2d = CreateMatrixRndInt(3, 2, 1, 11);
PrintMatrix(array2d);
Console.WriteLine();
int[,] array2dTrans = GetTransposeMatrix(array2d);
PrintMatrix(array2dTrans);
```
# Задание 4: Замена отрицательных элементов в двумерном массиве
```
Описание: Задайте двумерный массив. Замените все отрицательные числа на их
абсолютные значения.

Пример входных данных:
1 -2 3
-4 5 -6
7 -8 9

Пример результата:
1 2 3
4 5 6
7 8 9
```
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

void PrintMatrix(int[,] matrix)
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

int[,] RepNegativeNumMatrix(int[,] matrix)
{   
    int rows = matrix.GetLength(0);
    int columns = matrix.GetLength(1);
    int[,] matrixOut = new int[rows, columns];        
    for (int i = 0; i < rows; i++)           
    {
        for (int j = 0; j < columns; j++)
        {
            if (matrix[i, j]<0)
            {
                matrixOut[i, j] = matrix[i, j]*-1;
            }
            else
            {
                matrixOut[i, j] = matrix[i, j];
            }
                 
        }                                       
    }                                           
    return matrixOut;
}

int[,] array2d = CreateMatrixRndInt(3, 3, -11, 11);
PrintMatrix(array2d);
Console.WriteLine();
int[,] array2dTrans = RepNegativeNumMatrix(array2d);
PrintMatrix(array2dTrans);
```