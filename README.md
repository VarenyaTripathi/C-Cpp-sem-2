# Hello-world
codes for Da1

/** Write a program which calculates expression n^n where n is an integer value filled
by the user **/
#include <stdio.h>
#include <stdlib.h>
#include <math.h> 
double power(int base, int exponent) { 
    int result = 1;
    for (int i = 1; i<=exponent;i++)
        result *= base;
    return result;
}
int main() {
    printf("enter a number: ");
    int n = 0;
    scanf("%d", &n);

    printf("%d^2=%lf\n",n, power(n,2));
    printf("%d^%d=%lf\n", n, n, power(n,n));
    printf("%d^%d=%lf", n, n, pow(n,n));
    return 0;
}

/**
2^3:
int result = 1;
result = result * 2; // 2
result = result * 2; // 4
result = result * 2; // 8

n^n:
int result = 1;
use a loop that runs n times
result *= n;
**/
/** Write a program which reads a sequence of real values filled by the user and stops by
displaying "done" when the sum of these values exceeds 100 **/

#include <stdio.h>
#include <stdlib.h>

int main() {
    printf("enter numbers:\n");
    int n = 0;
    int sum = 0;

    for (; sum <= 100 ;) {
        scanf("%d", &n);
        sum += n;
        printf("sum=%d\n", sum);
    }

    printf("done");
    return 0;
}
/** Write a program which reads a sequence of positive integer values and shows their
product and their sum when the user fills a negative number **/

#include <stdio.h>
#include <stdlib.h>

int main()
{
    int sum = 0;
    int product = 1;
    int n = 0;

    printf("enter numbers, enter a negative number to stop:\n");
    while (1) {
        scanf("%d", &n);
        if (n < 0)
            break;
        sum += n;
        product *= n;
    }

    printf("sum= %d, product = %d", sum, (sum==0) ? 0 : product);
    return 0;
}
/** Write a program which reads a positive integer value and shows its divisors
Notes:
let n be our number
- let d be a divisor of n --> n/d gives a remainder = 0
- n is a divisor of n
- The strict divisors of n are <= n/2 (excluding n)
**/
#include <stdio.h>
#include <stdlib.h>

int main() {
    printf("enter your number: ");
    int n = 0;
    scanf("%d", &n);
    if ( n == 1)
        printf("1");
    else {
            printf("the divisors of %d are: ", n);
            printf("1 ");
            for (int i = 2; i <= n/2; i++)
                if (n%i == 0)
                    printf("%d ", i);
            printf("%d", n);
    }

    return 0;
}
/** Write a program which reads a positive integer value N and indicates if N is a perfect
 number or not. (N = the sum of its strict divisors) **/

#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("enter your number: ");
    int n = 0;
    scanf("%d", &n);

    int sum = 1; /// 1 is a divisor
    for (int i = 2; i <= n/2; i++)
                if (n%i == 0)
                    sum += i;
    printf((sum == n) ? "perfect number" : "not perfect number");


    return 0;
}
/** Write a program which reads a positive integer value N,then calculates and shows the
 result of the expression: 1 + 4 + 7 + 10 +... ( <=N )

 ex:
 N=7: 1+4+7
 N=12: 1+4+7+10
**/

#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("enter a number: ");
    int n = 0;
    scanf("%d", &n);

    int sum = 0;
    for (int i = 1; i <= n; i += 3)
        sum += i;
    printf("%d",sum);

    return 0;
}
/**
 Write a program which reads a positive integer value N, calculates and shows the
 sum of the even numbers <= N

 (also, modify to get the sum of odd numbers)
**/

#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("enter a number: ");
    int n = 0;
    scanf("%d", &n);

    int sumEven = 0;
    int sumOdd = 0;
    for (int i = 1; i <= n; i++)
        if (i%2 == 0)
            sumEven += i;
        else
            sumOdd += i;

    printf("%d\n",sumEven);
    printf("%d",sumOdd);
    return 0;
}
/**
 Write a program which reads a positive integer value n, calculates and shows the
 result of the expression
**/

