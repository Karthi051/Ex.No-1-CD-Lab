# Ex. No : 1

# IMPLEMENTATION OF SYMBOL TABLE

# Register Number :212223230101

# Date :19/03/2025

# AIM:

To write a C program to implement a symbol table.

# ALGORITHM:

1. Start the program.
2. Get the input from the user with the terminating symbol ‘$’.
3. Allocate memory for the variable by dynamic memory allocation function.
4. If the next character of the symbol is an operator then only the memory is allocated.
5. While reading, the input symbol is inserted into symbol table along with its memory address.
6. The steps are repeated till ‘$’ is reached.
7. To reach a variable, enter the variable to be searched and symbol table has been checked for corresponding variable, the variable along with its address is displayed as result.
8. Stop the program.

# PROGRAM:
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>
#include <stdlib.h>

#define MAX_EXPRESSION_SIZE 100

int main() {
    int i = 0, j = 0, x = 0, n, flag = 0;
    char b[MAX_EXPRESSION_SIZE], d[15], c, srch;
    

    void *add[15];
    
    printf("Enter the Expression terminated by $: ");
    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }
    b[i] = '\0';
    n = i - 1;

    printf("Given Expression: %s\n", b);
    printf("\nSymbol Table\n");
    printf("Symbol\taddr\t\ttype\n");
    for (j = 0; j <= n; j++) {
        c = b[j];
        if (isalpha((unsigned char)c)) {
            if (j == n || !isalpha((unsigned char)b[j + 1])) {
                add[x] = &b[j]; 
                d[x] = c; 
                printf("%c\t%p\tidentifier\n", c, add[x]);
                x++;
            }
        }
        else if (c == '+' || c == '-' || c == '*' || c == '=') {
            add[x] = &b[j];
            d[x] = c; 
            printf("%c\t%p\toperator\n", c, add[x]);
            x++;
        }
    }
    printf("\nThe symbol to be searched: ");
    getchar();
    srch = getchar();

    for (i = 0; i < x; i++) {
        if (srch == d[i]) {
            printf("Symbol Found\n");
            printf("%c@address%p\n", srch, add[i]);
            flag = 1;
            break;
        }
    }

    if (flag == 0) {
        printf("Symbol Not Found\n");
    }

    return 0;
}
```

# OUTPUT:
![image](https://github.com/user-attachments/assets/cb55b1b1-53f4-4e2d-b0fb-e5a80d1098e5)
![image](https://github.com/user-attachments/assets/b6050949-4be6-479c-88dc-31e89e94fdd6)



# RESULT:

The program to implement a symbol table is executed and the output is verified.
