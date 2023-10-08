# 100 Day's Problem with Solution  
> Total Day = 6 , Total Problem Solved = 12

> ## Day 1  
>  #### Maximum SubArray Product  

  Approach 1 : iterate 3 loop i , j & k product = product * k then taking max  o(n^3)

  Approach 2 : Remove the extra loop k just do Product *=j . o(n^2)

  Approach 3: 
   * if Array have all Positive then the product of all element is the Answer 
   *  if Array Have Even Negative then that part also is Possible answer 
   * if Array Have Odd Negative then we carry Suffix product or Prefix Product then take Max of both 
   * if Array Have 0 then we not take it that because 0 makes whole Product is 0 
    
    Approach 3 Takes o(n) .
   ----
   ____

 ## Day 2  
 > #### Count Inversions  in Array 
 Approach 1: basic Approach is we Select the one and iterate on whole Array and left is greater right then count going to be +1  

 Approach 2 : this Approach is Basically Based on the Merge Sort Useally we sort using the comparision and then merge if we compared our left part with the right part then if our left lowest value is greter then right so count is going to be plus equal the length of the left part 

 >          [1 9  3 5 10] 
             /          \
         [1 9 3]       [ 5 ,10]
         /    \          /  \
        [1 9]  [3]      [5]  [10]
        /    \
        [1]  [9]  


        [1 , 9 , 3 ,5 ,10]
            /           \
         [1 9 3]       [ 5 ,10]
         /    \          /  \
        [1 9]  [3]      [5]  [10]
        /    \
        [1]  [9]  // this going to be combine . if 1 > 9 then count is increse by left part length but its not true   so count remain same.

        likewise we combine likw our calls happens and we check if the left part lowest value is greter then the right part increse by length of left[mid-cnt+1] if the left lowest is smaller then we increre the count and then check (increse the count means we check using Next index value because our Array part is sorted Now) 

        [1 , 9]   [ 3]  here 1 > 3 false so we increse the count and now our counter point to 9 ( value) then check 9>3 increse the count and merge [1 ,3 ,9]  likewise all calls Happens  
-----
----
  ## Day3
> #### Missing & Repeating Number   

Approach 1 : iterate the outer loop = n and in inner loop check the inner loop of i == outer loop value then counter increse to one if counter is 2 then return repeating value and if the counter is zero then return missing value  

        Approach 2 : Using Hashing or Hashmap we add all Values in the HashMap and the iterate on the Hash array or HashMap and check the repeated value and check 1 to n which in not in Hash Array or Hashmap return in Missing that Value


        Approach 3 : Using the Math 
           Sn = (N*(N+1))/2  sum of the natural number  
           then we calculate the Sum of the Array Element S - sn = (X & Y) (Equation 1)we get the combination(sum) of Missing and Repeating Value   


           S2n = (N*(N+1)*(2N+1))/6  sum of the Squares of the Natural Number  

           then we calculate the sum of the Squares S2 of the Array Element then we get (X & Y again )(Equation 2) 
           we solve the Equation and get X and Y means Missing and repeating value  

           X+Y = (S2 - S2n) / (X-Y) [From equation 1, we get the value X-Y] equate and get value  . 
> 

------
----
## Day 4 
> #### Q-1 Maximum SubArraySum 
Approach 1: iterate  i=n j=i (j<n) & k=j k(<n) array and sum += k and take max of all like max = Math.max(max,sum) then we get but it take O(n^3) complexity 

Approach 2 : iterate i=n & (j=i ,j<n) sum+=j and take the max as previous this takes O(n^2) Complexity 

Approach 3 : Optimal Approach Using Kadans Algoritham  we itearte one loop and take one sum =0 then we sum+=arr[i] and take maximum of (max,sum) and store in max and the next step we check our taken sum is <0 then sum makes to 0 sum=0  at the last max contain maximum sum   

> #### Q-2   Sort 0 ,1's & 2's (without Sorting) 
Approach 1 : brute force Approach is we just take 3 counter varible for count 0 ,1 & 2's then iterate loop for everone until count is not zero and stored in the array so we get [0,0,0,1,1,1,2,2,2] like this 

Approach 2 : National Dutch Man Flag ALoritham  
in this method we have 3 pointer low mid and high  to begin with low=0 , mid=0  high = n-1  we have 3 checks  
1. arr[mid]==0 => then we do swap (low++,mid++) and increse by one both  

2. arr[mid]==2 => then we have swap(mid ,high--) here we decre the high only 

3. arr[mid]==1 so this is right position so we increse mid+1  

