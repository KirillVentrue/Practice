Задача 2: Напишите программу, которая на вход принимает два числа и выдаёт, какое число большее, а какое меньшее.
a = 5; b = 7 -> max = 7
a = 2 b = 10 -> max = 10
a = -9 b = -3 -> max = -3

Console.WriteLine("Введите число A");
int numberA = int.Parse(Console.ReadLine());
Console.WriteLine("Введите число B");
int numberB = int.Parse(Console.ReadLine());
if (numberA < numberB)
Console.WriteLine("Число B больше");
else
Console.WriteLine("Число A больше");

Задача 4: Напишите программу, которая принимает на вход три числа и выдаёт максимальное из этих чисел.
2, 3, 7 -> 7
44 5 78 -> 78
22 3 9 -> 22

Console.WriteLine("Введите numberA");
int numberA = int.Parse(Console.ReadLine());
Console.WriteLine("Введите numberB");
int numberB = int.Parse(Console.ReadLine());
Console.WriteLine("Введите numberC");
int numberC = int.Parse(Console.ReadLine());
if (numberA > numberB && numberA > numberC) 
Console.WriteLine("numberA максимальное число");
else if (numberB > numberA && numberB > numberC) 
Console.WriteLine("numberB максимальное число");
else  
Console.WriteLine("numberC максимальное число");
