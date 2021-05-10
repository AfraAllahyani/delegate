using System;

namespace delegate_practice
{
    class Program
    {
        delegate int Transformer(int x);
        static int square(int x) { return x * x; }

        static void Main(string[] args)
        {
            Transformer t = square;
            int result = t(3);
            Console.WriteLine(result);
        }
    }
}