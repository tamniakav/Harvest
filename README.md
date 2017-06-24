# Harvest
Just another repository
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Harvest
{
    class Harvest
    {
        static void Main(string[] args)
        {
            int area = int.Parse(Console.ReadLine());
            double grapePerMeter = double.Parse(Console.ReadLine());
            int neededLiters = int.Parse(Console.ReadLine());
            int workers = int.Parse(Console.ReadLine());

            double grape = area * grapePerMeter;
            double wine = (grape * 0.40) / 2.5;

            if (wine >= neededLiters)
            {
                double wineOver = Math.Ceiling(wine - neededLiters);
                double winePerPerson = Math.Ceiling(wineOver / (double)workers);
                Console.WriteLine($"Good harvest this year! Total wine: {Math.Floor (wine)} liters.");
                Console.WriteLine($"{wineOver} liters left -> {winePerPerson} liters per person.");
            }
            else
            {
                double wineLess = Math.Floor(neededLiters - wine);
                Console.WriteLine($"It will be a tough winter! More {wineLess} liters wine needed.");
            }
        }
    }
}
