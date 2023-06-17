# C/C++ codes done in lab and from courses I took

//Codes from C/C++ courses

// Program to calculate n^n 

#include <stdio.h> 

#include <stdlib.h> 

    double power (int base, int exponent) 

    { 

        int result=1; 

        for (int i=0;i<exponent;i++){ 

            result=result*base; 

        } 

        return result; 

    } 

int main() 

{ 

    int n; 

    scanf("%d",&n); 

    printf("%d^%d=%lf",n,n,power(n,n)); 

    return 0; 

} 

 

/** Write a program which reads a sequence of real values filled by the user and stops by 

displaying "done" when the sum of these values exceeds 100 **/ 

#include <stdio.h> 

int main() 

{ 

    int n=0,sum=0; 

    do{ 

        printf("Enter a number:"); 

        scanf("%d",&n); 

        sum=sum+n; 

        printf("Sum:%d\n",sum); 

    }while(sum<=100); 

    printf("done"); 

    return 0; 

} 

 

/** Write a program which reads a sequence of positive integer values and shows their 

product and their sum when the user fills a negative number **/ 

#include <stdio.h> 

#include <stdlib.h> 

int main() 

{ 

    int n=0,sum=0,prod=1; 

    printf("Enter a number, enter a negative number to stop:"); 

    while (1){ 

        scanf("%d",&n); 

        if (n<0){ 

            break; 

        } 

        sum=sum+n; 

        prod=prod*n; 

    } 

    printf("Sum=%d,Product=%d",sum,prod); 

    return 0; 

} 

 

//Write a program which reads a positive integer value and shows its divisors 
#include <stdio.h> 
int main() 
{ 
    int n=0; 
    printf("Enter your number:"); 
    scanf("%d",&n); 
    if (n==1){ 
        printf("1"); 
    } 
    else{ 
    printf("The divisors of %d are:",n); 
    printf("1 "); 
    for (int i=2;i<=n/2;i++){ 
        if (n%i==0){ 
            printf("%d",i); 
        } 
    } 
    printf("%d",n); 
    } 
    return 0; 
} 

 

// Write a program to read a positive integer and check whether it's a perfect number or not 
#include <stdio.h> 
int main() 
{ 
    int n=0; 
    printf("Enter your number:"); 
    scanf("%d",&n); 
    int sum=1;/// 1 is a divisor always 
    for (int i=2;i<=n/2;i++){ 
        if (n%i==0){ 
            sum=sum+i; 
        } 
    } 
    printf((sum=n)?"Perfect number":"Not a perfect number"); 
    return 0; 
} 

 

// Write a program to read a positive integer n and calculate the value of expression 1+4+7+10+...(<=n) 
#include <stdio.h> 
int main() 
{ 
    int n=0,sum=0; 
    printf("Enter a number:"); 
    scanf("%d",&n); 
    for (int i=1;i<=n;i=i+3){ 
        sum=sum+i; 
    } 
    printf("The result of expression is:%d",sum); 
    return 0; 
} 

 

//Write a program which reads a positive integer n and calculates the sum of even and odd numbers<=n 
#include <stdio.h> 
int main() 
{ 
    printf("Enter a number:"); 
    int n=0,sum_of_even=0,sum_of_odd=0; 
    scanf("%d",&n); 
    for (int i=2;i<=n;i=i+2){ 
        sum_of_even=sum_of_even+i; 
    } 
    printf("Sum of even numbers <=%d is:%d\n",n,sum_of_even); 
    for (int i=1;i<=n;i=i+2){ 
        sum_of_odd=sum_of_odd+i; 
    } 
    printf("Sum of odd numbers <=%d is:%d",n,sum_of_odd); 
    return 0; 
} 

 

/* Write a C program which reads a positive integer n and shows the result of expression: summation of (i+3)/(i^2-5), where i is from 1 to n */ 

#include <stdio.h> 

int main() 

{ 

    printf("Enter a number:"); 

    int n;  

    double sum=0; 

    scanf("%d",&n); 

    for (int i=1;i<=n;i++){ 

        sum=sum+((i+3)/(i*i-5.0)); 

    } 

    printf("Result is:%lf",sum); 

    return 0; 

} 

 

/* WAP to read a positive integer n and calculate the result of: 

n divisible by 7: 1/1+1/2+1/3+...+1/n 

else: n/1+n/2+n/3+...+n/(n-1)+1 */ 

#include <stdio.h> 

int main() 

