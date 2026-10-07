# Finding Time Complexity of Algorithms

## 1. Problem: Finding Complexity Using Counter Method

Convert the following algorithm into a program and find its time complexity using the counter method.

```c
void function(int n)
{
    int i = 1;
    int s = 1;

    while (s <= n) {
        i++;
        s += i;
    }
}
```

### Note
No counter increment is needed for declarations, `scanf()`, or `printf()` statements.

### Input
- A positive integer `n`

### Output
- Print the value of the counter variable

### C Program
```c
#include <stdio.h>

int main() {
    int n, count = 0;
    scanf("%d", &n);

    int i = 1;
    count++;
    int s = 1;
    count++;

    while (count++, s <= n) {
        i++;
        count++;

        s += i;
        count++;
    }

    printf("%d", count);
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20085937.png)

## 2. Problem: Finding Complexity Using Counter Method

Convert the following algorithm into a program and find its time complexity using the counter method.

```c
void func(int n)
{
    if (n == 1) {
        printf("*");
    } else {
        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= n; j++) {
                printf("*");
                printf("*");
                break;
            }
        }
    }
}
```

### Note
No counter increment is needed for declarations, `scanf()`, or `printf()` statements.

### Input
- A positive integer `n`

### Output
- Print the value of the counter variable

### C Program
```c
#include <stdio.h>

