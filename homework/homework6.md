* Задача 1: 
```
Задайте двумерный массив символов (тип char [,]).
Создать строку из символов этого массива.
```
```
char[,] CreateMatrixRndChar(int rowCount, int intColums)
{
    string symbols = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
    char[,] matrix = new char[rowCount, intColums]; //3x4
    Random rnd = new Random();

    for (int i = 0; i < matrix.GetLength(0); i++)
    {
        for (int j = 0; j < matrix.GetLength(0); j++)
        {
            matrix[i, j] = symbols[rnd.Next(symbols.Length)];
        }
    }
    return matrix;
}

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
char[,] arr = CreateMatrixRndChar(3, 4);
PrintMatrix(arr);
Console.WriteLine();
string str = CreateStringToArray2d(arr);
Console.Write(str);
```
* Задача 2
```
Задайте строку, содержащую латинские буквы в обоих регистрах. 
Сформируйте строку, в которой все заглавные буквы заменены на строчные.
```
```
string CreateStrLowerCase(int length)
{
    string symbols = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
    string result = string.Empty;
    Random r = new Random();

    for (int i = 0; i < length; i++)
    {
            result += symbols[r.Next(symbols.Length)];
    }
    return result;
}

string strrnd = CreateStrLowerCase(10);
Console.Write(strrnd);
Console.WriteLine();
Console.WriteLine(strrnd.ToLower());
```
* Задача 3 
```
Задайте произвольную строку. Выясните, является ли она палиндромом.
```
```
void PalindromeCheck()
{
    Console.Write("Введите слово: ");
    string input = Console.ReadLine();

    if (IsPalindrome(input))
    {
        Console.WriteLine("Да, это палиндром.");
    }
    else
    {
        Console.WriteLine("Нет, это не палиндром.");
    }
}

bool IsPalindrome(string s)
    {
        return s == new string(s.Reverse().ToArray());
    }

PalindromeCheck();
```
* Задача 4.
```
Задайте строку, состоящую из слов, разделенных пробелами.
Сформировать строку, в которой слова расположены в обратном порядке.
В полученной строке слова должны быть также разделены пробелами.
```
```
Console.Write("Введите слово: ");
string? input = Console.ReadLine();

string ReverseWords(string sentence)
    {
        var words = sentence.Split(' ').ToList();
        words.Reverse();
        return String.Join(" ", words);
    }

string result = ReverseWords(input);
Console.Write(result);
```