{ 

    printf("Enter your number:"); 

    int n; 

    double sum=0; 

    scanf("%d",&n); 

    if (n%7==0){ 

        for (double i=1;i<=n;i++){ 

            sum=sum+(1/i); 

        } 

    } 

    else{ 

        for (int i=1;i<=n;i++){ 

            sum=sum+((double)n/i); 

        } 

    } 

    printf("Result is:%lf",sum); 

    return 0; 

} 

 

// WAP to check whether a positive integer is a prime or not 

#include <stdio.h> 

#include <stdbool.h> 

int main() 

{ 

    printf("Enter a number:"); 

    int n; 

    scanf("%d",&n); 

    bool isPrime=true; 

    for (int i=2;i<=n/2;i++){ 

        if (n%i==0){ 

            isPrime=false; 

            break; 

        } 

    } 

    printf("n is %s",(isPrime)?"prime":"not prime"); 

    return 0; 

} 

 

//WAP to read 10 real numbers, then show the maximum and the minimum one 

#include <stdio.h> 

int main() 

{ 

    printf("Enter your numbers:"); 

    int n=0; 

    scanf("%d",&n); 

    int min=n,max=n; 

    for (int i=1;i<=9;i++){ 

        scanf("%d",&n); 

        min=(n<min)?n:min; 

        max=(n>max)?n:max; 

    } 

    printf("min=%d,max=%d",min,max); 

    return 0; 

} 

 

/* WAP to read positive real numbers. The program stops when user fills a negative number and shows maximum and minimum of the given numbers.*/ 

#include <stdio.h> 

int main() 

{ 

    printf("Enter the number:"); 

    int n=0; 

    scanf("%d",&n); 

    if (n<0) return 0; 

    int min=n,max=n; 

    while(1){ 

        scanf("%d",&n); 

        if (n<0) break; 

        min=(n<min)?n:min; 

        max=(n>max)?n:max; 

    } 

    printf("min=%d,max=%d",min,max); 

    return 0; 

} 

 

//WAP to read two positive integers and show their GCD and LCM 

#include <stdio.h> 

int main() 

{ 

    printf("Enter the two numbers:"); 

    int i1=0,i2=0; 

    scanf("%d %d",&i1,&i2); 

    int GCD=0; 

    int max=(i1>i2)?i1:i2; 

    for (int i=1;i<=max/2;i++){ 

        if (i1%i==0 && i2%i==0){ 

            GCD=i; 

        } 

    } 

    int LCM=max; 

    for (;LCM<=i1*i2;LCM++){ 

        if (LCM%i1==0 && LCM%i2==0){ 

            break; 

        } 

    } 

    printf("GCD=%d,LCM=%d",GCD,LCM); 

    return 0; 

} 

 

// WAP to print the fibonacci series 

#include <stdio.h> 

int main() 

{ 

    printf("Enter n:"); 

    int n=0; 

    scanf("%d",&n); 

    if (n==1 || n==2){ 

        printf("The fibonacci number is 1"); 

        return 0; 

    } 

    int fibN=0; 

    int i1=1,i2=1; 

    for (int i=1;i<=n-2;i++){ 

        fibN=i1+i2; 

        i1=i2; 

        i2=fibN; 

    } 

    printf("The fibonacci number is:%d",fibN); 

    return 0; 

} 

 

/* WAP to find whether a four digit number is a lucky number. ABCD is a lucky number if A+B=C+D */ 

#include <stdio.h> 

int main() 

{ 

    printf("Enter a 4-digit number:"); 

    int n=0; 

    scanf("%d",&n); 

    printf("%d",n%10+(n/10)%10==(n/100)%10+(n/1000)%10); 

    return 0; 

} 

 

/* 0,1,1,2,3,5,8,13....... upto n terms. 

print using array and also print sum of array*/ 

#include <iostream> 

using namespace std; 

int main() 

{ 

    int n; 

    cin>>n; 

    int a[n]; 

    int i; 

    a[0]=0; 

    a[1]=1; 

    for(int i=2;i<=n;i++){ 

        a[i]=a[i-1]+a[i-2]; 

    } 

    for (i=0;i<=n;i++){ 

        cout<<a[i]<<" "; 

    } 

    int sum=0; 

    for(int i=0;i<=n;i++){ 

        sum=sum+a[i]; 

    } 

    cout<<"\n"<<sum; 

     

} 

 

// 0,1,1,2,3,5,8,13....... upto n. 

