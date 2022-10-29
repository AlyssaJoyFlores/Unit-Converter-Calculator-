//Title: Unit Converter (Calculator)
//Description: Unit Converter (Calculator) is a simple and convenient program with 12 converters and a standard calculator.
//Programmers:
//1. Alyssa Joy G. Flores
//2. Sharmaine S. Blanca
//3. John Cedrick A. Melegrito
//4. Evangeline P. Turno
//5. Lady Champagne B. Eranista
//Date Submitted: October 29, 2022
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace UnitConverterCalculator
{
    class unitConverter
    {
        public Stack<double> result = new Stack<double>();
        double total;

        public void mtocm(double a)
        {
            total = a * 100;
            Console.WriteLine("\n[RESULT]\nMeter to Centimeter: {0}cm", total);
            result.Push(total);
        }
        public void cmtom(double a)
        {
            total = a / 100;
            Console.WriteLine("\n[RESULT]\nCentimeter to Meter: {0}m", total);
            result.Push(total);
        }
        public void kmtom(double a)
        {
            total = a * 1000;
            Console.WriteLine("\n[RESULT]\nKilometer to Meter: {0}m", total);
            result.Push(total);
        }
        public void mtokm(double a)
        {
            total = a / 1000;
            Console.WriteLine("\n[RESULT]\nMeter to Kilometer: {0}km", total);
            result.Push(total);
        }
        public void kgtog(double a)
        {
            total = a * 1000;
            Console.WriteLine("\n[RESULT]\nKilogram to Gram: {0}gm", total);
            result.Push(total);
        }
        public void gtokg(double a)
        {
            total = a / 1000;
            Console.WriteLine("\n[RESULT]\nGram to Kilogram: {0}kg", total);
            result.Push(total);
        }
        public void smtoskm(double a)
        {
            total = a / 1000000;
            Console.WriteLine("\n[RESULT]\nSquare m to Square km: {0} ", total);
            result.Push(total);
        }
        public void skmtosm(double a)
        {
            total = a * 1000000;
            Console.WriteLine("\n[RESULT]\nSquare km to Square m: {0} ", total);
            result.Push(total);
        }
        public void ltoml(double a)
        {
            total = a * 1000;
            Console.WriteLine("\n[RESULT]\nLiter to Milliliter: {0}ml", total);
            result.Push(total);
        }
        public void mltol(double a)
        {
            total = a / 1000;
            Console.WriteLine("\n[RESULT]\nMilliliter to Liter: {0}l", total);
            result.Push(total);
        }
        public void ftoc(double a)
        {

            total = (a - 32) * 5 / 9;
            Console.WriteLine("\n[RESULT]\nFahrenheit to Celsius: {0}°C", total);
            result.Push(total);

        }

        public void ctof(double a)
        {
            total = ((a * 9) / 5 + 32);
            Console.WriteLine("\n[RESULT]\nCelsius to Fahrenheit: {0}°F", total);
            result.Push(total);
        }

        public void add(double a, double b)
        {
            total = a + b;
            Console.WriteLine("\n[RESULT]\nSum is:{0}", total);
            result.Push(total);
        }
        public void sub(double a, double b)
        {
            total = a - b;
            Console.WriteLine("\n[RESULT]\nDifference is:{0}", total);
            result.Push(total);
        }
        public void mul(double a, double b)
        {
            total = a * b;
            Console.WriteLine("\n[RESULT]\nProduct is:{0} ", total);
            result.Push(total);
        }
        public void div(double a, double b)
        {
            if (b != 0)
            {
                total = a / b;
                Console.WriteLine("\n[RESULT]\nQuotient is:{0}", total);
                result.Push(total);
            }
            else
            {
                Console.WriteLine("Error: Cannot divide by 0");
            }
        }

        public void undo()
        {
            if (result.Count == 0)
            {
                Console.WriteLine("UNDO IS NOT AVAILABLE");
            }
            result.Pop();
            total = result.Pop();
            Console.WriteLine("Running total:{0}", total);
        }
        public void clear()
        {
            while (result.Count != 0)
                result.Pop();
            total = 0;
            Console.WriteLine("Running total:{0}", total);
        }

        class Program
        {
            static int Main(string[] args)
            {
                unitConverter uc = new unitConverter();
                unitConverter calc = new unitConverter();
                Console.WriteLine("|*****UNIT CONVERTER (CALCULATOR)*****|");


                while (true)
                {
                    string choice, enter;

                    Console.Write("\n[a]Unit Conversion\n[b]Standard Calculator\n[c]Operation\nEnter your Choice: ");
                    enter = Console.ReadLine();

                    if (enter == "c")
                    {
                        Console.Write("CHOOSE OPERATION:\n[1]Exit\n[2]Undo\n[3]Clear\nCHOICE: ");
                        choice = Console.ReadLine();

                        if (choice == "1")
                        {
                            Console.WriteLine("Exiting program...\nProgram Terminated");
                            break;
                        }
                        else if (choice == "2")
                        {
                            uc.undo();
                        }
                        else if (choice == "3")
                        {
                            uc.clear();
                        }

                    }
                    else if (enter == "b")
                    {
                        Console.WriteLine("\n=====CALCULATOR=====");

                        Console.Write("\nWrite the first number: ");
                        double a = Convert.ToDouble(Console.ReadLine());

                        Console.Write("Write the second number:");
                        double b = Convert.ToDouble(Console.ReadLine());

                        Console.Write("CHOOSE OPERAND:\n[a]Add\n[b]Subtract\n[c]Multiply\n[d]Divide\nCHOICE: ");
                        string compute = Console.ReadLine();


                        if (compute == "a")
                            calc.add(a, b);
                        if (compute == "b")
                            calc.sub(a, b);
                        if (compute == "c")
                            calc.mul(a, b);
                        if (compute == "d")
                            calc.div(a, b);
                    }

                    else if (enter == "a")
                    {
                        Console.WriteLine("\n=====UNIT CONVERSION=====");

                        Console.Write("\nENTER VALUE TO CONVERT: ");
                        double a = Convert.ToDouble(Console.ReadLine());


                        Console.Write("CHOOSE OPERATION:\n[a] Meter to Centimeter\n[b] Centimeter to Meter\n[c] Kilometer to Meter\n[d] Meter to Kilometer\n[e] Kilogram to Gram\n[f] Gram to Kilogram\n[g] Square m to Square km\n[h] Square km to Square m\n[i] Liter to Milliliter\n[j] Milliliter to Liter\n[k] Fahrenheit to Celsius\n[l] Celsius to Fahrenheit\nCHOICE: ");
                        string convert = Console.ReadLine();


                        if (convert == "a")
                            uc.mtocm(a);
                        if (convert == "b")
                            uc.cmtom(a);
                        if (convert == "c")
                            uc.kmtom(a);
                        if (convert == "d")
                            uc.mtokm(a);
                        if (convert == "e")
                            uc.kgtog(a);
                        if (convert == "f")
                            uc.gtokg(a);
                        if (convert == "g")
                            uc.smtoskm(a);
                        if (convert == "h")
                            uc.skmtosm(a);
                        if (convert == "i")
                            uc.ltoml(a);
                        if (convert == "j")
                            uc.mltol(a);
                        if (convert == "k")
                            uc.ftoc(a);
                        if (convert == "l")
                            uc.ctof(a);

                    }
                    else
                    {
                        Console.WriteLine("Invalid Choice!");
                    }
                }

                return 0;
            }
        }
    }
}
