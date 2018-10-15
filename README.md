# Integer-Divisions-Loop
A Java program which first calculates and prints out the sum of the digits of a number with at most 7 digits. Then it prints out all the divisors of the sum number that is calculated in the previous step.

import java.util.Scanner;

public class Integer_division {

	public static void main(String[] args) {

		int userInput,digits,i,j,k; double sum; String repeat;
		
		Scanner keyboard = new Scanner(System.in);
		
		System.out.println("   Welcome to our Integer Division Program!\n---------------------------------------------\n");
		
		do{
			System.out.print("\nEnter a number with at most 7-digits: ");
			
			userInput=Integer.parseInt(keyboard.nextLine());
			
			//Calculate how many digits of userInput
			i=1; digits=1;
			for (i=1;i<=7;i++)
				if (userInput>=(Math.pow(10, i-1))&&userInput<Math.pow(10, i))
					digits=i;
		
			//Calculate sum of the digits
			j=1; sum=0;
			for (j=1;j<=digits;j++)
				sum=sum+(userInput%(Math.pow(10, j))-userInput%(Math.pow(10, j-1)))/(Math.pow(10, j-1));
			System.out.println("\nSum of the digits of "+userInput+" is: "+Math.round(sum)); 

			//Print out divisors of userInput
			System.out.println("\nThe divisors of "+Math.round(sum)+" are as follows:\n");
			k=1;
			for (k=1;k<=sum;k++)
				if (sum%k==0)
					System.out.print(k+" ");
			
			//Repeat or not
			System.out.print("\n\n\nDo you want to try another number? (yes to repeat, no to stop) ");
			repeat=keyboard.nextLine().toUpperCase();
			if (repeat.compareTo("NO")==0)
				System.out.println("\nThanks and Have a Great Day!"); 
			
		}while (repeat.compareTo("YES")==0);
		
		keyboard.close();

	}

}
