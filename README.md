# Check-Whether-or-Not-the-Number-is-an-Armstrong-Number
Check Whether or Not the Number is an Armstrong Number
Given an integer input, the objective is to check whether or not the number input is an Armstrong number or not.

However, Armstrong number is any number following the given rule –

abcd… = an + bn + cn + dn + …
Where n is the order(length/digits in number)
Also check – Armstrong Number in a given Range in Java

Armstrong Numbers
Example
Input : 371
Output : It's an Armstrong Number.
Explanation: 371 = 3^3 + 7^3 + 1^3
Therefore it's an Armstrong number.
Armstrong Number in Java
Method 1: Using Iteration
In this method we’ll use loops to check for Whether or not the number input is an Armstrong Number.

Working
For an integer input number, we do the following operations

Run a for loop to extract the last digit and break the number by size-1 with every iteration.
With each iteration raise the extracted digit to the power of the length of the number.
Append the value to the sum variable.
Print the sum variable when the loop is terminated.
Let’s implement the above logic in Java Language.

Java Code
Run
public class Main
{
  public static void main (String[]args)
  {
    int num = 407, len;

    // function to get order(length)
      len = order (num);

    // check if Armstrong
    if (armstrong (num, len))
        System.out.println(num + " is armstrong");
    else
        System.out.println(num + " is armstrong");

  }


  static int order (int x)
  {
    int len = 0;
    while (x != 0 )
      {
	len++;
	x = x / 10;
      }
    return len;
  }

  static boolean armstrong (int num, int len)
  {

    int sum = 0, temp, digit;
    temp = num;

    // loop to extract digit, find power & add to sum
    while (temp != 0)
      {
	// extract digit
	digit = temp % 10;

	// add power to sum
	sum = sum + (int)Math.pow(digit, len);
	temp /= 10;
      };

    return num == sum;
  }
}
Output
407 is armstrong
Method 2: Using Recursion
In this method we’ll use Recursion to check whether or not the number is an Armstrong Number. To know more about recursion in Java check out, Java Recursion .

Working
For an input integer, we do the following

Define a recursive function with base case as number == 0.
Set recursive step call as checkArmstrong(num/10, length).
Keep append the sum variable with each recursive call and return the sum variable.
Print the sum variable.
Let’s implement the above logic in Java Language.

Java Code
Run
import java.util.*;
import java.lang.*;

class Main {

    // Driver code
    public static void main(String[] args)
    {
        //variables initialization
        int num = 1634, reverse = 0;
        int len = order(num);

        if (num == getArmstrongSum(num, len))
            System.out.println(num + " is an Armstrong Number");
        else
            System.out.println(num + " is not an Armstrong Number");

    }

    private static int getArmstrongSum(int num, int order) {
        if(num == 0)
            return 0;

        int digit = num % 10;

        return (int) Math.pow(digit, order) + getArmstrongSum(num/10, order);
    }

    private static int order(int num) {
        int len = 0;
        while (num!=0)
        {
            len++;
            num = num/10;
        }
        return len;
    }

}
Output
1634 is an Armstrong Number
