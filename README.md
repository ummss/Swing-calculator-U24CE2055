# Swing-calculator-U24CE2055

public class Calculator {

    // Static methods for basic arithmetic operations
    public static double add(double a, double b) {
        return a + b;
    }

    public static double subtract(double a, double b) {
        return a - b;
    }

    public static double multiply(double a, double b) {
        return a * b;
    }

    public static double divide(double a, double b) {
        if (b == 0) {
            System.out.println("Error: Division by zero is not allowed!");
            return Double.NaN; // Return "Not a Number" for invalid division
        }
        return a / b;
    }

    public static double modulus(double a, double b) {
        if (b == 0) {
            System.out.println("Error: Modulus by zero is not allowed!");
            return Double.NaN;
        }
        return a % b;
    }

    // Main method to interact with the user
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.println("Welcome to the Static Calculator!");
        System.out.println("Choose an operation:");
        System.out.println("1. Addition (+)");
        System.out.println("2. Subtraction (-)");
        System.out.println("3. Multiplication (*)");
        System.out.println("4. Division (/)");
        System.out.println("5. Modulus (%)");
        System.out.println("6. Exit");

        while (true) {
            System.out.print("\nEnter your choice (1-6): ");
            int choice = scanner.nextInt();

            if (choice == 6) {
                System.out.println("Exiting the calculator. Goodbye!");
                break;
            }

            // Validate choice
            if (choice < 1 || choice > 6) {
                System.out.println("Invalid choice! Please select a valid option.");
                continue;
            }

            // Get input numbers
            System.out.print("Enter the first number: ");
            double num1 = scanner.nextDouble();
            System.out.print("Enter the second number: ");
            double num2 = scanner.nextDouble();

            // Perform the selected operation
            double result;
            switch (choice) {
                case 1:
                    result = add(num1, num2);
                    System.out.printf("Result: %.2f + %.2f = %.2f\n", num1, num2, result);
                    break;
                case 2:
                    result = subtract(num1, num2);
                    System.out.printf("Result: %.2f - %.2f = %.2f\n", num1, num2, result);
                    break;
                case 3:
                    result = multiply(num1, num2);
                    System.out.printf("Result: %.2f * %.2f = %.2f\n", num1, num2, result);
                    break;
                case 4:
                    result = divide(num1, num2);
                    if (!Double.isNaN(result)) {
                        System.out.printf("Result: %.2f / %.2f = %.2f\n", num1, num2, result);
                    }
                    break;
                case 5:
                    result = modulus(num1, num2);
                    if (!Double.isNaN(result)) {
                        System.out.printf("Result: %.2f %% %.2f = %.2f\n", num1, num2, result);
                    }
                    break;
            }
        }

        scanner.close();
    }
}
