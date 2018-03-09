# OMG-# 
using System;
using static System.Console;

namespace GreenVilleRevenue
{
    class Program
    {
        static void Main(string[] args)
        {
            // Variables
            const double ENTRANCE_FEE = 25.00;
            const int MINIMUM = 0;
            const int MAX = 30;
            string strUserInput;
            int iLastYear = -1;
            int iThisYear = -1;
            double dblRevenue;
            bool bIsThisYearGreater;

            // Prompt user for last year's number of constestants
            do
            {
                Write("Enter the number of the contestants last year (Between {0} and {1} contestants) >> ", MINIMUM, MAX);
                strUserInput = ReadLine();
                iLastYear = Convert.ToInt32(strUserInput);
            } while (iLastYear < MINIMUM || iLastYear > MAX);
            
            Write("Enter number of contestants last year >> ");
            strUserInput = ReadLine();
            iLastYear = Convert.ToInt32(strUserInput);

            // Prompt user for this year's number of contestants
            while(iThisYear < MINIMUM || iThisYear > MAX)
            {
                Write("Enter the number of the contestants this year (Between {0} and {1} contestants) >> ", MINIMUM, MAX);
                strUserInput = ReadLine();
                iThisYear = Convert.ToInt32(strUserInput);
            }
            Write("Enter number of contestants this year >> ");
            strUserInput = ReadLine();
            iThisYear = Convert.ToInt32(strUserInput);

            for (int i = 0; i < 10; i++)
            {
                WriteLine("Number = {0}", i);
            }

            // Display all input data
            WriteLine("\nLast year's competition had {0} contestants, and this year's has {1} contestants", iLastYear, iThisYear);

            // Compute revenue expected this year
            dblRevenue = iThisYear * ENTRANCE_FEE;

            // Display revenue expected this year
            WriteLine("\nRevenue expected last year is {0}", dblRevenue.ToString("C"));

            // Display comparison this year to last year
            bIsThisYearGreater = iThisYear > iLastYear;
            WriteLine("\nIts {0} that this year's competition is larger than last year", bIsThisYearGreater);
        }
    }
}
