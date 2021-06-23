# weekly_Programs
//Question_1: Currency


import java.util.*;
import java.lang.*;

public class currency
{
    public static void countCurrency(int amount)
    {
        int[] notes = new int[]{ 2000, 500, 200, 100, 50, 20, 10, 5, 2,1 };
        int[] noteCounter = new int[10];
   
        for (int i = 0; i < 10; i++) 
        {
            if (amount >= notes[i]) 
            {
                noteCounter[i] = amount / notes[i];
                amount = amount - noteCounter[i] * notes[i];
            }
        }
    
        // Print notes
        System.out.println("Currency Count ->");
        for (int i = 0; i < 10; i++)
        {
                System.out.print(noteCounter[i]+" ");
        }
    }
    
 
    public static void main(String args[])
    {
        
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the Savings:");
        int amount = sc.nextInt();
        if(amount<0 || amount>25000)
            System.out.println("Error");
        else
            countCurrency(amount);
    }
    
}


//output

Enter the Savings:
8644
Currency Count ->
4 1 0 1 0 2 0 0 2 0 