#include <stdio.h>
#include <stdlib.h>
#include <math.h>
int main()
{
    printf("enter your number: ");
    int n = 0;
    scanf("%d", &n);

    double sum = 0;
    for (int i = 1; i<=n; i++)
        sum += (i+3) / (pow(i,2) -5);
    printf("%lf", sum);


    return 0;
}
/**
 Write a program which reads a positive integer number n, calculates and shows the
 following:

 if n is divisible by 7: 1/1 + 1/2 + 1/3 + 1/4 +... + 1/n
 else: n/1 + n/2 + n/3 + n/4 +... + n/(n-1) + 1

**/

#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("enter your number: ");
    int n = 0;
    scanf("%d", &n);

    double sum = 0;
    if (n%7 == 0)
        for (double i = 1; i<=n; i++)
            sum += 1/i;
    else
        for (int i = 1; i<=n; i++)
            sum += (double) n/i;

    printf("%lf", sum);

    return 0;
}
/**
 Write a program which indicates if a positive number N, filled by the user, is prime
 or not
(N is a prime number if its divisors are 1 and N only)
**/

#include <stdio.h>
#include <stdlib.h>
#include <stdbool.h>

bool isPrime(int n) {
    for(int i = 2; i <= n/2; i++)
        if(n%i == 0)
            return false;
    return true;
}
int main() {
    printf("enter your number: ");
    int n = 0;
    scanf("%d", &n);

    printf("n is %s", ((isPrime(n))? "prime" : "not prime"));

    return 0;
}
/**
 Write a program which reads 10 real numbers. The program must then show the
 maximum and the minimum of these numbers

**/

#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("enter your numbers: ");
    int n = 0;
    scanf("%d", &n);

    int min=n, max=n;
    for(int i = 1; i<=9; i++) {
        scanf("%d", &n);

        min = (n < min) ? n : min;
        max = (n > max) ? n : max;
    }

    printf("min=%d , max=%d", min, max);

    return 0;
}
/**
 Write a program which reads a sequence of positive real numbers. The program
 stops when the user fills a negative value and show the maximum and the minimum
 of these numbers.
**/

#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("enter number: ");
    int n = 0;
    scanf("%d", &n);

    if (n < 0) return 0;

    int min = n, max = n;
    while(1) {
        scanf("%d", &n);
        if(n < 0) break;

        min = (n < min) ? n : min;
        max = (n > max) ? n : max;

    }

    printf("min=%d , max=%d", min, max);

    return 0;
}
/**
 Write a program which reads two positive integer values and shows their GCD
 (Greatest Common Divisor) and their LCM (Least Common Multiple).
example:
-GCD
5: 1,2
15: 1,2,3,4,5,6,7

-LCM
3: 3*1,3*2,3*3,3*4,3*5
5: 5*1,5*2,5*3

5: 5,10,15,...
15: 15,30,...

note:
15 is a multiple of 3 -> 3 divides 15 (15 % 3 == 0)
**/


#include <stdio.h>
#include <stdlib.h>
int main()
{
    printf("enter the two numbers: ");
    int i1 = 0, i2 = 0;
    scanf("%d %d", &i1, &i2);


    int GCD = 0;
    int max = (i1 > i2) ? i1 : i2;
    for(int i = 1; i <= max/2; i++)
        if( i1%i==0 && i2%i==0)
            GCD = i;
    int LCM = max;
    for( ; LCM <= i1*i2 ; LCM++ )
        if(LCM%i1 == 0 && LCM%i2 == 0)
            break;

    printf("GCD=%d , LCM=%d", GCD, LCM);

    return 0;
}
/**
Fibonacci sequence:  1, 1, 2, 3, 5, 8, 13, 21,...
**/

#include <stdio.h>
#include <stdlib.h>

int fib(int n) {
    if(n==1 || n==2) return 1;

    int i1=1, i2=1;

    int fibNumber = 0;
    for(int i = 1; i <= n-2; i++) {
        fibNumber = i1 + i2;
        i1 = i2;
        i2 = fibNumber;
    }

    return fibNumber;
}


int main() {
    printf("enter n: ");
    int n = 0;
    scanf("%d", &n);

    printf("the fib number is %d", fib(n));

    return 0;
}
/**
Write a program to find out if a 4-digit number is a lucky number.
A is a lucky number if A+B = C+D
**/

