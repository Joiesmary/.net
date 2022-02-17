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
