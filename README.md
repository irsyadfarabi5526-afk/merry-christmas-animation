
#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#include <unistd.h>

#define RESET   "\033[0m"
#define RED     "\033[1;31m"
#define GREEN   "\033[1;32m"
#define YELLOW  "\033[1;33m"
#define BLUE    "\033[1;34m"
#define PURPLE  "\033[1;35m"
#define CYAN    "\033[1;36m"
#define WHITE   "\033[1;37m"

int main(void) {
    int i, j, frame = 0;
    struct timespec delay = {0, 180000000};

    srand((unsigned int)time(NULL));

    while (1) {
        printf("\033[2J\033[H");

        printf(CYAN);
        printf("\n");
        printf("       *       .       *       .\n");
        printf("   .       *       .       *\n\n");
        printf(RESET);

        printf(YELLOW);
        printf("                 *\n");
        printf(RESET);

        for (i = 0; i < 7; i++) {
            for (j = 0; j < 6 - i; j++)
                printf(" ");

            for (j = 0; j < 2 * i + 1; j++) {
                int light = rand() % 5;

                if (light == 0)
                    printf(RED "o" RESET);
                else if (light == 1)
                    printf(YELLOW "*" RESET);
                else if (light == 2)
                    printf(BLUE "+" RESET);
                else if (light == 3)
                    printf(PURPLE "o" RESET);
                else
                    printf(GREEN "^" RESET);
            }
            printf("\n");
        }

        printf("           ");
        printf(YELLOW "|||||" RESET);
        printf("\n");
        printf("           ");
        printf(YELLOW "|||||" RESET);
        printf("\n\n");

        printf(RED);
        printf("      *       *       *       *\n");
        printf(RESET);

        printf(GREEN);
        printf("     =========================\n");
        printf(RESET);

        printf(YELLOW);
        printf("          MERRY CHRISTMAS!\n");
        printf(RESET);

        printf(CYAN);
        printf("       May your days be full of joy\n");
        printf("          and your dreams shine!\n");
        printf(RESET);

        printf(PURPLE);
        printf("\n          Season's Greetings!\n");
        printf(RESET);

        printf(WHITE);
        printf("\n       Press CTRL+C to exit\n");
        printf(RESET);

        fflush(stdout);
        nanosleep(&delay, NULL);
        frame++;
    }

    return 0;
}
# merry-christmas-animation
a colorful Merry Christmas animation made in C
