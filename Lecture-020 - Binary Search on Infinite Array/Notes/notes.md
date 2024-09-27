# Binary Search

> Find minimum absolute difference of element in array.

=> What is absolute difference?
-> This difference does not consider signs. E.g. |10-6| and |6-10| both are |4|

-> We have to find target - arr[j] == value and this element should be minimum.

> > Easy approach

1. Use floor and ceil algorithm for binary search and get floor and ceil value.
2. Answer will be the minimum of Abs(target - floor) and Abs(target - ceil).
3. If floor does not exist then answer will be Abs(target - ceil).
4. If ceil does not exist then answer will be Abs(target - floor).

> > Efficient Approach.

1. Take a temp variable ans = -1.
2. Perform Binary Search operation on the array.
3. If the target is present in the array then answer will be Min.abs(target - arr[ans]) = 0.
4. If target does not exist, then check if end = -1 (went beyond start of array which means that the target value is smaller than the first element), then answer is Math.abs(target - arr[start]).
5. If above is not the case, then check if start = arr.length (went beyond end of array which means that the target value is greater than the last element), then answer is Math.abs(target - arr[end]).
6. If all cases fails that means that the element is within the range then take the minimum of Math.abs(target - arr[start]) i.e. ceiling value and Math.abs(target - arr[end]) i.e. floor value as the answer..
7. If the array is empty then Minimum Absolute Value is not possible.

> Find the target in an infinite length ascending sorted array (important for interview and will not be asked in online tests as this is hypothetical and we cannot provide and array in the program which has infinite length).

1. Take the first value as start and 2nd value as end.
2. Check if the number is greater than the 2nd element.
3. If it is then modify the end and increase it by multiple of 2 and change the start to the end.
4. Perform step 2 and 3 till the element is less than the element at end position.
5. Take the start and end as new range of array and apply binary search algorithm on that to get the element.

> Find first occurrence of 1 in binary infinite sorted array.

1. Use the above method to find the range.
2. With that range apply the first occurrence binary search algorithm.
