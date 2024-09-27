# Binary Search

> Find first/last occurrence of an element in a sorted array.

1. Perform agnostic search to determine whether array is sorted in ascending order or descending order.
2. Initialize a temp variable ans = -1.
3. If array is sorted in ascending order then perform Binary Search for ascending order.
4. When checking condition of element -> arr[mid] == target, consider mid as potential answer.
5. If we need first occurrence then change the end index -> end = mid - 1.
6. If we need last occurrence then change the start index -> start = mid + 1.
7. Continue the loop as till start <= end.
8. The resultant ans will the first occurrence.
9. If the array is sorted in descending order then perform Binary Search for descending order.
10. Perform the exact same steps as step 4 and 5.
11. The resultant ans will the first occurrence.
12. In any case if ans is -1, then the element is not present.

> Find the floor/ceil value of an element if the element is not present in array.

1. Perform agnostic search to determine whether array is sorted in ascending order or descending order.
2. Initialize a temp variable ans = -1.
3. If array is sorted in ascending order then perform Binary Search for ascending order.
4. When checking condition of element -> arr[mid] == target, if the element is found then break the loop.
5. If the element is not found and if we need floor value then consider the else case as potential answer.
6. If the element is not found and if we need ceil value then consider arr[mid] > target as potential answer.
7. Continue the loop as till start <= end.
8. The resultant ans will the floor value of the target.
9. If the array is sorted in descending order then perform Binary Search for descending order.
10. Perform the exact same steps as step 4 and 5.
11. The resultant ans will the floor value of the target.
12. In any case if ans is -1, then the element is not present.
