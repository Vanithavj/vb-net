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


**12.C# program to perform File comparison**
using System;<br>
using System.IO;<br>
namespace ex12<br>
{<br>
    class FileRead<br>
    {<br>
        public static void Main()<br>
        {<br>
            string file1;<br>
            string file2;<br>
            Console.Write("enter the first file path");<br>
            file1 = Console.ReadLine();<br>
            Console.Write("Enter the second file path");<br>
            file2 = Console.ReadLine();<br>
            if (!File.Exists(file1))<br>
            {<br>
                Console.WriteLine("first file does not exist!");<br>
            }<br>
            else if (!File.Exists(file2))<br>
            {<br>
                Console.WriteLine("second file does not exist!");<br>
            }<br>
            else if (File.ReadAllText(file1) == File.ReadAllText(file2))<br>
            {<br>
                Console.WriteLine("Both the files contain the same content");<br>
            }<br>
            else<br>
            {<br>
                Console.WriteLine("Contents of files are not same");<br>
            }<br>
        }<br>
    }<br>
}<br><br><br><br>
**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940767/154637493-20aa1b32-b387-4c13-86bf-c998bdf3b492.png)
![image](https://user-images.githubusercontent.com/97940767/154637546-e390a333-2cfb-430f-89f9-5ef839e7570f.png)
![image](https://user-images.githubusercontent.com/97940767/154637612-6be5f45c-15dd-4c0c-a28f-3165edb8b652.png)
![image](https://user-images.githubusercontent.com/97940767/154637838-20eb6345-511e-4169-86ab-f0f030d3ee36.png)
![image](https://user-images.githubusercontent.com/97940767/154637902-a7528741-ce03-4ae4-86fc-f33c2709cfb1.png)
![image](https://user-images.githubusercontent.com/97940767/154637983-8507a495-0559-4e38-94ef-24958184f8cf.png)




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




                                        **PART-B**

**23.C# Program to Convert Digit to Words.**

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace WindowsFormsApp4<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>

        private void textBox1_TextChanged(object sender, EventArgs e)<br>
        {<br>

        }<br>

        private void label1_Click(object sender, EventArgs e)<br>
        {<br> }<br>

        private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            lbl_words.Text = NumtoWord(long.Parse(txt_num.Text));<br>
        }<br>
        public string NumtoWord(long number)<br>
        {<br>
            string word = "";<br>
            if (number == 0)<br>
            {<br>
                return "Zero";<br>
            }<br>
            if (number < 0)<br>
            {<br>
                return "Minus" + Math.Abs(number);<br>
            }<br>
            if (number / 10000000 > 0)<br>
            {<br>
                word += NumtoWord(number / 10000000) + "Corer";<br>
                number %= 10000000;<br>
            }<br>

        if (number / 100000 > 0)<br>
            {<br>
                word += NumtoWord(number / 100000) + "Lacs";<br>
                number %= 100000;<br>
            }<br>
            if (number / 1000 > 0)<br>
            {<br>
                word += NumtoWord(number / 1000) + "Thousand";<br>
                number %= 1000;<br>
            }<br>
            if (number / 100 > 0)<br>
            {<br>
                word += NumtoWord(number / 100) + "Hundred";<br>
                number %= 100;<br>
            }<br>
            if (number > 0)<br>
            {<br>
                string[] units = new string[] { "Zero", "One", "Two", "Three", "Four", "Five", "Six",
"Seven", "Eight", "Nine", "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen",
"Seventeen", "Eighteen", "Nineteen" };<br>
                string[] Tens = new string[] { "Zero", "Ten", "Twenty", "Thirty", "Fourty", "Fifty",
"Sixty", "Seventy", "Eighty", "Ninety" };<br>
                if (number < 20)<br>
                {<br>
                    word += units[number];<br>
                }<br>
                else<br>
                {<br>
                    word += Tens[number / 10];<br>
                    if (number % 10 > 0)<br>
                    {<br>
                        word += units[number % 10];<br>
                    }<br>
                }<br>
            }<br>
            return word;<br>

        }<br>
    }<br>
}<br>

<br><br><br><br>

![image](https://user-images.githubusercontent.com/97940332/157816687-ec4d7eaa-52b5-45b2-b435-5e1db1bebdb5.png)












**OUTPUT:**


![image](https://user-images.githubusercontent.com/97940332/157816839-3a700b01-b879-4320-b7a9-4a0f2f726a14.png)




**25.C# program to Reversal,Padding and Trimming operation on string.**

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace exw25<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        { <br>
            InitializeComponent();<br>
        }<br>

        private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString, revstr = "";<br>
            int Length;<br>
            inputString = txtInput.Text;<br>
            Length = inputString.Length - 1;<br>
            while (Length >= 0)<br>
            {<br>
                revstr = revstr + inputString[Length];<br>
                Length--;<br>
            }<br>
            MessageBox.Show("Reverse String Is : " + revstr, "Result");<br>
        }<br>

        private void button2_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString;<br>
            inputString = txtInput.Text;<br>
            MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result");<br>
        }<br>

        private void button3_Click(object sender, EventArgs e)<br>
        {<br>
            string inputString;<br>
            inputString = txtInput.Text;<br>
            inputString = inputString.PadLeft(10, '*');<br>
            inputString = inputString.PadRight(15, '*');<br>
            MessageBox.Show("String After Padding : " + inputString, "Result");<br>
        }<br>
    }<br>
}<br><br><br><br><br><br>

