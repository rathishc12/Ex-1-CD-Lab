# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# Register Number : 212223040086
# Date : 15/04/2025 
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol and memory address are inserted into the symbol table.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and the symbol table has been checked for the corresponding variable, the variable along with its address is displayed as a result.
8.	Stop the program. 
# PROGRAM
```
#include <stdio.h>
#include <ctype.h>
#include <string.h>
#include <stdlib.h>
#define MAX_EXPRESSION_SIZE 100

int main() {
    int i = 0, j = 0, x = 0, n, flag = 0;
    char b[MAX_EXPRESSION_SIZE], d[15], c, srch;

    printf("Enter the Expression terminated by $: ");
    while ((c = getchar()) != '$' && i < MAX_EXPRESSION_SIZE - 1) {
        b[i++] = c;
    }
    b[i] = '\0'; 
    n = i - 1;

    printf("\nGiven Expression: %s\n", b);

    printf("\nSymbol Table\n");
    printf("Symbol\tType\n");

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
                d[x] = c;
                printf("%c\tidentifier\n", c);
                x++;
            }
        }
    }
    while ((c = getchar()) != '\n' && c != EOF);

    printf("\nEnter the symbol to search: ");
    srch = getchar();

    for (i = 0; i < x; i++) {
        if (srch == d[i]) {
            printf("Symbol Found\n");
            flag = 1;
            printf("Address : %lld",&d[i]);
            break;
        }
    }
    if (flag == 0)
        printf("Symbol Not Found\n");

    return 0;
}
```
# OUTPUT

SYMBOL  FOUND:


![image](https://github.com/user-attachments/assets/4aa7b01b-e6bd-4eca-a5dc-93fe57c96650)


SYMBOL NOT FOUND :


![image](https://github.com/user-attachments/assets/3b73245d-8cd9-4b5e-9bef-3b8a82e54373)



# RESULT
### The program to implement a symbol table is executed and the output is verified.
