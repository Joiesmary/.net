# .net

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

    program 2

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

    program 3


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


    program 4


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



     program:5

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


<br>program 8:</br>

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


<br>program 9:
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

     program 10:

                 
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

program : 11

           
		   
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



program 12


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


program 13:


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

program 14

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


program 15:

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




 
                   








