# GuessNumberGame
BelajarGame
using System;

namespace GuessNumberGame
{
    class Program
    {
        static void Main(string[] args)
        {
            Random random = new Random();
            int numberToGuess = random.Next(1, 101);
            int numberOfTries = 0;
            int guess;
            bool win = false;

            Console.WriteLine("Welcome to the Guess Number Game!");
            Console.WriteLine("I'm thinking of a number between 1 and 100.");

            while (!win)
            {
                Console.Write("Enter your guess: ");
                guess = int.Parse(Console.ReadLine());
                numberOfTries++;

                if (guess < 1 || guess > 100)
                {
                    Console.WriteLine("Your guess is out of bounds! Please guess a number between 1 and 100.");
                }
                else if (guess < numberToGuess)
                {
                    Console.WriteLine("Your guess is too low.");
                }
                else if (guess > numberToGuess)
                {
                    Console.WriteLine("Your guess is too high.");
                }
                else
                {
                    win = true;
                    Console.WriteLine("Congratulations! You've guessed the number in " + numberOfTries + " tries.");
                }
            }
        }
    }
}