#include <iostream> 

using namespace std; 

int main() 

{ 

    int i=0; 

    int c=0; 

    int n; 

    cin>>n; 

    int a=0,b=1; 

    while(c<n){ 

        c=a+b; 

        swap(a,b); 

        swap(b,c); 

        cout<<c<<" "; 

    } 

    return 0; 

} 

 

// Write a function to check if a number is prime or not 

#include <iostream> 

using namespace std; 

bool isPrime(int n){ 

    for(int i=2;i<=n-1;i++){ 

        if (n%i==0){ 

            return false; 

        } 

    } 

    return true; 

} 

int main() 

{ 

    int n; 

    cin>>n; 

    if(isPrime(n)){ 

        cout<<"Prime"<<endl; 

    }else{ 

        cout<<"Not Prime"<<endl; 

    } 

    return 0; 

} 

 

// Write a function to generate all prime functions 

#include <iostream> 

using namespace std; 

bool isPrime(int n) 

{ 

    for(int i=2;i<=n-1;i++){ 

        if(n%i==0){ 

            return false; 

        } 

    } 

    return true; 

} 

void generatePrime(int n) 

{ 

    for(int i=2;i<=n;i++){ 

        if(isPrime(i)){ 

            cout<<i<<endl; 

        } 

    } 

} 

int main() 

{ 

    int n; 

    cin>>n; 

    generatePrime(n); 

    return 0; 

} 

 

// Write a function to return the factorial of a number 

#include <iostream> 

using namespace std; 

void generateFac(int n){ 

    int fac=1; 

    for(int i=1;i<=n;i++){ 

        fac=i*fac; 

    } 

    cout<<fac; 

} 

int main() 

{ 

    int n; 

    cin>>n; 

    generateFac(n); 

    return 0; 

} 

 

// Write a function to generate NCR= n!/(n-r)!r! 

#include <iostream> 

using namespace std; 

int generateFac(int n){ 

    int fac=1; 

    for(int i=1;i<=n;i++){ 

        fac=i*fac; 

    } 

    return fac; 

} 

int main() 

{ 

    int n,r; 

    cin>>n>>r; 

    cout<<(generateFac(n))/((generateFac(n-r))*(generateFac(r)))<<endl; 

    return 0; 

} 

 

/* Print the pattern for value of n if n=6, then: 

1 

11 

111 

1001 

11111 

100001 */ 

#include<iostream> 

using namespace std; 

  

void print(int n){ 

    int i=1; 

    while(i<=n) 

    { 

        if(i%2!=0){ 

            for(int j=1;j<=i;j++){ 

                cout<<"1"; 

            } 

        } 

        else{ 

            cout<<"1"; 

            for(int k=1;k<=i-2;k++){ 

                cout<<"0"; 

            } 

            cout<<"1"; 

        } 

        cout<<"\n"; 

        i++; 

    } 

} 

int main() 

{ 

    int n; 

    cin>>n; 

    print(n); 

    return 0; 

} 

 

/*Print the sequence if n=5, then: 

1   

2	2   

3	0	3     

4	0	0	4   

5	0	0	0	5*/ 

#include<iostream> 

using namespace std; 

  

void print(int n){ 

    int i=2; 

    cout<<"1"<<endl; 

    while(i<=n) 

    { 

        cout<<i<<"\t"; 

        for(int j=1;j<=i-2;j++){ 

            cout<<"0"<<"\t"; 

        } 

        cout<<i<<"\t"<<endl; 

        i++; 

    } 

} 

int main() 

{ 

    int n; 

    cin>>n; 

    print(n); 

    return 0; 

} 

 

//Write a function which prints first N1 terms of the series 3n + 2 which are not multiples of N2 

 #include<iostream> 

using namespace std; 

  

void print(int n){ 

    int i=2; 

    cout<<"1"<<endl; 

    while(i<=n) 

    { 

        cout<<i-1; 

        for(int j=2;j<i;j++){ 

            cout<<"0"; 

        } 

        cout<<i-1<<endl; 

        i++; 

    } 

} 

int main() 

{ 

    int n; 

    cin>>n; 

    print(n); 

    return 0; 

} 

 

// Print “UPPERCASE” when A-Z are input and “lowercase” when a-z are input and “Invalid” for all other characters 

#include<iostream> 

using namespace std; 

  