#include <stdio.h>
#include <stdlib.h>

int main() {
    printf("enter a 4-digit number: ");
    int n = 0;
    scanf("%d", &n);

    int isLucky = n%10 + (n/10)%10 == (n/100)%10 + (n/1000)%10;
    printf((isLucky) ? "lucky number" : "not lucky number");
    return 0;
}
/**
fill an array of integers and calculate the sum and the product of its elements
**/

#include <stdio.h>
#include <stdlib.h>

void fillArray(int arr[], int n) {
    for(int i = 0; i<n; i++)
        scanf("%d", &arr[i]);
}
int main() {
    int arr[5] = {};

//    fillArray(arr, 5);

    int sum = 0;
    int product = 1;
    for(int i = 0; i<5; i++) {
        sum += arr[i];
        product *= arr[i];
    }

    printf("%d %d", sum, product);
    return 0;
}
/**
check how many times an element N occurs in an array
**/

#include <stdio.h>
#include <stdlib.h>

int occurs(int arr[], int n, int searchElement) {
    int count = 0;
    for(int i = 0; i<n; i++)
        if(arr[i] == searchElement)
            count++;
    return count;
}

int main() {
    int arr[] = {1,5,6,3,8,9,4,1,0,4};
    printf("1 occurs %d times\n", occurs(arr, 10, 1));
    printf("3 occurs %d times\n", occurs(arr, 10, 3));
    printf("4 occurs %d times\n", occurs(arr, 10, 4));


    return 0;
}
/**
get the max and min in an array and how much they occur
**/
#include <stdio.h>
#include <stdlib.h>


int occurs(int arr[], int n, int searchElement) {
    int count = 0;
    for(int i = 0; i<n; i++)
        if(arr[i] == searchElement)
            count++;
    return count;
}

int getMin(int arr[], int n) {
    int min = arr[0];
    for(int i = 1; i<n; i++)
        min = (arr[i] < min) ? arr[i] : min;

    return min;
}

int getMax(int arr[], int n) {
    int max = arr[0];
    for(int i = 1; i<n; i++)
        max = (arr[i] > max) ? arr[i] : max;

    return max;
}
int main() {
    int arr[] = {-9,0,1,2,-2,3,4,-9,-9,4};

    int max = getMax(arr,10);
    int min = getMin(arr,10);
    printf("the max is %d it occurs %d\n", max, occurs(arr,10,max));
    printf("the min is %d it occurs %d", min, occurs(arr,10,min));

    return 0;
}
/**
show the multiples of 7 in the array
**/

#include <stdio.h>
#include <stdlib.h>

int main() {
    int arr[] = {1,2,7,8,14,15,20,21};

    for(int i = 0; i < 8; i++)
        if(arr[i] % 7 == 0)
            printf("%d ", arr[i]);

    return 0;
}
/**
fill an array with elements <= 150
if the user enters a number > 150 this number should not be inserted in the array
**/
#include <stdio.h>
#include <stdlib.h>

void fillArray(int arr[], int n) {
    for(int i = 0; i<n; i++)
        do {
            scanf("%d", &arr[i]);
        } while(arr[i] > 150);
}

void printArray(int arr[], int n) {
    for(int i = 0; i < n; i++)
        printf("%d ", arr[i]);
}

int main() {
    int arr[5] = {};
    fillArray(arr, 5);
    printArray(arr, 5);
    return 0;
}
#include <stdio.h>
#include <stdlib.h>

void printArrayRow(double arr[][12], int rows, int columns) {
    for(int i = 0; i < rows; i++) {
        for(int j = 0; j < columns; j++)
            printf("%.2lf ", arr[i][j]);
        printf("\n");
    }
}

