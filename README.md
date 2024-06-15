# Итоговая контрольная работа по основному блоку

Для решения задачи используем два массива
первый изначальный нам задан и выбирается из несколких вариантов при помощи оператора switch.

Массив inputArray проверяем на длину строк при помощи переменной maxLength, строки длина которых меньше или равна переменной maxLength формируются в новый массив newArray. оба массива выводятся на экран. 


## Блок-схема
![Блок-схема](https://github.com/BuroffSergey/Homework_C-/blob/main/blok-diogram_c%23.png)


## Решение


![Блок-схема](https://github.com/BuroffSergey/Homework_C-/blob/main/blok-diogram_c%23.png)

string[] inputArray = new string[] {};

string fromUser = ReadInput("Введите команду: ");
switch (fromUser)
{
    case "1":
        inputArray = new string[] { "Hello", "2", "world", ":-)" };
        break;
    case "2":
        inputArray = new string[] { "1234", "1567", "-2", "computer science" };
        break;
    case "3":
        inputArray = new string[] { "Russia", "Denmark", "Kazan" };
        break;
    default:
        Console.WriteLine($"{fromUser} - Такой команды нет");
        break;
}
int maxLength = 3;
int lenNewArray = 0;
for (int i = 0; i <= inputArray.Length - 1; i++)
{
    if (inputArray[i].Length <= maxLength) lenNewArray++;
}

string[] newArray = new string[lenNewArray];
int idx = 0;

for (int i = 0; i <= inputArray.Length - 1; i++)
{
    if (inputArray[i].Length <= maxLength)
    {
        newArray[idx] = inputArray[i];
        idx++;
    }
}

PrintArray(inputArray);
Console.Write("→ ");
PrintArray(newArray);

// Функция: Вывод команд для работы с программой
void Commands()
{
    Console.WriteLine();
    Console.WriteLine("СПИСОК КОМАНД:");
    Console.WriteLine("1 – использовать массив: [“Hello”, “2”, “world”, “:-)”]");
    Console.WriteLine("2 – использовать массив: [“1234”, “1567”, “-2”, “computer science”]");
    Console.WriteLine("3 – использовать массив: [“Russia”, “Denmark”, “Kazan”]");
    Console.WriteLine();
}

// Функция ввода
string ReadInput(string msg)
{
    Console.Write(msg);
    return Console.ReadLine();
}

//  Функция вывода массива в терминал
void PrintArray(string[] array)
{
    Console.Write("[ ");
    for (int i = 0; i < array.Length; i++)
    {
        Console.Write($"“{array[i]}”, ");
    }
    Console.Write("] ");
}



