EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

```
#include <stdio.h>
int main() {
    int n;
    printf("Enter a number: ");
    scanf("%d", &n);
    switch (n) {
        case 1:
            printf("one\n");
            break;
        case 2:
            printf("two\n");
            break;
        case 3:
            printf("three\n");
            break;
        case 4:
            printf("four\n");
            break;
        case 5:
            printf("five\n");
            break;
        case 6:
            printf("six\n");
            break;
        case 7:
            printf("seven\n");
            break;
        case 8:
            printf("eight\n");
            break;
        case 9:
            printf("nine\n");
            break;
        case 10:
            printf("ten\n");
            break;
        case 11:
            printf("eleven\n");
            break;
        case 12:
            printf("twelve\n");
            break;
        case 13:
            printf("thirteen\n");
            break;
        default:
            printf("Greater than 13\n");
            break;
    }

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/f8569840-dca6-4552-84d6-d2d6f5f0d934)


Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

```
#include<stdio.h>
#include<string.h>
#include<ctype.h>
int main()
{
    char string[100];
    int count[10] = {0};
    printf("Enter the string : ");
    fgets(string,100,stdin);
    string[strlen(string)-1] = '\0';
    for(int i=0;i<strlen(string);i++)
    {
        if(isdigit(string[i]))
        {
            count[string[i] - '0']++;
        }
    }
    for(int i=0;i<10;i++)
    {
        printf("%d ",count[i]);
    }
}
```

Output:

![image](https://github.com/user-attachments/assets/71f6a70a-dfee-465c-b615-5846f8268263)



Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
void swap(char* a, char* b) {
    char temp = *a;
    *a = *b;
    *b = temp;
}

void reverse(char* str, int start, int end) {
    while (start < end) {
        swap(&str[start], &str[end]);
        start++;
        end--;
    }
}

int next_permutation(char* str, int n) {
    int i = n - 2;

    while (i >= 0 && str[i] >= str[i + 1]) {
        i--;
    }

    if (i < 0) {
        return 0;
    }
    int j = n - 1;
    while (str[j] <= str[i]) {
        j--;
    }
    swap(&str[i], &str[j]);
    reverse(str, i + 1, n - 1);

    return 1;
}

int main() {
    char* s;
    int n;
    s = (char*)malloc(50 * sizeof(char)); 
    if (s == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }
    printf("Enter a string: ");
    scanf("%s", s);
    n = strlen(s);

    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (s[i] > s[j]) {
                swap(&s[i], &s[j]);
            }
        }
    }

    do {
        printf("%s\n", s);
    } while (next_permutation(s, n));

    free(s);
    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/425d0332-d44c-4ca9-bf27-862307331030)


Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

```
#include <stdio.h>
int main() {
    int n, len;
    printf("Enter the value of n: ");
    scanf("%d", &n);
    len = n * 2 - 1;
    for (int i = 0; i < len; i++) {
        for (int j = 0; j < len; j++) {
            int min = i < j ? i : j;
            if (min > len - i - 1) min = len - i - 1;
            if (min > len - j - 1) min = len - j - 1;
            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/fabf8f59-aab3-43bc-b567-0b1f99bde552)


Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

```
#include <stdio.h>
int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main() {
    int result;
    result = square();
    printf("The square of the number is: %d\n", result);

    return 0;
}
```

Output:

![image](https://github.com/user-attachments/assets/081e44e1-f9af-4c7e-9e8b-6671b6ac3cee)




Result:
Thus, the program is verified successfully
