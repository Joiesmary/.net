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
	
![image](https://user-images.githubusercontent.com/19484531/154413109-3b55ef21-e1e8-4002-b574-b9e6882416e2.png)
![image](https://user-images.githubusercontent.com/19484531/154413310-f59eaffd-272a-417e-912f-fbd4d5211e30.png)
![image](https://user-images.githubusercontent.com/19484531/154413391-a631b4f5-d9ba-4605-8c41-fdaa3d9bf7b1.png)






                   