**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/158939647-1a693036-dd3b-4bf9-8cfe-48b5ea22e074.png)
![image](https://user-images.githubusercontent.com/97940332/158939700-f19a0eb4-ac38-46be-83b1-d9037e51d8ad.png)
![image](https://user-images.githubusercontent.com/97940332/158939793-dd271ac5-ffc6-489f-b235-eedded91abee.png)



**26.C# program to create a progress bar control.**


using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading;<br>
using System.Windows.Forms;<br>

namespace exw26<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>

        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
            backgroundWorker1.WorkerReportsProgress = true;<br>
            backgroundWorker1.RunWorkerAsync();<br>
        }<br>

        private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)<br>
        {<br>
            for(int i=1;i<=100;i++)<br>
            {<br>
                Thread.Sleep(50);<br>
                backgroundWorker1.ReportProgress(i);<br>
            }<br>
        }<br>

        private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)<br>
        {<br>
            progressBar1.Value = e.ProgressPercentage;<br>
            this.Text = "Progress:" + e.ProgressPercentage.ToString() + "%";<br>
        }<br>
    }<br>
}<br><br><br><br><br><br>




**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/158940049-8044b53a-91ab-4d3f-9a14-e5bacf31a0fd.png)



**27.Develop a winform application to create flat clock.**




using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace ex27<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>

        private void circularProgressBar1_Click(object sender, EventArgs e)<br>
        {<br>

        }<br>

        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>
            System.Timers.Timer timer = new System.Timers.Timer();<br>
            timer.Interval = 1000;//1s<br>
            timer.Elapsed += Timer_Elapsed;<br>
            timer.Start();<br>
        }<br>
        private void Timer_Elapsed(object sender, System.Timers.ElapsedEventArgs e)<br>
        {<br>
            circularProgressBar1.Invoke((MethodInvoker)delegate<br>
            {<br>
                circularProgressBar1.Text = DateTime.Now.ToString("hh:mm:ss");<br>
                circularProgressBar1.SubscriptText = DateTime.Now.ToString("tt");//AM or PM<br>
            });<br>
        }<br>
    }<br>
}<br><br><br><br><br><br>
    



**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/158940529-95973974-c261-4fca-bda2-f36f35f6c928.png)


**28.C# program for perform a number guessing game.**


using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;<br>

