// Задайте значения M и N. Напишите программу, которая выведет все натуральные числа в промежутке от M до N.
// Использовать рекурсию, не использовать циклы

using System;
namespace Task2
{
    class Test
    {
        static int SumNumbers(int M, int N)
        {
            if (M == 0) return (N * (N + 1)) / 2;            // Если M равно нулю
            else if (N == 0) return (M * (M + 1)) / 2;       // Если N равно нулю
            else if (M == N) return M;                       // Если M=N
            else if (M < N) return N + SumNumbers(M, N - 1); // Если M<N
            else return N + SumNumbers(M, N + 1);            // Если M>N
        }
        static void Main(string[] args)
        {
            Console.Write("M = ");
            int M = int.Parse(Console.ReadLine());
            Console.Write("N = ");
            int N = int.Parse(Console.ReadLine());
            Console.WriteLine($"Result, S = {SumNumbers(M, N)}");
            Console.ReadLine();
        }
    }
}

//Задача 2: Напишите программу вычисления функции Аккермана с помощью рекурсии. Даны два неотрицательных числа m и n.
using System; 
 
class Program 
{ 
    static void Main() 
    { 
        Console.Write("Введите неотрицательное число m: "); 
        int m = int.Parse(Console.ReadLine()); 
 
        Console.Write("Введите неотрицательное число n: "); 
        int n = int.Parse(Console.ReadLine()); 
 
        int result = AckermannFunction(m, n); 
        Console.WriteLine($"Значение функции Аккермана для ({m}, {n}) равно: {result}"); 
    } 
 
    static int AckermannFunction(int m, int n) 
    { 
        if (m == 0) 
            return n + 1; 
        else if (n == 0) 
            return AckermannFunction(m - 1, 1); 
        else 
            return AckermannFunction(m - 1, AckermannFunction(m, n - 1)); 
    } 
}


// Задайте произвольный массив. Выведете его элементы, начиная с конца. Использовать рекурсию, не использовать циклы.
using System; 
 
class Program 
{ 
    static void Main() 
    { 
        int[] myArray = { 10, 20, 30, 40, 50 }; 
 
        Console.WriteLine("Элементы массива, начиная с конца:"); 
        PrintArrayReverse(myArray, myArray.Length - 1); 
    } 
 
    static void PrintArrayReverse(int[] arr, int index) 
    { 
        if (index >= 0) 
        { 
            Console.Write(arr[index] + " "); 
            PrintArrayReverse(arr, index - 1); 
        } 
    } 
}
