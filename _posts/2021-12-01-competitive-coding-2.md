---

layout: single
title: "[Big-O] Calculating Time-Complexity and Space-Complexity of Algorithms"
tags: [big-o]
categories: algorithms

---

# Understanding Time-Complexity and Space-Complexity of Algorithms

## Calculating Time Complexity

#### Simplifying Complexity

1. Drop all lower terms
2. Drop all constant multipliers

ex) For the equation below...drop '2n+1' and 3.
$$
T(n)=3n^3 +2n+1
$$
After dropping terms, becomes:
$$
T(n)=n^3
$$
Thus, time complexity is: 
$$
O(n^3)
$$

#### Calculating Time Complexity of Algorithms

1. ###### **Single Loop (O(n))**

   ```c++
   for(i=0; i<=n; i++) { //runs n times
   	x=y+z; //constant time
   }
   ```

   - Inner code takes constant time to run, and the loop runs 'n' number of times.
   - Assuming constant time is c, the time complexity is O(c*n), which is simplified to **O(n)**.

   

2. ###### **Nested Loop (O(n^2))**

   ```c++
   for(i=0; i<=n; i++) { //n times
   	for(j=1; j<=n; j++) { //n times
   		x=y+z; //constant time
   	}
   }
   ```

   - Inner code takes constant time to run, and each loop runs 'n' number of times.
   - Assuming constant time is c, the time complexity is O(c*n*n), which is simplified to **O(n^2)**.

3. ###### Sequential Statements

   ```c++
   a = a + 2; //c1
   for(i=0; i<=n; i++) { //c2 * n
   	x=y+z; 
   }
   for(i=1; i<=n; i++) { 
   	x=y+z; //c3 * 
   }
   ```

   - If we have sequential statements, *add* their time complexities.
   - By adding, we get c1 + c2*n + c3*n = **O(n)**.

4. ###### If-else statements

   - Since we look for worst-case, just use the code that has the worse complexity.

   - ex)  Here, use time complexity is **O(n^2)**

     ```
     if (condition) {
     	...	//has complexity O(n)
     }
     else {
     	...	//has complexity O(n^2)
     }
     ```



#### Comparison of Time Complexities

- O(1) < O(log n) < O(n) < O(n log n) < O(n^c) < O(c^n) < O(n!)

![image-20211201031447333](/images/2021-12-01-competitive-coding-2/image-20211201031447333.png)

###### Time Complexities of Various Sorting Algorithms:

![image-20211201031655832](/images/2021-12-01-competitive-coding-2/image-20211201031655832.png)



## What is Space Complexity?

- Amount of space(or memory) taken by algorithm

###### Example

```c++
int a,b;
int z = a + b;
return z;
```

- Here, we have 3 integers declared.
  - Assuming each integers take 4 bytes, this program takes 4 * 3 + 4(for return statement)= 16 bytes, which is a **constant**.

## Notes

- Time Complexity and Space Complexity has a negative correlation.
  - If one decrease, the other decrease!

## References

https://www.youtube.com/watch?v=KXAbAa1mieU