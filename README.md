# Codsoft-task1-number-game
import java.util.Random;
import java.util.Scanner;

public class NumberGame {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        int lowerBound = 1;     // Lower bound of the number range
        int upperBound = 100;   // Upper bound of the number range
        int secretNumber = random.nextInt(upperBound - lowerBound + 1) + lowerBound;
        int attempts = 0;
        boolean hasGuessedCorrectly = false;

        System.out.println("Welcome to the Number Guessing Game!");
        System.out.println("I have chosen a number between " + lowerBound + " and " + upperBound + ".");
        System.out.println("Can you guess what it is?");

        while (!hasGuessedCorrectly) {
            System.out.print("Enter your guess: ");
            int guess = scanner.nextInt();
            attempts++;

            if (guess < secretNumber) {
                System.out.println("Too low! Try guessing higher.");
            } else if (guess > secretNumber) {
                System.out.println("Too high! Try guessing lower.");
            } else {
                hasGuessedCorrectly = true;
                System.out.println("Congratulations! You guessed the number " + secretNumber + " correctly.");
                System.out.println("Number of attempts: " + attempts);
            }
        }

        scanner.close();
    }
}
