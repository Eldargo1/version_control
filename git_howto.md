using System;

class Program
{
    static void Main(string[] args)
    {
        Console.WriteLine("Введите элементы массива через запятую:");
        string input = Console.ReadLine();

        string[] inputArray = input.Split(',');

        // Убираем пробелы в начале и в конце каждой строки
        for (int i = 0; i < inputArray.Length; i++)
        {
            inputArray[i] = inputArray[i].Trim();
        }

        // Подсчитываем количество строк, удовлетворяющих условию
        int count = 0;
        foreach (string str in inputArray)
        {
            if (str.Length <= 3)
            {
                count++;
            }
        }

        // Создаем новый массив нужного размера
        string[] newArray = new string[count];
        int index = 0;

        // Заполняем новый массив подходящими строками
        foreach (string str in inputArray)
        {
            if (str.Length <= 3)
            {
                newArray[index] = str;
                index++;
            }
        }

        // Выводим новый массив на экран
        Console.WriteLine("Новый массив строк с длиной <= 3:");
        foreach (string str in newArray)
        {
            Console.WriteLine(str);
        }
    }
}
