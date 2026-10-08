#include <stdio.h>
#include <ctype.h>

int main() {
    char s[50];
    int i = 0, valid = 1;

    printf("Enter expression: ");
    scanf("%s", s);

    if (!isdigit(s[0]))
        valid = 0;

    for (i = 1; s[i] != '\0'; i++) {
        if (i % 2 == 1) {
            if (s[i] != '+' && s[i] != '-' &&
                s[i] != '*' && s[i] != '/')
                valid = 0;
        } else {
            if (!isdigit(s[i]))
                valid = 0;
        }
    }

    if (valid)
        printf("Valid Syntax\n");
    else
        printf("Invalid Syntax\n");

    return 0;
}
