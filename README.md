# vb-net
**1.//C# Program to print a Binary triangle <br>**

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
![image](https://user-images.githubusercontent.com/97940332/154631843-cabcb888-1532-4f2f-bed3-253ad3a612d3.png)


**2.//C# Program to Check Whether the Entered Number is an Amicable Number or Not.**

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
![image](https://user-images.githubusercontent.com/97940332/154632095-30232a1e-0c1a-42a8-8513-d3dcffee1c82.png)
![image](https://user-images.githubusercontent.com/97940332/154632183-5baa4312-fa57-4bf0-96b8-368ee620dabd.png)

**3.//C# Program to Illustrate multilevel inheritence with virtual methods  (displaying student details).**

using System;
namespace ex3<br>
{<br>
    class PersonalDetails<br>
    {<br>
        string name;<br>
        int age;<br>
        string gender;<br>
        public PersonalDetails(string name, int age, string gender)<br>
        {<br>
            this.name = name;<br><br>
            this.age = age;<br>
            this.gender = gender;<br>
        }<br>
        public virtual void display()<br>
        {<br>
            Console.WriteLine("\n----------PERSONAL DETAILS------------\n");<br>
            Console.WriteLine("Name     :" + name);<br><br>
            Console.WriteLine("Age      :" + age);<br>
            Console.WriteLine("Gender   :" + gender);<br>
        }<br>
    }<br>
    class CourseDetails : PersonalDetails<br>
    {<br>
        int regno;<br>
        string course;<br>
        int semester;<br>
        public CourseDetails(string name, int age, string gender, int regno, string course, int semester) : base(name, age, gender)<br>
        {<br>
            this.regno = regno;<br>
            this.course = course;<br>
            this.semester = semester;<br>
        }<br>

        public override void display()<br>
        {<br>
            base.display();<br>
            Console.WriteLine("\n---------COURSE DETAILS------------\n");<br>
            Console.WriteLine("Register Number:" + regno);<br>
            Console.WriteLine("Course         :" + course);<br>
            Console.WriteLine("Semester       :" + semester);<br>
        }<br>
    }<br>

    class MarksDetails : CourseDetails<br>
    {<br>
        int[] marks = new int[5];<br>
        int total;<br>
        float average;<br>
        string grade;<br>
        int flagFail;<br>
        public MarksDetails(string name, int age, string gender, int regno, string course, int semester, int[] marks) : base(name, age, gender, regno, course, semester)<br>
        {<br>
            total = 0;<br>
            for (int i = 0; i < 5; i++)<br>
            { <br>this.marks[i] = marks[i];<br>
                total += marks[i];<br>
                if (marks[i] < 35)<br>
                {<br>
                    flagFail = 1;<br>
                }<br>
            }<br>
            Calculate();<br>
        }<br>
        private void Calculate()<br>
        {<br>
            average = total/5;<br>
            if (flagFail == 1 || average < 40)<br>
                grade = "Fail";<br>
            else if (average >= 70)<br>
                grade = "Distinction";<br>
            else if (average >= 60)<br>
                grade = "First class";<br>
            else if (average >= 50)<br>
                grade = "Second class";<br>
            else grade = "Pass class";<br>
        }<br>
        public override void display()<br>
        {<br>
            base.display();<br>
            Console.WriteLine("\n------------MARKS DETAILS-------------\n");<br>
            Console.WriteLine("Marks in 5 subjects:");<br>
            for (int i = 0; i < 5; i++)<br>
                Console.WriteLine(marks[i] + "    ");<br>
            Console.WriteLine();<br>
            Console.WriteLine("Total    :" + total);<br>
            Console.WriteLine("Average  :" + average);<br>
            Console.WriteLine("Grade    :" + grade);<br>
        }<br>
    }<br>
    class Multilevel<br>
    {<br>
        public static void Main(String[] args)<br>
        {<br>
            MarksDetails student = new MarksDetails("Abijith", 22, "Male", 2021001, "M.Sc", 5, new int[] { 77, 80, 98, 95, 90 });<br>
            student.display();<br>
        }<br>
      }<br>
    }<br>
     ![image](https://user-images.githubusercontent.com/97940332/154631537-967c59f3-6374-46ea-b0c8-353f167d84ec.png)
    
   ** 4.//C# Program to Create a Gray code**
    
    using System;
    namespace ex4<br>
    {<br>
    class GrayCode<br>
    {<br>
        static int getGray(int n)<br>
        {<br>
            return n ^ (n >> 1);<br>
        }<br>
        static void Main(string[] args)<br>
        {<br>
            int Inputnum, Graynum;<br>
            Console.Write("\nEnter thr decimal number:");<br>
            Inputnum = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\nBinary equivalent of {0}: {1}", Inputnum, Convert.ToString(Inputnum, 2));<br>
            Graynum = getGray(Inputnum);<br>
            Console.WriteLine("\n Gray code equivalent of {0}:{1}",Inputnum,Convert.ToString(Graynum,2));<br>
        }<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97940332/154633208-69079708-76f8-4520-a498-13545af1eb86.png)

**5.//C# program to calculate volume of 2 boxes and find the resultant volume after addition of 2 boxes by implementing operator overloading.**

using System;
namespace ex5<br>
{<br>
    class Box<br>
    {<br>
        float width;<br>
        float height;<br>
        float length;<br>
        public float Volume<br>
        {<br>
            get { return width * height * length; }<br>
        }<br>
        public Box(float width,float height,float length)<br>
        { <br>
            this.width = width;<br>
            this.height = height;<br>
            this.length = length;<br>
        }<br>
        public static float operator+(Box box1,Box box2)<br>
        {<br>
            return box1.Volume + box2.Volume;<br>
        }<br>
        public override string ToString()<br>
        {<br>
            return "Box with width " + width + ",height " + height + " and length " + length;<br>
        }<br>
       
    }<br>
    class OperatorOverloading<br>
    {<br>
        public static void Main()<br>
        {<br>
            Box box1 = new Box(10,20,30);<br>
            Box box2 = new Box(25,32,15);<br>
            Console.WriteLine("Volume of {0} is:{1} ", box1, box1.Volume);<br>
            Console.WriteLine("Volume of {0} is:{1} ", box2, box2.Volume);<br>
            Console.WriteLine("Volume after adding boxes:{0} ", box1 + box2);<br>
        }<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97940332/154633872-d548148e-0658-4e2d-a431-92600e16f3fc.png)


**6.//C# program to implement principles of delegates(converting input storing to uppercase first,last and entire string).**

using System;

namespace ex6<br>
{<br>
    class Delegates<br>
    {<br>
        delegate string UppercaseDelegate(string input);<br>
        static string UppercaseFirst(string input)<br>
        {<br>
            char[] buffer = input.ToCharArray();<br>
            buffer[0] = char.ToUpper(buffer[0]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseLast(string input)<br>
        {<br>
             char[] buffer = input.ToCharArray();<br>
            buffer[buffer.Length - 1] = Char.ToUpper(buffer[buffer.Length - 1]);<br>
            return new string(buffer);<br>
        }<br>
        static string UppercaseAll(string input)<br>
        {<br>
            return input.ToUpper();<br>
        }<br>
        static void WriteOutput(string input,UppercaseDelegate  del)<br>
        {<br>
            Console.WriteLine("Input String :{0} ", input);<br>
            Console.WriteLine("Output string :{0} ", del(input));<br>
        }<br>
        static void Main()<br>
        {<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseFirst));<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseLast));<br>
            WriteOutput("tom", new UppercaseDelegate(UppercaseAll));<br>
            Console.ReadLine();<br>
            }<br>
      }<br>
}<br>
![image](https://user-images.githubusercontent.com/97940332/154635266-afef9f08-b5d5-40f8-9dc3-4d49e6a9319e.png)


**7.//C# program to generate register number automatically for 100 students using static constructor**
  
  using System;
   namespace ex7<br>
   {<br>
    class RegisterNum<br>
    {<br>
        int regNo;<br>
        static int startNum;<br>

        static RegisterNum()<br>
        {<br>
            startNum = 20210000;<br>
        }<br>
        RegisterNum()<br>
        {<br>
            regNo = ++startNum;<br>
        }<br>
        public static void Main(string[]args)<br>
        {<br>
            for (int i = 0; i < 100; i++)<br>
                {<br>
                RegisterNum student = new RegisterNum();<br>
                Console.WriteLine("Student {0}:{1}", i + 1, student.regNo);<br>
                }<br>
               }<br>
             }<br>
           }<br>
![image](https://user-images.githubusercontent.com/97940332/154636098-361d57e9-1cd5-456b-ab9e-0ab89d6decf1.png)
![image](https://user-images.githubusercontent.com/97940332/154636200-2de71c06-b38f-4207-a810-56b2496f40ad.png)


**8.//C# program to find the frequency of the word "is" in a given sentence**

using System;

namespace ex8<br>
{<br>
    class FrequencyIS<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int count = 0;<br>
            string inputstring;<br>
            Console.WriteLine("\n---------Frequency of word 'is'------------");<br>
            Console.WriteLine("\n Enter the input string: ");<br>
            inputstring = Console.ReadLine();<br>
            char[] separator = { ',', ' ', '.', '!', '\n' };<br>
            string teststring = inputstring.ToLower();<br>
            String[] outcomes = teststring.Split(separator);<br>

            foreach(String s in outcomes)<br>
            {<br>
                Console.WriteLine(s);<br>
                if (s == "is")<br>
                    count++;<br>
            }<br>
            Console.WriteLine("\nNumber of 'is' in '" + inputstring + "'is:" + count);<br>
        }<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97940332/154637213-d25719c5-6732-4179-8483-d7358e2037cf.png)


**9.C# program that benchmark 2D,jagged array allocation**

using System;
using System.Diagnostics;

namespace ex9<br>
{<br>
    class BenchmarkAllocation<br>
    {<br>
        const int _max = 100000;<br>
        static void Main(string[] args)<br>
        {<br>
            var Arr2D = new int[100, 100];<br>
            var ArrJagged = new int[100][];<br>
            for (int i = 0; i <100; i++)<br>
            {<br>
                ArrJagged[i] = new int[100];<br>
            }<br>
            var Stopwatch2D = Stopwatch.StartNew();<br>
            for (int i = 0; i < _max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>
                {<br>
                    for (int k = 0; k < 100; k++)<br>
                    {<br>
                        Arr2D[j, k] = k;<br>
                    }<br>
                }<br>
            }<br>
            Stopwatch2D.Stop();<br>
            var StopwatchJagged = Stopwatch.StartNew();<br>
            for (int i = 0; i < _max; i++)<br>
            {<br>
                for (int j = 0; j < 100; j++)<br>
                {<br>
                    for (int k = 0; k < 100; k++)<br>
                    {<br>
                        ArrJagged[j][k] = k;<br>
                    }<br>
                }<br>
            }<br>
            StopwatchJagged.Stop();<br>
            Console.Write("\nTime taken for allocation in case of 2D array:");<br>
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + "milliseconds");<br>
            Console.Write("\n Time taken for allocation in case of jagged array;");<br>
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + "milliseconds");<br>
        }<br>
    }<br>
}<br>
![image](https://user-images.githubusercontent.com/97940332/154638094-032fb71a-0cd2-414b-b7f3-a321f8214aea.png)


**10.//C# program to find the sum of the values on Diagonal of the Matrix.**

using System;<br>
namespace ex10<br>
{<br>
    class SumOfDiagonals<br>
    {<br>
        static void Main(string[] args)<br>
        {<br>
            int MaxRow, MaxCol, sum = 0;<br>
            int[,] matrix;<br>
            Console.WriteLine("\n---------SUM OF DIAGONAL OF A MATRIX---------\n");<br>
            Console.WriteLine("\n Enter the number of rows:");<br>
            MaxRow = Convert.ToInt32(Console.ReadLine());<br>
            Console.WriteLine("\nEnter the number of Coloumns:");<br>
            MaxCol = Convert.ToInt32(Console.ReadLine());<br>
            if(MaxRow!=MaxCol)<br>
            { <br>
                Console.WriteLine("\nThe Dimensiond entered are not of square matrix");<br>
                Console.WriteLine("\nExiting the program----");<br>
                return;<br>
            }<br>
            matrix = new int[MaxRow, MaxCol];<br>
            for(int i=0;i<MaxRow;i++)<br>
            {<br>
                for(int j=0;j<MaxCol;j++)<br>
                {<br>
                    Console.WriteLine("\n Enter the ({0},{1})th element of the matrix:",(i + 1),(j + 1));<br>
                    matrix[i, j] = Convert.ToInt32(Console.ReadLine());<br>
                }<br>
            }<br>
            Console.WriteLine("\n The entered Matrix is:");<br>
            for(int i=0;i<MaxRow;i++)<br>
            {<br>
                for(int j=0;j<MaxCol;j++)<br>
                {<br>
                    Console.Write(" " + matrix[i, j]);<br>
                    if(i==j)<br>
                    {<br>
                        sum += matrix[i, j];<br>

                    }<br>
                }<br>
                Console.WriteLine();<br>
            }<br>
            Console.WriteLine("\n The sum of Diagonal is: " + sum);<br>
        }<br>
    }<br>
}<br>


**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/155669840-f659019f-48bd-4ead-a9cc-90aa85e14f51.png)


**11.C# program to create a file, check the existence of a file, and Read the contents of the file.**

using System;<br>
using System.IO;<br>
namespace ex11<br>
{<br>class FileRead<br>
{<br>public static void Main()<br>{<br>
string fileName;<br>
while (true)<br>
{<br> Console.WriteLine("\n --------MENU-------\n");<br>
      Console.WriteLine("\n 1.Create a File");<br>
      Console.WriteLine("\n 2.Existence of the File\n");<br>
       Console.WriteLine("\n 3.Read the contents of the File\n");<br>
       Console.WriteLine("\n 4.Exit\n");<br>
                Console.WriteLine("\n Enter your choice:");<br>
                int ch = int.Parse(Console.ReadLine());<br>
                switch (ch)<br>
                {<br>
                    case 1:<br>
                        Console.Write("\nEnter the file name to create:");<br>
                        fileName = Console.ReadLine();<br>
                        Console.WriteLine("\nWrite the contents to the file:\n");<br>
                        string r = Console.ReadLine();<br>
                        using (StreamWriter fileStr = File.CreateText(fileName))<br>
                        {<br>
                            fileStr.WriteLine(r);<br>
                        }<br>
                        Console.WriteLine("File is created----");<br>
                        break;<br>
                    case 2:<br>
                        Console.WriteLine("\nEnter the file name:");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            Console.WriteLine("File exists------");<br>
                        }<br>
                        else<br>
                        {<br>
                            Console.WriteLine("File does not exist in the current directory!");<br>
                        }<br>
                        break;<br>
                    case 3:<br>
                        Console.Write("Enter the file name to read the contents:\n");<br>
                        fileName = Console.ReadLine();<br>
                        if (File.Exists(fileName))<br>
                        {<br>
                            using (StreamReader sr = File.OpenText(fileName))<br>
                            {<br>
                                string s = " ";<br>
                                Console.WriteLine("Here is the content of the file:");<br>
                            while ((s = sr.ReadLine()) != null)<br>
                            {<br>
                                Console.WriteLine(s);<br>
                            }<br>
                            Console.WriteLine(" ");<br>
                        }<br>
                }<br>
                else<br>
            {<br>
                Console.WriteLine("\nFile does not exists");<br>
            }<br>
            break;<br>
                case 4:<br>
                    Console.WriteLine("Exiting-----");<br>
                return;<br>
            default:<br>
                Console.WriteLine("\n Invalid choice");<br>
            break;<br>
        }<br>
    }<br>}<br>
    }<br>
}<br>


**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/155671200-bf96f4b2-77c8-4d76-8d40-5a1832b66872.png)
![image](https://user-images.githubusercontent.com/97940332/155671492-7ed6fb8c-2fbf-4d6b-a1b3-15d4eaf17dbe.png)
![image](https://user-images.githubusercontent.com/97940332/155671822-8d6f6fcf-0b35-4bd9-a810-62719de766a6.png)


12.C# program to perform File comparison


**13.C# program to implememnt IComparable Interface**

using System;<br>
namespace ex13<br>
{<br>
class Fraction : IComparable <br>
    {<br>
        int z, n;<br>
        public Fraction(int z,int n)<br>
        {<br>
            this.z = z;<br>
            this.n = n;<br>
        }<br>
        public static Fraction operator +(Fraction a,Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);<br>
        }<br>
        public static Fraction operator*(Fraction a,Fraction b)<br>
        {<br>
            return new Fraction(a.z * b.z, a.n * b.n);<br>
        }<br>
        public int CompareTo(Object obj)<br>
        { Fraction f = (Fraction)obj;<br>
            if ((float)z/n < (float)f.z / f.n)<br>
                return -1;<br>
            else if ((float)z / n > (float)f.z / f.n)<br>
                return 1;<br>
            else<br>
                return 0;<br>
        }<br>
        public override string ToString()<br>
        {<br>
            return z + "/" + n;<br>
        }<br>
    }<br>
    class ICompInterface<br>
    {<br>
        public static void Main()<br>
        {<br>
            Fraction[] a =<br>
            {<br>
                new Fraction(5,2),<br>
                 new Fraction(29,6),<br>
                  new Fraction(4,5),<br>
                   new Fraction(10,8),<br>
                    new Fraction(34,7),<br>
            };<br>
            Array.Sort(a);<br>
            Console.WriteLine("Implementing the Icomparable Interface in " + "Displaying fractions:");<br>
            foreach(Fraction f in a)<br>
            {<br> Console.WriteLine(f + " ");<br>
            }<br>
            Console.WriteLine();<br>
            Console.ReadLine();<br>
        }<br>
    }<br>
}<br>


**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/156502834-78a9360d-e51c-4d0f-8323-af3fba02d37a.png)


**14.C# program to Create thread pools.**
using System;<br>
using System.Threading;<br>
namespace ex14<br>
{<br>
    class  ThreadPoolProg<br>
    {<br>
        public void ThreadFun1(object obj)<br>
        {<br>
            int loop = 0;<br>
            for (loop = 0; loop <= 4; loop++)<br>
            {<br>
                Console.WriteLine("Thread 1 is executing");<br>
            }<br>
        }<br>
        public void ThreadFun2(object obj)<br>
            { <br>
            int loop = 0;<br>
            for( loop=0;loop<=4;loop++)<br>
                { <br>
                Console.WriteLine("Thread 2 is executing");<br>
                }<br>
            }<br>
            public static void Main(string[]args)<br>
            { <br>
                ThreadPoolProg TP = new ThreadPoolProg();<br>
            for(int i=0;i<2;i++)<br>
                {<br>
                    ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));<br>
                    ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));<br>

                }<br>
                Console.ReadKey();<br>
            }<br>
        }<br>
    }<br>
    <br>
    **OUTPUT:**
    
    
    ![image](https://user-images.githubusercontent.com/97940332/156503350-aedab4f7-457e-43c5-a9b7-77a3777b6244.png)


**15.C# Program to demonstrate error handling using Try,Catch and Finally block.
**
using System;
namespace ex15  <br>
{  <br>
    class ExceptionHandling  <br>
    {  <br> 
        static void Main()  <br>
        {  <br>
            Age a = new Age();  <br>
            try   <br>
            {  <br>
                a.DisplayAge();  <br>
            }  <br>
            catch(AgeIsNegativeException e)  <br>
            {  <br>
                Console.WriteLine("AgeIsNegativeException:{0}", e.Message);  <br>
            }  <br>
            finally  <br>
            {  <br>
                Console.WriteLine("Execution of Finally block is done.");  <br>
            }  <br>
        }  <br>
    }  <br>
}  <br>
public class AgeIsNegativeException : Exception  <br>
{  <br>
    public AgeIsNegativeException(string message) : base(message)  <br>
    {  <br>

    }  <br>
}  <br>
public class Age  <br>
{  <br>
    int age = 5;  <br>
    public void DisplayAge()  <br>
    {  <br>
        if (age < 0)  <br>
            throw (new AgeIsNegativeException("Age can not be negative"));  <br>
        else  <br>
            Console.WriteLine("Age is:{0}", age);  <br>
    }  <br>
}  <br>
  <br>
    <br>
    **OUTPUT:**
    
    ![image](https://user-images.githubusercontent.com/97940332/156504011-ba05c92d-614e-44c0-a77c-fca078dbf371.png)


**16.C# program to find the fibonacci series.**
using System; <br>
public class FibonacciExample <br>
{ <br>
    public static void Main(string[] args) <br>
    { <br>
        int n1 = 0, n2 = 1, n3, i, number; <br>
        Console.Write("Enter the number of elements: "); <br>
        number = int.Parse(Console.ReadLine()); <br>
        Console.Write(n1 + " " + n2 + " "); <br>    
        for (i = 2; i < number; ++i) <br> 
        { <br>
            n3 = n1 + n2; <br>
            Console.Write(n3 + " "); <br>
            n1 = n2; <br>
            n2 = n3; <br>
        } <br>
    } <br>
} <br>
 <br>
  <br>
  **OUTPUT:**
  
  ![image](https://user-images.githubusercontent.com/97940332/156504356-a0303f71-de78-44c7-9be7-0036c58e46c5.png)


**17. C# program to Check whether given number is prime or not**

using System;
public class PrimeNumberExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, i, m = 0, flag = 0;<br>
        Console.Write("Enter the Number to check Prime: ");<br>
        n = int.Parse(Console.ReadLine())<br>;
        m = n / 2;<br>
        for (i = 2; i <= m; i++)<br>
        {<br>
            if (n % i == 0)<br>
            {<br>
                Console.Write("Number is not Prime number.");<br>
                flag = 1;<br>
                break;<br>
            }<br>
        }<br>
        if (flag == 0)<br>
            Console.Write("Number is Prime number.");<br>
    }<br>
}<br>
<br>
<br>
**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/156504698-26a29b51-8c9f-4fdb-9da4-2ca28fe5d93a.png)
![image](https://user-images.githubusercontent.com/97940332/156504741-70e2356a-99dd-47dc-9fb8-399b1ec65c3b.png)


**18.C# program to check whether the given number is palindrom or not.**


using System;
public class PalindromeExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, r, sum = 0, temp;<br>
        Console.Write("Enter the Number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        temp = n;<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            sum = (sum * 10) + r;<br>
            n = n / 10;<br>
        }<br>
        if (temp == sum)<br>
            Console.Write("Number is Palindrome.");<br>
        else<br>
            Console.Write("Number is not Palindrome");<br>
    }<br>
}<br>
<br><br><br>
**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/156505144-2a4970b5-8303-496f-a4e3-7796abb1681e.png)
![image](https://user-images.githubusercontent.com/97940332/156505205-ef1404a4-7030-4b57-a6d0-cae216874d1e.png)


**19.C# program to find a factorial of a number.**

using System;
public class FactorialExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int i, fact = 1, number;<br>
        Console.Write("Enter any Number: ");<br>
        number = int.Parse(Console.ReadLine());<br>
        for (i = 1; i <= number; i++)<br>
        {<br>
            fact = fact * i;<br>
        }<br>
        Console.Write("Factorial of " + number + " is: " + fact);<br>
    }<br>
}<br><br><br>**OUTPUT:**


