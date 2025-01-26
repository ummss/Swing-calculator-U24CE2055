# Swing-calculator-U24CE2055
import java.util.Scanner;

public class SimpleCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Simple Calculator");
        System.out.println("Select an operation:");
        System.out.println("1. Addition (+)");
        System.out.println("2. Subtraction (-)");
        System.out.println("3. Multiplication (*)");
        System.out.println("4. Division (/)");
        System.out.println("5. Exit");

        while (true) {
            System.out.print("\nEnter your choice (1-5): ");
            int choice = scanner.nextInt();

            if (choice == 5) { // Exit condition
                System.out.println("Exiting the calculator. Goodbye!");
                break;
            }

            // Validate choice
            if (choice < 1 || choice > 5) {
                System.out.println("Invalid choice! Please select a valid option.");
                continue;
            }

            // Get input numbers from the user
            System.out.print("Enter the first number: ");
            double num1 = scanner.nextDouble();
            System.out.print("Enter the second number: ");
            double num2 = scanner.nextDouble();

            // Perform the operation based on the user's choice
            switch (choice) {
                case 1: // Addition
                    System.out.printf("Result: %.2f + %.2f = %.2f\n", num1, num2, num1 + num2);
                    break;
                case 2: // Subtraction
                    System.out.printf("Result: %.2f - %.2f = %.2f\n", num1, num2, num1 - num2);
                    break;
                case 3: // Multiplication
                    System.out.printf("Result: %.2f * %.2f = %.2f\n", num1, num2, num1 * num2);
                    break;
                case 4: // Division
                    if (num2 == 0) {
                        System.out.println("Error: Division by zero is not allowed!");
                    } else {
                        System.out.printf("Result: %.2f / %.2f = %.2f\n", num1, num2, num1 / num2);
                    }
                    break;
                default:
                    System.out.println("Invalid choice! Please try again.");
                    break;
            }
        }

        scanner.close();
    }
}
