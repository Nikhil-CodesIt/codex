# codex

#include <stdio.h>
#include <stdlib.h>

int main() {
    int pin, enteredPin, choice;
    float balance = 10000.0, deposit, withdraw;

    pin = 1234; // Set your ATM PIN here

    printf("Welcome to Dev Bhoomi ATM \n");
    printf("Please enter your 4-digit PIN: ");
    scanf("%d", &enteredPin);

    if (enteredPin != pin) {
        printf("Incorrect PIN. Access Denied.\n");
        return 0;
    }

    do {
        printf("\n========= ATM MENU =========\n");
        printf("1. Check Balance\n");
        printf("2. Deposit Money\n");
        printf("3. Withdraw Money\n");
        printf("4. Exit\n");
        printf("============================\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf(" Your current balance is ₹%.2f\n", balance);
                break;
            case 2:
                printf("Enter amount to deposit: ₹");
                scanf("%f", &deposit);
                if (deposit > 0) {
                    balance += deposit;
                    printf(" ₹%.2f deposited successfully.\n", deposit);
                } else {
                    printf("Invalid deposit amount.\n");
                }
                break;
            case 3:
                printf("Enter amount to withdraw: ₹");
                scanf("%f", &withdraw);
                if (withdraw > 0 && withdraw <= balance) {
                    balance -= withdraw;
                    printf("₹%.2f withdrawn successfully.\n", withdraw);
                } else {
                    printf("Insufficient balance or invalid amount.\n");
                }
                break;
            case 4:
                printf(" Thank you for using Dev Bhoomi ATM. Goodbye!\n");
                break;
            default:
                printf("Invalid choice. Please try again.\n");
        }
    } while (choice != 4);

    return 0;
}



