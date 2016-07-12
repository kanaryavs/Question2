using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Question2
{
    class Program
    {
        static void Main(string[] args)
        {
            int input;
            do
            {
                input = Int32.Parse(Console.ReadLine());
            } while (input < 0 || input > 1000);

            int[,] array = new int[input, input];

            for (int i = 0; i < input; i++)
            {
                string[] row = Console.ReadLine().Split(' ');
                for (int j = 0; j < input; j++)
                {
                    array[i, j] = Int32.Parse(row[j]);
                }
            }
            for (int i = 0; i < input; i++)
            {
                for (int j = 0; j < input; j++)
                {
                    int limit = input - 1;
                    if (i == 0 && j == 0)
                    {
                        Console.Write(array[i, j + 1] + array[i + 1, j + 1] + array[i + 1, j]);
                    }
                    else if (i == 0 && j == limit)
                    {
                        Console.Write(array[i, j - 1] + array[i + 1, j] + array[i + 1, j - 1]);
                    }
                    else if (i == 0 && j < limit)
                    {
                        Console.Write(array[i, j - 1] + array[i + 1, j - 1] + array[i + 1, j] + array[i + 1, j + 1] + array[i, j + 1]);
                    }
                    else if (i < limit && j == 0)
                    {
                        Console.Write(array[i - 1, j] + array[i - 1, j + 1] + array[i, j + 1] + array[i + 1, j + 1] + array[i + 1, j]);
                    }
                    else if (i < limit && j == limit)
                    {
                        Console.Write(array[i - 1, j] + array[i - 1, j - 1] + array[i, j - 1] + array[i + 1, j - 1] + array[i + 1, j]);
                    }
                    else if (i == limit && j == 0)
                    {
                        Console.Write(array[i - 1, j] + array[i - 1, j + 1] + array[i, j + 1]);
                    }
                    else if (i == limit && j < limit)
                    {
                        Console.Write(array[i - 1, j - 1] + array[i - 1, j] + array[i - 1, j + 1] + array[i, j - 1] + array[i, j + 1]);
                    }
                    else if (i == limit && j == limit)
                    {
                        Console.Write(array[i, j - 1] + array[i - 1, j - 1] + array[i - 1, j]);
                    }
                    else if (i == limit && j == 0)
                    {
                        Console.Write(array[i, j + 1] + array[i - 1, j] + array[i - 1, j + 1]);
                    }
                    else
                    {
                        Console.Write(array[i - 1, j - 1] + array[i - 1, j] + array[i - 1, j + 1] + array[i, j - 1] + array[i, j + 1] + array[i + 1, j + 1] + array[i + 1, j] + array[i + 1, j - 1]);
                    }
                    Console.Write(" ");
                }
                Console.WriteLine();
            }
        }
    }
}
