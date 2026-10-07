FINDING TIME COMPLEXITY OF ALGORITHM

Problem 1: Finding Complexity using counter method

Playing with Numbers:


Ram and Sita are playing with numbers by giving puzzles to each other. Now it was Ram term, so he gave Sita a positive integer ‘n’ and two numbers 1 and 3. He asked her to find the possible ways by which the number n can be represented using 1 and 3.Write any efficient algorithm to find the possible ways.

Example 1:

Input: 6
Output:6
Explanation: There are 6 ways to 6 represent number with 1 and 3
         1+1+1+1+1+1
         3+3
         1+1+1+3
         1+1+3+1
         1+3+1+1
         3+1+1+1
Input Format
First Line contains the number n
 
Output Format

Print: The number of possible ways ‘n’ can be represented using 1 and 3


Sample Input
 
6


```c
#include<stdio.h>

long long  count(int n){
    if(n<0) return 0;
    if(n==0 || n==1 || n==2) return 1;
    long long  dp[n+1];
    dp[0]=1;
    dp[1]=1;
    dp[2]=1;
    for(int i=3;i<=n;i++){
        dp[i]=dp[i-1]+dp[i-3];
    }
    return dp[n];
}
int main(){
    int n;
    scanf("%d",&n);
    printf("%lld",count(n));
    return 0;
}
```


Problem 2: Finding Complexity using Counter method

Convert the following algorithm into a program and find its time complexity using the counter method.
void func(int n)
{
    if(n==1)
    {
      printf("*");
    }
    else
    {
     for(int i=1; i<=n; i++)
     {
       for(int j=1; j<=n; j++)
       {
          printf("*");
          printf("*");
          break;
       }
     }
   }                      
 }

Note: No need of counter increment for declarations and scanf() and  count variable printf() statements.
Input:
 A positive Integer n
Output:
Print the value of the counter variable

```c
#include <stdio.h>
int main()
{
    int n,count=0;
    scanf("%d",&n);
    
    if(n==1)
    {
      count++;
    }
    else {
        int i = 1;
        count++; 

        while (count++, i <= n) {
            count++; 
            count++; 
            count++; 

            i++;
            count++; 
        }
    }      
   printf("%d",count);
   return 0;
 }

```
Problem 3: Finding Complexity using Counter Method

Convert the following algorithm into a program and find its time complexity using counter method.
 Factor(num) {
 {
    for (i = 1; i <= num;++i)
    {
     if (num % i== 0)
        {
          printf("%d ", i);
        }        
     } 
  }
 
 
Note: No need of counter increment for declarations and scanf() and counter variable printf() statement.

Input:
 A positive Integer n
Output:
Print the value of the counter variable

```c
#include<stdio.h>
int main(){
    int count=0;
    count++;
    int num;
    scanf("%d",&num);
    for(int i=1;i<=num;i++){
        if(num%i==0){
            count++;
        }
        count+=2;
    }
    printf("%d",count);
    return 0;
}
```

Problem 4: Finding Complexity using Counter Method

Convert the following algorithm into a program and find its time
complexity using counter method.
            
void function(int n)
{
    int c= 0;
    for(int i=n/2; i<n; i++)
        for(int j=1; j<n; j = 2 * j)
            for(int k=1; k<n; k = k * 2)
                c++;
}
 
Note: No need of counter increment for declarations and scanf() and  count variable printf() statements.

Input:
 A positive Integer n
Output:
Print the value of the counter variable
```c
#include<stdio.h>
int main(){
    int count=0,n;
    scanf("%d",&n);
    count++;
    for(int i=n/2; i<n; i++){
        count+=2;
        for(int j=1; j<n; j = 2 * j){
            count+=2;
            for(int k=1; k<n; k = k * 2){
                count+=2;
            }
        }
    }
    count++;
    printf("%d",count);
    return 0;
}
```

Problem 5: Finding Complexity using counter method

Convert the following algorithm into a program and find its time complexity using counter method.

void reverse(int n)
{
   int rev = 0, remainder;
   while (n != 0) 
    {
        remainder = n % 10;
        rev = rev * 10 + remainder;
        n/= 10;
        
    }
print(rev);
}
 
Note: No need of counter increment for declarations and scanf() and  count variable printf() statements.

Input:
 A positive Integer n
Output:
Print the value of the counter variable
```c
#include<stdio.h>
int main(){
   int n,count=2;
   int rev=0,remainder;
   scanf("%d",&n);
   while (count++,n != 0) 
    {
        remainder = n % 10;
        rev=rev*10+remainder;
        n/= 10;
        count+=3;
        
    }
    printf("%d",count);
    return 0;
}
```