---- 
---- 
## Day 5 
> #### Q-1 Print All Sum  
In this We Use the Pick & Not Pick Case & Genrate tha All Possible Case & Print th sum   
* We print  sum before the   calling and then at
  the time of backtraking we print sum so 
  all possible sum print 

> #### Q-2 Combination Sum - 1    
* We can Use one Element only once  
  we have Given  array = [2,3,6,7], target = 7 ,
Output: [[2,2,3],[7]] this Question Approach As Previous we Used in Q-1 here only we have Apply one check that is sum +arr[i]<= target then take it  in array that element 
 and at the time of returning that array keep in array of array .
 here at the time of Backtracking we pop out the last index of array so we can make not pick case or check all Possible  

> #### Q-3 Combination Sum - 2   
 Combination Sum 2 State that Print All Possible Sum that makes target but it should be Unique means [1,1,6]=8  [1,6,1] =8 so we consider only one  in Combination sum-1 it Consider 2 Solution  
 but here we have to find Unique one 
   

   Approach 1 :
 This going to be Same Approach as Used Combination Sum - 1 here at the time of returing we sort the Array and stored into set then  its give Unique Combinations   
  
  this Approach Takes extra time complexity  

  Approach 2 :  
  [1 ,1,1 ,2] (0 -> 2 index all are one if i am take 0th ind and make Combination or Start with 1th ind No Change or 2nd No Change So we have to skip if the iterateble i > ind & arr[i]=arr[i-1] same value so we doing continue we dont need to  manage recursion case because our i is iterate less then arr.length so we dont need to manage it) 
  and one check if(arr[i]>target)loop break;  
  in under loop
  ds.add(i)
  call for next 
  ds.remove(i) => here i represent the arr element at the backTracing time we remove the last one
> #### Q-4 Subset Sum - 1  
   Subset Sum-1 is Same as Previous Approach we have to print all Subset sum so we use the take or not take case and genrate the all subset sum 
   and we Use our virtual sum (means we pass sum in the call like sum+arr[i] so our actual sum not affected) at the time of backtracking we have to just increse the index dont need to update the sum beacause sum not updated for those sum only update for called index
> #### Q-5 Subset Sum - 2  

Subset Sum-2 is Totally depend on Subset sum-1 
here inly we Use the Conatiner for Carrying that element in Previous we find sum so dont need to container to track which element make that sum but here we track element which Subset makes that target Sum 


___ 
___
 
## Day 6 
> #### Q-1 : nth Fibbonacci Number(Using DP) 
The Fibonacci sequence is a series of numbers where each number is the sum of the two preceding ones.
Example we want 5th fibbonacci then we have to need the calculate the sum of  3rd & 4th 
then for 3rd we have need to 1st & 2nd and for the 4rth we have to find 3rd & 2nd the Problem again Occur so we use DP (its Use for the Solving The Overlaping Problem)  
 
> memoization  
```java   

if(dp[ind]!=-1) return dp[ind]
return dp[ind]=fib(ind-1)+fib(ind-2);
 
```
> Tabulation  
``` 
int dp[] = new int[n]; 
dp[0]=0 & dp[1]=1 
for(2 to n)
dp[i]=dp[i-1]+[dp-2]; 

return dp[n]; 

```
> #### Q-2 Climbing Stairs  
we have to reach nth Stairs and tell total possile ways to reach out at nth . we can move 1 stair or 2 at a time. 
this Question Approach is Going to same as the Fibbonaci one . 
Base Case at 0th & 1st take 1 total ways to  reach at nth stair . and follow the fibbonaci tabulation.
we can Space Optimization Also Using The Varibles be Store the Previous and the Last Previous and calculate .  

---- 
----

## Day 7
> #### Rotate Matrix 90deg 
Approach:

Step 1: Transpose the matrix. (transposing means changing columns to rows and rows to columns)
 
 #### Step 2: Reverse each row of the matrix.  
----
----



## Day 8  
> #### Q-1 Next Greater Element in Circular Array  
[1,9,2,8,1,2,11] => [9,11,8,11,11,11,-1] 
this is the Next Greater elemnt Array 

Here We use Stack and start to iterate from the at the end and check arr[i]>st.peek() => push into stack & NGE array Also arr[i]<st.peek() => pop()
until this condition is going to failed for the circular one we iterate 1 to 2*n-1 and take it (i % length of real one (n)) 

Time Coplexity O(2n + 2n) => O(n)
Space Complexity O(n) 

> #### Q-2 Preorder  & Postorder & Inorder Traversal  
For Preorder we have to Remember  

* PreOrder => Root -> left -> right  
* PostOrder => left->right->Root  
* InOrder  => left-> Root -> right 

 this order we have to call 