int main() {
    int n, count = 0;
    scanf("%d", &n);

    if (n == 1) {
        count++;
    } else {
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

    printf("%d", count);
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20091133.png)

## 3. Problem: Finding Complexity Using Counter Method

Convert the following algorithm into a program and find its time complexity using the counter method.

```c
Factor(num) {
    for (i = 1; i <= num; ++i) {
        if (num % i == 0) {
            printf("%d ", i);
        }
    }
}
```

### Note
No counter increment is needed for declarations, `scanf()`, or `printf()` statements.

### Input
- A positive integer `n`

### Output
- Print the value of the counter variable

### C Program
```c
#include <stdio.h>

int main() {
    int count = 0;
    count++;

    int num;
    scanf("%d", &num);

    for (int i = 1; i <= num; i++) {
        if (num % i == 0) {
            count++;
        }
        count += 2;
    }

    printf("%d", count);
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20091159.png)

## 4. Problem: Finding Complexity Using Counter Method

Convert the following algorithm into a program and find its time complexity using the counter method.

```c
void function(int n)
{
    int c = 0;

    for (int i = n / 2; i < n; i++)
        for (int j = 1; j < n; j = 2 * j)
            for (int k = 1; k < n; k = k * 2)
                c++;
}
```

### Note
No counter increment is needed for declarations, `scanf()`, or `printf()` statements.

### Input
- A positive integer `n`

### Output
- Print the value of the counter variable

### C Program
```c
#include <stdio.h>

int main() {
    int count = 0, n;
    scanf("%d", &n);
    count++;

    for (int i = n / 2; i < n; i++) {
        count += 2;

        for (int j = 1; j < n; j = 2 * j) {
            count += 2;

            for (int k = 1; k < n; k = k * 2) {
                count += 2;
            }
        }
    }

    count++;
    printf("%d", count);
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20150617.png)

## 5. Problem: Finding Complexity Using Counter Method

Convert the following algorithm into a program and find its time complexity using the counter method.

```c
void reverse(int n)
{
    int rev = 0, remainder;

    while (n != 0) {
        remainder = n % 10;
        rev = rev * 10 + remainder;
        n /= 10;
    }

    print(rev);
}
```

### Note
No counter increment is needed for declarations, `scanf()`, or `printf()` statements.

### Input
- A positive integer `n`

### Output
- Print the value of the counter variable

### C Program
```c
#include <stdio.h>

int main() {
    int n, count = 2;
    int rev = 0, remainder;
    scanf("%d", &n);

    while (count++, n != 0) {
        remainder = n % 10;
        rev = rev * 10 + remainder;
        n /= 10;
        count += 3;
    }

    printf("%d", count);
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20150758.png)

# GREEDY ALGORITHM

## 1-G-Coin Problem
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


## 2-G-Cookies Problem

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

## 3-G-Burger Problem

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

## 4-G-Array Sum max problem

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

## 5-G-Product of Array elements-Minimum
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

# DIVIDE AND CONQUER
##1-Number of Zeros in a Given Array

Problem Statement
Given an array of 1s and 0s this has all 1s first followed by all 0s. Aim is to find the number of 0s. Write a program using Divide and Conquer to Count the number of zeroes in the given array.
Input Format
   First Line Contains Integer m – Size of array
   Next m lines Contains m numbers – Elements of an array
Output Format
   First Line Contains Integer – Number of zeroes present in the given array.

```c
#include<stdio.h>
int count(int arr[], int low, int high){
    if(low>high){
        return 0;
    }
    if(arr[low]==0){
        return (high-low+1);
    }
    if(arr[high]==1){
        return 0;
    }
    int mid=low+(high-low)/2;
    return count(arr,low,mid)+count(arr,mid+1,high);
}
int main(){
    int m;
    scanf("%d",&m);
    int arr[m];
    for(int i=0;i<m;i++){
        scanf("%d",&arr[i]);
    }
    printf("%d",count(arr,0,m-1));
    return 0;
}
```
![output]()
## 2-Majority Element
Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.

 

Example 1:

Input: nums = [3,2,3]
Output: 3
Example 2:

Input: nums = [2,2,1,1,1,2,2]
Output: 2
 

Constraints:

n == nums.length
1 <= n <= 5 * 104
-231 <= nums[i] <= 231 - 1

For example:

Input	Result
3
3 2       3
3
7
2 2 1 1 1 2 2
2
```c

#include<stdio.h>
int main(){
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    int c=1,find=arr[0];
    for(int i=0;i<n;i++){
        if(c==0){
            find=arr[i];
            c=1;
        }else if(arr[i]==find){
            c++;
        }else{
            c--;
        }
    }
    printf("%d",find);
    return 0;
}
```
![output]()
## 3-Finding Floor Value
Problem Statement:
Given a sorted array and a value x, the floor of x is the largest element in array smaller than or equal to x. Write divide and conquer algorithm to find floor of x.
Input Format
   First Line Contains Integer n – Size of array
   Next n lines Contains n numbers – Elements of an array
   Last Line Contains Integer x – Value for x
 
Output Format
   First Line Contains Integer – Floor value for x

```c
#include<stdio.h>
int find(int arr[], int low, int high,int x){
    if(low>high){
        return -1;
    }if(x>=arr[high]){
        return arr[high];
    }
    int mid=(low+high)/2;
    
    if(arr[mid]==x){
        return arr[mid];
    }
    if(mid>0 && arr[mid-1]<=x && x<arr[mid]){
        return arr[mid-1];
    }
    if(x<arr[mid]){
        return find(arr,low,mid-1,x);
    }
    return find(arr,mid+1,high,x);
}
int main(){
    int n,x;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    scanf("%d",&x);
    printf("%d",find(arr,0,n-1,x));
    return 0;
}

```
![output]()
## 4-Two Elements sum to x
Problem Statement:
Given a sorted array of integers say arr[] and a number x. Write a recursive program using divide and conquer strategy to check if there exist two elements in the array whose sum = x. If there exist such two elements then return the numbers, otherwise print as “No”.
Note: Write a Divide and Conquer Solution
Input Format
   First Line Contains Integer n – Size of array
   Next n lines Contains n numbers – Elements of an array
   Last Line Contains Integer x – Sum Value
Output Format
   First Line Contains Integer – Element1
   Second Line Contains Integer – Element2 (Element 1 and Elements 2 together sums to value “x”)

```c
#include<stdio.h>
int find(int arr[],int left,int right,int x){
    if(left>=right){
        printf("No");
        return 0;
    }
    int sum=arr[left]+arr[right];
    if(sum==x){
        printf("%d\n%d",arr[left],arr[right]);
        return 1;
    }else if(sum<x){
        return find(arr,left+1,right,x);
    }else{
        return find(arr,left,right-1,x);
    }
}
int main(){
    int n,x;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    scanf("%d",&x);
    find(arr,0,n-1,x);
    return 0;
}
```
![output]()
## 5-Implementation of Quick Sort
Write a Program to Implement the Quick Sort Algorithm

Input Format:
The first line contains the no of elements in the list-n
The next n lines contain the elements.

Output:
Sorted list of elements

For example:

Input	Result
5
67 34 12 98 78
12 34 67 78 98

```c
#include<stdio.h>
void swap(int *a,int *b){
    int temp=*a;
    *a=*b;
    *b=temp;
}
int part(int arr[],int low,int high){
    int pivot=arr[high];
    int i=low-1;
    for(int j=low;j<high;j++){
        if(arr[j]<pivot){
            i++;
            swap(&arr[i],&arr[j]);
        }
    }
    swap(&arr[i+1],&arr[high]);
    return i+1;
}
void quick(int arr[],int low,int high){
    if(low<high){
        int pi=part(arr,low,high);
        quick(arr,low,pi-1);
        quick(arr,pi+1,high);
    }
}
int main(){
    int n;
    scanf("%d",&n);
    int arr[n];
    for(int i=0;i<n;i++){
        scanf("%d",&arr[i]);
    }
    quick(arr,0,n-1);
    for(int i=0;i<n;i++){
        printf("%d ",arr[i]);
    }
    return 0;
}
```
![output]()# Dynamic Programming

## 1. DP - Playing with Numbers

### Problem
Ram and Sita are playing with numbers by giving puzzles to each other. Now it was Ram's turn, so he gave Sita a positive integer `n` and two numbers `1` and `3`. He asked her to find the number of ways by which `n` can be represented using `1` and `3`.

### Example
Input: `6`

Output: `6`

Explanation:

There are 6 ways to represent 6 using 1 and 3:

- `1 + 1 + 1 + 1 + 1 + 1`
- `3 + 3`
- `1 + 1 + 1 + 3`
- `1 + 1 + 3 + 1`
- `1 + 3 + 1 + 1`
- `3 + 1 + 1 + 1`

### Input Format
- The first line contains the number `n`.

### Output Format
- Print the number of possible ways `n` can be represented using `1` and `3`.

### Sample Input
```text
6
```

### Sample Output
```text
6
```

### C Program
```c
#include <stdio.h>

long long count(int n) {
    if (n < 0) return 0;
    if (n == 0 || n == 1 || n == 2) return 1;

    long long dp[n + 1];
    dp[0] = 1;
    dp[1] = 1;
    dp[2] = 1;

    for (int i = 3; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 3];
    }

    return dp[n];
}

