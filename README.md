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
![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20085937.png)

Problem 2: Finding Complexity using Counter method

Convert the following algorithm into a program and find its time complexity using the counter method.

````markdown

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

````

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
![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20091133.png)
Problem 3: Finding Complexity using Counter Method

Convert the following algorithm into a program and find its time complexity using counter method.
````markdown
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
 ````
 
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
![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20091159.png)

Problem 4: Finding Complexity using Counter Method

Convert the following algorithm into a program and find its time
complexity using counter method.
````markdown        
void function(int n)
{
    int c= 0;
    for(int i=n/2; i<n; i++)
        for(int j=1; j<n; j = 2 * j)
            for(int k=1; k<n; k = k * 2)
                c++;
}
````
 
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
![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20150617.png)


Problem 5: Finding Complexity using counter method


Convert the following algorithm into a program and find its time complexity using counter method.
````markdown
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
 ````
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
![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20150758.png)

GREEDY ALGORITHM

1-G-Coin Problem
Write a program to take value V and  we want to make change for V Rs, and we have infinite supply of each of the denominations in Indian currency, i.e., we have infinite supply of { 1, 2, 5, 10, 20, 50, 100, 500, 1000} valued coins/notes, what is the minimum number of coins and/or notes needed to make the change.

Input Format:

Take an integer from stdin.

Output Format:

print the integer which is change of the  number.

Example Input :

64

Output:

4

Explanaton:

We need a 50 Rs note and a 10 Rs note and two 2 rupee coins.


```C
#include <stdio.h>

int main() {
    int arr[9] = {1000, 500, 100, 50, 20, 10, 5, 2, 1};
    int n;
    scanf("%d", &n);

    int c = 0;
    for (int i = 0; i < 9; i++) {
        if (n >= arr[i]) {
            c += n / arr[i];
            n %= arr[i];
        }
    }

    printf("%d", c);
    return 0;
}
```
![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20151348.png)


2-G-Cookies Problem

Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child i has a greed factor g[i], which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s[j]. If s[j] >= g[i], we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximize the number of your content children and output the maximum number.

Example 1:

Input: 

3

1 2 3

2

1 1

Output: 

1

Explanation: You have 3 children and 2 cookies. The greed factors of 3 children are 1, 2, 3. 

And even though you have 2 cookies, since their size is both 1, you could only make the child whose greed factor is 1 content.

You need to output 1.

Constraints:

1 <= g.length <= 3 * 10^4

0 <= s.length <= 3 * 10^4

1 <= g[i], s[j] <= 2^31 - 1

```c
#include <stdio.h>

int main() {
    int n, m;

    // Read greed factors size and array
    if (scanf("%d", &n) != 1) return 0;
    int g[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &g[i]);
    }

    // Read cookie sizes size and array
    if (scanf("%d", &m) != 1) return 0;
    int s[m];
    for (int i = 0; i < m; i++) {
        scanf("%d", &s[i]);
    }

    // Bubble sort for array g
    for (int i = 0; i < n - 1; i++) {
        for (int j = 0; j < n - i - 1; j++) {
            if (g[j] > g[j + 1]) {
                int temp = g[j];
                g[j] = g[j + 1];
                g[j + 1] = temp;
            }
        }
    }

    // Bubble sort for array s
    for (int i = 0; i < m - 1; i++) {
        for (int j = 0; j < m - i - 1; j++) {
            if (s[j] > s[j + 1]) {
                int temp = s[j];
                s[j] = s[j + 1];
                s[j + 1] = temp;
            }
        }
    }

    // Two-pointer greedy match
    int child_ptr = 0;
    int cookie_ptr = 0;

    while (child_ptr < n && cookie_ptr < m) {
        if (s[cookie_ptr] >= g[child_ptr]) {
            child_ptr++;
        }
        cookie_ptr++;
    }

    printf("%d\n", child_ptr);
    return 0;
}
```
![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20151514.png)

3-G-Burger Problem

 A person needs to eat burgers. Each burger contains a count of calorie. After eating the burger, the person needs to run a distance to burn out his calories. 
 If he has eaten i burgers with c calories each, then he has to run at least 3i * c  kilometers to burn out the calories. For  example, if he ate 3
 burgers with the count of calorie in the order: [1, 3, 2], the kilometers he needs to run are (30 * 1) + (31 * 3) + (32 * 2) = 1 + 9 + 18 = 28.
 But this is not the minimum, so need to try out other orders of consumption and choose the minimum value. Determine the minimum distance
 he needs to run. Note: He can eat burger in any order and use an efficient sorting algorithm.Apply greedy approach to solve the problem.
Input Format
First Line contains the number of burgers
Second line contains calories of each burger which is n space-separate integers 
 
Output Format
 
Print: Minimum number of kilometers needed to run to burn out the calories
 
Sample Input
 
3
5 10 7
 
Sample Output
76


```c
#include<stdio.h>
#include<math.h>
#include<stdlib.h>
int main(){
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    for(int i=0;i<n;i++){
        for(int j=i+1;j<n;j++){
            if(arr[i]<arr[j]){
                int temp=arr[i];
                arr[i]=arr[j];
                arr[j]=temp;
            }
        }
    }
    
    int run=0;
    for(int i=0;i<n;i++){
        run+=pow(n,i)*arr[i];
    }
    printf("%d",run);
    return 0;
}
```
![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20151645.png)

4-G-Array Sum max problem

Given an array of N integer, we have to maximize the sum of arr[i] * i, where i is the index of the element (i = 0, 1, 2, ..., N).Write an algorithm based on Greedy technique with a Complexity O(nlogn).

 Input Format:

First line specifies the number of elements-n

The next n lines contain the array elements.

Output Format:

Maximum Array Sum to be printed.

Sample Input:

5

2 5 3 4 0

Sample output:

40

```c
#include<stdio.h>
int main(){
    int n;
    scanf("%d",&n);
    int a[n];
    int s=0;
    for(int i=0;i<n;i++){
        scanf("%d",&a[i]);
    }
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            if(a[i]<a[j]){
                int temp=a[i];
                a[i]=a[j];
                a[j]=temp;
            }
        }
    }
    for(int i=0;i<n;i++){
        s+=a[i]*i;
    }
    printf("%d",s);
    return 0;
}
```
![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20153520.png)

5-G-Product of Array elements-Minimum
Given two arrays array_One[] and array_Two[] of same size N. We need to first rearrange the arrays such that the sum of the product of pairs( 1 element from each) is minimum. That is SUM (A[i] * B[i]) for all i is minimum.

For example:

Input	Result
3
1
2
3
4
5
6
28

```c
#include<stdio.h>
int main(){
    int n;
    scanf("%d",&n);
    int a[n];
    int b[n];
    for(int i=0;i<n;i++){
        scanf("%d",&a[i]);
    }
    for(int i=0;i<n;i++){
        scanf("%d",&b[i]);
    }
    for(int i=0;i<n;i++){
        for(int j=i+1;j<n;j++){
            if(a[i]>a[j]){
                int temp=a[i];
                a[i]=a[j];
                a[j]=temp;
            }
        }
    }
    for(int i=0;i<n;i++){
        for(int j=i+1;j<n;j++){
            if(b[i]<b[j]){
                int temp=b[i];
                b[i]=b[j];
                b[j]=temp;
            }
        }
    }
    int s=0;
    for(int i=0;i<n;i++){
       s+=a[i]*b[i];
    }
    printf("%d",s);
    return 0;
}
```
![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20153715.png)









