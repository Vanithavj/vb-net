# vb-net
//C# Program to print a Binary triangle <br>
using System;

namespace ex1 <br>
{ <br>
    class BinaryTriangle <br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
        int num, digit = 1;<br>    
        Console.WriteLine("\n Enter the number of lines");<br>
        num = Convert.ToInt32(Console.ReadLine());<br>
        for(int i=1;i<=num;i++)<br>
        {<br>
            for(int space=num-i;space>0;space--)<br>
            {<br>
                Console.Write(" \n ");<br>
            }<br>
            for(int j=0;j<i;j++)<br>
            {<br>
                Console.Write(digit + " ");<br>
                digit = (digit == 1) ? 0 : 1;<br>
            }<br>
                Console.Write("\n ");<br>
            }<br>
        }<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97940332/154630295-8cb45046-0155-4f1b-aa0d-5105d8c3568f.png)


//C# Program to Check Whether the Entered Number is an Amicable Number or Not.
using System;

namespace ex2<br>
{<br>
    class AmicableNumber<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int num1, num2, sum1 = 0, sum2 = 0;<br>
            Console.WriteLine("\n------------AMICABLE NUMBERS-------------\n");<br>
            Console.WriteLine("\n Enter the first number:");<br>
            num1 = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\n Enter the second number:");<br>
            num2 = Convert.ToInt32(Console.ReadLine());<br>
            for(int i=1;i<num1;i++)<br>
            {<br>
                if(num1%i==0)<br>
                {<br> sum1 += i;<br>
                }<br>
            }<br>
            for(int i=1;i<num2;i++)<br>
            { <br>if(num2%i==0)<br>
                { <br>sum2 += i;<br>
                }<br>
            }<br>
            if(sum1==num2 && sum2==num1)<br>
            {<br> Console.WriteLine("\n The numbers {0} and {1} are amicable.", num1, num2);<br>
            }<br>
            else<br>
            {<br> Console.WriteLine("\n The number {0} and {1} are not amicable.", num1, num2);<br>
            }<br>
        }<br>
    }<br>
}<br>

![image](https://user-images.githubusercontent.com/97940332/154629998-708d3c58-1242-4703-8af7-92079a38064e.png)
![image](https://user-images.githubusercontent.com/97940332/154630103-b4939130-b098-43ca-ace4-5045269d34d0.png)