void print(int n){   /// I wanted to pass character variable, but udemy is not allowing , so i am passing integer 

    char c = n;      // to get character   65 is 'A' 1 97 is 'a' .... 

    // complete this function 

    if((65<=n)&&(n<=90)){ 

        cout<<"UPPERCASE"; 

    } 

    else if((97<=n)&&(n<=122)){ 

        cout<<"lowercase"; 

    } 

    else{ 

        cout<<"Invalid"; 

    } 

} 

int main() 

{ 

    int n; 

    cin>>n; 

    print(n); 

    return 0; 

} 

 

//Input coefficients of a quadratic equation and print whether that equation has real and distinct, real and equal or imaginary roots and also print the roots 

#include<iostream> 

#include<cmath> 

using namespace std; 

  

void print(int a,int b,int c){ 

    // complete this function 

    if(((pow(b,2))-(4*a*c))>0){ 

        cout<<"Real and Distinct"<<endl; 

        cout<<(-b - sqrt(pow(b,2) - 4*a*c))/2*a<<" "<<(-b + sqrt(pow(b,2) - 4*a*c))/2*a; 

    } 

    else if(((pow(b,2))-(4*a*c))==0){ 

        cout<<"Real and Equal"<<endl; 

        cout<<(-b - sqrt(pow(b,2) - 4*a*c))/2*a<<" "<<(-b + sqrt(pow(b,2) - 4*a*c))/2*a; 

    } 

    else{ 

        cout<<"Imaginary"; 

    } 

} 

int main() 

{ 

    int a,b,c; 

    cin>>a; 
    cin>>b; 
    cin>>c; 

    print(a,b,c); 

    return 0; 

} 

 

/* Check whether a number is prime or not 
#include<iostream> 

using namespace std; 

  

void print(int n){ 

    // complete this function 

    for(int i=2;i<n;i++){ 

        if(n%i==0){ 

            cout<<"Not Prime"; 

            return; 

        } 

    } 

    cout<<"Prime"; 

} 

int main() 

{ 

    int n; 

    cin>>n; 

    print(n); 

    return 0; 

} 

 

// Print the reverse of a number 

#include<iostream> 

using namespace std; 

  

void print(int n){ 

    // complete this function 

    int rev=0; 

    while(n!=0){ 

        int digit=n%10; 

        rev=rev*10+digit; 

        n=n/10; 

    } 

    cout<<rev; 

} 

int main() 

{ 

    int n; 

    cin>>n; 

    print(n); 

    return 0; 

} 

 

/* Due to an immense rise in Pollution, Home Minister is back with the Odd and Even Rule in City. The scheme is as follows, each car will be allowed to run on Sunday if the sum of digits which are even is divisible by 4 or sum of digits which are odd in that number is divisible by 3. However to check every car for the above criteria can't be done by the City Police. You need to help City Police by finding out if a car numbered N will be allowed to run on Sunday? */ 

#include<iostream> 

using namespace std; 

  

void print(int n){ 

    // complete this function 

    int sumodd=0,sumeven=0; 

    while(n!=0){ 

        int digit=n%10; 

        if(digit%2==0){ 

            sumeven=sumeven+digit; 

        } 

        else{ 

            sumodd=sumodd+digit; 

        } 

        n=n/10; 

    } 

    if((sumeven%4==0)||(sumodd%3==0)){ 

        cout<<"Yes"; 

    } 

    else{ 

        cout<<"No"; 

    } 

} 

int main() 

{ 

    int n; 

    cin>>n; 

    print(n); 

    return 0; 

} 

 

/* Take the following as input. 

Minimum Fahrenheit value 
Maximum Fahrenheit value 
Step 

Print as output the Celsius conversions. Use the formula C = (5/9)(F – 32) E.g. for an input of 0, 100 and 20 the output is 
0 -17 
20 -6 
40 4 
60 15 
80 26 
100 37 */ 

#include<iostream> 

using namespace std; 

  

void print(int ll, int ul,int step){ 

    // complete this function 

    for(int i=ll;i<=ul;i=i+step){ 

        int c=(int)((5.0/9)*(i-32)); 

        cout<<i<<"\t"<<c<<endl; 

    } 

} 

int main() 

{ 

    int ll,ul,step; 

    cin>>ll; 

    cin>>ul; 

    cin>>step; 

    print(ll,ul,step); 

    return 0; 

} 
                

//Codes from lab class
                
