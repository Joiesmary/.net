# .net
     1) C# Program to Print a Binary Triangle.
<br>program 1</br>

<br>using System;</br>
<br>public class Example1</br>
<br>{</br>
    <br>public static void Main()</br>
   <br> {</br>
        <br>int i, j, n,digit=1;</br>
       <br> Console.Write("Input number of rows for this pattern :");</br>
        <br>n = Convert.ToInt32(Console.ReadLine());</br>
       <br> for (i=0;i<n;i++)</br>
       <br> {</br></br>
          <br>  for (j=1;j<n-i;j++)</br>
          <br>  {</br>
           <br>     Console.Write(" ");</br>
           <br> }</br>
          <br>  for (int k=1;k<=2*i-1;k++)</br>
           <br> {</br>
           <br> Console.Write(digit + " ");</br>
           <br> digit = (digit == 1) ? 0 : 1;</br>
      <br>  }</br>
           <br> Console.Write("\n");</br>
       <br> }</br>
    <br>}</br>
<br>}</br>

![image](https://user-images.githubusercontent.com/19484531/154408925-b55c991a-a53f-4486-851c-4a08a8a67f88.png)

    program 2: C# Program to Check Whether the Entered Number is an Amicable 
     Number or Not

    using System;

    namespace project1
    {
      class Program
    {
        static void Main(string[] args)
        {
            int num1, num2, sum1=0, sum2=0;
            Console.WriteLine("\n ---Amicable number\n");
            Console.Write("\nEnter the first number:");
            num1 = Convert.ToInt32(Console.ReadLine());
            Console.Write("\n Enter second number:");
            num2 = Convert.ToInt32(Console.ReadLine());
            for(int i=1;i<num1;i++)
            {
                if(num1%i==0)
                {
                    sum1 += i;
                }
            }
            for(int i=1;i<num2;i++)
            {
                if(num2%i==0)
                {
                    sum2 += i;
                }
            }
            if(sum1==num2 && sum2==num1)
            {
                Console.WriteLine("\n The number {0} & {1} are  amicable", num1, num2);
            }
            else
            {
                Console.WriteLine("\n The number {0} & {1} are not amicable", num1, num2);
            }
        }
    }
    }

![image](https://user-images.githubusercontent.com/19484531/154427251-07c96f4f-5f4e-499c-973c-1d85ffe60c77.png)

![image](https://user-images.githubusercontent.com/19484531/154427402-62e50180-84b3-445f-a0a5-a09cad755cfa.png)

    program 3 : C# Program to Illustrate Multilevel Inheritance with Virtual 
     Methods (displaying student details).


	    using System;

	    namespace project3
	    {
	    class Program
	    {
		string name;
		int age;
		string gender;
		public Program(String name, int age,String gender)
		{
		    this.name = name;
		    this.age = age;
		    this.gender = gender;
		}
		public virtual void Display()
		{
		    Console.WriteLine("\n--- Personal Details ---\n");
		    Console.WriteLine("Name : " + name);
		    Console.WriteLine("Age :" + age);
		    Console.WriteLine("gender :" + gender);

		}
	    }
	    class CourseDetails:Program
	    {
		int regno;
		string course;
		int semister;
		public CourseDetails(String name,int age,String gender, int regno,String course,int semister):base(name,age,gender)
		{
		    this.regno = regno;
		    this.course = course;
		    this.semister = semister;
		}
		public override void Display()
		{
		    base.Display();
		    Console.WriteLine("\n--- course details---\n");
		    Console.WriteLine("Register number:" + regno);
		    Console.WriteLine("course : " + course);
		    Console.WriteLine("semister :" + semister);

		}

	    }
	    class MarksDetails:CourseDetails
	    {
		int[] marks = new int[5];
		int total;
		float average;
		string grade;
		int flagFail;
		public MarksDetails(string name,int age,string gender,int regno,string course,int semister,int[] marks):base(name,age,gender,regno,course,semister)
		{
		    total = 0;
		    for(int i=0;i<5;i++)
		    {
			this.marks[i] = marks[i];
			total += marks[i];
			if(marks[i]<35)
			{
			    flagFail = 1;
			}
		    }
		    calculate();
		}
		private void calculate()
		{
		    average = total / 5;
		    if (flagFail == 1 || average < 40)
			grade = "Fail";
		    else if (average >= 70)
			grade = "Distinction";
		    else if (average >= 60)
			grade = "First class";
		    else if (average >= 50)
			grade = "Second class";
		    else
			grade = "pass class";
		}
		public override void Display()
		{
		    base.Display();
		    Console.WriteLine("\n---Marks details--\n");
		    Console.Write("marks in subject: ");
		    for (int i = 0; i < 5; i++)
			Console.Write(marks[i] + "");
		    Console.WriteLine();
		    Console.WriteLine("total :" + total);
		    Console.WriteLine("Average: " + average);
		    Console.WriteLine("grade :" + grade);
		}
	    }
	    class MultiLevel
	    {
		public static void Main(String[] args)
		{
		    MarksDetails Student1 = new MarksDetails("abijith", 22, "male", 2019001, "MSC", 5, new int[] { 77, 80, 98, 95, 90 });
		    Student1.Display();
		}
	    }
	    }
![image](https://user-images.githubusercontent.com/19484531/154426618-d5e93876-7357-42b6-a1ab-f54c709f3d98.png)


    program 4: C# Program to Create a Gray Code.


    using System;

    namespace project2
     {
    class Program
    {
        static int getGray(int n)
        {
        return n^(n>>1);
        }
        static void Main(string[] args)
        {
        int InputNum, GrayNum;
        Console.Write("\n Enter the decimal number:");
        InputNum = (Convert.ToInt32(Console.ReadLine()));
        Console.WriteLine("\n Binary Equivalent of {0}:{1}", InputNum, Convert.ToString(InputNum, 2));
        GrayNum = getGray(InputNum);
        Console.WriteLine("\n Gray code equivalent of {0} : {1}", InputNum, Convert.ToString(GrayNum, 2));
        }
    }
    }

![image](https://user-images.githubusercontent.com/19484531/154427696-25ef41c1-c1c3-4892-8b41-c39d848fd537.png)



     program5: C# program to calculate volume of 2 boxes and find the resultant volume after addition of 2 boxes by implementing operator overloading



    <br>using System;</br>

    <br>namespace ConsoleApp5</br>
    <br>{</br>
        <br>class Box</br>
        <br>{</br>
            <br>float width;</br>
           <br>float height;</br>
           <br> float length;</br>

            public float Volume
            {
                get { return width * height * length; }
            }
            public Box(float width, float height, float length)
            {
                this.width = width;
                this.height = height;
                this.length = length;
            }
            public static float operator+(Box box1, Box box2)
            {
                return box1.Volume + box2.Volume;
            }
            public override string ToString()
            {
                return "box with width" + width + ",height" + height + "and length" + length;

            }
        }
        class OperatorOverloading
        {
            public static void Main()
            {
            Box box1 = new Box(10, 20, 30);
            Box box2 = new Box(25, 32, 15);
            Console.WriteLine("Volume of {0} is {1}",box1,box1.Volume);
            Console.WriteLine("Volume of {0} is {1}", box2,box2.Volume);
            Console.WriteLine("Volume after adding boxes:{0}",box1+box2);
            }
        }
}

![image](https://user-images.githubusercontent.com/19484531/154410221-c2677375-e62c-4959-abba-b6dbb17fa36d.png)

             6) C# Program to Implement Principles of Delegates (converting 
    input string to uppercase first, last and entire string).
    
    using System;
     namespace Exercises
     {
    class Delegates
    {
        delegate string UppercaseDelegate(string input);
        static string UppercaseFirst(string input)
        {
            char[] buffer = input.ToCharArray();
            buffer[0] = char.ToUpper(buffer[0]);
            return new string(buffer);
        }
        static string UppercaseLast(string input)
        {
            char[] buffer = input.ToCharArray();
            buffer[buffer.Length - 1] = char.ToUpper(buffer[buffer.Length - 1]);
            return new string(buffer);
        }
        static string UppercaseAll(string input)
        {
            return input.ToUpper();
        }
        static void WriteOutput(string input, UppercaseDelegate del)
        {
            Console.WriteLine("Input String: {0}", input);
            Console.WriteLine("Output String: {0}", del(input));
        }
        static void Main()
        {
            WriteOutput("tom ", new UppercaseDelegate(UppercaseFirst));
            WriteOutput("tom", new UppercaseDelegate(UppercaseLast));
            WriteOutput("tom", new UppercaseDelegate(UppercaseAll));
            Console.ReadLine();
        }
    }
    }
    
    o/p
    
   ![image](https://user-images.githubusercontent.com/19484531/156504015-6d3aedce-07f5-4c0f-b976-51713298b081.png)


     7) C# Program to Generate Register Number automatically for 100 Students using Static Constructor

<br>program 7:</br>
<br>using System;</br>

<br>namespace ConsoleApp7</br>
<br>{</br>
   <br> class RegisterNum</br>
    <br>{</br>
       <br> int regNo;</br>
      <br>  static int startNum;</br>
      <br> static RegisterNum()</br>
       <br> {</br>
          <br> startNum = 20210000;</br>
       <br>}</br>
       <br> RegisterNum()</br>
        <br>{</br>
            <br>regNo = ++startNum;</br>
        <br>}</br>
        <br>public static void Main(string[] args)</br>
       <br>{</br>
            <br>for(int i=0;i<100;i++)</br>
           <br> {</br>
                <br>RegisterNum Student = new RegisterNum();</br>
               <br> Console.WriteLine("Student {0} : {1}", i + 1, Student.regNo);</br>

            <br>}</br>
       <br> }</br>

   <br> }</br>
<br>}</br>


![image](https://user-images.githubusercontent.com/19484531/154410537-f8766c26-421f-4e73-a183-888a0126372c.png)
![image](https://user-images.githubusercontent.com/19484531/154410573-965caeeb-b723-4e7c-b044-8944643c3019.png)


     <br>program 8:</br> C# Program to Find the Frequency of the Word ʺisʺ in a given 
      Sentence.

<br>using System;</br>

<br><br>namespace ConsoleApp8</br>
<br>{
   <br> class FrequencyIS</br>
    <br>{
       <br>static void Main(String[] args)</br>
       <br> {
           <br> int count = 0;</br>
            <br>String inputString;</br>
            <br>Console.WriteLine("---------Frequency of word is-----------");</br>
            <br>Console.Write("\n Enter input string:'");</br>
            <br>inputString = Console.ReadLine();</br>
            <br>char[] separator = { ',', ' ', '.', '!', '\n' };</br>
           <br>string testString = inputString.ToLower();</br>
            <br>String[] outcomes = testString.Split(separator);</br>
           <br> foreach(String s in outcomes)</br>
            <br>{</br>
              <br>  Console.WriteLine(s);</br>
              <br>  if (s == "is")</br>
                   <br> count++;</br>
           <br>}
            <br>Console.WriteLine("\n Number of 'is' in '" + inputString + " 'is:" + count);</br>
       <br> }</br>
   <br> }</br>
<br>}</br>


![image](https://user-images.githubusercontent.com/19484531/154410969-117f3ca6-06da-48a1-8620-0411df344eeb.png)


     <br>program 9:  C# program that benchmarks 2D, jagged array allocation.
<br>using System;</br> 
<br>using System.Diagnostics;</br> 
<br>namespace ConsoleApp9</br> 
<br>{</br> 
    <br>class BenchmarkAllocation</br> 
    <br>{</br> 
       <br> const int _max= 100000;</br> 
       <br> static void Main(String[] args)</br> 
      <br>  {</br> 
             <br>  var Arr2D = new int[100, 100];</br> 
             <br>  var ArrJagged = new int[100][];</br> 
             <br>  for (int i = 0; i < 100; i++)</br> 
              <br> {</br> 
                  <br> ArrJagged[i] = new int[100];</br> 
             <br> }</br> 
              <br> var Stopwatch2D = Stopwatch.StartNew();</br> 
              <br> for (int i = 0; i < _max; i++)</br> 
              <br> {</br> 
                  <br> for (int j = 0; j < 100; j++)</br> 
                <br>   {</br> 
                      <br> for (int k = 0; k < 100; k++)</br> 
                      <br> {</br> 
                        <br>   Arr2D[j, k] = k;</br> 
                     <br>  }</br> 
                 <br>  }</br> 
            <br>   }</br> 
              <br> Stopwatch2D.Stop();</br> 
              <br> var StopwatchJagged = Stopwatch.StartNew();</br> 
             <br>  for (int i = 0; i < _max; i++)</br> 
              <br> {</br> 
                <br>   for (int j = 0; j < 100; j++)</br> 
                <br>   {</br> 
                     <br>  for (int k = 0; k < 100; k++)</br> 
                      <br> {</br> 
                        <br>   ArrJagged[j][k] = k;</br> 
                      <br> }</br> 

               }  
             } 
            StopwatchJagged.Stop();
            Console.Write("\n Time taken for allocation in case of 2Darray:");
            Console.WriteLine(Stopwatch2D.Elapsed.TotalMilliseconds + "milliseconds");
            Console.Write("\n Time taken for allocation in case of Jagged array:");
            Console.WriteLine(StopwatchJagged.Elapsed.TotalMilliseconds + "milliseconds");
        }
    }
}</br> 

![image](https://user-images.githubusercontent.com/19484531/154411411-ea68d691-e58d-46b2-9abb-3d4a5b5402c2.png)

     program 10: C# Program to Find the Sum of the Values on Diagonal of the 
     Matrix.


                 
				 using System;

          namespace ConsoleApp10
       {
    class SumOfDiagonals
    {
       static void Main(String[] args)
        {
            int MaxRow, MaxCol, sum = 0;
            int[,] Matrix;
            Console.WriteLine("\n----Sum of Diagonal of a matrix---\n");
            Console.Write("\n Enter the number of rows:");
            MaxRow = Convert.ToInt32(Console.ReadLine());
            Console.Write("\n Enter the number of columns:");
            MaxCol = Convert.ToInt32(Console.ReadLine());
            if(MaxRow!=MaxCol)
            {
                Console.WriteLine("\n The Dimentions entered are not of square matrix.");
                Console.WriteLine("\n Existing the Program.");
                return;
            }
            Matrix = new int[MaxRow, MaxCol];
            for(int i=0;i<MaxRow;i++)
            {
                for(int j=0;j<MaxCol;j++)
                {
                    Console.Write("\n Entered the ({0},{1})th element of the matrix :", (i + 1), (j + 1));
                    Matrix[i, j] = Convert.ToInt32(Console.ReadLine());


                
				}
            }
            Console.WriteLine("\n The entered matrix is:");
            for (int i = 0; i < MaxRow; i++)
            {
                for(int j = 0; j < MaxCol; j++)
                {
                    Console.Write(" " + Matrix[i, j]);
                    if(i==j)
                    {
                        sum += Matrix[i, j];

                    }
                }
                Console.WriteLine();
            }
            Console.WriteLine("\n The sum of Diagonal is " + sum);
        }
    }
    }
	
![image](https://user-images.githubusercontent.com/19484531/154412111-98f009ef-8bdb-4140-a30a-d685f1065635.png)
![image](https://user-images.githubusercontent.com/19484531/154412241-debd47f5-c42c-4471-9df9-2b2c7a5cba55.png)

     program : 11  C# Program to Create a File, Check the Existence of a File and 
     Read the Contents of the File.


           
		   
		   using System;
       using System.IO;
      namespace ConsoleApp11
     {
    class FileRead
    {
        public static void Main()
        {
            String fileName;
            while (true)
            {
                Console.WriteLine("\n--- Menu---\n");
                Console.WriteLine("\n 1. Create a file");
                Console.WriteLine("\n 2. Existence of the File");
                Console.WriteLine("\n 3. Read the content of the file");
                Console.WriteLine("\n 4. Exit");
                Console.WriteLine("\n enter your choice:");
                int ch = int.Parse(Console.ReadLine());
                switch (ch)
                {
                case 1:
                Console.WriteLine("\n Enter the file name to create:");
                fileName = Console.ReadLine();
                Console.WriteLine("\n Write the Content of the File;\n");
                String r = Console.ReadLine();
                using (StreamWriter fileStr = File.CreateText(fileName))
                {
                    fileStr.WriteLine(r);
                }
                Console.WriteLine("File is created:");
                break;
            case 2:
                Console.Write("\n Enter the file name:");
                fileName = Console.ReadLine();
                if (File.Exists(fileName))
                {
                    Console.WriteLine("File exist.");

                }
                else
                {
                    Console.WriteLine("File does not exist in the current directory!");
                }
                break;
            case 3:
                Console.WriteLine("\n Enter the file name to read the content:\n");
                fileName = Console.ReadLine();
                if (File.Exists(fileName))
                {
                    using (StreamReader sr = File.OpenText(fileName))
                    {
                        string s = " ";
                        Console.WriteLine("here is the content of the File:");
                        while ((s = sr.ReadLine()) != null)
                        {
                            Console.WriteLine(s);

                        }
                        Console.WriteLine(" ");
                    }
                }
                else
                {
                    Console.WriteLine("File does not exist");
                }
                break;
            case 4:
                Console.WriteLine("\n existing---");
                return;
                default:
                Console.WriteLine("\n Invalid choice");
                break;
            }
        } 
    }
     }
    }
    
    
![image](https://user-images.githubusercontent.com/19484531/154415635-988253e6-92cd-4b3e-9caa-23caa49f4139.png)

	
![image](https://user-images.githubusercontent.com/19484531/154413109-3b55ef21-e1e8-4002-b574-b9e6882416e2.png)
![image](https://user-images.githubusercontent.com/19484531/154413310-f59eaffd-272a-417e-912f-fbd4d5211e30.png)
![image](https://user-images.githubusercontent.com/19484531/154413391-a631b4f5-d9ba-4605-8c41-fdaa3d9bf7b1.png)



     program 12: C# Program to Perform File Comparison


     using System;
    using System.IO;
    namespace ConsoleApp12
    {
    class FileRead
    {
        public static void Main()
        {
            string file1;
            string file2;
            Console.Write("Enter the first file path");
            file1 = Console.ReadLine();

            Console.Write("Enter the second file path");
            file2 = Console.ReadLine();

            if(!File.Exists(file1))
            {
                Console.WriteLine("First file does not exist!");
            }
            else if(!File.Exists(file2))
            {
                Console.WriteLine("Second file does not exist!");
            }
            else if(File.ReadAllText(file1)==File.ReadAllText(file2))
            {
                Console.WriteLine(" Both file contains same content");
            }
            else
            {
                Console.WriteLine("Content of files are not same");
            }
        }
    }
    }
    
    Files:
    
![image](https://user-images.githubusercontent.com/19484531/154415092-f1a9d895-52e7-4d2a-90d7-0cf9dd122502.png)
![image](https://user-images.githubusercontent.com/19484531/154415120-4b2f1fcc-d1ff-41e7-8b46-ea9d6db021a2.png)
![image](https://user-images.githubusercontent.com/19484531/154415149-0b61b870-c5e1-4e7e-ae5c-6c9cee221590.png)


![image](https://user-images.githubusercontent.com/19484531/154413913-20c3f1c1-0e84-4a4a-b96c-c950150fecc0.png)
![image](https://user-images.githubusercontent.com/19484531/154413995-e0142e9f-8132-41b4-8f88-c25f765492e5.png)
![image](https://user-images.githubusercontent.com/19484531/154414092-46d2778d-94b8-4da3-9967-3598da124f4b.png)


     program 13: C# Program to Implement IComparable Interface.


    using System;

    namespace ConsoleApp13
     {
    class Fraction:IComparable
    {
        int z, n;
        public Fraction(int z, int n)
        {
            this.z = z;
            this.n = n;
        }
        public static Fraction operator+(Fraction a,Fraction b)
        {
            return new Fraction(a.z * b.n + a.n * b.z, a.n * b.n);
        }
        public static Fraction operator*(Fraction a,Fraction b)
        {
            return new Fraction(a.z *b.z,a.n * b.n);
        }
        public int CompareTo(object obj)
        {
            Fraction f = (Fraction)obj;
            if ((float)z / n < (float)f.z / f.n)
                return -1;
            else if ((float)z / n > (float)f.z / f.n)
                return 1;
            else
                return 0;
        }
        public override string ToString()
        {
            return z + "/" + n;
        }
    }
    class IComInterface
    {
        public static void Main()
        {
            Fraction[] a =
            {
                new Fraction(5,2),
                new Fraction(29,6),
                new Fraction(4,5),
                new Fraction(10,8),
                new Fraction(34,7)
            };
            Array.Sort(a);
            Console.WriteLine("Implementing the IComparable Interface in " + "Displaying Fraction:");
            foreach(Fraction f in a)
            {
                Console.WriteLine(f + "");
            }
            Console.WriteLine();
            Console.ReadLine();
        }
    }
    }
    
    
   ![image](https://user-images.githubusercontent.com/19484531/154414275-6204baf6-39a6-4b0e-8d10-9d59bbaf3190.png)

    program 14: C# Program to Create Thread Pools

    using System;
    using System.Threading;
    namespace ConsoleApp14
     {
    class ThreadPoolProg
    {
        public void ThreadFun1(object obj)
        {
            int loop = 0;
            for(loop=0;loop<=4;loop++)
            {
                Console.WriteLine("Thread1 is exicuting");
            }
        }
        public void ThreadFun2(object obj)
        {
            int loop = 0;
            for(loop=0;loop<=4;loop++)
            {
                Console.WriteLine("Thread2 is executing");
            }
        }
        public static void Main()
        {
            ThreadPoolProg TP = new ThreadPoolProg();
            for(int i=0;i<2;i++)
            {
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun1));
                ThreadPool.QueueUserWorkItem(new WaitCallback(TP.ThreadFun2));
            }
            Console.ReadKey();
        }
    }
    }
    
   ![image](https://user-images.githubusercontent.com/19484531/154414420-811ec35e-e868-411e-a07d-21690c40ccc4.png)


    	program 15:Write a C# program to demonstrate error handling using Try, Catch 
      and Finally block.


     using System;

    namespace ConsoleApp15
     {
    class ExceptionHandling
    {
        static void Main(string[] args)
        {
            Age a = new Age();
            try
            {
                a.displayAge();
            }
            catch(AgeIsNegativeException e)
            {
                Console.WriteLine(" Age is NegativeException:{0}", e.Message);
            }
            finally
            {
                Console.WriteLine("Execution of Finally block done");
            }
        }
    }
    }
    public class AgeIsNegativeException:Exception
    {
    public AgeIsNegativeException(string message):base(message)
    {

    }
    }
    public class Age
    {
    int age = -5;
    public void displayAge()
    {
        if(age<0)
        {
            throw (new AgeIsNegativeException("Age can not be negative"));
        }
        else
        {
            Console.WriteLine("Age is :{0}", age);

        }
    }
    }
    
    
  ![image](https://user-images.githubusercontent.com/19484531/154414636-4ff422c7-d3e6-4a72-986a-8e883f860bd4.png)



     Extra programs;


            1)Fibonacci Series


     using System;
     public class FibonacciExample
     {
    public static void Main(string[] args)
    {
        int n1 = 0, n2 = 1, n3, i, number;
        Console.Write("Enter the number of elements: ");
        number = int.Parse(Console.ReadLine());
        Console.Write(n1 + " " + n2 + " "); //printing 0 and 1    
        for (i = 2; i < number; ++i) //loop starts from 2 because 0 and 1 are already printed    
        {
            n3 = n1 + n2;
            Console.Write(n3 + " ");
            n1 = n2;
            n2 = n3;
        }
    }
    }
    
 ![image](https://user-images.githubusercontent.com/19484531/155664675-7ae3b2d9-dc78-4f0c-8228-34e8ba0cbc06.png)

    2) Write a c# program to check prime number.

       using System;
       public class PrimeNumberExample
        {
        public static void Main(string[] args)
        {
        int n, i, m = 0, flag = 0;
        Console.Write("Enter the Number to check Prime: ");
        n = int.Parse(Console.ReadLine());
        m = n / 2;
        for (i = 2; i <= m; i++)
        {
            if (n % i == 0)
            {
                Console.Write("Number is not Prime.");
                flag = 1;
                break;
            }
        }
        if (flag == 0)
            Console.Write("Number is Prime.");
       }
       }
       
    ![image](https://user-images.githubusercontent.com/19484531/155664923-1464fa32-5936-4bc4-b656-92a381abe29a.png)
![image](https://user-images.githubusercontent.com/19484531/155665028-786400b9-9511-4bb0-82f3-4ee3ea065821.png)


    3)Write a c# program to check palindrome number.

     using System;
     public class PalindromeExample
    {
    public static void Main(string[] args)
    {
        int n, r, sum = 0, temp;
        Console.Write("Enter the Number: ");
        n = int.Parse(Console.ReadLine());
        temp = n;
        while (n > 0)
        {
            r = n % 10;
            sum = (sum * 10) + r;
            n = n / 10;
        }
        if (temp == sum)
            Console.Write("Number is Palindrome.");
        else
            Console.Write("Number is not Palindrome");
    }
    }
       
       
 ![image](https://user-images.githubusercontent.com/19484531/155665266-75077728-7bb7-4678-8c18-543e741fd448.png)
![image](https://user-images.githubusercontent.com/19484531/155665320-56c7d7c5-0430-45e3-92d0-23e6e93c9dfa.png)


    4)Write a c# program to print factorial of a number.

     using System;
     public class FactorialExample
     {
    public static void Main(string[] args)
    {
        int i, fact = 1, number;
        Console.Write("Enter any Number: ");
        number = int.Parse(Console.ReadLine());
        for (i = 1; i <= number; i++)
        {
            fact = fact * i;
        }
        Console.Write("Factorial of " + number + " is: " + fact);
    }
    }
    
  ![image](https://user-images.githubusercontent.com/19484531/155665504-c4460178-d7a1-49a1-a984-d702f6e67ab5.png)

     5) Write a c# program to check armstrong number.
     using System;
     public class ArmstrongExample
     {
    public static void Main(string[] args)
    {
        int n, r, sum = 0, temp;
        Console.Write("Enter the Number= ");
        n = int.Parse(Console.ReadLine());
        temp = n;
        while (n > 0)
        {
            r = n % 10;
            sum = sum + (r * r * r);
            n = n / 10;
        }
        if (temp == sum)
            Console.Write("Armstrong Number.");
        else
            Console.Write("Not Armstrong Number.");
    }
    }
    
    
  ![image](https://user-images.githubusercontent.com/19484531/155665732-aff99645-895f-4e1f-9a37-3a4893b7175f.png)
![image](https://user-images.githubusercontent.com/19484531/155665800-cfcaa7a8-045e-4d02-84ab-40b5fc499e18.png)


    6) Write a c# program to print sum of digits.
    
    using System;
    public class SumExample
    {
    public static void Main(string[] args)
    {
        int n, sum = 0, m;
        Console.Write("Enter a number: ");
        n = int.Parse(Console.ReadLine());
        while (n > 0)
        {
            m = n % 10;
            sum = sum + m;
            n = n / 10;
        }
        Console.Write("Sum is= " + sum);
    }
    }
    
  ![image](https://user-images.githubusercontent.com/19484531/155665993-7752813b-6889-4901-9c76-f13bae2e2df8.png)
  
    7)Write a c# program to reverse given number.

    using System;
    public class ReverseExample
     {
    public static void Main(string[] args)
    {
        int n, reverse = 0, rem;
        Console.Write("Enter a number: ");
        n = int.Parse(Console.ReadLine());
        while (n != 0)
        {
            rem = n % 10;
            reverse = reverse * 10 + rem;
            n /= 10;
        }
        Console.Write("Reversed Number: " + reverse);
    }
    }
![image](https://user-images.githubusercontent.com/19484531/155666160-2b58d7eb-5239-4eb8-af2e-c2f2ab8cf6df.png)



    Windows Application form

     using System;
    using System.Collections.Generic;
    using System.ComponentModel;
    using System.Data;
    using System.Drawing;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    using System.Windows.Forms;

    namespace ConvertDigitstoword
     {
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            lbl_words.Text = NumtoWord(long.Parse(txt_num.Txt));
        }
        public string NumtoWord(long number)
        {
            string word = "";
            if(number==0)
            {
                return "Zero";
            }
            if(number<0)
            {
                return "Minus" + Math.Abs(number);
            }
            if(number/10000000>0)
            {
                word += NumtoWord(number / 10000000) + "Corer";
                number %= 10000000;
            }
            if(number/100000>0)
            {
                word += NumtoWord(number / 100000) + "lacs";
                number %= 100000;
            }
            if(number/1000>0)
            {
                word += NumtoWord(number / 1000) + "Thousand";
                number %= 1000;
            }
            if(number/100>0)
            {
                word += NumtoWord(number / 100) + "Hundread";
                number %= 100;
            }
            if(number>0)
            {
                string[] units=new string[]{ "zero", "one", "Two", "three", "four", "five", "six", "seven", "eight", "nine", "eleven", "twelve", "Thirteen", "forteen", "fifteen", "sixteen", "seventeen", "eighteen", "nineteen" };
                String[] Tens = new string[] { "zero", "ten", "Twenty", "thirty", "fourty", "fifty", "sixty", "seventy", "Eighty", "ninty" };
                if (number < 20)
                {
                    word += units[number];
                }
                else
                {
                    word += Tens[number / 10];
                    if(number%10>0)
                    {
                        word += units[number % 10];
                    }
                }
            }
            return word;
        }

        
    }
    }
    
    output: 
  ![image](https://user-images.githubusercontent.com/19484531/157640098-03bcfe8e-4f0b-4cd5-89de-4422e026f6e3.png)
![image](https://user-images.githubusercontent.com/19484531/157640158-eeba6b36-9571-4d7d-8bc4-3b7775fbf140.png)


![image](https://user-images.githubusercontent.com/19484531/157641718-bed9ab7d-f231-4987-8978-eea0511f98bf.png)
![image](https://user-images.githubusercontent.com/19484531/157641827-fb31644a-6a11-450b-8a5c-ae4bc18a7d01.png)


     3)
         using System;
     using System.Collections.Generic;
    using System.ComponentModel;
    using System.Data;
    using System.Drawing;
    using System.Linq;
     using System.Text;
    using System.Threading.Tasks;
    using System.Windows.Forms;

    namespace WindowsFormsApp2
    {
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void btnrev_Click(object sender, EventArgs e)
        {
            string inputString, revstr = "";
            int Length;
            inputString = txtInput.Text;
            Length = inputString.Length - 1;
            while (Length >= 0)
            {
                revstr = revstr + inputString[Length];
                Length--;
            }
            MessageBox.Show("Reverse String Is : " + revstr, "Result");
        }

        private void btntrim_Click(object sender, EventArgs e)
        {
            string inputString;
            inputString = txtInput.Text;
            MessageBox.Show("The String After Trimming : " + inputString.Trim(), "Result");
        }

        private void btnpad_Click(object sender, EventArgs e)
        {
            string inputString;
            inputString = txtInput.Text;
            inputString = inputString.PadLeft(10, '*');
            inputString = inputString.PadRight(15, '*');
            MessageBox.Show("String After Padding : " + inputString, "Result");

        }
    }
    }


![image](https://user-images.githubusercontent.com/19484531/158738991-a873a7a6-64e6-4508-ae9c-020a9b8edb0a.png)
![image](https://user-images.githubusercontent.com/19484531/158739083-0550181a-d89f-40ae-bf65-6883920c0eca.png)
![image](https://user-images.githubusercontent.com/19484531/158739127-b886e63c-942c-40d8-b132-2e124992bdd4.png)
![image](https://user-images.githubusercontent.com/19484531/158739163-804bacfb-e867-47b7-b833-e228b94091f4.png)


    4) Progress Bar
     using System;
     using System.Collections.Generic;
    using System.ComponentModel;
    using System.Data;
    using System.Drawing;
    using System.Linq;
    using System.Text;
    using System.Threading;
    using System.Windows.Forms;

    namespace ProgresBar
    {
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            backgroundWorker1.WorkerReportsProgress = true;
            backgroundWorker1.RunWorkerAsync();
        }

        private void backgroundWorker1_DoWork(object sender, DoWorkEventArgs e)
        {
            for (int i = 1; i <= 100; i++)
            {
                Thread.Sleep(50);
                backgroundWorker1.ReportProgress(i);
            }
        }

        private void backgroundWorker1_ProgressChanged(object sender, ProgressChangedEventArgs e)
        {
            progressBar1.Value = e.ProgressPercentage;
            this.Text = "Progress: " + e.ProgressPercentage.ToString() + "%";
        }
    }
    }

![image](https://user-images.githubusercontent.com/19484531/158745439-8bbf5e14-8852-4b05-b2be-e0a5d2e936d3.png)


![image](https://user-images.githubusercontent.com/19484531/158745318-3787943c-0731-4e87-a628-bcae19bc3655.png)



     20. Develop a winform application to create flat clock.
     using System;
     using System.Collections.Generic;
     using System.ComponentModel;
     using System.Data;
     using System.Drawing;
    using System.Linq;
    using System.Text;
    using System.Threading;
    using System.Windows.Forms;
    namespace clock
    {
        public partial class Form1 : Form
        {
          public Form1()
          {
             InitializeComponent();
              timer1.Start();
          }
     private void Form1_Load(object sender, EventArgs e)
    {
        System.Timers.Timer timer = new System.Timers.Timer();
          timer.Interval = 1000;//1s
        timer.Elapsed += Timer_Elapsed;
       timer.Start();
     }
    private void Timer_Elapsed(object sender, System.Timers.ElapsedEventArgs e)
    {
        circularProgressBar1.Invoke((MethodInvoker)delegate
          {
             circularProgressBar1.Text = DateTime.Now.ToString("hh:mm:ss");
              circularProgressBar1.SubscriptText = DateTime.Now.ToString("tt");//AM or PM
         });
     } 
    }
    }
    
    using System;
    using System.Collections.Generic;
     using System.ComponentModel;
     using System.Data;
     using System.Drawing;
     using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
      using System.Windows.Forms;

     namespace Game
     {
    public partial class Form1 : Form
    {
        static Random r = new Random();
        int value;
        int guessnum;
        int win = 10;
        int guess = 1;
      
        public Form1()
        {
            InitializeComponent();
            value = r.Next(100);
            this.Controls.Clear();
            this.BackColor = Color.SkyBlue;
            this.AutoSize = true;
            this.Padding = new Padding(16);
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

        private void button1_Click(object sender, EventArgs e)
        {
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
                    MessageBox.Show("Wrong Guess and number of guesses  left are " + (10 - guess));

                }
                else if (guessnum > value)
                {
                    richTextBox2.Text += guessnum + "\n";
                    MessageBox.Show("Wrong Guess and number of guesses  left are " + (10 - guess));
                }
                guess++;
                win--;
            }
            if (guess == 11)
            {
                MessageBox.Show("You loose,Correct Guess is " + value);
            }
        }
        
    }
    }
    


![image](https://user-images.githubusercontent.com/19484531/158954933-6a96738d-6223-4edf-a1de-82c39fab9eea.png)

![image](https://user-images.githubusercontent.com/19484531/158955158-f5bc0619-ec6e-45df-92f2-87b1f60e08ef.png)
![image](https://user-images.githubusercontent.com/19484531/158955310-c971447c-146e-4da6-8bbf-21183cc5a95d.png)
![image](https://user-images.githubusercontent.com/19484531/158955687-64ea5d78-f365-4647-b200-83bd7b42a07c.png)

     C# Program to Perform binary tree

     using System;
    using System.Collections.Generic;
    using System.ComponentModel;
    using System.Data;
    using System.Drawing;
    using System.Linq;
    using System.Text;
    using System.Threading.Tasks;
    using System.Windows.Forms;
    using System.Drawing.Drawing2D;

     namespace BinaryTree
     {
    public partial class Form1 : Form
    {
        private Node root;
        public Form1()
        {
            InitializeComponent();
            this.root = null;
            test();
        }
        void test()
        {
            textBox1.Text = "5";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "3";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "2";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "1";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "4";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "7";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "6";
            btnAdd_Click(btnAdd, null);
            textBox1.Text = "8";
            btnAdd_Click(btnAdd, null);
        }
        private void btnCreate_Click(object sender, EventArgs e)
        {
           
                root = null;
                pictureBox1.Image = null;
          

        }

        private void btnAdd_Click(object sender, EventArgs e)
        {
            int value = int.Parse(textBox1.Text);
            if (root == null)
                root = new Node(value);
            else

            {
                if (root.Add(value) == false)
                    MessageBox.Show("The value already exists!");

            }
            drawTree();

        }

        private void btnRemove_Click(object sender, EventArgs e)
        {
            int value = int.Parse(textBox1.Text);
            if (root != null)

            {
                bool status = root.Remove(value, root, ref root);
                if (status == false)

                {
                    MessageBox.Show("the value does not exists");

                }

            }
            drawTree();
        }

        private void btnSearch_Click(object sender, EventArgs e)
        {
            string msg;
            int value = int.Parse(textBox1.Text);
            if (root == null)

            {
                msg = "Tree is empty";
            }
            else

            {
                if (root.Exists(value))

                {
                    msg = "Value found";
                }
                else

                {
                    msg = "Value not found";

                }

            }
            MessageBox.Show(msg);
        }
        void drawTree()
        {
            if (root != null)
                pictureBox1.Image = root.Draw();
            else
                pictureBox1.Image = null;
            this.Update();
        }
        /*static void Main()
        {
            Application.Run(new Form1());
        }*/
    }

    class Node
    {
        internal Node left { get; set; }
        internal Node right { get; set; }
        internal int value;
        internal int center = 12;
        private static Bitmap nodeBg = new Bitmap(30, 25);
        private static Font font = new Font("Arial", 14);
        internal Node(int value)
        {
            this.value = value;
        }
        internal bool Add(int value)
        {
            Node node = new Node(value);
            if (value < this.value)
            {
                if (this.left == null)
                {
                    this.left = node;
                    return true;
                }
                else
                    return this.left.Add(value);
            }
            else if (value > this.value)
            {
                if (this.right == null)
                {
                    this.right = node;
                    return true;
                }
                else
                    return this.right.Add(value);
            }
            return false;
        }
        internal bool Remove(int value, Node parent, ref Node root)
        {
            if (value < this.value)
            {
                if (left != null)
                {
                    return left.Remove(value, this, ref root);
                }
            }
            else if (value > this.value)
            {
                if (right != null)
                {
                    return right.Remove(value, this, ref root);
                }
            }
            else if (value == this.value)
            {
                bool isLeft = (this == parent.left);
                if (left == null && right == null)
                {
                    if (root == this)
                        root = null;
                    else
                    if (isLeft) parent.left = null; else parent.right = null;
                }
                else if (right == null)
                {
                    if (isLeft) parent.left = left; else parent.right = left;
                    if (root == this)
                        root = left;
                }
                else
                {
                    if (right.left == null)
                    {
                        right.left = left;
                        if (isLeft) parent.left = right;
                        else
                            parent.right = right;
                        if (root == this)
                            root = right;
                    }
                    else
                    {
                        Node node = right;
                        while (node.left.left != null)
                            node = node.left;
                        Console.WriteLine("Node: " + node.value);
                        this.value = node.left.value;
                        Console.WriteLine("here");
                        node.left = null;
                    }
                }
                return true;
            }
            return false;
        }
        public Image Draw()
        {
            Size lSize = new Size(nodeBg.Width / 2, 0);
            Size rSize = new Size(nodeBg.Width / 2, 0);
            Image lNodeImg = null;
            Image rNodeImg = null;
            int lCenter = 0, rCenter = 0;

            if (this.left != null)
            {
                lNodeImg = left.Draw();
                lSize = lNodeImg.Size;
                this.center = lSize.Width;
                lCenter = left.center;
            }
            if (this.right != null)
            {
                rNodeImg = right.Draw();
                rSize = rNodeImg.Size;
                rCenter = right.center;
            }
            int maxHeight = (lSize.Height < rSize.Height) ? rSize.Height : lSize.Height;
            if (maxHeight > 0) maxHeight += 35;
            Size resultSize = new Size(lSize.Width + rSize.Width, nodeBg.Size.Height +
            maxHeight);
            Bitmap result = new Bitmap(resultSize.Width, resultSize.Height);

            Graphics g = Graphics.FromImage(result);
            g.SmoothingMode = SmoothingMode.HighQuality;
            g.FillRectangle(Brushes.White, new Rectangle(new Point(0, 0), resultSize));
            g.DrawImage(nodeBg, lSize.Width - nodeBg.Width / 2, 0);

            string str = "" + value;
            g.DrawString(str, font, Brushes.Black, lSize.Width - nodeBg.Width / 2 + 7,
           nodeBg.Height / 2f - 12);
            Pen pen = new Pen(Brushes.Black, 1.2f);
            float x1 = center;
            float y1 = nodeBg.Height;
            float y2 = nodeBg.Height + 35;
            float x2 = lCenter;
            var h = Math.Abs(y2 - y1);
            var w = Math.Abs(x2 - x1);
            if (lNodeImg != null)
            {
                g.DrawImage(lNodeImg, 0, nodeBg.Size.Height + 35);
                var points1 = new List<PointF>
      {
     new PointF(x1, y1),
     new PointF(x1 - w/6, y1 + h/3.5f),
      new PointF(x2 + w/6, y2 - h/3.5f),
     new PointF(x2, y2),
      };
                g.DrawCurve(pen, points1.ToArray(), 0.5f);
            }
            if (rNodeImg != null)
            {
                g.DrawImage(rNodeImg, lSize.Width, nodeBg.Size.Height + 35);
                x2 = rCenter + lSize.Width;
                w = Math.Abs(x2 - x1);
                var points = new List<PointF>
    {
     new PointF(x1, y1),
     new PointF(x1 + w/6, y1 + h/3.5f),
    new PointF(x2 - w/6, y2 - h/3.5f),
    new PointF(x2, y2)
    };
                g.DrawCurve(pen, points.ToArray(), 0.5f);
            }
            return result;
        }
        public bool Exists(int value)
        {
            bool res = value == this.value;
            if (!res && left != null)
                res = left.Exists(value);
            if (!res && right != null)
                res = right.Exists(value);
            return res;
        }
    }
    }

![image](https://user-images.githubusercontent.com/19484531/159863826-f9d7d6b5-7ed5-4833-ac76-864a2549ffd7.png)
![image](https://user-images.githubusercontent.com/19484531/159864014-133ca64a-e760-463b-af6e-251b0ff8bda8.png)
![image](https://user-images.githubusercontent.com/19484531/159864202-23243460-9933-45c5-8441-42fdffb11c75.png)
![image](https://user-images.githubusercontent.com/19484531/159864248-93db5013-940f-4247-9d1f-f4252f16db95.png)
![image](https://user-images.githubusercontent.com/19484531/159864285-2ebb000e-f8be-4885-b1a1-092feb19f052.png)
