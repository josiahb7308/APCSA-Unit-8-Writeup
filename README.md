# Process Writeup

## Name: Josiah Benitez
## Course: Unit 8 Writeup
## Period: 7
## Concept: 2-d Arrays

### Overview

Unit 8 is all about 2-d arrays, 2-d arrays organize data in rows and columns, effectively making code more concise and giving more ways to use arrays to hold important data. This unit was pretty challenging for me to understand in the beginning but it got easier over time.
## First Challenge
### Swapping rows in a 2-d array

On question 4 of the Unit 8 exam the question asked which pieces of code would be able to swap the first and second rows in a 2-d array and I messed by picking this code:

```java
for (int k = 0; k < a[0].length; k++) 
{
  int second = 1;
  a[0][k] = a[second][k];
  a[second][k] = a[0][k];
}
```
 
The issue with this code is that the value of a[0][k] gets lost because if you look at the code there is no temporary variable that it gets saved to before its changed. The value of the first row needs to be saved so it can be put in for the second row. The code that successfully does this is:

```java
for (int k = 0; k < a[0].length; k++) 
{
  int second = 1;
  int temp = a[0][k]; 
  a[0][k] = a[second][k];
  a[second][k] = temp;
}
```

This code saves a[0][k] as temp before changing it so it can be put into the second row. This one change determines whether the code works or doesnt and I missed on that.


## Second Challenge
### Columns and Rows Mixup

Question 11 on the exam gives us a code snippet and asks what it does. This is the code:

```java
int[][] a = /* initialization not shown */;
int j = 3;
for (int i = 0; i < a[0].length; i++)
{
  int temp = a[j + 1][i];
  a[j + 1][i] = a[j][i];
  a[j][i] = temp;
} 
```
I picked an answer that says that it swaps columns with index 3 and 4 but the real answer was that it swapped the rows with index 3 and 4. This one was very annoying to get wrong because I knew the right answer but just was too confident because I felt like I had it in the bad and ended up being reckless. Since the first index was being accessed it is for the rows and also it iterates among columns not the rows. 

## Third Challenge 
### Calculating amount of cells in an array

The questions gives us a question which asks us to calculate how many cells are in the array. I picked the answer with this code:

```java
grid[0].length * grid[grid.length - 1].length
```
 This code would be rught if the number of rows is equal to the number of columns but if at any time the number of rows is different it would result in the wrong answer. This answer was the closest to the right answer but I didnt take in to account that if the rows and columns werent equal the code would be faulty. The correct code goes like this:

 ```java
grid.length * grid[grid.length - 1].length
```

This code ensures that even with varying numbers of columns and rows it can still calculate how many cells are in the array. 

### Takeaways

* Even when confident make sure to double check your answers and slow it down a bit so you can comfirm your points.
* Review the beginning of the units before the test because those are normally the things least fresh in your memory so you can refresh on them.
* Put more time towards questions that require more reading of code so you are less likely to skim over important code and end up losing a chance on points you could have got.
* In the 2-d arrays section for example I had to make sure my fundamentals on normal arrays were on point so I could build on them and learn the new skill that adds on.