void printArrayColumn(double arr[][12], int rows, int columns) {
    for(int i = 0; i < columns; i++) {
        for(int j = 0; j < rows; j++)
            printf("%.2lf ", arr[j][i]);
        printf("\n");
    }
}
int main() {
    double rainFall[5][12] = { /// 5 years, 12 months
                                {4.3, 4.3, 4.3, 3.0, 2.0, 1.2, 0.2, 0.2, 0.4, 2.4, 3.5, 6.6},
                                {8.5, 8.2, 1.2, 1.6, 2.4, 0.0, 5.2, 0.9, 0.3, 0.9, 1.4, 7.3},
                                {9.1, 8.5, 6.7, 4.3, 2.1, 0.8, 0.2, 0.2, 1.1, 2.3, 6.1, 8.4},
                                {7.2, 9.9, 8.4, 3.3, 1.2, 0.8, 0.4, 0.0, 0.6, 1.7, 4.3, 6.2},
                                {7.6, 5.6, 3.8, 2.8, 3.8, 0.2, 0.0, 0.0, 0.0, 1.3, 2.6, 5.2}
                            };
    printArrayColumn(rainFall, 5, 12);
}
#include <stdio.h>
#include <stdlib.h>

int main() {
    double rainFall[5][12] = { /// 5 years, 12 months
                                {4.3, 4.3, 4.3, 3.0, 2.0, 1.2, 0.2, 0.2, 0.4, 2.4, 3.5, 6.6},
                                {8.5, 8.2, 1.2, 1.6, 2.4, 0.0, 5.2, 0.9, 0.3, 0.9, 1.4, 7.3},
                                {9.1, 8.5, 6.7, 4.3, 2.1, 0.8, 0.2, 0.2, 1.1, 2.3, 6.1, 8.4},
                                {7.2, 9.9, 8.4, 3.3, 1.2, 0.8, 0.4, 0.0, 0.6, 1.7, 4.3, 6.2},
                                {7.6, 5.6, 3.8, 2.8, 3.8, 0.2, 0.0, 0.0, 0.0, 1.3, 2.6, 5.2}
                            };

    /** calculate the rain fall of each year **/
//    double rainFallYear[5] = {};
//    for(int i = 0; i < 5; i++)
//        for(int j = 0; j < 12; j++)
//            rainFallYear[i] += rainFall[i][j];
//
//    for(int i = 0; i < 5; i++)
//        printf("%.2lf ", rainFallYear[i]);

    /** calculate the monthly average of each month**/
    double monthlyAverage[12] = {};
    for(int i = 0; i < 12; i++) {
        for(int j = 0; j < 5; j++)
            monthlyAverage[i] += rainFall[j][i];
        monthlyAverage[i] /= 5;
    }

    for(int i = 0; i < 12; i++)
        printf("%.2lf ", monthlyAverage[i]);
    return 0;
}
#include <stdio.h>
#include <stdlib.h>

int main() {

    printf("Hello, welcome to Our Carpet Cleaning Service\n");

    int smallRooms = 0;
    printf("\nHow many small rooms would you like cleaned? ");
    scanf("%d", &smallRooms);

    int largeRooms = 0;
    printf("\nHow many large rooms would you like cleaned? ");
    scanf("%d", &largeRooms);

    const double  pricePerSmallRoom = 25.0;
    const double  pricePerLargeRoom = 35.0;

    const double salesTax = 0.06;
    const int estimateExpiry = 30; /// days

    printf("\nEstimate for carpet cleaning service\n");
    printf("Number of small rooms: %d\n", smallRooms);
    printf("Number of large rooms: %d\n\n", largeRooms);

    printf("Price per small room: $%.2lf\n", pricePerSmallRoom);
    printf("Price per large room: $%.2lf\n", pricePerLargeRoom);

    double cost = (pricePerSmallRoom * smallRooms) + (pricePerLargeRoom * largeRooms);
    printf("Cost : $%.2lf\n", cost);

    double tax =  cost * salesTax;
    printf("Tax: $%.2lf\n", tax);

    printf("===============================\n");
    printf("Total estimate: $%.2lf\n", cost + tax);
    printf("This estimate is valid for %d days\n", estimateExpiry);


    return 0;
}
#include <stdio.h>
#include <stdlib.h>