namespace EX28<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        static Random r = new Random();<br>
        int value;<br>
        int guessnum;<br>
        int win = 10;<br>
        int guess = 1;<br>
        TextBox textBox1;<br>
        Button button1;<br>
        RichTextBox richTextBox1;<br>
        RichTextBox richTextBox2;<br>
        Label label4;<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>

            value = r.Next(10);<br>
            this.Controls.Clear();<br>
            this.BackColor = Color.SkyBlue;<br>
            this.AutoSize = true;<br>
            this.Padding = new Padding(16);<br>

            Label label = new Label();
            label.Text = "Pick a number between 1 and 100";
            label.Bounds = new Rectangle(10, 20, 340, 40);
            label.Font = new Font("Arial", 16);
            textBox1 = new TextBox();
            textBox1.Bounds = new Rectangle(20, 50, 120, 80);
            textBox1.Font = new Font("Arial", 24);
            button1 = new Button();
            button1.Text = " Check Your Guess ";
            button1.Bounds = new Rectangle(160, 50, 120, 40);
            button1.BackColor = Color.LightGray;
            button1.Click += new EventHandler(button1_Click);
            Label label2 = new Label();
            label2.Text = "Low Guess";
            label2.Bounds = new Rectangle(20, 150, 160, 40);
            label2.Font = new Font("Arial", 18);
            richTextBox1 = new RichTextBox();
            richTextBox1.Bounds = new Rectangle(20, 190, 160, 300);
            richTextBox1.Font = new Font("Arial", 16);
            Label label3 = new Label();
            label3.Text = "High Guess";
            label3.Bounds = new Rectangle(180, 150, 160, 40);
            label3.Font = new Font("Arial", 18);
            richTextBox2 = new RichTextBox();
            richTextBox2.Bounds = new Rectangle(180, 190, 160, 300);
            richTextBox2.Font = new Font("Arial", 16);
            label4 = new Label();
            label4.Bounds = new Rectangle(20, 100, 340, 40);
            label4.Font = new Font("Arial", 16);
            this.Controls.Add(label);
            this.Controls.Add(textBox1);
            this.Controls.Add(button1);
            this.Controls.Add(label4);
            this.Controls.Add(label2);
            this.Controls.Add(label3);
            this.Controls.Add(richTextBox1);
            this.Controls.Add(richTextBox2);

        }

        private void Form1_Load(object sender, EventArgs e)
        {

        }
        private void button1_Click(object sender, EventArgs e)
        {
            // Coding of game 
            if (textBox1.Text == "")
            {
                return;
            }
            guessnum = Convert.ToInt32(textBox1.Text);
            textBox1.Text = String.Empty;
            if (win >= 0)
            {
                if (guessnum == value)
                {
                    MessageBox.Show("You have guessed the number! \n The number was " + value);
                    InitializeComponent();
                }
                else if (guessnum < value)
                {
                    richTextBox1.Text += guessnum + "\n";
                    MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));

                }
                else if (guessnum > value)
                {
                    richTextBox2.Text += guessnum + "\n";
                    MessageBox.Show("wrong Guess and number of guesses left are  " + (10 - guess));

                }
                guess++;
                win--;
            }
            if (guess == 11)
            {
                label4.Text = "You loose,Correct Guess is " + value;
            }
        }
    }
}

**OUTPUT:**

