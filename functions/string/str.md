# Строки
* string Функция создаёт строку и записывает в неё рандомные символы.
```
string CreateStrLowerCase(int length)
{
    string symbols = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
    string result = "";
    Random r = new Random();

    for (int i = 0; i < length; i++)
    {
            result += symbols[r.Next(symbols.Length)];
    }
    return result;
}
```
* string Проверка строки на строку полиндром
```
void PolindromCheck()
{
    Console.Write("Введите слово: ");
    string? str = Console.ReadLine();
    int n = str.Length;
    bool check = true;
    for (int i = 0; i < n / 2; i++)
    {
        if (str[i] == str[n - i - 1]) check = true;
        else
        {
            check = false;
        }
    }
    if (check == true) Console.Write("Слово палиндром!");
    else
    {
        Console.Write("Слово не палиндром!");
    }
}
```