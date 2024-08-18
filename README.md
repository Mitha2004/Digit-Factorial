# Digit-Factorial

#include <stdio.h>

int factorial(int n) {
    if (n == 0 || n == 1) return 1;
    return n * factorial(n - 1);
}

int digitFactorialSum(int n) {
    int sum = 0;
    while (n > 0) {
        sum += factorial(n % 10);
        n /= 10;
    }
    return sum;
}

int main() {
    int sum = 0;
    for (int i = 3; i < 100000; i++) { // Upper bound can be adjusted
        if (digitFactorialSum(i) == i) {
            sum += i;
        }
    }
    printf("%d\n", sum);
    return 0;
}
