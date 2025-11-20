#include <stdio.h>   // For input/output functions like printf, scanf

#define MAX 100      // Maximum number of students allowed

struct Student {
    int roll;            // Roll number of the student
    char name[50];       // Name of the student
    float marks;         // Marks scored by the student
};

// Array to store student records
// count = current number of students added
struct Student students[MAX];
int count = 0;

void addStudent() {

    // If array is full, no more students can be added
    if (count >= MAX) {
        printf("Storage full! No more students can be added.\n");
        return;
    }

    // Taking student details from the user
    printf("Enter roll number: ");
    scanf("%d", &students[count].roll);

    printf("Enter name: ");
    scanf("%s", students[count].name);

    printf("Enter marks: ");
    scanf("%f", &students[count].marks);

    // Increase total count of students
    count++;

    printf("Student added successfully!\n");
}

void displayStudents() {

    // If no student is added yet
    if (count == 0) {
        printf("No students available.\n");
        return;
    }
    printf("\n--- Student List ---\n");

    // Printing details of each student
    for (int i = 0; i < count; i++) {
        printf("Roll: %d | Name: %s | Marks: %.2f\n",
               students[i].roll,
               students[i].name,
               students[i].marks);
    }
}

void searchStudent() {

    int r;
    printf("Enter roll number to search: ");
    scanf("%d", &r);

    // Linear search through the array
    for (int i = 0; i < count; i++) {

        // Match found
        if (students[i].roll == r) {
            printf("Student Found!\n");
            printf("Roll: %d | Name: %s | Marks: %.2f\n",
                   students[i].roll,
                   students[i].name,
                   students[i].marks);
            return; // Exit the function once student is found
        }
    }

    // If loop finishes without finding a match
    printf("Student not found.\n");
}
void deleteStudent() {

    int r;
    printf("Enter roll number to delete: ");
    scanf("%d", &r);
    
    // Searching for the student to delete
    for (int i = 0; i < count; i++) {

        if (students[i].roll == r) {
            // Shifting elements to left to fill the gap
            for (int j = i; j < count - 1; j++) {
                students[j] = students[j + 1];
            }
            // Reduce the student count
            count--;
            printf("Student deleted successfully!\n");
            return;
        }
    }
    printf("Student not found.\n");
}

void sortByRoll() {
    // Simple comparison-based sorting
    for (int i = 0; i < count - 1; i++) {
        for (int j = i + 1; j < count; j++) {

            // Swap if roll numbers are not in ascending order
            if (students[i].roll > students[j].roll) {

                struct Student temp = students[i];
                students[i] = students[j];
                students[j] = temp;
            }
        }
    }
    printf("Students sorted by roll number!\n");
}

int main() {
    int choice;
    // Loop runs until user chooses Exit
    while (1) {
        printf("\n--- Student Management System ---\n");
        printf("1. Add Student\n");
        printf("2. Display Students\n");
        printf("3. Search Student\n");
        printf("4. Delete Student\n");
        printf("5. Sort by Roll Number\n");
        printf("6. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        // Switch-case for menu options
        switch (choice) {
            case 1:
                addStudent();      
                break;
            case 2:
                displayStudents(); 
                break;
            case 3:
                searchStudent();   
                break;
            case 4:
                deleteStudent();   
                break;
            case 5:
                sortByRoll();      
                break;
            case 6:
                printf("Exiting program...\n");
                return 0;          // End program
            default:
                printf("Invalid choice! Try again.\n");
        }
    }
    return 0;
}
