## TopBasics20_programming_questions

## 1. Write a function that checks if a given number is a multiple of both 3 and 5.

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


## 4. Write a function that finds the product of all numbers from 1 to a given number.

```c
#include <stdio.h>

long long productOfNumbers(int num) {
    long long product = 1;
    for (int i = 1; i <= num; i++) {
        product *= i;
    }
    return product;
}

int main() {
    int number;
    printf("Enter a number: ");
    scanf("%d", &number);

    long long result = productOfNumbers(number);
    printf("The product of numbers from 1 to %d is %lld.\n", number, result);

    return 0;
}

```

## 5. Write a function that checks if a given string is a palindrome.

```c
#include <stdio.h>
#include <string.h>

int isPalindrome(char *str) {
    int len = strlen(str);
    for (int i = 0; i < len / 2; i++) {
        if (str[i] != str[len - i - 1]) {
            return 0;  // Not a palindrome
        }
    }
    return 1;  // It's a palindrome
}

int main() {
    char str[100];
    printf("Enter a string: ");
    scanf("%s", str);

    if (isPalindrome(str)) {
        printf("%s is a palindrome.\n", str);
    } else {
        printf("%s is not a palindrome.\n", str);
    }

    return 0;
}


```

## 6. Write a function that finds the reverse of a given string.

```c
#include <stdio.h>
#include <string.h>

void reverseString(char str[]) {
    int length = strlen(str);
    for (int i = 0; i < length / 2; i++) {
        char temp = str[i];
        str[i] = str[length - i - 1];
        str[length - i - 1] = temp;
    }
}

int main() {
    char input[100];
    printf("Enter a string: ");
    scanf("%s", input);
    
    reverseString(input);
    
    printf("Reversed string: %s\n", input);
    
    return 0;
}


```

## 7. Write a function that finds the factorial of a given number.

```c
#include <stdio.h>

int factorial(int num) {
    if (num == 0) {
        return 1;  // 0! is defined as 1
    }
    int result = 1;
    for (int i = 1; i <= num; i++) {
        result *= i;
    }
    return result;
}

int main() {
    int number;
    printf("Enter a number: ");
    scanf("%d", &number);

    int result = factorial(number);
    printf("%d! = %d\n", number, result);

    return 0;
}

```

## 8. Write a function that checks if a given string contains a given substring.

```c
#include <stdio.h>
#include <string.h>

int containsSubstring(char *str, char *substr) {
    if (strstr(str, substr) != NULL) {
        return 1;  // Substring found
    }
    return 0;  // Substring not found
}

int main() {
    char str[100], substr[100];
    printf("Enter a string: ");
    scanf("%s", str);
    printf("Enter a substring to search for: ");
    scanf("%s", substr);

    if (containsSubstring(str, substr)) {
        printf("'%s' contains the substring '%s'.\n", str, substr);
    } else {
        printf("'%s' does not contain the substring '%s'.\n", str, substr);
    }

    return 0;
}

```

## 9. Write a function that removes all vowels from a given string.

```c
#include <stdio.h>
#include <string.h>

int isVowel(char c) {
    // Check if a character is a vowel (both uppercase and lowercase)
    return (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u' || c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U');
}

void removeVowels(char *str) {
    int i, j;
    for (i = 0, j = 0; str[i] != '\0'; i++) {
        if (!isVowel(str[i])) {
            str[j] = str[i];
            j++;
        }
    }
    str[j] = '\0';
}

int main() {
    char str[100];
    printf("Enter a string: ");
    scanf("%s", str);

    removeVowels(str);
    printf("String after removing vowels: %s\n", str);

    return 0;
}

```

## 10. Write a function that checks if a given string is a pangram (contains every letter of the alphabet).
```c
#include <stdio.h>
#include <string.h>
#include <stdbool.h>

bool isPangram(char *str) {
    // Create an array to mark the presence of each letter in the alphabet
    bool alphabet[26] = {false};

    int len = strlen(str);
    for (int i = 0; i < len; i++) {
        if ('a' <= str[i] && str[i] <= 'z') {
            alphabet[str[i] - 'a'] = true;
        } else if ('A' <= str[i] && str[i] <= 'Z') {
            alphabet[str[i] - 'A'] = true;
        }
    }

    // Check if all alphabet characters are marked
    for (int i = 0; i < 26; i++) {
        if (alphabet[i] == false) {
            return false;
        }
    }

    return true;
}

int main() {
    char str[100];
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    if (isPangram(str)) {
        printf("The string is a pangram.\n");
    } else {
        printf("The string is not a pangram.\n");
    }

    return 0;
}

```
