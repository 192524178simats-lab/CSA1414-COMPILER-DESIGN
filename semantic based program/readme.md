#include <stdio.h>
#include <string.h>

int main() {
    char type[10], var[10], value[10];

    printf("Enter data type: ");
    scanf("%s", type);

    printf("Enter variable: ");
    scanf("%s", var);

    printf("Enter value: ");
    scanf("%s", value);

    if (strcmp(type, "int") == 0) {
        if (strchr(value, '.') == NULL)
            printf("Semantic Analysis: Valid\n");
        else
            printf("Semantic Analysis: Type Error\n");
    }
    else if (strcmp(type, "float") == 0) {
        printf("Semantic Analysis: Valid\n");
    }
    else {
        printf("Invalid Data Type\n");
    }

    return 0;
}
