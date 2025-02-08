import javax.swing.JOptionPane;

public class SimpleCalculator {

    public static void main(String[] args) {
        // Getting the first number from the user
        String num1Str = JOptionPane.showInputDialog("Enter the first number:");
        double num1 = Double.parseDouble(num1Str); // Convert string input to double

        // Getting the second number from the user
        String num2Str = JOptionPane.showInputDialog("Enter the second number:");
        double num2 = Double.parseDouble(num2Str); // Convert string input to double

        // Presenting the user with an operation selection
        String[] operations = {"+", "-", "*", "/"};
        String operation = (String) JOptionPane.showInputDialog(
                null, "Select an operation", "Simple Calculator",
                JOptionPane.PLAIN_MESSAGE, null, operations, operations[0]);

        double result = 0;

        // Perform the operation based on user choice
        if (operation != null) {
            switch (operation) {
                case "+":
                    result = num1 + num2;
                    break;
                case "-":
                    result = num1 - num2;
                    break;
                case "*":
                    result = num1 * num2;
                    break;
                case "/":
                    // Checking for division by zero
                    if (num2 == 0) {
                        JOptionPane.showMessageDialog(null, "Error: Cannot divide by zero.");
                        return; // Exit the program
                    }
                    result = num1 / num2;
                    break;
            }
        }

        // Displaying the result
        String message = "Result: " + num1 + " " + operation + " " + num2 + " = " + result;
        JOptionPane.showMessageDialog(null, message);
    }
}
