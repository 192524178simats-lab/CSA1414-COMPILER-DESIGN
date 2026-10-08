#include <stdio.h>
#include <ctype.h>
#include <string.h>

int main() {
    char s[100], word[20];
    int i = 0, j;

    printf("Enter code: ");
    fgets(s, sizeof(s), stdin);

    while (s[i] != '\0') {
        if (isalpha(s[i])) {
            j = 0;
            while (isalnum(s[i]))
                word[j++] = s[i++];
            word[j] = '\0';

            if (!strcmp(word,"int") || !strcmp(word,"float") ||
                !strcmp(word,"if") || !strcmp(word,"else"))
                printf("%s -> Keyword\n", word);
            else
                printf("%s -> Identifier\n", word);
        }
        else if (isdigit(s[i])) {
            printf("%c -> Number\n", s[i++]);
        }
        else if (strchr("+-*/=<>", s[i])) {
            printf("%c -> Operator\n", s[i++]);
        }
        else
            i++;
    }

    return 0;
}
