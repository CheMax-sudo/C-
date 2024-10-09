* Задание 1.
```
Задайте массив. Напишите программу, которая определяет,
присутствует ли заданное число в массиве. Программа
должна выдать ответ: Да/Нет.
Примеры
[1 3 4 19 3], 8 => Нет
[-4 3 4 1], 3 => Да
```
```
int[] array = { 1, 3, 4, 19, 3, 4 };
Console.Write("Введите число: ");
int reqNum = Convert.ToInt32(Console.ReadLine());
bool answer = false;

for (int i = 0; i < array.Length; i++)
{
    if (reqNum == array[i]) answer = true;
}                                               //string result = answer ? "Да" : "Нет";  Тернарный оператор. 
                                                //если answer true ?(ТОГДА) Да :(ИНАЧЕ)Нет
Console.Write(answer ? "Да" : "Нет");
```
* Задание 2.
```
Задайте массив из 10 элементов, заполненный числами из
промежутка [-10, 10]. Замените отрицательные элементы на
положительные, а положительные на отрицательные.
Пример:
[1 -5 6] => [-1 5 -6]
```
```
int [] array = {1, -5, 6, 7, -8, -9};

for (int i = 0; i < array.Length; i++)
{
    array[i] *= -1;
}

for (int i = 0; i < array.Length; i++)
{
    Console.Write(array[i]+" ");
}
```
* Задание 3.
```
Найдите произведения пар чисел в одномерном массиве. Парой
считаем первый и последний элемент, второй и предпоследний и
т.д. Результат запишите в новый массив.
Пример
[1 3 2 4 2 3] => [3 6 8]
[2 3 1 7 5 6 3] => [6 18 5] (элемент 7 не имеет пары)
```
```
int[] array = { 1, 5, 6, 7, 8, 9 };
int[] arrayResult = new int[array.Length / 2];
int n = array.Length;
for (int i = 0; i < n / 2; i++)
{
    arrayResult[i] = array[i] * array[n - 1];
}

for (int i = 0; i < arrayResult.Length; i++)
{
    Console.Write(arrayResult[i] + " ");
}
```
* Задание 4.
```
Дано натуральное трёхзначное число. Создайте массив, состоящий из
цифр этого числа. Младший разряд числа должен располагаться на 0-
м индексе массива, старший – на 2-м.
Пример
456 => [6 5 4]
781 => [1 8 7]
```
```
Console.Write("Введите целое трёхзначное число: ");
int inNum = Convert.ToInt32(Console.ReadLine());
int[] array = new int[3];
if (inNum > 99 || inNum < 1000)
{
    array[0] = inNum % 10;
    array[1] = inNum / 10 % 10;
    array[2] = inNum / 100 % 10;
}
Console.WriteLine(array[0] + " " + array[1] + " " + array[2]);
```
#### Ещё вариант решения задачи.
```
Console.Write("Введите трёхзначное число: ");
int num = Convert.ToInt32(Console.ReadLine());

int numCopy = num;
int count = 0;

//Считает количество чисел
while(numCopy != 0)
{
    numCopy /= 10;
    count++;
}

//Создаём массив на count чисел
int[] arr = new int[count];
int index = 0;
while (num != 0)
{
arr[index] = num % 10;
num /= 10; // num = num / 10;
index++;
}
Console.Write("[");
for(int i = 0; i < arr.Length; i++)
{
    Console.Write($" {arr[i]}");
}
Console.Write(" ]");
```