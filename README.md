# fakejobtitle-2-project
import java.util.Random;
import java.util.Scanner;

public class SillyJobMaker {
    
    public static void main(String[] args) {
        // Let's set up our word banks first - these are the building blocks for our fake jobs
        String[] descriptors = {
            "Quantum", "Digital", "Synergy", "Global", "Virtual", 
            "Chief", "Senior", "Cloud", "Blockchain", "AI",
            "Ninja", "Wizard", "Rockstar", "Unicorn", "Guru",
            "Creative", "Innovative", "Dynamic", "Agile", "Scalable"
        };
        
        String[] roles = {
            "Developer", "Designer", "Officer", "Manager", "Specialist",
            "Consultant", "Architect", "Engineer", "Analyst", "Strategist",
            "Marketer", "Evangelist", "Hacker", "Programmer", "Technician"
        };
        
        // Tools we'll need
        Scanner keyboard = new Scanner(System.in);
        Random rand = new Random(); // This will help us pick random words
        boolean keepGoing = true;
        
        System.out.println("\n=== WELCOME TO THE FAKE JOB TITLE GENERATOR ===");
        System.out.println("(Perfect for LinkedIn, resumes, and confusing your parents)\n");
        
        // Keep generating titles until the user says stop
        while (keepGoing) {
            // Grab one random word from each list
            String firstWord = descriptors[rand.nextInt(descriptors.length)];
            String secondWord = roles[rand.nextInt(roles.length)];
            
            // Mash them together to create corporate nonsense
            String fakeJob = firstWord + " " + secondWord;
            
            // Show the glorious result
            System.out.println("Your new fake job title is:");
            System.out.println(">>> " + fakeJob + " <<<");
            System.out.println(); // Just some breathing room
            
            // Ask if they want another
            System.out.print("Want another? (y/n): ");
            String answer = keyboard.nextLine().toLowerCase();
            
            // Check if they've had enough corporate buzzwords
            if (answer.equals("n") || answer.equals("no")) {
                keepGoing = false;
                System.out.println("\nGo update your LinkedIn profile!");
            }
        }
        
        keyboard.close(); // Always clean up after yourself
    }
}