root is always print and other one is going to call 
like 
Traversal(root.left) & (root.right) 
the stop condtion is root==null so return 


# Day -9
#### Revision the All Previous Concepts 

---- 
----
# Day -10
> #### Q-1 Rain Water Trapping Problem
In this Problem we have Given One Array Numbers That behave like block and you have to tell the 
maximum Trapped water into Block .

> Approach 1 : Left Array: For each block, we find the maximum block height on its left side.

Example: If the blocks have heights [1, 4, 2, 6, 1], the left array would be [1, 4, 4, 6, 6].

Right Array: For each block, we find the maximum block height on its right side.

Example: Using the same heights [1, 4, 2, 6, 1], the right array would be [6, 6, 6, 6, 1].

Minimum of Left and Right: We then find the minimum height between the left and right arrays. This represents the maximum height of water the block can hold.

Example: If we have [1, 4, 4, 6, 1], this means the water level is at most 4 units high.

Check if Water Can Be Trapped: We compare the minimum height with the actual block height. If the block height is equal to or greater than the water level, it means there's no water trapped (height - water level is 0).

Example: For the blocks [1, 4, 4, 6, 1], only the middle two blocks can trap water. The trapped water amounts to min[i] - arr[i].

So, in this example, we have 4 - 4 = 0 units of water trapped. 


> Approach 2:  
This i sgoing to be Same but Here We not use any extra Space we work on Pointers and takel that left & right array Usage .

here we take left=0 & right=n-1 pointers and take the leftMax=0 & rightMax=0 intial and take Counter=0 
for the traping water the condition are following :
* left < right   
      1 . we check left[i]<=right[i]  if true    

          1.1  then we check left[i]>=leftMax if true so we update our leftMax=left[i]
          means we get maximum height Block
          1.2 else part we update counter = leftMax-left[i] this going to tell the trapped water count  
           

           left++


    2. left[i]>right[i] 
          
           2.1  we check right[i]>=rightMax so we Update our rightMax because we get the maximum piller that conatin more water 

           2.2 else we increse the count = rightMax-right[i]  

           right--

> #### Q-2 Maximum Depth In Tree 
we Have 2 Approaches Using levelOrder & Using Recursion in this I solved Recursive Approach 
.we Pass root if root become null we return 0 ; then call for left(root.left) then call for right(root.right) and take the max(left,right)+1 return 

         



----
---
> # Day-11 
> #### Q-1 Ninja's Training [DP]
The Problem state that ninja's have n*3 Matrix there three task ninjas's can perform anyone at sigle day. he can't do same task in next day so You have to find the maximum value get By Performing take ninja's can , earn.
 
 > Why Greedy Not Work 

{ [10 , 40, 60] ,[100 , 10 , 190] }  
according to Greedy we Take for every array max 
so in day-1 we take 60 (Q.state you not perform same task at next day) we cant able to chose 190 so max is 100 so total is 160 but here the Maximum is 230 (perform 1st -40 then 2nd -> 190) all condition fullfill & this is the max

> When Greedy Fails We have to Check All Possible Combination 
For checking the all possible combination Recursion comes and then for reducing the overlapping we use Dp here. 


here we check all posible and Use day for perform task and one last varible that helps to tell this task done previous so we not take that and then return the maximum 

``` 
 3 Important Rules for Applying Dp or Recusion 

 1. if Your Question is not index Based So canged into indexing  
 2.  Do all Possible Stuffs on That Index.
 3. Perfom The task that Question States

``` 
here we take our Day As Index . 

>  Q.2 Next Permutation

Find the break-point, i: Break-point means the first index i from the back of the given array where arr[i] becomes smaller than arr[i+1].
For example, if the given array is {2,1,5,4,3,0,0}, the break-point will be index 1(0-based indexing). Here from the back of the array, index 1 is the first index where arr[1] i.e. 1 is smaller than arr[i+1] i.e. 5.
To find the break-point, using a loop we will traverse the array backward and store the index i where arr[i] is less than the value at index (i+1) i.e. arr[i+1].
If such a break-point does not exist i.e. if the array is sorted in decreasing order, the given permutation is the last one in the sorted order of all possible permutations. So, the next permutation must be the first i.e. the permutation in increasing order.
So, in this case, we will reverse the whole array and will return it as our answer.
If a break-point exists:
Find the smallest number i.e. > arr[i] and in the right half of index i(i.e. from index i+1 to n-1) and swap it with arr[i].
Reverse the entire right half(i.e. from index i+1 to n-1) of index i. And finally, return the array.


    

            





