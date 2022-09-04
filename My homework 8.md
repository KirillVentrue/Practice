Задача 54: Задайте двумерный массив.
Напишите программу, которая упорядочит по убыванию
элементы каждой строки двумерного массива.
Например, задан массив:
1 4 7 2
5 9 2 3
8 4 2 4
В итоге получается вот такой массив:
7 4 2 1
9 5 3 2
8 4 4 2

Console.WriteLine("Введите размер 'x' -  ");
int x = int.Parse(Console.ReadLine());
Console.WriteLine();
Console.WriteLine("Введите размер 'y' -  ");
int y = int.Parse(Console.ReadLine());
Console.WriteLine();
int[,] array = new int[x, y];

int[,] FillArray(int[,] array)
{
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

void BubbleSort(int[,] array)
{
    Console.WriteLine();
    for (int i = 0; i < array.GetLength(0); i++)
    {
        for (int j = 0; j < array.GetLength(1); j++)
        {
            for (int k = 0; k < array.GetLength(1) - 1; k++)
            {
                if (array[i, k] <= array[i, k + 1])
                {
                    int x = array[i, k];
                    array[i, k] = array[i, k + 1];
                    array[i, k + 1] = x;
                }
            }
            Console.Write(array[i, j] + " ");
        }
        System.Console.WriteLine();
    }
}
BubbleSort(FillArray(array));

Задача 56: Задайте прямоугольный двумерный массив.
Напишите программу, которая будет находить строку с
наименьшей суммой элементов.
Например, задан массив:
1 4 7 2
5 9 2 3
8 4 2 4
5 2 6 7
Программа считает сумму элементов в каждой строке
и выдаёт номер строки с наименьшей суммой элементов:
1 строка

Console.WriteLine("Введите размер 'x' -  ");
int x = int.Parse(Console.ReadLine());
Console.WriteLine();
Console.WriteLine("Введите размер 'y' -  ");
int y = int.Parse(Console.ReadLine());
Console.WriteLine();
int[,] array = new int[x, y];

int[,] FillArray(int[,] array)
{
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

void MinString(int[,] array)
{
    Console.WriteLine();
    int count = 0;
    double min = 100;
    double sum = 0;
    for (int i = 0; i < array.GetLength(0); i++)
    {
        for (int j = 0; j < array.GetLength(1); j++)
        {
            sum += array[i, j];
        }
        if (sum < min)
        {
            min = sum;
            count = i;
            sum = 0;
        }
    }
    System.Console.WriteLine("Строка с наименьшей суммой элементов - " + (count + 1));

}
FillArray(array);
MinString(array);

Задача 58: Задайте две матрицы. Напишите программу,
которая будет находить произведение двух матриц.
Например, даны 2 матрицы:
2 4 | 3 4
3 2 | 3 3
Результирующая матрица будет:
18 20
15 18

Console.WriteLine("Введите размер 'x' -  ");
int x = int.Parse(Console.ReadLine());
Console.WriteLine();
Console.WriteLine("Введите размер 'y' -  ");
int y = int.Parse(Console.ReadLine());
Console.WriteLine();
int[,] array0 = new int[x, y];
int[,] array1 = new int[x, y];

int[,] FillArray(int[,] array0)
{
    for (int i = 0; i < array0.GetLength(0); i++)
    {
        for (int j = 0; j < array0.GetLength(1); j++)
        {
            array0[i, j] = new Random().Next(0, 10);
            Console.Write(array0[i, j] + " ");
        }
        Console.WriteLine();
    }
    return array0;
}

void Produkt(int[,] array0, int[,] array1)
{
    int[,] matrix = new int[array0.GetLength(0), array0.GetLength(1)];
    for (int i = 0; i < array0.GetLength(0); i++)
    {
        for (int j = 0; j < array0.GetLength(1); j++)
        {
            matrix[i, j] = array0[i, j] * array1[i, j];
            System.Console.Write(matrix[i, j] + " ");
        }
        System.Console.WriteLine();
    }
}

System.Console.WriteLine("Первый массив :");
FillArray(array0);
System.Console.WriteLine();
System.Console.WriteLine("Второй массив :");
FillArray(array1);
System.Console.WriteLine();
System.Console.WriteLine("Произведение массивов :");
Produkt(array0, array1);

Задача 60. ...Сформируйте трёхмерный массив из
неповторяющихся двузначных чисел.
Напишите программу, которая будет построчно выводить
массив, добавляя индексы каждого элемента.
Массив размером 2 x 2 x 2
66(0,0,0) 25(0, 0, 1)
34(0, 1, 0) 41(0, 1, 1)
27(1, 0, 0) 90(1, 0, 1)
26(1, 1, 0) 55(1, 1, 1)

int[,,] array3D = new int[2, 2, 2];
int[,,] FillArray(int[,,] array3D)
{
    for (int i = 0; i < array3D.GetLength(0); i++)
    {
        for (int j = 0; j < array3D.GetLength(1); j++)
        {
            for (int k = 0; k < array3D.GetLength(2); k++)
            {
                array3D[i, j, k] = new Random().Next(0, 10);
                Console.Write(array3D[i, j, k] + "(" + i + "," + j + "," + k + ") ");
            }
            Console.WriteLine();
        }
    }
    return array3D;
}
FillArray(array3D);

Доп.задача 62.Напишите программу, которая заполнит
спирально массив 4 на 4.
Например, на выходе получается вот такой массив:
01 02 03 04
12 13 14 05
11 16 15 06
10 09 08 07

int n = 4;
int[,] sqareMatrix = new int[n, n];
int temp = 1;
int i = 0;
int j = 0;
while (temp <= sqareMatrix.GetLength(0) * sqareMatrix.GetLength(1))
{
    sqareMatrix[i, j] = temp;
    temp++;
    if (i <= j + 1 && i + j < sqareMatrix.GetLength(1) - 1)
        j++;
    else if (i < j && i + j >= sqareMatrix.GetLength(0) - 1)
        i++;
    else if (i >= j && i + j > sqareMatrix.GetLength(1) - 1)
        j--;
    else
        i--;
}

WriteArray(sqareMatrix);
void WriteArray(int[,] array)
{
    for (int i = 0; i < array.GetLength(0); i++)
    {
        for (int j = 0; j < array.GetLength(1); j++)
        {
            if (array[i, j] / 10 <= 0)
                Console.Write($" {array[i, j]} ");

            else Console.Write($"{array[i, j]} ");
        }
        Console.WriteLine();
    }
}
