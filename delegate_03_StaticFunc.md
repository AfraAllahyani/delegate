using System;

namespace delegate_practice
{
    class Program
    {
        public delegate int Transformer(int x);

        class Test
        {
            public static int square (int x)
            {
                return x * x;
            }
        }
        static void Main(string[] args)
        {
            Transformer t = new Transformer(Test.square);
            Console.WriteLine(t(10));
        }
    }
}