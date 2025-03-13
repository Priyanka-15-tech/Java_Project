# This Java project analyzes a user-input number and determines whether it meets various mathematical properties. 
import java.util.*;
public class NumberManipulation {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter a number to analyze: ");
        int number = sc.nextInt();

        System.out.println("--------NUMBER MANIPULATION---------");
        System.out.println("Choose analysis type:");
        System.out.println("1. Even/Odd Number");
        System.out.println("2. Reverse Number");
        System.out.println("3. Buzz Number");
        System.out.println("4. Harshad Number");
        System.out.println("5. Palindrome Number");
        System.out.println("6. Rectangle Number");
        System.out.println("7. Prime Number");
        System.out.println("8. Armstrong Number");
        System.out.println("9. Automorphic Number");
        System.out.println("10. Perfect Number");
        System.out.println("11. Analyze All");
        System.out.print("Enter your choice: ");
        int choice = sc.nextInt();

        int original = number;

        if (choice == 1 || choice == 11) {
            System.out.println("Even/Odd Number: " + (number % 2 == 0 ? "Even" : "Odd"));
        }
        
        if (choice == 2 || choice == 11) {
            int reversed = 0, temp = number;
            while (temp > 0) {
                reversed = reversed * 10 + temp % 10;
                temp /= 10;
            }
            System.out.println("Reversed Number: " + reversed);
        }

        if (choice == 3 || choice == 11) {
            System.out.println("Buzz Number: " + (number % 7 == 0 || number % 10 == 7 ? "Yes" : "No"));
        }

        if (choice == 4 || choice == 11) {
            int sum = 0, tempNum = number;
            while (tempNum > 0) {
                sum += tempNum % 10;
                tempNum /= 10;
            }
            System.out.println("Harshad Number: " + (number % sum == 0 ? "Yes" : "No"));
        }

        if (choice == 5 || choice == 11) {
            int reverse = 0, tempVal = number;
            while (tempVal > 0) {
                reverse = reverse * 10 + tempVal % 10;
                tempVal /= 10;
            }
            System.out.println("Palindrome Number: " + (original == reverse ? "Yes" : "No"));
        }

        if (choice == 6 || choice == 11) {
            boolean isRectangle = false;
            for (int i = 1; i * (i + 1) <= number; i++) {
                if (i * (i + 1) == number) {
                    isRectangle = true;
                    break;
                }
            }
            System.out.println("Rectangle Number: " + (isRectangle ? "Yes" : "No"));
        }

        if (choice == 7 || choice == 11) {
            boolean isPrime = number > 1;
            for (int i = 2; i <= Math.sqrt(number); i++) {
                if (number % i == 0) {
                    isPrime = false;
                    break;
                }
            }
            System.out.println("Prime Number: " + (isPrime ? "Yes" : "No"));
        }

        if (choice == 8 || choice == 11) {
            int armstrongSum = 0, tempArm = number, digits = String.valueOf(number).length();
            while (tempArm > 0) {
                armstrongSum += Math.pow(tempArm % 10, digits);
                tempArm /= 10;
            }
            System.out.println("Armstrong Number: " + (number == armstrongSum ? "Yes" : "No"));
        }

        if (choice == 9 || choice == 11) {
            int square = number * number;
            System.out.println("Automorphic Number: " + (String.valueOf(square).endsWith(String.valueOf(number)) ? "Yes" : "No"));
        }

        if (choice == 10 || choice == 11) {
            int perfectSum = 0;
            for (int i = 1; i <= number / 2; i++) {
                if (number % i == 0) {
                    perfectSum += i;
                }
            }
            System.out.println("Perfect Number: " + (perfectSum == number ? "Yes" : "No"));
        }

        if (choice < 1 || choice > 11) {
            System.out.println("Invalid choice.");
        }
    }
}
