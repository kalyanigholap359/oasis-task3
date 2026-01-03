# oasis-task3
import java.util.Scanner;

public class ATMInterface {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        int balance = 10000;   // initial balance
        int choice;

        System.out.println("===== ATM INTERFACE =====");

        do {
            System.out.println("\n1. Check Balance");
            System.out.println("2. Withdraw");
            System.out.println("3. Deposit");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");
            choice = sc.nextInt();

            switch (choice) {

                case 1:
                    System.out.println("Current Balance: " + balance);
                    break;

                case 2:
                    System.out.print("Enter amount to withdraw: ");
                    int withdraw = sc.nextInt();
                    if (withdraw <= balance) {
                        balance = balance - withdraw;
                        System.out.println("Withdraw Successful");
                    } else {
                        System.out.println("Insufficient Balance");
                    }
                    break;

                case 3:
                    System.out.print("Enter amount to deposit: ");
                    int deposit = sc.nextInt();
                    balance = balance + deposit;
                    System.out.println("Deposit Successful");
                    break;

                case 4:
                    System.out.println("Thank You for using ATM");
                    break;

                default:
                    System.out.println("Invalid Choice");
            }

        } while (choice != 4);

        sc.close();
    }
}
