Задача 64: Задайте значения M и N.
Напишите программу, которая выведет все натуральные
числа в промежутке от M до N.
M = 1; N = 5. -> ""1, 2, 3, 4, 5""
M = 4; N = 8. -> ""4, 6, 7, 8""

int m = 1;
int n = 5;
int NaturalInteger(int m, int n)
{
    if (m > n && n > 0)
    {
        return NaturalInteger(n, m);
    }
    else if (m > 0 && m < n)
    {
        System.Console.Write(m + " ");
        return NaturalInteger(m + 1, n);
    }
    else
    {
        return m;
    }
}
NaturalInteger(m, n);

Задача 66: Задайте значения M и N.
Напишите программу, которая найдёт сумму натуральных
элементов в промежутке от M до N.
M = 1; N = 15-> 120
M = 4; N = 8. -> 30

int m = 4;
int n = 8;
int NaturalInteger(int m, int n)
{
    int sum = 0;
    for (int i = m; i <= n; i++)
    {
        sum += i;
    }
    return sum;
}
System.Console.WriteLine(NaturalInteger(m, n));

Задача 68: Напишите программу вычисления функции
Аккермана с помощью рекурсии. Даны два неотрицательных
числа m и n.
m = 2, n = 3->A(m, n) = 9

int m = 2;
int n = 3;
int Akkerman(int m, int n)
{
    if (m == 0)
        return m + 1;
    else
      if ((m != 0) && (m == 0))
        return Akkerman(m - 1, 1);
    else
        return Akkerman(m - 1, Akkerman(m, m - 1));
}
Console.WriteLine(Akkerman(m, n));
