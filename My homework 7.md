Задача 47. Задайте двумерный массив размером m×n,
заполненный случайными вещественными числами.
m = 3, n = 4.
0,5  7    -2    -0,2
1    -3,3  8    -9,9
8    7,8   -7,1 9

void Array(int m, int n)
{
    double[,] array = new double[m, n];
    for (int i = 0; i < array.GetLength(0); i++)
    {
        for (int j = 0; j < array.GetLength(1); j++)
        {
            array[i, j] = new Random().Next(-10, 10) + new Random().NextDouble();
            Console.Write(array[i, j] + " ");
        }
        Console.WriteLine();
    }
}

Console.WriteLine("Введите размер m -  ");
int m = int.Parse(Console.ReadLine());
Console.WriteLine();
Console.WriteLine("Введите размер n -  ");
int n = int.Parse(Console.ReadLine());
Console.WriteLine();
Array(m, n);


Задача 50. Напишите программу, которая на вход
принимает число, и возвращает индексы этого
элемента или же указание, что такого элемента нет.
Например, задан массив:
 1 4 7 2
 5 9 2 3
 8 4 2 4
17 -> такого числа в массиве нет

int[,] FillArray(int x, int y)
{
    int[,] array = new int[x, y];
    for (int i = 0; i < array.GetLength(0); i++)
    {
        for (int j = 0; j < array.GetLength(1); j++)
        {
            array[i, j] = new Random().Next(10, 100);
            Console.Write(array[i, j] + " ");
        }
        Console.WriteLine();
    }
    return array;
}
void integer(int[,] array, int chislo)
{
    int count = 0;
    for (int i = 0; i < array.GetLength(0); i++)
    {
        for (int j = 0; j < array.GetLength(1); j++)
        {
            if (array[i, j] == chislo)
            {
                Console.WriteLine("Число " + chislo + " находится по координатам :  " + (i + 1) + "," + (j + 1));
                count++;
            }
        }

    }
    if (count == 0)
    {
        Console.WriteLine(chislo + " -> такого числа нет.");
    }
}


Console.WriteLine("Введите размер матрицы 'x' -  ");
int x = int.Parse(Console.ReadLine());
Console.WriteLine();
Console.WriteLine("Введите размер матрицы 'y' -  ");
int y = int.Parse(Console.ReadLine());
Console.WriteLine();
Console.WriteLine("Введите двузначное целое число для поиска в массиве -  ");
int chislo = int.Parse(Console.ReadLine());
Console.WriteLine();
integer(FillArray(x, y), chislo);


Задача 52. Задайте двумерный массив из целых чисел.
Найдите среднее арифметическое элементов в каждом
столбце.
Например, задан массив:
1 4 7 2
5 9 2 3
8 4 2 4
Среднее арифметическое каждого столбца: 4,6; 5,6; 3,6; 3.

Console.WriteLine("Введите размер x -  ");
int x = int.Parse(Console.ReadLine());
Console.WriteLine();
Console.WriteLine("Введите размер y -  ");
int y = int.Parse(Console.ReadLine());
Console.WriteLine();
Sum(FillArray(x, y));

int[,] FillArray(int x, int y)
{
    int[,] array = new int[x, y];
    for (int i = 0; i < array.GetLength(0); i++)
    {
        for (int j = 0; j < array.GetLength(1); j++)
        {
            array[i, j] = new Random().Next(0, 10);
            Console.Write(array[i, j] + " ");
        }
        Console.WriteLine();
    }
    return array;
}

void Sum(int[,] array)
{
    Console.WriteLine();
    for (int j = 0; j < array.GetLength(1); j++)
    {
        double sum = 0;
        for (int i = 0; i < array.GetLength(0); i++)
        {
            sum += array[i, j];
        }
        Console.WriteLine("Среднее арифметическое в колонке [" + (j + 1) + "] равно -  " + sum / array.GetLength(0));
    }

}
