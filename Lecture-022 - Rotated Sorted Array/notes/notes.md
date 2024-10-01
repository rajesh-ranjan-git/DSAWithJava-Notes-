# Sorted Rotated Array

> Two types of Rotated Sorted Array ->

1. Clockwise Rotated Sorted Array
2. Anti-Clockwise Rotated Sorted Array

E.g. { 43, 2, 2, 4, 4, 5, 7, 11 }

1. Clockwise Rotation Count = index of minimum element in the array
2. Anti-Clockwise Rotation Count = array length - index of minimum element in the array.

> Formula - >

1. Clockwise Rotation Count = index of minimum element in the array
2. Anti-Clockwise Rotation Count = ( arr.length - index ) % arr.length

> Observation

In both types of sorted rotated array, there would following possibilities :

1. If right side to mid will be sorted then the left side will be unsorted.
2. If left side of mid element is sorted then right side will be unsorted.
3. Both sides are sorted and in this case the starting element will be minimum element.
4. Both sides will never be unsorted.

> Find the minimum element in sorted rotated array.

1. Start a loop which will continue till starting index is less than end element.
   Note -> We are not taking the equal condition as in this case the same element will be the minimum element which we will get from starting index directly.
2. Check if mid is greater than the starting index and mid element is less than its previous, then mid will point to the minimum element so break the loop.
3. If the above condition is false, then check which side is sorted.
4. If mid element is less than the end element, then right side is sorted so we have to check on the left side by modifying the end to mid - 1.
5. If the above condition is false then, left side is sorted so we have to move right by modifying start to mid + 1.
6. At the end of loop, the start element will point to the minimum element.

> > Handling edge cases.

1. If there are duplicates in the array, then change the condition for checking which side is sorted by checking mid element is less than and equal to end element (Step 4).
2. If the start and end are equal, we skip them to decrease the search space by increase 1 to start and decreasing 1 from end.

> Find the maximum element in sorted rotated array.

1. Start a loop which will continue till starting index is less than end element.
   Note -> We are not taking the equal condition as in this case the same element will be the maximum element which we will get from ending index directly.
2. Check if mid is less than the ending index and mid element is greater than its next, then mid will point to the maximum element so break the loop.
3. If the above condition is false, then check which side is sorted.
4. If mid element is less than the end element, then right side is sorted so we have to check on the left side by modifying the end to mid - 1.
5. If the above condition is false then, left side is sorted so we have to move right by modifying start to mid + 1.
6. At the end of loop, the end element will point to the minimum element.

> Find element in sorted rotated array.

1. Take a temp variable ans = -1 and start a loop which will continue till starting index is less than and equal to end element.
   Note -> We are taking the equal condition as in this case we do not have to check minimum or maximum case so we need to include all possibilities.
2. Check if mid is equal to target, if it is then break the loop and assign ans with mid.
3. If the above condition is false, then check which side is sorted.
4. Check if mid is less than the ending index, then right is sorted.
5. Check if target lies between mid and end, if yes then modify start to mid + 1 else modify end to mid - 1.
6. If step 4 condition is false then target lies on the right side.
7. Check if target ;lies between start mid, if yes then modify end to mid - 1 else modify start to mid + 1;
8. At the end of loop, ans will tell if the element was found in the array or not.