/* Write a C++ program by creating an 'Employee' class having the following functions and print the final salary. 

1 - 'getInfo()' which takes the salary, number of hours of work per day of employee as parameters 

2 - 'AddSal()' which adds $10 to the salary of the employee if it is less than $500. 

3 - 'AddWork()' which adds $5 to the salary of the employee if the number of hours of work per day is more than 6 hours. 

Input constraints: 

- The initial salary of the employee is an integer between 0 and 1000 (inclusive). 

- The number of work hours per day is an integer between 1 and 10 (inclusive). 

 

Output constraints: 

- The final salary of the employee is an integer between 0 and 1000 (inclusive). */ 
 

#include <iostream> 
using namespace std; 
class employee 
{ 
    double salary; 
    int no_of_hours; 
public: 
    employee() {} 
    void getinfo() 
    { 
        cout<<"Enter the salary of employee:"<<endl; 
        cin>>salary; 
        cout<<"Enter the number of hours:"<<endl; 
        cin>>no_of_hours; 
    } 
    void AddSal() 
    { 
        if (salary<500){ 
            salary=salary+10; 
        } 
    } 
    void AddWork() 
    { 
        if (no_of_hours>6){ 
            salary=salary+5;; 
        } 
    } 
    void DisplaySal() 
    { 
        cout<<salary; 
    } 
}; 
int main() 
{ 
    int n; 
    cout<<"Enter the number of employees:"<<endl; 
    cin>>n; 
    employee*emp=new employee[n]; 
    for (int i=0;i<n;i++){ 
        emp[i].getinfo(); 
        emp[i].AddSal(); 
        emp[i].AddWork(); 
    } 
    for (int i=0;i<n;i++){ 
        cout<<"\nThe final salary of employee "<<i<<" is:"<<endl; 
        emp[i].DisplaySal(); 
    } 
} 

 

/ WAP to calculate volume of a cube using constructor 
#include <iostream> 
class cube 
{ 
    private: 
        double side_length; 
    public: 
        //Constructor 
        cube(double length){ 
            side_length=length; 
        } 
        //To calculate volume 
        double calculate_volume(){ 
            return side_length*side_length*side_length; 
        } 
}; 
int main() 
{ 
    double length; 
    std::cout<<"Enter length of side of cube:"; 
    std::cin>>length; 
    //Create a cube object 
    cube cube(length); 
    //Calculate volume 
    double volume=cube.calculate_volume(); 
    std::cout<<"Volume of cube is:"<<volume<<std::endl; 
    return 0; 
} 
 

 
 

// WAP to calculate volume of a cube using constructor 
#include <iostream> 
class rectangle 
{ 
    private: 
        double length; 
        double width; 
    public: 
        //Constructor 
        rectangle(double len,double wid){ 
            length=len; 
            width=wid; 
        } 
        //To calculate area 
        double calculate_area(){ 
            return length*width; 
        } 
}; 
int main() 
{ 
    double length,width; 
    std::cout<<"Enter length of rectangle:"; 
    std::cin>>length; 
    std::cout<<"Enter width of rectangle:"; 
    std::cin>>width; 
    //Create a rectangle object 
    rectangle rectangle(length,width); 
    //Calculate volume 
    double area=rectangle.calculate_area(); 
    std::cout<<"Area of rectangle is:"<<area<<std::endl; 
    return 0; 
} 

 

/* WAP to create a BankAccount class in C++ that stimulates a bank account. It should have methods to withdraw,deposit and check account balance. Use necessary constructors and accessors. */ 

#include <iostream> 

using namespace std; 

class BankAccount 

{ 

    private: 

    double balance; 

    public: 

    BankAccount (){ 

        balance=0; 

    } 

    void deposit(double amount) 

    { 

        balance=balance+amount; 

    } 

    void withdraw(double amount) 

    { 

        if (amount>balance) 

        { 

            cout<<"Insufficient Balance"; 

        } 

        else 

        { 

            balance=balance-amount; 

        } 

    } 

    double getBalance() 

    { 

        return balance; 

    } 

}; 

int main() { 

    BankAccount acc; 

    int n; 

    double amt; 

    while (true) 

    { 

        amt=0; 

        cout<<"\nTo Deposit money press 1.\nTo Withdraw money press 2.\nTo Display balance press 3.\nTo Quit press 4."<<endl; 

        cin>>n; 

         if (n==1) 

        { 

            cout<<"Enter the Amount to deposit"<<endl; 

            cin>>amt; 

            acc.deposit(amt); 

        } 

        else if(n==2) 

        { 

            cout<<"Enter the Amount to Withdraw"<<endl; 

            cin>>amt; 

            acc.withdraw(amt); 

        } 

        else if (n==3) 

        { 

            cout<<"Balance is:"<<acc.getBalance()<<endl; 

        } 

        else if(n==4) 

        { 

            break; 

        } 

     } 

    return 0; 

} 

 

