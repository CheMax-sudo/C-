# Массивы и строки

* Задание 1.
```
Задайте массив символов (тип char []). Создайте строку из
символов этого массива.
Указание
Конструктор строки вида string(char []) не использовать.

Пример
[‘a’, ‘b’, ‘c’, ‘d’] => “abcd”
```
```
string CharArrayToSrting(char[] arr) // Метод создаёт из массива символов строку 
{
    string res = string.Empty; // Пустая строка
    for (int i = 0; i < arr.Length; i++)
    {
        res += arr[i];
    }
    return res;
}

char[] array = { 'a', 'b', 'c', 'd', 'e', 'f' };
string result = CharArrayToSrting(array);
Console.WriteLine(result);
```
* Задание 2. 
```
На основе символов строки (тип string) сформировать массив
символов (тип char[]). Вывести массив на экран.
Указание
Метод строки ToCharArray() не использовать.
Пример:
“Hello!” => [‘H’, ‘e’, ‘l’, ‘l’, ‘o’, ‘!’ ]
```
```
char[] StringToCharArray(string s) // Метод формирует из строки массив символов
{
    

    char[] strArr = new char[s.Length];
    for (int i = 0; i < s.Length; i++)
    {
        strArr[i] = s[i];
    }
    return strArr;
}

void PrintArray(char[] array) // Метод выводит массив в консоль
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

Console.Write("Введите строку: ");
string str = Console.ReadLine();
char[] arrStr = StringToCharArray(str);
PrintArray(arrStr);
```
* Задание 3. 
```
Считать строку с консоли, состоящую из латинских
букв в нижнем регистре. Выяснить, сколько среди
введённых букв гласных.
Пример:
“hello” => 2
“world” => 1
```
```
int CountVowels(string str) //Метод подсчитывает сколько среди букв гласных.
{
    string vowels = "aeiouy";
    int count = 0;
    for (int i = 0; i < str.Length; i++) // При функции Contains понадобиться только один цикл for
    {                                    
        for (int j = 0; j < vowels.Length; j++)
        {
            if (vowels[j] == str[i])     // if (vowels.Contains(str[i]))
            {
                count++;
            }
        } 
    }
    return count;
}
Console.Write("Введите строку: ");
string str = Console.ReadLine();
int result = CountVowels(str);
Console.WriteLine($"В слове {result} гласных буквы");


