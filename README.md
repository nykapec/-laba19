
using System;


namespace ConsolApp6
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.Write("Введiть початкове значення X1min: ");
            double x1Min = Double.Parse(Console.ReadLine());

            Console.Write("Введiть кiнцеве значення X1max: ");
            double x1Max = double.Parse(Console.ReadLine());

            Console.Write("Введiть прирiст dX1: ");
            double dx1 = double.Parse(Console.ReadLine());

            Console.Write("Введiть початкове значення X2min: ");
            double x2Min = Double.Parse(Console.ReadLine());

            Console.Write("Введiть кiнцеве значення X2max: ");
            double x2Max = double.Parse(Console.ReadLine());

            Console.Write("Введiть прирiст dX2: ");
            double dx2 = double.Parse(Console.ReadLine());

            double y;
            double x1 = x1Min;
            double x2 = x2Min;

            double z = 0;

            while (x1 <= x1Max)
            {
                while (x2 <= x2Max)
                {
                    double numerator = Math.Pow(x2, 2) * x1 / x2;
                    double denominator = Math.Cos(Math.Pow(x1, 3) + Math.Pow(x2, 5)) + 2 * x1;
                    y = Math.Sqrt(numerator / denominator);
                    Console.WriteLine("x1 = {0:#.##}\tx2 = {1:#.##}\t\ty = {2:#.##}", x1, x2, y);

                    x2 = x2Min;
                    if (y > 0)
                    {
                        z *= y;
                    }
                    x2 += dx2;
                }
                x1 += dx1;

            }

            Console.WriteLine($"{z}");
            Console.ReadLine();
        }


    }

}
