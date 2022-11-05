using System;

namespace _04Logistic
{
    internal class Program
    {
        static void Main(string[] args)
        {
            int n = int.Parse(Console.ReadLine());
            double average = 0;
            double prBus = 0;
            double prTruck = 0;
            double prTrain = 0;
            double allSize = 0;
            int size = 0;
            int price = 0;
            int allAmount = 0;
            for (int i = 0; i < n; i++)
            {
                size = int.Parse(Console.ReadLine());
                if (size <=3)
                {
                    price = 200 * size;
                    prBus += size;
                }
                else if(size>3 && size <=13)
                {
                    price = 175 * size;
                    prTruck += size;
                } 
                else if (size>13)
                {
                    price = 120 * size;
                    prTrain += size;
                }
                allAmount += price;
                price = 0;
            }
            allSize = prBus + prTruck + prTrain;
            average = allAmount / allSize;
            double p1 = prBus / allSize * 100;
            double p2 = prTruck / allSize * 100;
            double p3 = prTrain / allSize * 100;
            Console.WriteLine($"{average:f2}");
            Console.WriteLine($"{p1:f2}%");
            Console.WriteLine($"{p2:f2}%");
            Console.WriteLine($"{p3:f2}%");

        }
    }
}
