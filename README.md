#include<stdio.h>
#include<conio.h>
#include<math.h>
#include<stdlib.h>

#define KEY "Enter the calculator Operation you want to do:"
int x=22;
int y=50;

void addition();
void subtraction();
void multiplication();
void division();
void modulus();
void power();
int factorial();
void calculator_operations();

char Calc_oprn,ch;

int main()
{
    while(1)
    {
        calculator_operations();
        printf("\n");
        printf("%s : ", KEY);

        Calc_oprn=getche();

        switch(Calc_oprn)
        {
        case '+':
            addition();
            break;
        case '-':
            subtraction();
            break;

        case '*':
            multiplication();
            break;

        case '/':
            division();
            break;

        case '?':
            modulus();
            break;

        case '!':
            factorial();
            break;

        case '^':
            power();
            break;

        case 'H':
        case 'h':
            calculator_operations();
            break;

        case 'Q':
        case 'q':
            exit(0);
            break;
        case 'c':
        case 'C':
            system("cls");
            calculator_operations();
            break;

        default :
            system("cls");

            printf("\n**********You have entered unavailable option");
            printf("***********\n");
            printf("\n*****Please Enter any one of below available ");
            printf("options****\n");
            printf("\n\n\t\t\t\tPress enter to continue.\n");
            gets(ch);
            calculator_operations();
        }
    }
}
void deletefunc()
{
    printf("\n\n\t\t\t\tPress enter to continue.\n");
    gets(ch);
    calculator_operations();
}


void calculator_operations()
{
    system("cls");  //use system function to clear
    //screen instead of clrscr();
    int i,j;
    for(i=0; i<x; i++)
    {
        for(j=0; j<y; j++)
        {
            if(i==0||j==0||i==x-1||j==y-1)
                printf("*");
            else if(i==2&&j==14)
            {
                printf("Welcome to C calculator");
                j+=22;
            }
            else if(i==5&&j==4)
            {
                printf("******* Press 'Q' or 'q' to quit");
                j+=31;
            }
            else if(i==6&&j==4)
            {
                printf("the program ********");
                j+=19;
            }
            else if(i==7&&j==4)
            {
                printf("***** Press 'H' or 'h' to display ");
                j+=33;
            }
            else if(i==8&&j==4)
            {
                printf("below options *****");
                j+=18;
            }
            else if(i==9&&j==4)
            {
                printf("Enter 'C' or 'c' to clear the screen and");
                j+=39;
            }
            else if(i==11&&j==14)
            {
                printf("Display available option ");
                j+=24;
            }
            else if(i==14&&j==4)
            {
                printf("Enter + symbol for Addition ");
                j+=27;
            }
            else if(i==15&&j==4)
            {
                printf("Enter - symbol for Subtraction ");
                j+=30;
            }
            else if(i==16&&j==4)
            {
                printf("Enter * symbol for Multiplication ");
                j+=33;
            }
            else if(i==17&&j==4)
            {
                printf("Enter / symbol for Division ");
                j+=27;
            }
            else if(i==18&&j==4)
            {
                printf("Enter ? symbol for Modulus");
                j+=25;
            }
            else if(i==19&&j==4)
            {
                printf("Enter ^ symbol for Power ");
                j+=24;
            }
            else if(i==20&&j==4)
            {
                printf("Enter ! symbol for Factorial ");
                j+=28;
            }
            else
                printf(" ");
        }
        printf("\n");
    }

}

void addition()
{
    int n, total=0, k=0, number;
    printf("\nEnter the number of elements you want to add:");
    scanf("%d",&n);
    printf("Please enter %d numbers one by one: \n",n);
    while(k<n)
    {
        scanf("%d",&number);
        total=total+number;
        k=k+1;
    }
    printf("Sum of %d numbers = %d \n",n,total);
}

void subtraction()
{
    int a, b, c = 0;
    printf("\nPlease enter first number  : ");
    scanf("%d", &a);
    printf("Please enter second number : ");
    scanf("%d", &b);
    c = a - b;
    printf("\n%d - %d = %d\n", a, b, c);
}

void multiplication()
{
    int a, b, mul=0;
    printf("\nPlease enter first numb   : ");
    scanf("%d", &a);
    printf("Please enter second number: ");
    scanf("%d", &b);
    mul=a*b;
    printf("\nMultiplication of entered numbers = %d\n",mul);
}

void division()
{
    int a, b, d=0;
    printf("\nPlease enter first number  : ");
    scanf("%d", &a);
    printf("Please enter second number : ");
    scanf("%d", &b);
    d=a/b;
    printf("\nDivision of entered numbers=%d\n",d);
}

void modulus()
{
    int a, b, d=0;
    printf("\nPlease enter first number   : ");
    scanf("%d", &a);
    printf("Please enter second number  : ");
    scanf("%d", &b);
    d=a%b;
    printf("\nModulus of entered numbers = %d\n",d);
}

void power()
{
    double a,num, p;
    printf("\nEnter two numbers to find the power \n");
    printf("number: ");
    scanf("%lf",&a);

    printf("power : ");
    scanf("%lf",&num);

    p=pow(a,num);

    printf("\n%lf to the power %lf = %lf \n",a,num,p);
}

int factorial()
{
    int i,fact=1,num;

    printf("\nEnter a number to find factorial : ");
    scanf("%d",&num);

    if (num<0)
    {
        printf("\nPlease enter a positive number to");
        printf(" find factorial and try again. \n");
        printf("\nFactorial can't be found for negative");
        printf(" values. It can be only positive or 0  \n");
        return 1;
    }

    for(i=1; i<=num; i++)
        fact=fact*i;
    printf("\n");
    printf("Factorial of entered number %d is:%d\n",num,fact);
    return 0;
}
