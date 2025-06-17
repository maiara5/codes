#include <stdio.h>

int main() {
    int N;
    scanf("%d", &N);

    int a = 0, b = 1, c;

    for (int i = 0; i < N; i++) {
        if (i == 0) {
            printf("0");
        } else if (i == 1) {
            printf(" 1");
        } else {
            c = a + b;
            printf(" %d", c);
            a = b;
            b = c;
        }
    }

    printf("\n");
    return 0;
}
