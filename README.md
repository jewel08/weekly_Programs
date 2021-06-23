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



//Question_2_DailyMarket


import java.util.*;

public class DailyMarket
{
    
    public static void Calculations(float x, float y, float z, float t, float w, int month,int year)
    {
        float days=numberDays(month,year);
        float daily= x+y+z+t+w;
        float monthly = daily*days;
        System.out.print(daily+" "+monthly);
    }
    public static boolean isDateValid(int month, int year)
    {
        if(month<0||month>12||year<0)
            return false; 
        return true;
    }
    public static boolean checkYear(int year)
    {
        if (((year % 4 == 0) && (year % 100!= 0)) || (year%400 == 0))
            return true; 
        return false;
    }
    public static float numberDays(int month,int year)
    {
        float[] days= new float[]{31,28,31,30,31,30,31,31,30,31,30,31};
        boolean leap=checkYear(year);
        if (leap==true)
            days[1]=29;
        float day = days[month-1];
        return day;
    }
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter the values:");
        float x=sc.nextFloat();
        float y=sc.nextFloat();
        float z=sc.nextFloat();
        float w=sc.nextFloat();
        float t=sc.nextFloat();
        int month=sc.nextInt();
        int year=sc.nextInt();
        boolean check= isDateValid(month,year);
        if(y<x || y<z || y<t || y<w || y==0 || x==0 || z==0|| w==0 || t==0 || check==false)
            System.out.println("Error");
        else
        {
            Calculations(x,y,z,t,w,month,year);
        }
    }
}



//Output

Enter the values:125.5 335.5 255 300.5 100.5 2 2016
1117.0 32393.0



//question_3_Swans and eggs

import java.util.*;

public class SwanEggs 
{
	
	public static void main(String[] args)
	{
	
		int total_no_of_eggs = 0;
		
		Scanner sc = new Scanner(System.in);
		System.out.println("Enter The number of swan and their weights in integer and separated by space.");
        int n= sc.nextInt(); 
		if(n==0)
		      System.out.print("0 ");
		else if(n<0)
		      System.out.print("Error");
		else
		{
		    int[] age=new int[n];
		    for(int i=0;i<n;i++)
		    {
		        age[i] = sc.nextInt();
		    }
		    for(int i=0;i<n;i++)
		    {
		        
		        if(age[i]>52)
		        {
		            total_no_of_eggs=total_no_of_eggs+16;
		        }
		        else
		        {
		            int rem_weeks = 4 - (52-age[i]);
		            if(rem_weeks >= 0)
                                total_no_of_eggs = total_no_of_eggs + (rem_weeks * 4);
                            else
                            {
                                System.out.println("error");
                                break;
                            }
                            
                        }
                       
                    }
                    
                     System.out.println("Total eggs in a month:"+total_no_of_eggs);
                }
	}
}

//output

Enter The number of swan and their weights in integer and separated by space.
6 51 50 48 49 52 50
Total eggs in a month:48


//Question_4_MagicalNumber

import java.util.*;

public class MagicalNumber
{
    public static void Check(long n)
    {   
        long count = 0,t1=1,t2=1,p=0,q=0;
        while (n != 0) 
        {
            long d=n%10;//digit Extraction
            if(d!=0)
            {
                if(count%2==0)
                    t1=t1*d;
                else
                    t2=t2*d;
            }
            n = n/10;
            d=0;
            count++;
        }
        if(count>10)
            System.out.print("Error ");
        else
        {
            if(count%2==0)
            {
                p=t1;
                q=t2;
            }
            else
            {
                p=t2;
                q=t1;
            }
            if(p>q)
                System.out.print("Dominant ");
            else
                System.out.print("Magical ");
        }
    }
    public static void main(String[] args)
    {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter total numbers input and the individual number separated by space.");
        int k= sc.nextInt();

        if(k<0)
            System.out.println("Error");
        else
        {
            long[] n= new long[k];
            for(int i=0;i<k;i++)
            {
                n[i]=sc.nextLong();
            }
            for(int i=0;i<k;i++)
            {
                long num=n[i];
                if(num<=0)
                    System.out.print("Error ");
                else
                    Check(num);
            }
        }
    }
}


