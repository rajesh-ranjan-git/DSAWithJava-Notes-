# Binary Search

1. This is efficient than linear search.
2. It is performed only on sorted arrays, either ascending or descending.
3. It is called Order Agnostic Binary Search where array is sorted but order (ascending or descending) is not known.

> Approach for Ascending array ->

1. Assign a variable ans = -1.
2. Find mid = (start + end) / 2
   -> It may lead to overflow condition sometimes so to avoid it we user a different formula.
   mid = start + ((end - start) / 2)

3. Check if the mid element is target or not.
   -> If it is then the element is the answer (ans = mid).
   -> If it is not then check if the element is less than or greater than the mid element.
   -> If it is greater, then we discard the previous half by modifying start and mid.
   => start = mid + 1
   => mid = start + ((end - start) / 2)
   -> If it is smaller, then we discard the next half by modifying end and mid.
   => end = mid - 1
   => mid = start + ((end - start) / 2)
   -> Perform the same operation till start <= end.

4. If at the end ans == -1, then the element was not present.

> Approach for Descending array ->

1. Assign a variable ans = -1.
2. Find mid = (start + end) / 2
   -> It may lead to overflow condition sometimes so to avoid it we user a different formula.
   mid = start + ((end - start) / 2)

3. Check if the mid element is target or not.
   -> If it is then the element is the answer (ans = mid).
   -> If it is not then check if the element is less than or greater than the mid element.
   -> If it is greater, then we discard the next half by modifying end and mid.
   => end = mid - 1
   => mid = start + ((end - start) / 2)
   -> If it is smaller, then we discard the previous half by modifying start and mid.
   => start = mid + 1
   => mid = start + ((end - start) / 2)
   -> Perform the same operation till start <= end.

4. If at the end ans == -1, then the element was not present.