int main() {
    /// define conversion values in cents
    const int dollarValue = 100;
    const int quarterValue = 25;
    const int dimeValue = 10;
    const int nickelValue = 5;

    int changeAmount = 0;

    /// Solution 1

    printf("Enter an amount in cents : ");
    scanf("%d", &changeAmount);

    int balance = 0, dollars = 0, quarters = 0, dimes = 0, nickels = 0, pennies = 0;

    dollars = changeAmount / dollarValue;
    balance = changeAmount - (dollars * dollarValue);

    quarters =  balance / quarterValue;
    balance -= quarters * quarterValue;

    dimes = balance / dimeValue;
    balance -= dimes * dimeValue;

    nickels = balance / nickelValue;
    balance -= nickels * nickelValue;

    pennies = balance;

    printf("\nYou can provide this change as follows :\n");
    printf("dollars  : %d\n", dollars);
    printf("quarters : %d\n", quarters);
    printf("dimes    : %d\n", dimes);
    printf("nickels  : %d\n", nickels);
    printf("pennies  : %d\n", pennies);



/// Solution 2 - using the modulo operator


    printf("\nSolution using the modulo operator\n");
    printf("----------------------------\n");

    balance = dollars = quarters = dimes = nickels = pennies = 0;  /// reset everthing to zero

    dollars = changeAmount / dollarValue;
    balance = changeAmount % dollarValue;

    quarters = balance / quarterValue;
    balance %= quarterValue;

    dimes = balance / dimeValue;
    balance %= dimeValue;

    nickels = balance / nickelValue;
    balance %= nickelValue;

    pennies = balance;

    printf("\nYou can provide this change as follows :\n");
    printf("dollars  : %d\n", dollars);
    printf("quarters : %d\n", quarters);
    printf("dimes    : %d\n", dimes);
    printf("nickels  : %d\n", nickels);
    printf("pennies  : %d\n", pennies);

    return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include "xo.h"


int main() {
    int game[3][3] = { {-1, -1, -1}, /// 1 X, 0 O, -1 " "
                       {-1, -1, -1},
                       {-1, -1, -1} };
    play(game);
    return 0;
}



#include <stdio.h>
#include <stdlib.h>
#include "menuProgram.h"

int main() {
    int arr[50] = {};
    int userChoice = 0;
    do {

        printf("1-Add number\n");
        printf("2-Remove number\n");
        printf("3-Print\n");
        printf("4-Print sorted\n");
        printf("5-Find a number\n");
        printf("6-Exit\n\n\n");

        printf("Enter your choice: ");
        scanf("%d", &userChoice);

        if( userChoice == 1 )
            addNumber(arr);
        else if (userChoice == 2)
            removeNumber(arr);
        else if (userChoice == 3)
            printArray(arr);
        else if (userChoice == 4)
            printSorted(arr);
        else if (userChoice == 5) {
            printf("Enter the number you want to find: ");
            int searchElement = 0;
            scanf("%d", &searchElement);

            printf(findNumber(arr, searchElement) >= 0 ? "found\n" : "not found\n");
        }

    } while (userChoice != 6);

    printf("Good Bye.");
    return 0;
}
/**
Read the user's name and say Hi to him
**/

#include <stdio.h>
#include <stdlib.h>

int main() {
    printf("Enter your full name: ");

    char name[20] = {};
//    scanf("%s", name); /// first last
    gets(name);
//    printf("Hi %s", name);
    puts(name);
    return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void copyString(char source[], char destination[]) {
    for(int i = 0; i < strlen(source); i++)
        destination[i] = source[i];
    destination[strlen(source)] = '\0';
}
int main() {
    char name[] = "Ali Badran";
    char copy[strlen(name) + 1];
    copyString(name, copy);
    printf("%d", strlen(copy));
//    puts(copy);

    return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void reverseString(char str[]) {
    char reverse[strlen(str) + 1];
    for(int i = strlen(str) - 1, j = 0 ; i >= 0; i--, j++)
        reverse[j] = str[i]; // 10
    reverse[strlen(str)] = '\0';

    for(int i = 0; i < strlen(reverse); i++)
        str[i] = reverse[i];
}
int main() {
    char str[] = "This is a test";
    reverseString(str);
//    puts(str);
    printf("%d", str[strlen(str)] == '\0');
    return 0;
}
#include <stdio.h>
#include <stdlib.h>

int strlen(char str[]) {
    int count = 0;
    for(int i = 0; str[i] != '\0'; i++)
        count++;
    return count;
}

int main() {

    printf("%d",strlen("")); // 0
    printf("%d",strlen("Ali")); // 3
    printf("%d",strlen("Badran"));
    printf("%d",strlen("Ali Badran"));

    return 0;
}
#include <stdio.h>
#include <stdlib.h>

int strlen(char str[]) {
    printf("hello in strlen\n");
    int count = 0;
    for(int i = 0; str[i] != '\0'; i++)
        count++;
    return count;
}

void strcpy(char destination[], char source[]) {
    printf("hello\n");
    for(int i = 0; i < strlen(source); i++)
        destination[i] = source[i];
    destination[strlen(source)] = '\0';
}
int main() {
    char str[] = "12345678910";
    char copy[10] = {};
    strcpy(copy, str); /// 12345678\0''''''
    puts(copy);
    return 0;
}
#include <stdio.h>
#include <stdlib.h>
//#include <string.h>

int strlen(char str[]) {

    int count = 0;
    for(int i = 0; str[i] != '\0'; i++)
        count++;
    return count;
}

int strcmp(char str1[], char str2[]) {
    for(int i = 0; i < strlen(str2); i++)
        if(str1[i] == str2[i])
            continue;
        else
            return (str1[i] > str2[i]) ? 1 : -1;
    return 0;
}

int main() {
    printf("%d\n", strcmp("abc", "abc"));
    printf("%d\n", strcmp("abc", "abcd"));
    printf("%d\n", strcmp("abcd", "abc"));
    return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void squeezSpaces(char str[]) {
    int strLength = strlen(str);
    char sqeezed[strLength + 1];
    int j = 0;

    for(int i = 0; i < strLength; i++)
        if (str[i] == ' ' && str[i + 1] == ' ')
            continue;
        else
            sqeezed[j++] = str[i];

    sqeezed[j] = '\0';
    strcpy(str, sqeezed);
}

int main() {
    char str[] = "star comedy by democrats!";
    squeezSpaces(str);
    puts(str);
    printf("%d", str[25] == '\0');
    return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void reverseString(char str[]) {
    char reverse[strlen(str) + 1];
    for(int i = strlen(str) - 1, j = 0 ; i >= 0; i--, j++)
        reverse[j] = str[i]; // 10
    reverse[strlen(str)] = '\0';

    for(int i = 0; i < strlen(reverse); i++)
        str[i] = reverse[i];
}

void squeezSpaces(char str[]) {
    int strLength = strlen(str);
    char sqeezed[strLength];
    int j = 0;

    for(int i = 0; i < strLength; i++)
        if (str[i] == ' ' && str[i + 1] == ' ')
            continue;
        else
            sqeezed[j++] = str[i];

    sqeezed[j] = '\0';
    strcpy(str, sqeezed);
}

int main() {
    char str[] = "This  is   a   test!";
    squeezSpaces(str);
    reverseString(str);
    puts(str);
    return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int startsWith(char str1[], char str2[]) {
    for(int i = 0; i < strlen(str2); i++)
        if (str1[i] == str2[i])
            continue;
        else return 0;

    return 1;
}
int main() {
    char str1[] = "Hello World!";
    char str2[] = "Helloo";

    printf((startsWith(str1, str2)) ? "yes" : "no");
    return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int startsWith(char str1[], char str2[]) {
    for(int i = 0; i < strlen(str2); i++)
        if (str1[i] == str2[i])
            continue;
        else return 0;

    return 1;
}

int stringOcc(char str1[], char str2[]) {
    int count = 0;
    for(int i = 0; i < strlen(str1); i++)
        count = (startsWith(&str1[i], str2)) ? count + 1 : count;

    return count;
}
int main() {
    char str1[] = "Hello World Hello Hello!";
    char str2[] = "Hello";

    printf("%d", stringOcc(str1, str2));
    return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int stringOcc(char str1[], char str2[]) {
    int count = 0;
    int foundOcc = 1;

    for(int i = 0; i < strlen(str1); i++) {
        foundOcc = 1;
        for(int j = i, k = 0; k < strlen(str2); j++, k++)
            if (str1[j] == str2[k])
                continue;
            else {
                foundOcc = 0;
                break;
            }
        if (foundOcc) count++;
    }

    return count;
}

int main() {
    char str1[] = "hello hellohellohello bye";
    char str2[] = "hello";

    printf("%d", stringOcc(str1, str2));
    return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int startsWith(char str1[], char str2[]) {
    for(int i = 0; i < strlen(str2); i++)
        if (str1[i] == str2[i])
            continue;
        else return 0;

    return 1;
}

int stringOcc(char str1[], char str2[]) {
    int count = 0;

    int j = 0;
    for(int i = 0; i < strlen(str1); i++)
        if (startsWith(&str1[i], str2)) {
            count++;
            printf("Occ %d is at %d\n", ++j, i);
        }

    return count;
}
int main() {
    char str1[] = "Hello World Hello Hello!"; /// 0, 12, 18
    char str2[] = "Hello";

    printf("%d", stringOcc(str1, str2));
    return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int stringOcc(char str1[], char str2[]) {
    int count = 0;
    int foundOcc = 1;


    for(int i = 0; i < strlen(str1); i++) {
        foundOcc = 1;
        for(int j = i, k = 0; k < strlen(str2); j++, k++)
            if (str1[j] == str2[k])
                continue;
            else {
                foundOcc = 0;
                break;
            }

        if (foundOcc) {
            static int j = 1; /// 3
            count++;
            printf("Occ %d is at %d\n", j++, i);
        }
    }

    return count;
}

int main() {
    char str1[] = "hello hellohellohello bye";
    char str2[] = "hello";

    printf("%d", stringOcc(str1, str2));
    return 0;
}
#include <stdio.h>
#include <stdlib.h>

//int indexOf(char str[], char search[]) {
//    int found = 1;
//    int lengthStr = strlen(str);
//    int lengthSearch = strlen(search);
//
//    for(int i = 0; i < lengthStr; i++) {
//        found = 1;
//        for(int j = i, k = 0; k < lengthSearch; j++, k++)
//            if (str[j] == search[k])
//                continue;
//            else {
//                found = 0;
//                break;
//            }
//
//        if (found) return i;
//    }
//
//    return -1;
//}


int startsWith(char str1[], char str2[]) {
    for(int i = 0; i < strlen(str2); i++)
        if (str1[i] == str2[i])
            continue;
        else return 0;

    return 1;
}

int indexOf(char str[], char search[]) {
    int lengthStr = strlen(str);

    for(int i = 0; i < lengthStr; i++)
        if (startsWith(&str[i], search)) return i;

    return -1;
}
int main() {
    char str[] = "012yHello World! Hello";
    printf("%d", indexOf(str,"Hello"));
    return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int startsWith(char str1[], char str2[]) {
    for(int i = 0; i < strlen(str2); i++)
        if (str1[i] == str2[i])
            continue;
        else return 0;

    return 1;
}

int lastIndexOf(char str[], char search[]) {
    int lengthStr = strlen(str);

    for(int i = lengthStr - 1; i >= 0; i--)
        if (startsWith(&str[i], search)) return i;

    return -1;
}

int main() {
    char str[] = "012yuello World! gello";
    printf("%d", lastIndexOf(str,"Hello"));
    return 0;
}
#include <stdio.h>
#include <stdlib.h>
#include <string.h>


void removeSpaces(char str[]) {
    int strLength = strlen(str);
    char removed[strLength + 1];
    int j = 0;

    for(int i = 0; i < strLength; i++)
        if (str[i] == ' ')
            continue;
        else
            removed[j++] = str[i];

    removed[j] = '\0';
    strcpy(str, removed);
}

void reverseString(char str[]) {
    char reverse[strlen(str) + 1];
    for(int i = strlen(str) - 1, j = 0 ; i >= 0; i--, j++)
        reverse[j] = str[i];
    reverse[strlen(str)] = '\0';

    strcpy(str, reverse);
}

int isPalindrome(char str[]) {
    char reverse[strlen(str) + 1];

    strcpy(reverse, str);
    removeSpaces(reverse);
    removeSpaces(str);

    reverseString(reverse);

    return !strcmp(str, reverse);
}
int main() {
    char str[] = "abba";


    printf("%d",isPalindrome(str));
    return 0;
}








