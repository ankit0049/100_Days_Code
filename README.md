# 100 Day's Problem with Solution 

> ### Day 1  
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

 ### Day 2  
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