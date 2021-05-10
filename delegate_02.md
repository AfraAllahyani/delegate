using System;

namespace delegate_practice
{
    class Program
    {
        public delegate int Transformer(int x);

        public static int square(int x) { return x * x; }
        public static int cube(int x) { return x * x * x; }

        public static void Transform(int[] values, Transformer t)
        {
            for (int i = 0; i < values.Length; i++)
            {
                values[i] = t(values[i]);
            }
        }
        static void Main(string[] args)
        {
            int[] values = { 2, 3, 4 };
            Transform(values, cube);

            foreach (int i in values)
            {
                Console.WriteLine(i + " ");
            }


        }
    }
}