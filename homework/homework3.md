* Задание 1
``` 
Поиск элемента в массиве
Описание: Задайте массив целых чисел. Напишите программу, которая проверяет, присутствует ли заданное число в массиве. Программа должна вывести: Присутствует/Не присутствует.
```
```
Console.Write("Введите поочерёдно целые числа: ");
int[] array = new int[10];
for (int i = 0; i < array.Length; i++)
{
    array[i] = Convert.ToInt32(Console.ReadLine());
}
Console.Write("Введите число которое хотите найти: ");
int num = Convert.ToInt32(Console.ReadLine());
bool result = false;
for (int i = 0; i < array.Length; i++)
{
    if (num == array[i])
    {
        Console.Write("Заданное число присутствует!");
        result = true;
        break;
    }    
}
if (result == false) Console.Write("Заданное число не присутствует!");
```
* Задание 2 
```
Замена элементов массива
Описание: Задайте массив из 10 элементов, заполненный числами от -10 до 10. Замените отрицательные числа на их абсолютные значения, а положительные числа на их отрицательные эквиваленты.
```
```
int [] arr = {-5, 4, -9, 3, 2, 0, -6, 7, 8, -1};
Console.Write("[ ");
for (int i = 0; i < arr.Length; i++)
{
   arr[i] *= -1;
   Console.Write(arr[i]+" "); 
}
Console.Write("]");
```
* Задание 3. 
```
Поиск среднего значения массива
Описание: Задайте массив из 10 целых чисел. Найдите среднее значение элементов
массива.
```
```
int [] arr = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
double averageNum;
int sum = 0;
for (int i = 0; i < arr.Length; i++)
{
    sum += arr[i];

}
averageNum = sum/arr.Length;
Console.Write(averageNum);
```
* Задание 4
```
Удаление всех отрицательных чисел
Описание: Задайте массив целых чисел. Напишите программу, которая удаляет все отрицательные числа из массива и возвращает новый массив, содержащий только неотрицательные числа.
```
```
int[] arr = { -2, 5, 6, -1, -9 };
int n = arr.Length;
int count = 0;
for (int i = 0; i < n; i++)
{
    if (arr[i] > 0) count++;
}

int[] arrNew = new int[count];
Console.WriteLine("[ -2, 5, 6, -1, -9 ]");
Console.Write("[ ");
for (int i = 0; i < n; i++)
{   
    if (arr[i] > 0)
    {
        arrNew[count - count] = arr[i];
        Console.Write(arrNew[count - count]+" ");
    }
}
Console.Write("]");
```