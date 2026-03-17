import java.util.Scanner;

// ============================================================
// JAVA CONTROL FLOW - LAB PRACTICE SUBMISSION
// Level 1: Programs 1, 2, 4, 5
// Level 2: Programs 1, 2, 4
// Level 3: Programs 1, 4
// ============================================================

class JavaControlFlowPractice {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        // Display menu
        System.out.println("========================================");
        System.out.println("  JAVA CONTROL FLOW - LAB PRACTICE");
        System.out.println("========================================");
        System.out.println("--- LEVEL 1 ---");
        System.out.println("  1. Check if a number is divisible by 5");
        System.out.println("  2. Check if first is smallest of 3 numbers");
        System.out.println("  3. Check natural number & sum of n natural numbers");
        System.out.println("  4. Check if a person can vote");
        System.out.println("--- LEVEL 2 ---");
        System.out.println("  5. Print odd and even numbers from 1 to n");
        System.out.println("  6. Employee bonus calculator");
        System.out.println("  7. FizzBuzz (for loop)");
        System.out.println("--- LEVEL 3 ---");
        System.out.println("  8. Leap Year checker");
        System.out.println("  9. Prime number checker");
        System.out.println("========================================");
        System.out.print("Enter program number (1-9): ");
        int programChoice = input.nextInt();

        // ============================================================
        // LEVEL 1
        // ============================================================

        // L1 - Program 1: Check if a number is divisible by 5
        if (programChoice == 1) {
            // Get number input from user
            System.out.print("Enter a number: ");
            int number = input.nextInt();

            // Check divisibility by 5 using modulus operator
            boolean isDivisibleByFive = (number % 5 == 0);
            System.out.println("Is the number " + number + " divisible by 5? " + isDivisibleByFive);
        }

        // L1 - Program 2: Check if first is smallest of 3 numbers
        else if (programChoice == 2) {
            // Get 3 number inputs from user
            System.out.print("Enter number1: ");
            int number1 = input.nextInt();
            System.out.print("Enter number2: ");
            int number2 = input.nextInt();
            System.out.print("Enter number3: ");
            int number3 = input.nextInt();

            // Check if number1 is less than both number2 and number3
            boolean isFirstSmallest = (number1 < number2) && (number1 < number3);
            System.out.println("Is the first number the smallest? " + isFirstSmallest);
        }

        // L1 - Program 3: Check natural number & sum of n natural numbers
        else if (programChoice == 3) {
            // Get number input from user
            System.out.print("Enter a number: ");
            int number = input.nextInt();

            // A natural number is a positive integer (>= 1)
            if (number >= 1) {
                // Formula: sum of n natural numbers = n * (n+1) / 2
                int sumOfNaturalNumbers = number * (number + 1) / 2;
                System.out.println("The sum of " + number + " natural numbers is " + sumOfNaturalNumbers);
            } else {
                System.out.println("The number " + number + " is not a natural number");
            }
        }

        // L1 - Program 4: Check if a person can vote (age >= 18)
        else if (programChoice == 4) {
            // Get age input from user
            System.out.print("Enter age: ");
            int age = input.nextInt();

            // Voting requires age 18 or above
            if (age >= 18) {
                System.out.println("The person's age is " + age + " and can vote.");
            } else {
                System.out.println("The person's age is " + age + " and cannot vote.");
            }
        }

        // ============================================================
        // LEVEL 2
        // ============================================================

        // L2 - Program 1: Print odd and even numbers from 1 to n
        else if (programChoice == 5) {
            // Get number input from user
            System.out.print("Enter a positive integer: ");
            int number = input.nextInt();

            // Validate that number is a natural number
            if (number >= 1) {
                System.out.println("Numbers from 1 to " + number + ":");
                // Loop from 1 to number and check odd or even each iteration
                for (int i = 1; i <= number; i++) {
                    if (i % 2 == 0) {
                        System.out.println(i + " is Even");
                    } else {
                        System.out.println(i + " is Odd");
                    }
                }
            } else {
                System.out.println(number + " is not a natural number");
            }
        }