//output

Enter total numbers input and the individual number separated by space.
2 123456789012 1254
Error Dominant


//Question_5_Granted


public class Granted_program
{
   
    public static boolean isDateValid(int date,int month, int year)
    {
        if(date<0||date>32||month<0||month>12||year<0)
            return false; 
        return true;
    }
    public static boolean checkYear(int year)
    {
        if (((year % 4 == 0) && (year % 100!= 0)) || (year%400 == 0))
            return true; 
        return false;
    }
    public static int totalDays(int current_date, int current_month, int current_year, int birth_date, int birth_month, int birth_year)
    {
        int totalDays=0;
        int copy_current_date=current_date;
        int copy_current_month=current_month;
        int copy_current_year=current_year;
        int[] month = new int[] { 0,31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
        if(isDateValid(current_date, current_month, current_year) || isDateValid(birth_date, birth_month, birth_year))
        {
            if (birth_date > current_date) 
            {
                copy_current_month = current_month - 1;
                copy_current_date = current_date + month[birth_month - 1];
            }

            if (birth_month > current_month)  
            {
                copy_current_year = current_year - 1;
                copy_current_month = current_month + 12;
            }


	    int calculated_date = copy_current_date - birth_date;
	    int calculated_month = copy_current_month - birth_month;
	    int calculated_year = copy_current_year - birth_year;
	    System.out.println("The person is "+calculated_year+" years "+calculated_month+" months "+calculated_date+" days old");
            for(int i=birth_year;i<current_year;i++)
            {
                if(checkYear(i))
                { 
                    totalDays =totalDays + 366;
                }
                else
                {
                    totalDays =totalDays + 365;
                }
            }
            
            boolean isLeap=checkYear(current_year);
            if (isLeap &&  calculated_month > 2)
			totalDays = totalDays + 1;
		for (int i = 1; i < calculated_month; i++) 
		{

			totalDays = totalDays + month[i];

		}

		return totalDays + calculated_date;
	}
	else
	       return 0;
    }
    public static void divisor(int totalDays)
    {
        int weeks= totalDays/7;
        System.out.println("Total Weeks = "+weeks);
        int array[]=new int[100];
        int m=0;
        for (int i=1;i<=weeks;i++)
        {
            if (weeks%i==0)
            {
                array[m]=i;
                m++;
            }      
        }
        System.out.println("Factors of total number of weeks are:");
        int u;
        for(u=0; u<m;u++)
        {
            System.out.println(array[u]+" ");
	
        }
        int q=0;//for prime
        int p=0;//for non prime
        int c=0;
        for(int x=0 ; x<m;x++)
        {
            int factors = array[x];
            for(int i = 3; i <factors; i++)
            {
                if(factors%i==0)
                c++;
            }
            if(c==0)
            {   
                System.out.println("prime factor="+factors);
                q=q+factors;
            }
            else
            {
                p=p+factors;
                System.out.println("non prime factor="+factors);
            }
        }
        System.out.println("Sum of all prime factors :"+q);
        System.out.println("Sum of all non prime factors :"+p);
        if(q>p)
            System.out.println("Granted");
        else
           System.out.println("NOT Granted");
    }
    public static void main(String[] args)
    {
        // present date
        int current_date = 23;
        int current_month = 6;
        int current_year = 2021;
 
        // birth dd/ mm/ yyyy
        int birth_date = 2;
        int birth_month = 8;
        int birth_year = 2000;
        int totalDays= totalDays( current_date,  current_month,  current_year,  birth_date,  birth_month,  birth_year);
        System.out.println("Total days number of days = "+totalDays);
        divisor(totalDays);
    }
}

     //Output
     
The person is 20 years 10 months 21 days old
Total days number of days = 7965
Total Weeks = 1137
Factors of total number of weeks are:
1 
3 
379 
1137 
prime factor=1
prime factor=3
prime factor=379
non prime factor=1137
Sum of all prime factors :383
Sum of all non prime factors :1137
NOT Granted