int main() {
    int n;
    scanf("%d", &n);
    printf("%lld", count(n));
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20163042.png)

## 2. DP - Playing with Chessboard

### Problem
Ram is given an `n x n` chessboard, with each cell having a monetary value. Ram stands at cell `(0, 0)`, the top-left white rook. He must reach the bottom-right black rook position `(n - 1, n - 1)` while moving only one step right or one step down at a time. The goal is to find the path with the maximum monetary value.

### Example
Input:

```text
3
1 2 4
2 3 4
8 7 1
```

Output:

```text
19
```

### Explanation
There are 6 possible paths, and the optimal path value is:

`1 + 2 + 8 + 7 + 1 = 19`

### Input Format
- The first line contains the integer `n`.
- The next `n` lines contain the values of the `n x n` chessboard.

### Output Format
- Print the maximum monetary value of the path.

### C Program
```c
#include <stdio.h>

int max(int a, int b) {
    return (a > b) ? a : b;
}

int main() {
    int n;
    scanf("%d", &n);

    int arr[n][n];
    int brr[n][n];

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            scanf("%d", &arr[i][j]);
        }
    }

    brr[0][0] = arr[0][0];
    for (int i = 1; i < n; i++) {
        brr[i][0] = brr[i - 1][0] + arr[i][0];
    }

    for (int j = 1; j < n; j++) {
        brr[0][j] = brr[0][j - 1] + arr[0][j];
    }

    for (int i = 1; i < n; i++) {
        for (int j = 1; j < n; j++) {
            brr[i][j] = arr[i][j] + max(brr[i - 1][j], brr[i][j - 1]);
        }
    }

    printf("%d\n", brr[n - 1][n - 1]);
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20163149.png)

## 3. DP - Longest Common Subsequence

### Problem
Given two strings, find the length of the longest common subsequence (not necessarily contiguous) between them.

### Example
```text
s1: ggtabe
s2: tgatasb
```

The length is `4`.

### Explanation
This is solved using dynamic programming.

### Example Table
| Input | Result |
| :--- | :--- |
| aab<br>azb | 2 |

### C Program
```c
#include <stdio.h>
#include <string.h>