        // L2 - Program 2: Employee bonus calculator (5% bonus for > 5 years)
        else if (programChoice == 6) {
            // Get salary and years of service from user
            System.out.print("Enter employee salary: ");
            double salary = input.nextDouble();
            System.out.print("Enter years of service: ");
            int yearsOfService = input.nextInt();

            // Bonus rate is fixed at 5%
            double bonusRate = 0.05;

            // Only employees with more than 5 years get a bonus
            if (yearsOfService > 5) {
                double bonusAmount = salary * bonusRate;
                System.out.println("Years of service: " + yearsOfService);
                System.out.println("Bonus amount (5%): " + bonusAmount);
            } else {
                System.out.println("Years of service: " + yearsOfService);
                System.out.println("No bonus - requires more than 5 years of service");
            }
        }

        // L2 - Program 4: FizzBuzz using for loop
        else if (programChoice == 7) {
            // Get number input from user
            System.out.print("Enter a positive integer: ");
            int number = input.nextInt();

            // Validate positive integer input
            if (number >= 1) {
                System.out.println("FizzBuzz from 1 to " + number + ":");
                // Loop from 1 to number
                for (int i = 1; i <= number; i++) {
                    // Check multiples of both 3 and 5 first (FizzBuzz)
                    if (i % 3 == 0 && i % 5 == 0) {
                        System.out.println("FizzBuzz");
                    } else if (i % 3 == 0) {
                        // Multiples of 3 only print Fizz
                        System.out.println("Fizz");
                    } else if (i % 5 == 0) {
                        // Multiples of 5 only print Buzz
                        System.out.println("Buzz");
                    } else {
                        System.out.println(i);
                    }
                }
            } else {
                System.out.println(number + " is not a positive integer");
            }
        }

        // ============================================================
        // LEVEL 3
        // ============================================================

        // L3 - Program 1: Leap Year checker
        else if (programChoice == 8) {
            // Get year input from user
            System.out.print("Enter a year (>= 1582): ");
            int year = input.nextInt();

            // Gregorian calendar only works from 1582 onwards
            if (year < 1582) {
                System.out.println("Year must be >= 1582 for the Gregorian calendar");
            } else if (year % 400 == 0) {
                // Divisible by 400 is always a leap year (e.g. 2000)
                System.out.println(year + " is a Leap Year");
            } else if (year % 100 == 0) {
                // Divisible by 100 but not 400 is NOT a leap year (e.g. 1800)
                System.out.println(year + " is not a Leap Year");
            } else if (year % 4 == 0) {
                // Divisible by 4 but not 100 is a leap year (e.g. 2024)
                System.out.println(year + " is a Leap Year");
            } else {
                System.out.println(year + " is not a Leap Year");
            }
        }

        // L3 - Program 4: Prime number checker
        else if (programChoice == 9) {
            // Get number input from user
            System.out.print("Enter a number greater than 1: ");
            int number = input.nextInt();

            // Prime number checks are only for numbers greater than 1
            if (number <= 1) {
                System.out.println("Prime numbers must be greater than 1");
            } else {
                // Assume prime is true until we find a divisor
                boolean isPrime = true;

                // Check every number from 2 up to number - 1
                for (int i = 2; i < number; i++) {
                    if (number % i == 0) {
                        // Found a divisor - not prime, break out of loop
                        isPrime = false;
                        break;
                    }
                }

                // Display result based on isPrime boolean
                if (isPrime) {
                    System.out.println(number + " is a Prime Number");
                } else {
                    System.out.println(number + " is not a Prime Number");
                }
            }
        }

        else {
            System.out.println("Invalid choice. Please enter a number between 1 and 9.");
        }

        // Close scanner stream
        input.close();
    }
}