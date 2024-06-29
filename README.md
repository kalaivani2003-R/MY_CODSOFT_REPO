import java.util.Random;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Random value = new Random();
        int min = 1;
        int max = 100;
        int attempts=3;
        int score=0;
        boolean playagain=true;
        boolean correctguess=false;
        Scanner sc = new Scanner(System.in);
        while(playagain){
            
        
        int randomNumber = value.nextInt((max - min + 1)) + min;
        System.out.println(randomNumber);
        System.out.println("enter the guess between(1-100): ");
    
        
        for(int count =1; count<=attempts;count++){
            int guess= sc.nextInt();
            System.out.println("attempts" + count + " ");
        
        if (guess == randomNumber){
            System.out.println("Your guess is right:");
            correctguess=true;
            score++;
            break;
            
        }
    
        else if(guess < randomNumber){
            System.out.println("Your guess is less than the generated random number:");
        }
        
        else {
            System.out.println("your guess is wrong:");
        }
        if (!correctguess){
            System.out.println("Sorry, you've used all your attempts. The correct number was " + randomNumber + ".");
        }
        }
        
        
        System.out.print("Do you want to play again? (yes/no): ");
            sc.nextLine(); // Consume the newline
            String response = sc.nextLine();

            if (!response.equals("yes")) {
                playagain = false;
            }
        }

        System.out.println("Your total score based upon number of win is: " + score);
        sc.close();
        
      
    }
}
