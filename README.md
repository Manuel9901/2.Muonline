// 2.Muonline

using System;

namespace MuOnline
{
    class MainClass
    {
        public static void Main(string[] args)
        {
            string[] rooms = Console.ReadLine().Split('|');
            int healt = 100;
            int coin = 0;

            for (int i = 0; i < rooms.Length; i++)
            {
                string[] splited = rooms[i].Split(' ');
                string name = splited[0];
                int numbers =int.Parse( splited[1]);

               if(name == "potion")
                {
                    int currentHealt = healt;
                    healt += numbers;
                    if(healt > 100)
                    {
                        healt = 100;
                    }
                    int total = healt - currentHealt;
                        Console.WriteLine($"You healed for {total} hp.\nCurrent health: {healt} hp.") ;
                }
               else if(name == "chest")
                {
                    coin += numbers;
                    Console.WriteLine($"You found {numbers} bitcoins.");
                }
                else
                {
                    healt -= numbers;

                    if (healt <= 0)
                    {
                        Console.WriteLine($"You died! Killed by {name}.\n Best room: {i + 1}");
                        return;
                    }
                    else
                    {

                    Console.WriteLine($"You slayed {name}.");
                    }
                }
            }
            Console.WriteLine($"You've made it!\nBitcoins: {coin}\nHealth: {healt}");
           
        }
    }
}
