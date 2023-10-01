# 100 Day's Problem with Solution 

> ## Day 1  
> Maximum SubArray Product  

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
 > Count Inversions  in Array 
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
        ### Day3
        > Missing & Repeating Number
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


