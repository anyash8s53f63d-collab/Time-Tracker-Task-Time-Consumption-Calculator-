/* # Time-Tracker-Task-Time-Consumption-Calculator-
Language: C    What is project: Measures and reports duration spent on a task using system time functions.    Key Concepts Used: time.h library, time_t, ctime(), difftime(), Loops, User Interaction. */

#include <stdio.h>
#include <time.h>

int main() {
    int choice;
    time_t start, end;
    double time_taken;

    while(1) {
        printf("\n----- TIME TRACKER MENU -----\n");
        printf("1. Start Task\n");
        printf("2. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("\nTask Started... Do your work.\n");
                printf("Press Enter to stop timer.\n");
                getchar(); // To catch previous \n
                getchar(); // To wait for enter

                start = time(NULL);

                printf("Tracking time... Press Enter when task finished.\n");
                getchar();

                end = time(NULL);

                time_taken = difftime(end, start);

                printf("\n----- TASK TIME REPORT -----\n");
                printf("Start Time : %s", ctime(&start));
                printf("End Time   : %s", ctime(&end));
                printf("Total Time Spent: %.2f seconds\n", time_taken);
                break;

            case 2:
                printf("Exiting the Program...\n");
                return 0;

            default:
                printf("Invalid Choice! Try again.\n");
        }
    }
}
