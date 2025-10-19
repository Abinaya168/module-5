# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    float length, breadth, area;
    float *p, *q;

   
    scanf("%f", &length);

   
    scanf("%f", &breadth);

    p = &length;
    q = &breadth;

    area = (*p) * (*q);

    printf("Area of Rectangle = %.2f\n", area);
    return 0;
}

```
## OUTPUT
<img width="1217" height="644" alt="image" src="https://github.com/user-attachments/assets/73c1c45a-768e-4161-82d2-949fd7aefdde" />

	       	


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main() {
    char *str;

    str = (char *)malloc(8 * sizeof(char)); // 7 letters + 1 for '\0'

    if (str == NULL) {
        printf("Memory not allocated.\n");
        return 1;
    }

    strcpy(str, "WELCOME");
    printf("%s\n", str);

    free(str);
    return 0;
}

```

## OUTPUT
<img width="1171" height="636" alt="image" src="https://github.com/user-attachments/assets/45f3e10d-4c94-47eb-ab87-8f6fd42ca776" />



## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.



# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct student {
    char name[20];
    int rollno;
    float marks;
};

int main() {
    struct student s;

    printf("Enter name: ");
    scanf("%s", s.name);

    printf("Enter roll number: ");
    scanf("%d", &s.rollno);

    printf("Enter marks: ");
    scanf("%f", &s.marks);

    printf("\nStudent Details:\n");
    printf("Name: %s\nRoll Number: %d\nMarks: %.2f\n", s.name, s.rollno, s.marks);

    return 0;
}

```

## OUTPUT
<img width="1198" height="777" alt="image" src="https://github.com/user-attachments/assets/48c595f7-7fcc-416c-bd8d-386980f075eb" />


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

struct employee {
    char name[20];
    int id;
    float basic, da, hra, gross;
};

int main() {
    struct employee e[3];
    int i;

    for(i = 0; i < 3; i++) {
        printf("\nEnter details of Employee %d\n", i+1);
        printf("Name: ");
        scanf("%s", e[i].name);
        printf("ID: ");
        scanf("%d", &e[i].id);
        printf("Basic Salary: ");
        scanf("%f", &e[i].basic);

        e[i].da = 0.8 * e[i].basic;
        e[i].hra = 0.1 * e[i].basic;
        e[i].gross = e[i].basic + e[i].da + e[i].hra;
    }

    printf("\nEmployee Details:\n");
    for(i = 0; i < 3; i++) {
        printf("\nName: %s\nID: %d\nGross Salary: %.2f\n", e[i].name, e[i].id, e[i].gross);
    }

    return 0;
}

```

 ## OUTPUT

 <img width="1249" height="778" alt="image" src="https://github.com/user-attachments/assets/0a4088b1-fbaf-47a4-b269-28007d506359" />


## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>

struct student {
    char name[20];
    int rollno;
    int marks[5];
    int total;
    float average;
};

int main() {
    struct student s[2];
    int i, j;

    for(i = 0; i < 2; i++) {
        printf("\nEnter name of student %d: ", i+1);
        scanf("%s", s[i].name);
        printf("Enter roll number: ");
        scanf("%d", &s[i].rollno);
        s[i].total = 0;

        printf("Enter 5 subject marks: ");
        for(j = 0; j < 5; j++) {
            scanf("%d", &s[i].marks[j]);
            s[i].total += s[i].marks[j];
        }

        s[i].average = s[i].total / 5.0;
    }

    printf("\nStudent Details:\n");
    for(i = 0; i < 2; i++) {
        printf("Name: %s\nRoll No: %d\nTotal: %d\nAverage: %.2f\n\n",
               s[i].name, s[i].rollno, s[i].total, s[i].average);
    }

    return 0;
}

```

## OUTPUT

 <img width="1255" height="808" alt="image" src="https://github.com/user-attachments/assets/24c41cc4-d681-49b9-9146-8991d15b6594" />


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


