using System;

namespace delegate_practice
{
    class Program
    {
        public delegate int Transformer(int x);

        class Test
        {
            public int square (int x)
            {
                return x * x;
            }
        }
        static void Main(string[] args)
        {
            Test test = new Test();
            Transformer t = new Transformer(test.square);
            Console.WriteLine(t(10));
        }
    }
}