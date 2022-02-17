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