int max(int a, int b) {
    return a > b ? a : b;
}

int main() {
    char a[1000], b[1000];
    scanf("%s %s", a, b);

    int n = strlen(a);
    int m = strlen(b);
    int dp[n + 1][m + 1];

    for (int i = 0; i <= n; i++) {
        dp[i][0] = 0;
    }

    for (int i = 0; i <= m; i++) {
        dp[0][i] = 0;
    }

    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= m; j++) {
            if (a[i - 1] == b[j - 1]) {
                dp[i][j] = dp[i - 1][j - 1] + 1;
            } else {
                dp[i][j] = max(dp[i - 1][j], dp[i][j - 1]);
            }
        }
    }

    printf("%d", dp[n][m]);
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20163256.png)

## 4. DP - Longest Non-decreasing Subsequence

### Problem
Find the length of the longest non-decreasing subsequence in a given sequence.

### Example
Input:

```text
9
-1 3 4 5 2 2 2 2 3
```

The subsequence is:

```text
[-1, 2, 2, 2, 2, 3]
```

Output:

```text
6
```

### C Program
```c
#include <stdio.h>

int max(int a, int b) {
    return a > b ? a : b;
}

int main() {
    int n;
    scanf("%d", &n);

    int arr[n];
    int dp[n];

    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
        dp[i] = 1;
    }

    for (int i = 1; i < n; i++) {
        for (int j = 0; j < i; j++) {
            if (arr[j] <= arr[i]) {
                dp[i] = max(dp[i], dp[j] + 1);
            }
        }
    }

    int ans = dp[0];
    for (int i = 1; i < n; i++) {
        ans = max(ans, dp[i]);
    }

    printf("%d", ans);
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20163403.png)
# Competitive Programming

## 1. Finding Duplicates (O(n^2) Time, O(1) Space)

### Problem
Find duplicate in array.

Given a read-only array of `n` integers between `1` and `n`, find one number that repeats.

### Input Format
- The first line contains the number of elements.
- The next `n` lines contain the array elements.

### Output Format
- Print the repeated element `x`.

### Example
| Input | Result |
| :--- | :--- |
| 5<br>1 1 2 3 4 | 1 |

### C Program
```c
#include <stdio.h>

int main() {
    int n;
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    int slow = arr[0];
    int fast = arr[0];

    do {
        slow = arr[slow];
        fast = arr[arr[fast]];
    } while (slow != fast);

    slow = arr[0];
    while (slow != fast) {
        slow = arr[slow];
        fast = arr[fast];
    }

    printf("%d", slow);
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20204926.png)

## 2. Finding Duplicates (O(n) Time, O(1) Space)

### Problem
Find duplicate in array.

Given a read-only array of `n` integers between `1` and `n`, find one number that repeats.

### Input Format
- The first line contains the number of elements.
- The next `n` lines contain the array elements.

### Output Format
- Print the repeated element `x`.

### Example
| Input | Result |
| :--- | :--- |
| 5<br>1 1 2 3 4 | 1 |

### C Program
```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int n;
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    int slow = arr[0];
    int fast = arr[0];

    do {
        slow = arr[slow];
        fast = arr[arr[fast]];
    } while (slow != fast);

    slow = arr[0];
    while (slow != fast) {
        slow = arr[slow];
        fast = arr[fast];
    }

    printf("%d", slow);
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20204926.png)

## 3. Print Intersection of Two Sorted Arrays (O(m*n) Time, O(1) Space)

### Problem
Find the intersection of two sorted arrays.

In other words, given two sorted arrays, find all elements that occur in both arrays.

### Input Format
- The first line contains `T`, the number of test cases.
- For each test case:
  1. The first line contains `N1`, followed by `N1` integers of the first array.
  2. The second line contains `N2`, followed by `N2` integers of the second array.

### Output Format
- Print the intersection of the arrays in a single line.

### Example
Input:

```text
1
3 10 17 57
6 2 7 10 15 57 246
```

Output:

```text
10 57
```

Input:

```text
1
6 1 2 3 4 5 6
2 1 6
```

Output:

```text
1 6
```

### Example Table
| Input | Result |
| :--- | :--- |
| 1<br>3 10 17 57<br>6<br>2 7 10 15 57 246 | 10 57 |

### C Program
```c
#include <stdio.h>

