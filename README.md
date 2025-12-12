# Veehoidla-tase
```
using System.ComponentModel.Design;

namespace Veehoidla_tase
{
    internal class Program
    {
        static void Main(string[] args)
        {
            string kasutajaNimi = KasutajaNimi();
            string correctUser = "siksseven";
            if (correctUser != kasutajaNimi)
            {
                Console.WriteLine(kasutajaNimi + ",Sinu nimi ei ole õige");
            }
            else
            {
                double veetase = 0d;
                Console.WriteLine("Tere" + correctUser + "Mis on veetaseme hetkeseis meetrites? ");
                bool errorState = false;
                do
                {
                    Console.WriteLine("Mis on sinu veetase anduril?:");
                    double andur = double.Parse(Console.ReadLine());
                    if (veetase < 1.00d && veetase > 4.25d)
                    {
                        errorState = true;
                        break;
                    }
                }
                while (veetase < 1.00d && veetase > 4.25d);
                HoiatusSõnum(veetase, errorState);

            }
        }


        private static void HoiatusSõnum(double veetase, bool errorState)
        {
            if (veetase >= 1.00d && veetase < 2.00d)
            {
                Console.WriteLine("VEETASE ON MADAL");
            }
            else if (veetase >= 2.0d && veetase < 3.5d)
            {
                Console.WriteLine("veetase on normaalne Paanikaks ei ole põhjust!!!");
            }
            else if (veetase >= 3.5d && veetase < 4.25d)
            {
                Console.WriteLine("tase on liiga kõrge, chll....");
            }
            else
            {
                errorState = true;
                Console.WriteLine("* anduri viga, kontrolli seadet *");
            }









        }
        private static string KasutajaNimi()
        {
            string sisestus = "";
            do
            {
                Console.WriteLine("Palun sisesta oma kustajanimi");
                sisestus = Console.ReadLine();
            } while (sisestus == "");
            return sisestus;
        }
    }
}
