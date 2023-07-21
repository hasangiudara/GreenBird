# Walkthrough of Binary Search in Java

Binary Search determines if a target value exists in a sorted array of n integers and if the target value is present in the array, it reports its index. The index starts with 0.

## Code explanation 

```
public static int binarySearch(int[] array, int target) {
        int left = 0;
        int right = array.length - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (array[mid] == target) {
                return mid;
            } else if (array[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }

        return -1; 
    }
```
The binarySearch method has two parameters. **int[] array**, is the sorted array that will be searched. **int target** is the value that we are looking for.

**int left** sets the left pointer to '0' and **int right** calculates the last index of the array.

Using the **while loop**, it runs until the array space until it is fully searched. The loop continues as long as the left pointer is less than or equal to the right pointer. 

**int mid** is created to calculate the middle value of the array. The array space is divided in half to locate the target element. While the loop runs until one of the conditions is met. 

Using the **if condition** it checks the three conditions. 
1. If the value at the middle index is equal to the target value, it returns an index of the middle value. 

2. If the value at the middle index is smaller than the target value it searches the right side. Then **if(array[mid] < target)** is executed. To search the right half of the array, the left pointer needs to be updated. So ***mid + 1***. This moves the left pointer one position to the right of the middle index, and then the left half of the array is discarded because all elements in the left half of the array are smaller than the **target**.

3. If the value at the middle index is bigger than the target value it searches the left side of the array. Then **else** is executed. To search the left half of the array, we need to update the right pointer to ***mid - 1***. This moves the right pointer one position to the left of the middle index and discards the right half of the array because all elements in the right half are greater than the **target**.

4. It will return -1 to indicate that the **target** is not in the array.


### Testing the Algorithm 

```
public static void main(String[] args) {
        int[] array = {7, 9, 14, 17, 20, 26, 30, 40};
        int target  = 17;

        int result = binarySearch(array, target);
        if (result != -1) {
            System.out.println("Element " + target + " found at index " + result);
        } else {
            System.out.println("Element " + target + " not found in the array.");
        }
    }
```
**int[] array**, is the array in ascending order.
**int target = 17**, 17 is the number we are looking for in the array. 

**binarySearch** is the method that was defined earlier. It performs the Binary Search to find the **target** in **array**. Here, variables **int [] array** & **int target** are passed.

**int result** is the name of the variable where we store the result of the binary search and contains the index where it is located in the array.

In the **if function** if the **result** is not equal to -1 it prints the index of the Element 17. If not it prints that Element is not found in the array.