int main() {
    int t;
    scanf("%d", &t);

    while (t--) {
        int n, m;
        scanf("%d", &n);

        int arr[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &arr[i]);
        }

        scanf("%d", &m);
        int brr[m];
        for (int i = 0; i < m; i++) {
            scanf("%d", &brr[i]);
        }

        int f = 1;
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (arr[i] == brr[j]) {
                    if (!f) {
                        printf(" ");
                    }
                    printf("%d", arr[i]);
                    f = 0;
                    break;
                }
            }
        }

        printf("\n");
    }

    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20205800.png)

## 4. Print Intersection of Two Sorted Arrays (O(m*n) Time, O(1) Space)

### Problem
Find the intersection of two sorted arrays.

In other words, given two sorted arrays, find all elements that occur in both arrays.

### Input Format
- The first line contains `T`, the number of test cases.
- For each test case:
  1. The first line contains `N1`, followed by `N1` integers of the first array.
  2. The second line contains `N2`, followed by `N2` integers of the second array.

### Output Format
- Print the intersection of the arrays in a single line.

### Example
Input:

```text
1
3 10 17 57
6 2 7 10 15 57 246
```

Output:

```text
10 57
```

Input:

```text
1
6 1 2 3 4 5 6
2 1 6
```

Output:

```text
1 6
```

### Example Table
| Input | Result |
| :--- | :--- |
| 1<br>3 10 17 57<br>6<br>2 7 10 15 57 246 | 10 57 |

### C Program
```c
#include <stdio.h>

int main() {
    int t;
    scanf("%d", &t);

    while (t--) {
        int n, m;
        scanf("%d", &n);

        int arr[n];
        for (int i = 0; i < n; i++) {
            scanf("%d", &arr[i]);
        }

        scanf("%d", &m);
        int brr[m];
        for (int i = 0; i < m; i++) {
            scanf("%d", &brr[i]);
        }

        int f = 1;
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (arr[i] == brr[j]) {
                    if (!f) {
                        printf(" ");
                    }
                    printf("%d", arr[i]);
                    f = 0;
                    break;
                }
            }
        }

        printf("\n");
    }

    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20205800.png)

## 5. Pair with Difference (O(n^2) Time, O(1) Space)

### Problem
Given an array `A` of sorted integers and another non-negative integer `k`, find whether there exist two indices `i` and `j` such that:

`A[j] - A[i] = k`, where `i != j`.

### Input Format
- The first line contains `n`, the number of elements in the array.
- The next `n` lines contain the array elements.
- The next line contains `k`, a non-negative integer.

### Output Format
- Print `1` if the pair exists.
- Print `0` if no pair exists.

### Explanation
YES, because `5 - 1 = 4`.

### Example
| Input | Result |
| :--- | :--- |
| 3<br>1 3 5<br>4 | 1 |

### C Program
```c
#include <stdio.h>

int main() {
    int n, t;
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    scanf("%d", &t);
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            if (arr[j] - arr[i] == t) {
                printf("1");
                return 0;
            }
        }
    }

    printf("0");
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20210047.png)

## 6. Pair with Difference (O(n^2) Time, O(1) Space)

### Problem
Given an array `A` of sorted integers and another non-negative integer `k`, find whether there exist two indices `i` and `j` such that:

`A[j] - A[i] = k`, where `i != j`.

### Input Format
- The first line contains `n`, the number of elements in the array.
- The next `n` lines contain the array elements.
- The next line contains `k`, a non-negative integer.

### Output Format
- Print `1` if the pair exists.
- Print `0` if no pair exists.

### Explanation
YES, because `5 - 1 = 4`.

### Example
| Input | Result |
| :--- | :--- |
| 3<br>1 3 5<br>4 | 1 |

### C Program
```c
#include <stdio.h>

int main() {
    int n, t;
    scanf("%d", &n);

    int arr[n];
    for (int i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }

    scanf("%d", &t);
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            if (arr[j] - arr[i] == t) {
                printf("1");
                return 0;
            }
        }
    }

    printf("0");
    return 0;
}
```

![output](https://github.com/Fathina-codes/DAA_Lab_Record/blob/main/result/Screenshot%202026-10-07%20210047.png)
