# Bitonic Array

In Bitonic Array elements are first in increasing order then decreasing order or vice versa. Here the element are strictly sorted with no duplicate element on each side. Overall in the array duplicates can be there but on the opposite sides.
Eg. : int arr[] = { 2, 4, 6, 8, 11, 16, 13, 11, 9, 4, 3, 2, 1 };

Note -> It is also solved by Binary Search Algorithm.

> Find minimum element in a Bitonic Array.

1. Minimum element in a Bitonic Array will be minimum of first and last element in the array.

> Find peak element in a Bitonic Array.

Note -> Peak is also called Bitonic point, maximum element.
-> Peak element is always greater or equal to its adjacent elements.

1. Consider start and end elements as boundaries and perform below steps till start <= end.
2. Find previous and next element.
3. next = (mid+1)%arr.length - This is done so that if the element is last element, then next points to the first element in array to avoid ArrayIndexOutOfBounds Exception.
4. prev = (mid-1 + arr.length)%arr.length - This is done so that if the element is first element, then prev points to the last element in array to avoid ArrayIndexOutOfBounds Exception.
5. We have to keep in mind that there is one unique property for peak element in Bitonic arrays i.e. peak element is greater than its prev as well as the next one.
6. Check if mid is greater than both prev and next, if yes then this is the answer.
7. If not then check which is greater than mid, prev or next.
8. If prev is greater, then modify end to mid - 1.
9. Else, if next is greater, then modify start to mid + 1.
10. When the loop end, ans will have the peak element index.

> Find element in a Bitonic Array.

Note -> Since it is bitonic, it cannot be determined on which side the element will be present.

1. Find peak element index by using above algorithm.
2. Check if the peak element is the target, if it is then it is answer or else proceed to next steps.
3. Find element using Binary Search Ascending algorithm.
4. If the element is found, it is the answer.
5. If the element is not found, then apply Binary Search Descending Algorithm.
6. If found the element, it is answer or else the element is not present.
