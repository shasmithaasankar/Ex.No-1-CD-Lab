# Ex. No : 1

# IMPLEMENTATION OF SYMBOL TABLE

# Register Number : 212224040311

# Date : 22.08.2025

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
#include <stdlib.h>   
#include <ctype.h>    
#include <string.h>

#define MAX_EXPRESSION_SIZE 100

int main() {
    int i = 0, j = 0, x = 0, n, flag = 0;
    void *add[100];  
    char b[MAX_EXPRESSION_SIZE], d[100], c, srch;

    printf("Enter the Expression terminated by $: ");
    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }
    b[i] = '\0'; 
    n = i - 1;

    printf("Given Expression: %s\n", b);

    printf("\nSymbol Table\n");
    printf("Symbol\tAddress\t\tType\n");

    for (j = 0; j <= n; j++) {
        c = b[j];
        if (isalpha((unsigned char)c)) {  
            int alreadyExists = 0;
            for (int k = 0; k < x; k++) {
                if (d[k] == c) {
                    alreadyExists = 1;
                    break;
                }
            }

            if (!alreadyExists) {
                void *p = malloc(sizeof(char));  
                add[x] = p;
                d[x] = c;
                printf("%c\t%p\tidentifier\n", c, p);
                x++;
            }
        }
    }
    while ((getchar()) != '\n');

    printf("\nEnter the symbol to be searched: ");
    srch = getchar();

    for (i = 0; i < x; i++) {
        if (srch == d[i]) {
            printf("Symbol Found\n");
            printf("%c @ address %p\n", srch, add[i]);
            flag = 1;
            break;
        }
    }

    if (flag == 0)
        printf("Symbol Not Found\n");
    for (i = 0; i < x; i++) {
        free(add[i]);
    }

    return 0;
}
```















# OUTPUT:
<img width="678" height="378" alt="image" src="https://github.com/user-attachments/assets/f335da7d-54d2-4933-92c1-2f8a12b83d32" />


# RESULT:

The program to implement a symbol table is executed and the output is verified.
