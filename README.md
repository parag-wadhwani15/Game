# Game

//I made a simple "Guess The Number" game using java programming language.

import java.util.Scanner;
import java.util.Random;

public class OASIS_GUESSTHENUMBER
{
    public static void main(String[] args)
	{
        Scanner input = new Scanner(System.in);
        boolean again;
        do 
		{
            playGame();
            
            System.out.print("Do you want to play again? (yes/no): ");
			
            String response = input.next();
			
            again = response.equalsIgnoreCase("yes");	
        } 
		while (again);
        System.out.println("Thanks for playing, hope you enjoyed !!");
    }
	
    public static void playGame() 
	{
		int randomNumber = (int) (Math.random() * 100);
        int guess;
        int attempts = 0;
		
        System.out.println("\n Welcome to the Guess the Number game!\n");
        System.out.println("\n I'm thinking of a number between 1 and 100. Can you guess what it is ?");
        
        Scanner input = new Scanner(System.in);
		
        do {
            System.out.print("Enter your guess: ");
            guess = input.nextInt();
            attempts++;
            
            if (guess < randomNumber)
			{
                System.out.println("Too low! Guess again.");
            }
			else if (guess > randomNumber)
			{
                System.out.println("Too high! Guess again.");
            }
        } 
		while (guess != randomNumber);
        
        System.out.println("Congratulations! You guessed the number in " + attempts + " guesses.");
    }
}
