using System;
using System.IO;

namespace delegate_practice
{
    class Program
    {

        public delegate void progressReporter(int percentComplete);

        public class Util
        {
            public static void hardWork(progressReporter p)
            {
                for (int i = 0; i < 10; i++)
                {
                    p(i * 10);
                    System.Threading.Thread.Sleep(100);
                }
            }
        }

        static void Main(string[] args)
        {
            progressReporter p = writeProgressToConsole;
            p += writeProgressToFile;
            Util.hardWork(p);


            void writeProgressToConsole(int percentComplete)
            {
                Console.WriteLine(percentComplete);
            }

            void writeProgressToFile(int percentComplete)
            {
              File.WriteAllText("progress.txt", percentComplete.ToString());
            }
        }
    }
}


