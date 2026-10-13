# day--10-

#include <stdio.h>

int main() {
    int units;
    float bill;

    printf("Enter electricity units consumed: ");
    scanf("%d", &units);

    if (units < 0) {
        printf("Invalid units");
    } else if (units <= 100) {
        bill = units * 1.5;
        printf("Electricity Bill = Rs. %.2f", bill);
    } else if (units <= 200) {
        bill = (100 * 1.5) + (units - 100) * 2.5;
        printf("Electricity Bill = Rs. %.2f", bill);
    } else if (units <= 300) {
        bill = (100 * 1.5) + (100 * 2.5)
               + (units - 200) * 4.0;
        printf("Electricity Bill = Rs. %.2f", bill);
    } else {
        bill = (100 * 1.5) + (100 * 2.5)
               + (100 * 4.0) + (units - 300) * 6.0;
        printf("Electricity Bill = Rs. %.2f", bill);
    }

    return 0;
}

#include <stdio.h>

int main() {
    int limit, n, temp, digit, sum, power, i, j;

    printf("Enter the limit: ");
    scanf("%d", &limit);

    printf("Armstrong numbers are: ");

    for (i = 1; i <= limit; i++) {
        n = i;
        temp = n;
        sum = 0;

        while (temp > 0) {
            digit = temp % 10;
            power = 1;

            for (j = 1; j <= 3; j++) {
                power = power * digit;
            }

            sum = sum + power;
            temp = temp / 10;
        }

        if (sum == n) {
            printf("%d ", n);
        }
    }

    return 0;
}

#include <stdio.h>

int add(int a, int b) {
    return a + b;
}

int subtract(int a, int b) {
    return a - b;
}

int multiply(int a, int b) {
    return a * b;
}

float divide(int a, int b) {
    return (float)a / b;
}

int modulus(int a, int b) {
    return a % b;
}

int main() {
    int a, b, choice;

    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);

    printf("\n1. Addition");
    printf("\n2. Subtraction");
    printf("\n3. Multiplication");
    printf("\n4. Division");
    printf("\n5. Modulus");

    printf("\nEnter your choice: ");
    scanf("%d", &choice);

    switch (choice) {
        case 1:
            printf("Result = %d", add(a, b));
            break;

        case 2:
            printf("Result = %d", subtract(a, b));
            break;

        case 3:
            printf("Result = %d", multiply(a, b));
            break;

        case 4:
            if (b != 0)
                printf("Result = %.2f", divide(a, b));
            else
                printf("Division by zero is not allowed");
            break;

        case 5:
            if (b != 0)
                printf("Result = %d", modulus(a, b));
            else
                printf("Modulus by zero is not allowed");
            break;

        default:
            printf("Invalid choice");
    }

    return 0;
}