![image](https://user-images.githubusercontent.com/97940332/156505563-a763466c-be14-4e0b-9b04-f402661320d3.png)

**20.C# program to find sum of digits in given number.**

using System;
public class SumExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, sum = 0, m;<br>
        Console.Write("Enter a number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n > 0)<br>
        {<br>
            m = n % 10;<br>
            sum = sum + m;<br>
            n = n / 10;<br>
        }<br>
        Console.Write("Sum is= " + sum);<br>
    }<br>
}<br>
<br><br><br>
**OUTPUT:**
![image](https://user-images.githubusercontent.com/97940332/156505974-3c19c344-f617-4626-8fb9-cc491f48ad19.png)


**21.C# program to reverse a number.**

using System;
public class ReverseExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, reverse = 0, rem;<br>
        Console.Write("Enter a number: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n != 0)<br>
        {<br>
            rem = n % 10;<br>
            reverse = reverse * 10 + rem;<br>
            n /= 10;<br>
        }<br>
        Console.Write("Reversed Number: " + reverse);<br>
    }<br>
}<br>
<br><br><br>
**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/156506255-d80ddfdc-f795-4136-a53f-11ca476e5eaa.png)


**22.C# program to swap 2 numbers.**


using System;
public class SwapExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int a, n;// = 5,<br>
        int b;// = 10;<br>
        Console.WriteLine("Enter 2 numbers:");<br>
        a = int.Parse(Console.ReadLine());<br>
        b = int.Parse(Console.ReadLine());<br>
        Console.WriteLine("Before swap a= " + a + " b= " + b);<br>
        a = a * b; //a=50 (5*10) <br>     
        b = a / b; //b=5 (50/10) <br>     
        a = a / b; //a=10 (50/5)   <br> 
        Console.Write("After swap a= " + a + " b= " + b);<br>
    }<br>
}<br>
<br><br><br>
**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/156506577-5f0a0340-c845-4979-93e1-c4dca5d91659.png)

