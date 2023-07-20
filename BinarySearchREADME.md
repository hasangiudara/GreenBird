##Walkthrough of Binary Search in Java

Binary Search determine if a target value exists in a sorted array of n integers and if target is present in the array, it reports its index. Index starts with 0.

Code explanation 

```
public static int binarySearch(int[] array1, int target) {
        int left = 0;
        int right = array1.length - 1;

        while (left <= right) {
            int mid = left + (right - left) / 2;

            if (array1[mid] == target) {
                return mid;
            } else if (array1[mid] < target) {
                left = mid + 1;
            } else {
                right = mid - 1;
            }
        }

        return -1; 
    }
```
The method has two parameters. **int[] array1**, is the sorted array which will be search. **int target** is number that we are looking for.

**int left** sets the left pointer to '0' (first index) and **int right** calculates the last index of the array.

Using the **while loop**, it runs until the array space is fully searched. The loop continues as long as the left pointer is less than or equal to the right pointer. 

**int mid** is created to calculate middle value of the array. The array space is divided in half to locate the target element. While loop runs until one of the conditions is met. 

Using the **if condition** it checks the three conditions. 
1. If the array's middle value is equal to the target value, it returns index of the middle value. 

2. If the middle value is smaller than the target value it searches the right side and to search the right half of the array, the left pointer needs to be updated. So ***mid + 1***. This moves the left pointer one position to the right of the middle index, then the left half of the array is discarded. 

3. If the middle value is bigger than the target value it searches the left side and to search the left half of the array, we need to update the right pointer to ***mid - 1***. This moves the right pointer one position to the left of the middle index, and discardes the right half of the array. 

4. It will return -1 to indicate that the **target** is not present in the array.


##Testing the Algorithm 

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
In main method passes one parameter; an array of strings called **args**, which passes command-line arguments to the Java program.

**int[] array** = is the array in the ascending order.
**int target = 17** 17 is the number we are looking for in the array. 

**binarySearch** is method which was defined earlier. It performs the Binary Search to find the **target** in **array**. In here, variables **int [] array** & **int target** are passed.

**int result** is the name of the variable where we store the result of the binary search and contains the index where it is located in the array.

In the **if function** if the **result** is not equal to -1 it prints the index of the Element 17. If not it prints that Element is not found in the array.


