EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim::
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:
#include <stdio.h>

#define SIZE 5

struct Person {
    char name[50];
    int age;
};

int main() {
    struct Person people[SIZE];
    int i;

    for(i = 0; i < SIZE; i++) {
        printf("Enter name of person %d: ", i + 1);
        scanf("%s", people[i].name);
        printf("Enter age of person %d: ", i + 1);
        scanf("%d", &people[i].age);
    }

    printf("\nVaccine Eligibility:\n");
    for(i = 0; i < SIZE; i++) {
        if(people[i].age > 6)
            printf("%s is Eligible for Vaccine.\n", people[i].name);
        else
            printf("%s is Not Eligible for Vaccine.\n", people[i].name);
    }

    return 0;
}



Output:



![Screenshot 2025-04-25 143227](https://github.com/user-attachments/assets/48a76a63-d5e7-4f10-99d4-93adcdc17537)


Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:

#include <stdio.h>

struct Person {
    char name[50];
    int age;
};

struct Person getOlder(struct Person p) {
    p.age += 1;
    return p;
}

void displayPerson(struct Person p) {
    printf("Name: %s\n", p.name);
    printf("Age: %d\n", p.age);
}

int main() {
    struct Person person1, person2;

    printf("Enter name: ");
    scanf("%s", person1.name);
    printf("Enter age: ");
    scanf("%d", &person1.age);

    person2 = getOlder(person1);

    displayPerson(person2);

    return 0;
}





Output:



![Screenshot 2025-04-25 134628](https://github.com/user-attachments/assets/08625420-198b-46b3-8af4-9c4b3accf030)




Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

#include <stdio.h>
#include <stdio.h>

int main() {
    char fileName[50];
    FILE *filePointer;
    scanf("%s", fileName);
    filePointer = fopen(fileName, "w");

    if (filePointer == NULL) {
        printf("Unable to create file.\n");
        return 1;
    }
    fclose(filePointer);

    printf("%s File Created Successfully\n%s File Opened\n%s File Closed", fileName,fileName,fileName);

    return 0;
}





Output:






![Screenshot 2025-04-25 143128](https://github.com/user-attachments/assets/3b03028b-8fc0-443e-a193-fa53944d072a)









Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:
#include <stdio.h>

int main() {
    char fileName[50];
    FILE *filePointer;
    int numStudents, rollNumber;
    scanf("%s", fileName);
    filePointer = fopen(fileName, "w");
    if (filePointer == NULL) {
        printf("Unable to create file.\n");
        return 1;
    }
    scanf("%d", &numStudents);
    for (int i = 0; i < numStudents; i++) {
        scanf("%d", &rollNumber);
        fprintf(filePointer, "%d\n", rollNumber);
    }
    fclose(filePointer);

    printf("%s Opened\nData added Successfully", fileName);

    return 0;
}




Output:





![Screenshot 2025-04-25 143034](https://github.com/user-attachments/assets/e698f6d9-d1b8-4edf-964a-3545fea5d552)





Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:
#include <stdio.h>

struct Student {
    int rollNo;
    char name[50];
    float marks;
};

int main() {
    struct Student s;

    printf("Enter student roll number: ");
    scanf("%d", &s.rollNo);

    printf("Enter student name: ");
    scanf("%s", s.name);

    printf("Enter student marks: ");
    scanf("%f", &s.marks);

    printf("\n--- Student Details ---\n");
    printf("Roll Number: %d\n", s.rollNo);
    printf("Name: %s\n", s.name);
    printf("Marks: %.2f\n", s.marks);

    return 0;
}




Output:


![Screenshot 2025-04-25 135237](https://github.com/user-attachments/assets/a70e2568-4596-4161-b503-f2ee34a6c42d)









Result:
Thus, the program is verified successfully
