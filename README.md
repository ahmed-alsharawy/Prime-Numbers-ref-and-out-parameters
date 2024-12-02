# Prime-Numbers-ref-and-out-parameters
# Prime  Numbers and  Return Function With Ref  and  Out

namespace TASK_28_12
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Prime numbers from 1 to 100:");
            Console.Write("enter Start of range :" );
            int st_range=int.Parse( Console.ReadLine() );
            Console.Write("enter End of range :");
            int End_range = int.Parse(Console.ReadLine());


            for (int i = st_range; i <= End_range; i++)
            {
                if (IsPrime(i))
                {
                    Console.Write(i + " ");
            
                }
               
            }




            Console.WriteLine("-------------------ref---------------------------------------------------------");

            /*   */
            int a = 10, b = 20, max = 0;
            int min = MultipleReturns(a, b, ref max);
            Console.WriteLine("Minimum Value: " + min);
            Console.WriteLine("Maximum Value: " + max);


            Console.WriteLine("----------------------------OUT------------------------------------------------");
            int x = 10, y = 20, max2 = 0;
            int min1 = MultipleReturns2(x, y, out max2);
            Console.WriteLine("Minimum Value: " + min1);
            Console.WriteLine("Maximum Value: " + max2);

        }

        static bool IsPrime(int number)
        {
            if (number <= 1)
            {
                Console.WriteLine("enter value more than 1");
                return false;
            }

            for (int i = 2; i <= Math.Sqrt(number); i++)
            {
                if (number % i == 0) return false;
            }
            return true;
        }


        /*
         we can return multiple values from function  

                Reference parameters
                Output parameters
        
         */

        public static int MultipleReturns(int a, int b, ref int max)
        {
            if (a < b)
            {
                max = a;
                return b;
            }
            else
            {
                max = b;
                return a;
            }
        }





        public static int MultipleReturns2(int a, int b, out int max)
        {
            if (a < b)
            {
                max = a;
                return b;
            }
            else
            {
                max = b;
                return a;
            }
        }

    }
}