**Example1:C# program to convert decimal number to binary.**

using System;
public class ConversionExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, i;<br>
        int[] a = new int[10];<br>
        Console.Write("Enter the number to convert: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        for (i = 0; n > 0; i++)<br>
        {<br>
            a[i] = n % 2;<br>
            n = n / 2;<br>
        }<br>
        Console.Write("Binary of the given number= ");<br>
        for (i = i - 1; i >= 0; i--)<br>
        {<br>
            Console.Write(a[i]);<br>
        }<br>
    }<br>
}<br>
<br><br><br>
**OUTPUT:**
![image](https://user-images.githubusercontent.com/97940332/156511687-1d301de4-a95f-4b1d-8fb8-25b48521c939.png)



**C# program to convert number into characters.**

using System;
public class ConversionExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int n, sum = 0, r;<br>
        Console.Write("Enter the Number= ");<br>
        n = int.Parse(Console.ReadLine());<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            sum = sum * 10 + r;<br>
            n = n / 10;<br>
        }<br>
        n = sum;<br>
        while (n > 0)<br>
        {<br>
            r = n % 10;<br>
            switch (r)<br>
            {<br>
                case 1:<br>
                    Console.Write("one ");<br>
                    break;<br>
                case 2:<br>
                    Console.Write("two ");<br>
                    break;<br>
                case 3:<br>
                    Console.Write("three ");<br>
                    break;<br>
                case 4:<br>
                    Console.Write("four ");<br>
                    break;<br>
                case 5:<br>
                    Console.Write("five ");<br>
                    break;<br>
                case 6:<br>
                    Console.Write("six ");<br>
                    break;<br>
                case 7:<br>
                    Console.Write("seven ");<br>
                    break;<br>
                case 8:<br>
                    Console.Write("eight ");<br>
                    break;<br>
                case 9:<br>
                    Console.Write("nine ");<br>
                    break;<br>
                case 0:<br>
                    Console.Write("zero ");<br>
                    break;<br>
                default:<br>
                    Console.Write("tttt ");<br>
                    break;<br>
            }//end of switch  <br>    
            n = n / 10;<br>
        }//end of while loop   <br>    
    }<br>
}<br>
<br><br><br>
**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/156511145-3c74e8af-b1d7-42fc-aaab-bf6542d17486.png)


