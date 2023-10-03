# oasisinfobytetask1
ONLINE EXAMINATION SYSTEM
import java.util.Scanner;

public class OnlineExamSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        boolean isLoggedIn = false;
        
        String username = "user123";
        String password = "pass123";
        String currentUser = null;

        while (true) {
            System.out.println("Online Examination System");
            System.out.println("1. Login");
            System.out.println("2. Exit");

            if (isLoggedIn) {
                System.out.println("3. Update Profile and Password");
                System.out.println("4. Start Exam");
                System.out.println("5. Logout");
            }

            System.out.print("Enter your choice: ");
            int choice = scanner.nextInt();
            scanner.nextLine(); // Consume newline

            switch (choice) {
                case 1:
                    if (!isLoggedIn) {
                        System.out.print("Enter username: ");
                        String enteredUsername = scanner.nextLine();
                        System.out.print("Enter password: ");
                        String enteredPassword = scanner.nextLine();

                        if (enteredUsername.equals(username) && enteredPassword.equals(password)) {
                            isLoggedIn = true;
                            currentUser = enteredUsername;
                            System.out.println("Login successful!");
                        } else {
                            System.out.println("Invalid username or password. Try again.");
                        }
                    } else {
                        System.out.println("You are already logged in.");
                    }
                    break;
                case 2:
                    System.out.println("Exiting the system. Goodbye!");
                    System.exit(0);
                    break;
                case 3:
                    if (isLoggedIn) {
                        // Implement logic for updating profile and password here.
                        System.out.println("Profile and Password Update logic goes here.");
                    } else {
                        System.out.println("You need to log in first.");
                    }
                    break;
                case 4:
                    if (isLoggedIn) {
                        // Implement logic to start the exam, including selecting answers, timer, and auto-submit.
                        System.out.println("Starting the exam...");
                    } else {
                        System.out.println("You need to log in first.");
                    }
                    break;
                case 5:
                    if (isLoggedIn) {
                        isLoggedIn = false;
                        currentUser = null;
                        System.out.println("Logged out successfully.");
                    } else {
                        System.out.println("You are not logged in.");
                    }
                    break;
                default:
                    System.out.println("Invalid choice. Please select a valid option.");
            }
        }
    }
}