![image](https://user-images.githubusercontent.com/97940332/159858746-9502a8ed-b304-48b7-b459-85fa7ccafd6a.png)
![image](https://user-images.githubusercontent.com/97940767/159859476-41266e55-fc1d-48b2-b716-b629088812f5.png)
![image](https://user-images.githubusercontent.com/97940767/159859593-a46374d4-a2a4-493d-8c8b-a998004cd252.png)


    
    
   **29. Develop an application to create a notepad. **

using System;<br> 
using System.IO; <br>
using System.Windows.Forms; <br>
using System.Drawing; <br>
namespace ex14<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        private string fileName;<br>
        private RichTextBox txtContent;<br>
        private ToolBar toolBar;<br>
        internal Form1()<br>
        {<br>
            fileName = null;<br>
            initializeComponents();<br>
        }<br>
        void initializeComponents()<br>
        {<br>
            this.Text = "My notepad";<br>
            this.MinimumSize = new Size(600, 450);<br>
            this.FormClosing += new FormClosingEventHandler(NotepadClosing); this.MaximizeBox = true;<br>
            toolBar = new ToolBar();<br>
            toolBar.Font = new Font("Arial", 16);<br>
            toolBar.Padding = new Padding(4);<br>
            toolBar.ButtonClick += new ToolBarButtonClickEventHandler(toolBarClicked);<br>
            ToolBarButton toolBarButton1 = new ToolBarButton(); <br>
            ToolBarButton toolBarButton2 = new ToolBarButton();<br>
            ToolBarButton toolBarButton3 = new ToolBarButton();<br>
            toolBarButton1.Text = "New";<br>
            toolBarButton2.Text = "Open";<br>
            toolBarButton3.Text = "Save";<br>
            toolBar.Buttons.Add(toolBarButton1);<br>
            toolBar.Buttons.Add(toolBarButton2);<br>
            toolBar.Buttons.Add(toolBarButton3);<br>
            txtContent = new RichTextBox();<br>
            txtContent.Size = this.ClientSize;<br>
            txtContent.Height -= toolBar.Height;<br>
            txtContent.Top = toolBar.Height;<br>
            txtContent.Anchor = AnchorStyles.Left | AnchorStyles.Right | AnchorStyles.Top | AnchorStyles.Bottom;<br>
            txtContent.Font = new Font("Arial", 16);<br>
            txtContent.AcceptsTab = true;<br>
            txtContent.Padding = new Padding(8);<br>

            this.Controls.Add(toolBar);<br>
            this.Controls.Add(txtContent);<br>
        }<br>
        private void toolBarClicked(Object sender, ToolBarButtonClickEventArgs e)<br>
        {<br>
            saveFile();<br>
            switch (toolBar.Buttons.IndexOf(e.Button))<br>
            {<br>
                case 0:<br>
                    this.Text += "My notepad";<br>
                    txtContent.Text = string.Empty;<br>
                    fileName = null;<br>
                    break;<br>
                case 1:<br>
                    OpenFileDialog openDlg = new OpenFileDialog();<br>
                    if (DialogResult.OK == openDlg.ShowDialog())<br>
                    {<br>
                        fileName = openDlg.FileName;<br>
                        txtContent.LoadFile(fileName);<br>
                        this.Text = "My notepad " + fileName;<br>
                    }<br>
                    break;<br>
            }<br>
        }<br>
        void saveFile()<br>
        {<br>
            if (fileName == null)<br>
            {<br>
                SaveFileDialog saveDlg = new SaveFileDialog();<br>
                if (DialogResult.OK == saveDlg.ShowDialog())<br>
                {<br>
                    fileName = saveDlg.FileName;<br>
                    this.Text += " " + fileName;<br>
                }<br>
            }<br>
            else<br>
            {<br>
                txtContent.SaveFile(fileName, RichTextBoxStreamType.RichText);<br>
            }<br>
        }<br>
        
        private void NotepadClosing(Object sender, FormClosingEventArgs e)<br>
        {<br>
            saveFile();<br>
            <br>
        }
        private void Form1_Load(object sender, EventArgs e)<br>
        {<br>

        }<br>
       
    }<br>
}<br><br><br>


**OUTPUT:**
![image](https://user-images.githubusercontent.com/97940767/160996988-d304ad7b-506e-4354-b74c-5cb5f988497d.png)
![image](https://user-images.githubusercontent.com/97940767/160997173-0dc28328-3c04-4377-a04b-5a8a81864d9b.png)
![image](https://user-images.githubusercontent.com/97940767/160997298-14eb7e84-1e36-4a80-a1d8-9fde2acd621b.png)




ex30.//Develop an application to construct a graphical binary search tree where you need to create, add, search and remove nodes.<br>

using System;<br>
using System.Collections.Generic;<br>
using System.ComponentModel;<br>
using System.Data;<br>
using System.Drawing;<br>
using System.Linq;<br>
using System.Text;<br>
using System.Threading.Tasks;<br>
using System.Windows.Forms;
using System.Drawing.Drawing2D;

namespace WindowsFormsApp6<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        private Node root;<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
            this.root = null;<br>
            test();<br>
        }<br>
        private void Form1_Load(object sender, EventArgs e)
        {<br>

        }<br>
        void test()<br>
        {<br>
            textBox1.Text = "5";<br>
            btnAdd_Click_1(btnAdd, null);<br>
            textBox1.Text = "3";<br>
            btnAdd_Click_1(btnAdd, null);<br>
            textBox1.Text = "2";<br>
            btnAdd_Click_1(btnAdd, null);<br>
            textBox1.Text = "1";<br>
            btnAdd_Click_1(btnAdd, null);<br>
            textBox1.Text = "4";<br>
            btnAdd_Click_1(btnAdd, null);<br>
            textBox1.Text = "7";<br>
            btnAdd_Click_1(btnAdd, null);<br>
            textBox1.Text = "6";<br>
            btnAdd_Click_1(btnAdd, null);<br>
            textBox1.Text = "8";<br>
            btnAdd_Click_1(btnAdd, null);<br>
        }<br>
        void drawTree()<br>
        {<br>
            if (root != null)<br>
                pictureBox1.Image = root.Draw();<br>
            else<br>
                pictureBox1.Image = null;<br>
            this.Update();<br>
        }<br>
        private void btnAdd_Click_1(object sender, EventArgs e)<br>
        {<br>
            int value = int.Parse(textBox1.Text); if (root == null)<br>
                root = new Node(value);<br>
            else<br>
            {<br>
                if (root.Add(value) == false)<br>
                    MessageBox.Show("The value already exists!");<br>
            }<br>
            drawTree();<br>
        }<br>
        private void btnRemove_Click_1(object sender, EventArgs e)<br>
        {<br>
            int value = int.Parse(textBox1.Text); if (root != null)<br>
            {<br>
                bool status = root.Remove(value, root, ref root); if (status == false)<br>
                {<br>
                    MessageBox.Show("the value does not exists");<br>
                }<br>
            }<br>
            drawTree();<br>
        }<br>

        private void btnCreate_Click_1(object sender, EventArgs e)<br>
        {<br>
            root = null;<br>
            pictureBox1.Image = null;<br>
            }<br>

        private void btnSearch_Click_1(object sender, EventArgs e)<br>
        {<br>
            string msg;<br>
            int value = int.Parse(textBox1.Text); if (root == null)<br>
            {<br>
                msg = "Tree is empty";<br>
            }<br>
            else<br>
            {<br>
                if (root.Exists(value))<br>
                {<br>
                    msg = "Value found";<br>
                }<br>
                else<br>
                {<br>
                    msg = "Value not found";<br>
                }<br>
            }<br>
            MessageBox.Show(msg);<br>
        }<br>
    }<br>
    class Node<br>
    {<br>
        internal Node left { get; set; }<br>
        internal Node right { get; set; }<br>
        internal int value;<br>
        internal int center = 12;<br>
        private static Bitmap nodeBg = new Bitmap(30, 25); private static Font font = new Font("Arial", 14);<br>
        internal Node(int value)<br>
        {<br>
            this.value = value;<br>
        }<br>
        internal bool Add(int value)<br>
        {<br>
            Node node = new Node(value);<br>
            if (value < this.value)<br>
            {<br>
                if (this.left == null)<br>
                {<br>
                    this.left = node;<br>
                    return true;<br>
                }<br>
                else<br>
                    return this.left.Add(value);<br>
            }<br>
            else if (value > this.value)<br>
            {<br>
                if (this.right == null)<br>

                {<br>
                    this.right = node;<br>
                    return true;<br>
                }<br>
                else<br>
                    return this.right.Add(value);<br>
            }<br>
            return false;<br>
        }<br>
        internal bool Remove(int value, Node parent, ref Node root)<br>
        {<br>
            if (value < this.value)<br>
            {<br>
                if (left != null)<br>
                {<br>
                    return left.Remove(value, this, ref root);<br>
                }<br>
            }<br>
            else if (value > this.value)<br>
            {<br>
                if (right != null)<br>
                {<br>
                    return right.Remove(value, this, ref root);<br>
                }<br>
            }<br>
            else if (value == this.value)<br>
            {<br>
                bool isLeft = (this == parent.left);<br>
                if (left == null && right == null)<br>
                {<br>
                    if (root == this)<br>
                        root = null;<br>
                    else<br>
                    if (isLeft) parent.left = null; else parent.right = null;<br>
                }<br>
                else if (right == null)<br>
                {<br>
                    if (isLeft) parent.left = left; else parent.right = left; if (root == this)<br>
                        root = left;<br>
                }<br>
                else<br>
                {<br>
                    if (right.left == null)<br>
                    {<br>
                        right.left = left;<br>
                        if (isLeft) parent.left = right;<br>
                        else<br>

                            parent.right = right;<br>
                        if (root == this)<br>
                            root = right;<br>
                    }<br>
                    else<br>
                    {<br>
                        Node node = right;<br>
                        while (node.left.left != null)<br>
                            node = node.left;<br>
                        Console.WriteLine("Node: " + node.value);<br>
                        this.value = node.left.value;<br>
                        Console.WriteLine("here");<br>
                        node.left = null;<br>
                    }<br>
                }<br>
                return true;<br>
            }<br>
            return false;<br>
        }<br>
        public Image Draw()<br>
        {<br>
            Size lSize = new Size(nodeBg.Width / 2, 0);<br>
            Size rSize = new Size(nodeBg.Width / 2, 0);<br>
            Image lNodeImg = null;<br>
            Image rNodeImg = null;<br>
            int lCenter = 0, rCenter = 0;<br>

            if (this.left != null)<br>
            {<br>
                lNodeImg = left.Draw();<br>
                lSize = lNodeImg.Size;<br>
                this.center = lSize.Width;<br>
                lCenter = left.center;<br>
            }<br>
            if (this.right != null)<br>
            {<br>
                rNodeImg = right.Draw();<br>
                rSize = rNodeImg.Size;<br>
                rCenter = right.center;<br>
            }<br>
            int maxHeight = (lSize.Height < rSize.Height) ? rSize.Height : lSize.Height; if (maxHeight > 0) maxHeight += 35;<br>

            Size resultSize = new Size(lSize.Width + rSize.Width, nodeBg.Size.Height + maxHeight);<br>
            Bitmap result = new Bitmap(resultSize.Width, resultSize.Height);<br>
            Graphics g = Graphics.FromImage(result);<br>
            g.SmoothingMode = SmoothingMode.HighQuality;<br>
            g.FillRectangle(Brushes.White, new Rectangle(new Point(0, 0), resultSize)); g.DrawImage(nodeBg, lSize.Width - nodeBg.Width / 2, 0);<br>
            string str = "" + value;<br>
            g.DrawString(str, font, Brushes.Black, lSize.Width - nodeBg.Width / 2 + 7, nodeBg.Height / 2f - 12);<br>
            Pen pen = new Pen(Brushes.Black, 1.2f);<br>
            float x1 = center;<br>
            float y1 = nodeBg.Height;<br>
            float y2 = nodeBg.Height + 35;<br>
            float x2 = lCenter;<br>
            var h = Math.Abs(y2 - y1);<br>
            var w = Math.Abs(x2 - x1);<br>
            if (lNodeImg != null)<br>
            {<br>
                g.DrawImage(lNodeImg, 0, nodeBg.Size.Height + 35); var points1 = new List<PointF><br>
{<br> new PointF(x1, y1),<br>
new PointF(x1 - w/6, y1 + h/3.5f),<br>
new PointF(x2 + w/6, y2 - h/3.5f),<br>
new PointF(x2, y2),<br>
};<br>
                g.DrawCurve(pen, points1.ToArray(), 0.5f);<br>
            }<br>
            if (rNodeImg != null)<br>

            {<br>
                g.DrawImage(rNodeImg, lSize.Width, nodeBg.Size.Height + 35); x2 = rCenter + lSize.Width;<br>
                w = Math.Abs(x2 - x1);<br>
                var points = new List<PointF><br>
{<br>
new PointF(x1, y1),<br>
new PointF(x1 + w/6, y1 + h/3.5f),<br>
new PointF(x2 - w/6, y2 - h/3.5f),<br>
new PointF(x2, y2)<br>
};<br>

                g.DrawCurve(pen, points.ToArray(), 0.5f);<br>
            }<br>
            return result;
        }<br>
        public bool Exists(int value)<br>
        {<br>
            bool res = value == this.value;<br>
            if (!res && left != null)<br>
                res = left.Exists(value);<br>
            if (!res && right != null)<br>
                res = right.Exists(value);<br>
            return res;<br>
        
        }<br>
    }<br>
}<br><br><br><br>
**OUTPUT:**



![image](https://user-images.githubusercontent.com/97940767/161211021-f009e57b-dc9d-4172-8912-ef68e2e459ac.png)


**//program to money conversion**


using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace Moneyconversion<br>
{<br>
    public partial class Form1 : Form<br>
    {<br>
        public Form1()<br>
        {<br>
            InitializeComponent();<br>
        }<br>
        private void Form1_Load(object sender, EventArgs e)<br>
  {<br>}<br>

        private void button1_Click(object sender, EventArgs e)<br>
        {<br>
            {<br>
                label4.Visible = true;<br>
                if (textBox1.Text == "")<br>
                {<br>
                    label4.Text = "Enter the amount";<br>
                }<br>
                else<br>
                {<br>
                    Double convertedamt = Convert.ToDouble(textBox1.Text);<br>
                    if (comboBox1.SelectedItem == "INR" && comboBox2.SelectedItem == "USD")<br>
                    {<br>
                        Double a = convertedamt / 74;<br>
                        label4.Text = a + " $";<br>
                    }<br>
                    else if (comboBox1.SelectedItem == "INR" && comboBox2.SelectedItem == "SAR")<br>
                    {<br>
                        Double a = convertedamt / 17;<br>
                        label4.Text = a + "SAR";<br>
                    }<br>
                    else if (comboBox1.SelectedItem == "INR" && comboBox2.SelectedItem == "EUR")<br>
                    {<br> Double a = convertedamt / 11;<br>
                        label4.Text = a + "EUR";<br>
                    }<br>
                    else<br>
                    {<br>
                        label4.Text = "Please Enter the conversion code";<br>
                    }<br>
                }<br>
            }<br>
}<br>private void button2_Click(object sender, EventArgs e)<br>
        {<br>
            textBox1.Text = "";<br>
            label4.Text = ""; <br> } <br>private void label1_Click(object sender, EventArgs e)<br>
        {<br>

        }<br>
    }<br>
}<br><br><br><br>


**OUTOUT:**
![image](https://user-images.githubusercontent.com/97940332/165696526-cba786b9-5d16-4973-ae3c-a2e790f9d290.png)




       
    


 
    
    
    
    
    
    
    
    
    
    
    
    
   
    
    
    
    
    
    
    
    
    
    
    
    
    


    




