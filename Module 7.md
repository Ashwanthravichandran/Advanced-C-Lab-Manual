EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
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

```
#include <stdio.h>

struct eligible {
    int age;          
    char name[50];    
};

int main() {
    struct eligible e;

    printf("Enter your name: ");
    scanf("%s", e.name);
    printf("Enter your age: ");
    scanf("%d", &e.age);

    if (e.age <= 6) {
        printf("\nVaccine Eligibility: No");
    } else {
        printf("\nVaccine Eligibility: Yes\n");
    }

    printf("Details:\n");
    printf("Age: %d\n", e.age);
    printf("Name: %s\n", e.name);
    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/a2d8dbc0-112a-4711-a130-1318eda34a2b)


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

```
#include <stdio.h>

struct numbers {
    int a;
    int b;
};

int add(struct numbers n) {
    return n.a + n.b;
}

int main() {
    struct numbers n;

    printf("Enter the value of a: ");
    scanf("%d", &n.a);
    printf("Enter the value of b: ");
    scanf("%d", &n.b);

    int result = add(n);

    printf("The sum of %d and %d is: %d\n", n.a, n.b, result);
    return 0;
}
```


Output:


![Screenshot 2025-05-19 184120](https://github.com/user-attachments/assets/de584eeb-a4d7-41e7-a05f-3ca037bbafac)





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

```
#include <stdio.h> 
int main() {
    FILE *p;
    char name[100];

    printf("Enter the name of the file (with extension): ");
    scanf("%s", name);

    printf("Creating file '%s'...\n", name);

    p = fopen(name, "w");
    if (p == NULL) {
        printf("Error: Unable to create or open the file!\n");
        return 1; 
    }

    printf("File '%s' has been opened successfully!\n", name);

    fclose(p);

    printf("File '%s' has been closed.\n", name);
    return 0;
}
```


Output:

![Screenshot 2025-05-19 184347](https://github.com/user-attachments/assets/65d42507-7686-4162-836a-ab59426caec5)


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
```
#include <stdio.h> 

int main() {
    FILE *p;            
    char name[100];    
    char text[1000];    
    int num;            
    printf("Enter the name of the file (with extension): ");
    scanf("%s", name);
    printf("Enter the number of strings you want to insert: ");
    scanf("%d", &num);

    p = fopen(name, "w");
    if (p == NULL) {
        printf("Error: Unable to create or open the file!\n");
        return 1; 
    }

    printf("File '%s' has been opened successfully!\n", name);

    for (int i = 0; i < num; i++) {
        printf("Enter string %d: ", i + 1);
        getchar(); 
        fgets(text, sizeof(text), stdin); 
        fputs(text, p); 
    }

    fclose(p);

    printf("Data has been successfully added to the file '%s'.\n", name);

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/1042d0d8-7691-4154-880d-9bb2dd5019b6)



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

```

#include <stdio.h>
#include <stdlib.h>

struct Subject {
    char name[100]; 
    int marks;      
};

int main() {
    int n; 
    struct Subject *s; 

    printf("Enter the number of subjects: ");
    scanf("%d", &n);

    s = (struct Subject *)malloc(n * sizeof(struct Subject));
    if (s == NULL) {
        printf("Error: Memory allocation failed!\n");
        return 1; 
    }

    for (int i = 0; i < n; i++) {
        printf("Enter details for subject %d:\n", i + 1);
        printf("Name: ");
        scanf("%s", s[i].name); 
        printf("Marks: ");
        scanf("%d", &s[i].marks); 
    }

    printf("\n--- Subject Details ---\n");
    for (int i = 0; i < n; i++) {
        printf("Subject %d:\n", i + 1);
        printf("Name: %s\n", s[i].name);
        printf("Marks: %d\n", s[i].marks);
    }

    free(s);
    return 0;
}
```


Output:

![image](https://github.com/user-attachments/assets/82b8efed-37c1-4b42-9e01-16ed1c40300b)


Result:
Thus, the program is verified successfully