/* Create a class called Stack that represents a stack data structure in C++ using array. It should have methods push(), pop() and isEmpty(). WAP to demonstrate functionality of Stack class by performing push and pop operations. */ 

#include <iostream> 

  

using namespace std; 

  

class Stack { 

private: 

    static const int MAX_SIZE = 100; 

    int data[MAX_SIZE]; 

    int top;  

public: 

    Stack() { 

        top = -1;  

    } 

  

    bool isEmpty() const { 

        return top == -1; 

    } 

  

    bool isFull() const { 

        return top == MAX_SIZE - 1; 

    } 

  

    void push(int element) { 

        if (isFull()) { 

            cout << "Stack is full. Cannot push element." << endl; 

        } else { 

            top++; 

            data[top] = element; 

            cout << "Pushed element: " << element << endl; 

        } 

    } 

  

    void pop() { 

        if (isEmpty()) { 

            cout << "Stack is empty. Cannot pop element." << endl; 

        } else { 

            int poppedElement = data[top]; 

            top--; 

            cout << "Popped element: " << poppedElement << endl; 

        } 

    } 

}; 

  

int main() { 

    Stack stack; 

  

    int choice; 

    int element; 

  

    do { 

        cout << "Stack Operations:" << endl; 

        cout << "1. Push" << endl; 

        cout << "2. Pop" << endl; 

        cout << "3. Exit" << endl; 

        cout << "Enter your choice: "; 

        cin >> choice; 

  

        switch (choice) { 

            case 1: 

                cout << "Enter element to push: "; 

                cin >> element; 

                stack.push(element); 

                break; 

            case 2: 

                stack.pop(); 

                break; 

            case 3: 

                cout << "Exiting program." << endl; 

                break; 

            default: 

                cout << "Invalid choice. Please try again." << endl; 

                break; 

        } 

  

        cout << endl; 

    } while (choice != 3); 

  

    return 0; 

} 

 

// There is a base class named shape. This base class has features such as length, breadth and height. There are sub classes namely square, rectangle, triangle, circle and parallelogram. Inherit the base class in the required places and implement a function to find the area of the shapes. Use constructors. 1 sq m = Rs 50. 
 

#include <iostream> 
using namespace std; 
class Shape 
{ 
    protected: 
        double length; 
        double breadth; 
        double height; 
    public: 
        Shape(double l=0,double b=0,double h=0): length(l),breadth(b),height(h){} 
        virtual double calculateArea()=0; 
}; 
class Square:public Shape 
{ 
    public: 
        Square(double side):Shape(side,side,0){} 
        double calculateArea() override{ 
            return length*length; 
        } 
}; 
class Rectangle:public Shape 
{ 
    public: 
        Rectangle(double l,double b):Shape(1,b,0){} 
        double calculateArea() override{ 
            return length*breadth; 
        } 
}; 
class Triangle:public Shape 
{ 
    public: 
        Triangle(double b,double h):Shape(0,b,h){} 
        double calculateArea() override{ 
            return 0.5*breadth*height; 
        } 
}; 
class Circle:public Shape 
{ 
    public: 
        Circle(double radius):Shape(radius,0,0){} 
        double calculateArea() override{ 
            return 3.14159*length*length; 
        } 
}; 
class Parallelogram:public Shape 
{ 
    public: 
        Parallelogram(double b,double h):Shape(0,b,h){} 
        double calculateArea() override{ 
            return breadth*height; 
        } 
}; 
int main() 
{ 
    Shape*shapes[]={ 
        new Square(5), 
        new Rectangle(4,6), 
        new Triangle(3,8), 
        new Circle(2), 
        new Parallelogram(4,5), 
    }; 
    double totalArea=0; 
    for(Shape*shape:shapes){ 
        double area=shape->calculateArea(); 
        totalArea=totalArea+area; 
        cout<<"Area:"<<area<<"sq.m"<<endl; 
    } 
    double costPerSqM=50; 
    double totalCost=totalArea*costPerSqM; 
    cout<<"Total cost: Rs"<<totalCost<<endl; 
    for(Shape*shape:shapes){ 
        delete shape; 
    } 
    return 0; 
} 
