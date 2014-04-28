ODD-EVEN-NUMBER--HOMEWORK--10--WEEK-10
======================================

ODD-EVEN NUMBER  HOMEWORK 10 WEEK 10


//  BY  REINA OLARTE

// ODD - EVEN NUMBER  ( HOMEWORK #10  WEEK 10 )

import java.util.Scanner;

public class OddEven 
{
	int RandomNumber;
	
	int computerNumber;
	
	int lownumber;
	
	int highnumber;
	
	int Count;
	
	int Wins;
	
	int Lose;
	
	String Guess;
	
	String CompResult;
	
	String Play;
	
	String KeepPlaying;
	
	boolean SIGAPlaying =true;
	
	boolean SIGA = true;
	
	Scanner input = new Scanner(System.in);
	
	public OddEven(int low, int high)
	{
		lownumber = low;
		
		highnumber = high;
	}
	public void displayMessage()
	{
		System.out.println("HI!!! LETS GO TO PLAY TO THE ODD-EVEN GAME");

	}
	public void playGame()
	{

		while(SIGA)
		{
			RandomNumber =  lownumber + (int)(Math.random() *(highnumber- lownumber));
			
			computerNumber = RandomNumber % 2;
			
			if (computerNumber == 1)
			{
				CompResult = "ODD";
			}
			else if (computerNumber == 0)
			{
				CompResult = "EVEN";
			}
			System.out.println("Please Guess Odd or Even: ");
			
			Guess = input.next();
			
			if(Guess.toUpperCase().equals(CompResult))
				
			{
				System.out.printf("You won\nYou Guessed %s\ncomputer number was %d\n\n", Guess, RandomNumber);
				
				++Count;
				
				++Wins;
			}
			else
			{
				System.out.printf("You Lost\nYou Guessed %s\nComputer number was %d\n\n", Guess, RandomNumber);
				
				
				++Count;
				
				++Lose;
			}
			System.out.printf("Would you like to continue within the range %d and %d?\n",lownumber, highnumber);
			
			KeepPlaying = input.next();
			
			if(KeepPlaying.toUpperCase().startsWith("N"))
				
			{
				SIGA = false;
			}
		}//End while loop
		
	}//End Game method
	
	public void displayResults()
	{
		System.out.printf("Here are your results\nGames Played %d\nGames Won %d\nGames Lost %d\nThanks for playing\n", Count, Wins, Lose);
	}
	public boolean keepPlaying()
	{
		System.out.println("\n\nWould you like to keep Playing?\nType yes or no:");
		
		KeepPlaying = input.next();
		
		if (KeepPlaying.toUpperCase().startsWith("Y"))
		{
			SIGAPlaying = true;
		}
		else
		{
			SIGAPlaying = false;
		}
		return SIGAPlaying;
	}
	public boolean GetKeepPlaying()
	{
		return SIGAPlaying;
	}
}//End Class
