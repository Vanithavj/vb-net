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
![image](https://user-images.githubusercontent.com/97940332/154628895-da89714d-7e4f-4de7-acb4-b745a6f0dab3.png)


