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


    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
   
    
    
    
    
    
    
    
    
    
    
    
    
    


    




