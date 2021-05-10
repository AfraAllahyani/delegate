using System;

namespace delegate_practice
{
    class Program
    {

        public delegate T Transformer<T>(T arg);

        public class Util
        {
            public static void Transform<T>(T[] values, Transformer<T> t)
            {
                for (int i = 0; i < values.Length; i++)
                {
                    values[i] = t(values[i]);
                }
            }
        }
        static void Main(string[] args)
        {
            int[] values = { 1, 2, 3 };
            Util.Transform(values, square);
            foreach (int i in values)
            {
                Console.WriteLine(i + " ");
            }

            int square (int x) { return x * x; }
        }
    }
}


