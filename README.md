Longest palindrome in an array
Here we find the longest palindrome number from the given array.

so here we need to sort the array in ascending order and later check from the last that the given number is palindrome or not.

the reason behind to sort an array is, we want the longest palindrome number so, in the sorted array, we got the largest number from the last element of the array, and check this is a palindrome or not and check till starting element. If there is no palindrome number so return -1 and print that there is no palindrome number.

Example
Input a[] = {1, 232, 54545, 999991};

Output: 54545

Input: arr[] = {1, 2, 3, 4, 5, 50};

Output: 5
now we will see the java program and working to find the largest number of the array.

Longest palindrome
Working
Step 1. Initialize arrays.

Step 2. Declare the scanner class for taking input.

Step 3. take array size from the user.

Step 4. Take an element of the array from the user.

Step 5.  store the return value of function largest in a larger variable.

largest(int a[], int size)

Step 1. Initialise temp variable.

Step 2.  Initialise the two-loop for sorting.

Step 3.  perform sorting.

Step 4. Initialise backward for loop for checking the large palindrome number.

Step 5. Check the current index value is a palindrome or not to call the ispalindrome Function. and return the current element.

Step 6. if there is not any palindrome number so return -1.

boolean isPalindrome(int n)

Step1. Copy the original number which is passed from the main function.

Step 2. Initialise while loop to find the reverse of the number.

Step 3. If the reverse of the number is equal to the original number then return true otherwise, return false. 

C	JAVA	Python
import java.util.Scanner;
import java.util.*;
public class Main
{
      public static boolean isPalindrome(int n) 
      {
             int remainder,number,reverse=0;
             number=n;
             //while loop for find the reverse of the number
             while(n!=0)
             {
                  remainder=n%10;
                  reverse=reverse*10+remainder;
                  n=n/10;
             }
              //check whether number is palindrome or not
             if(number==reverse)
                  return true;
             else
                  return false;
       }

       public static int largest(int []arr, int n) 
       {
             int i,j,temp;
             //sorting of number in ascending order
             for(i=0;i<n;i++)
             {
                 for(j=0;j<n;j++)
                 {
                     if(arr[i]<arr[j])
                     {
                         temp=arr[i];
                         arr[i]=arr[j];
                         arr[j]=temp;
                      }
                   }
                }
            //check from the last index of array that number is palindrome or not
            //start from last because we want longest palindrome number that is the reason of the sorting
            for (i = n - 1; i >= 0; --i) 
            { 
                 if (isPalindrome(arr[i])) 
                 return arr[i]; 
            }
            return -1; 
       }
       public static void main(String[] args) 
       {
            int[] arr= new int[50];
            Scanner sc=new Scanner(System.in);
            System.out.println("enter size");
            int size=sc.nextInt();
            System.out.println("enter element");
            for(int i=0;i<size;i++)
            {
                 arr[i]=sc.nextInt();
            }
            int larger=largest(arr, size);
            if(larger==-1)
                 System.out.println("There is no palindrome number in the array"); 
            else
                 System.out.println("Langest palindrome number in the array"+larger);
        }
}
Output
case 1:
enter size 
5
enter element
12
3
11
212
345
Longest palindrome number in the array 212
case 2:
enter size
4
enter element
21
32
41
27
there is no palindrome in the array