**Example3:C# program to create alphabet triangle.**

using System;
public class PrintExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        char ch = 'A';<br>
        int i, j, k, m;<br>
        for (i = 1; i <= 5; i++)<br>
        {<br>
            for (j = 5; j >= i; j--)<br>
                Console.Write(" ");<br>
            for (k = 1; k <= i; k++)<br>
                Console.Write(ch++);<br>
            ch--;<br>
            for (m = 1; m < i; m++)<br>
                Console.Write(--ch);<br>
            Console.Write("\n");<br>
            ch = 'A';<br>
        }<br>
    }<br>
}<br>
<br><br><br>

**OUTPUT:**


![image](https://user-images.githubusercontent.com/97940332/156514801-d966d0fb-eeec-4c68-a075-507ef69d9883.png)


**Example4:C# program to create digits triangle.**

using System;<br>
public class PrintExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int i, j, k, l, n;<br>
        Console.Write("Enter the Range=");<br>
        n = int.Parse(Console.ReadLine());<br>
        for (i = 1; i <= n; i++)<br>
        {<br>
            for (j = 1; j <= n - i; j++)<br>
            {<br>
                Console.Write(" ");<br>
            }<br>
            for (k = 1; k <= i; k++)<br>
            {<br>
                Console.Write(k);<br>
            }<br>
            for (l = i - 1; l >= 1; l--)<br>
            {<br>
                Console.Write(l);<br>
            }<br>
            Console.Write("\n");<br>
        }<br>
    }<br>
}<br>

<br><br><br>
**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/156515296-94001ad1-20c1-4d5c-9dad-c0c2c2f6e99b.png)


**Example5:C# program to fibonacci triangle.**

using System;
public class PrintExample<br>
{<br>
    public static void Main(string[] args)<br>
    {<br>
        int a = 0, b = 1, i, c, n, j;<br>
        Console.Write("Enter the limit: ");<br>
        n = int.Parse(Console.ReadLine());<br>
        for (i = 1; i <= n; i++)<br>
        {<br>
            a = 0;<br>
            b = 1;<br>
            Console.Write(b + "\t");<br>
            for (j = 1; j < i; j++)<br>
            {<br>
                c = a + b;<br>
                Console.Write(c + "\t");<br>
                a = b;<br>
                b = c;<br>
            }<br>
            Console.Write("\n");<br>
        }<br>
    }<br>
}<br>
<br><br><br>

**OUTPUT:**
![image](https://user-images.githubusercontent.com/97940332/156515644-47812d34-f4b2-4283-932c-cc883c896cd1.png)




    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
   
    
    
    
    
    
    
    
    
    
    
    
    
    


    




