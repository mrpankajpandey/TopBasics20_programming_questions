# TopBasics20_programming_questions

##Write a function that checks if a given number is a multiple of both 3 and 5.

```c
#include <stdio.h>

int isMultipleOf3And5(int num) {
    if (num % 3 == 0 && num % 5 == 0) {
        return 1;  // True
    } else {
        return 0;  // False
    }
}

int main() {
    int number;
    printf("Enter a number: ");
    scanf("%d", &number);

    if (isMultipleOf3And5(number)) {
        printf("%d is a multiple of both 3 and 5.\n", number);
    } else {
        printf("%d is not a multiple of both 3 and 5.\n", number);
    }

    return 0;
}

```


## 2. Write a function that checks if a given number is prime.

```c
#include <stdio.h>

int isPrime(int num) {
    if (num <= 1) {
        return 0;  // 0 and 1 are not prime
    }
    for (int i = 2; i * i <= num; i++) {
        if (num % i == 0) {
            return 0;  // If there's a divisor, it's not prime
        }
    }
    return 1;  // It's prime
}

int main() {
    int number;
    printf("Enter a number: ");
    scanf("%d", &number);

    if (isPrime(number)) {
        printf("%d is a prime number.\n", number);
    } else {
        printf("%d is not a prime number.\n", number);
    }

    return 0;
}


```

## 3. Write a function that finds the sum of all numbers from 1 to a given number.

```c
#include <stdio.h>

int sumOfNumbers(int num) {
    int sum = 0;
    for (int i = 1; i <= num; i++) {
        sum += i;
    }
    return sum;
}

int main() {
    int number;
    printf("Enter a number: ");
    scanf("%d", &number);

    int result = sumOfNumbers(number);
    printf("The sum of numbers from 1 to %d is %d.\n", number, result);

    return 0;
}


```
