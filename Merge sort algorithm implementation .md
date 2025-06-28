# Merge Sort Algorithm Implementation

### By Reema F. Almukhlifi  
As part of the Data Structures & Algorithms course – Princess Nourah University

This project showcases the implementation of the **Merge Sort algorithm in Java**, focusing on the recursive divide-and-conquer strategy.  
It was developed to strengthen understanding of sorting complexities, algorithm efficiency, and performance benchmarking.

---

## Project Overview

The implementation follows a structured recursive approach:

* Divides the array into subarrays  
* Recursively sorts each half  
* Merges the sorted halves into a final sorted array  

The algorithm guarantees **O(n log n)** time complexity and **stability** in sorting, making it reliable for large datasets.

---

## Key Features

* Clean implementation of Merge Sort using recursion  
* Prints both original and sorted arrays  
* Can be tested on different input sizes  
* Includes sample performance testing setup and results  

---

## Sample Output

```bash
Original Array: [5, 3, 8, 4, 2]  
Sorted Array:   [2, 3, 4, 5, 8]
```
---

## Java Code

```public class MergeSort {

    // Merge two subarrays
    public static void merge(int[] arr, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;

        int[] leftArr = new int[n1];
        int[] rightArr = new int[n2];

        for (int i = 0; i < n1; i++)
            leftArr[i] = arr[left + i];
        for (int j = 0; j < n2; j++)
            rightArr[j] = arr[mid + 1 + j];

        int i = 0, j = 0;
        int k = left;
        while (i < n1 && j < n2) {
            if (leftArr[i] <= rightArr[j]) {
                arr[k] = leftArr[i];
                i++;
            } else {
                arr[k] = rightArr[j];
                j++;
            }
            k++;
        }

        while (i < n1) {
            arr[k] = leftArr[i];
            i++;
            k++;
        }

        while (j < n2) {
            arr[k] = rightArr[j];
            j++;
            k++;
        }
    }

    // Recursive sort
    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int mid = left + (right - left) / 2;

            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);

            merge(arr, left, mid, right);
        }
    }

    public static void main(String[] args) {
        int[] arr = { 5, 3, 8, 4, 2 };

        System.out.print("Original Array: ");
        for (int num : arr) System.out.print(num + " ");
        System.out.println();

        mergeSort(arr, 0, arr.length - 1);

        System.out.print("Sorted Array:   ");
        for (int num : arr) System.out.print(num + " ");
        System.out.println();
    }
}

```
---

## Performance Summary

The algorithm was tested with arrays ranging from **10 to 10,000 elements**.  
Performance comparisons were made against:

* **QuickSort** – Generally faster in average cases  
* **Insertion Sort** – More efficient on nearly-sorted data  

**Merge Sort** demonstrated:

* Stable and predictable behavior across all inputs  
* Time complexity of **O(n log n)** in the worst case  
* Higher memory usage, but reliable for large datasets  

---

## Technologies Used

* **Java** – Core implementation language  
* **JDK 17+** – Recommended for compatibility  
* **VS Code / IntelliJ** – For development and testing  

---

## GitHub Repository

[View the Repository](https://github.com/iRemaF/LinkedInProjects/blob/main/Merge%20Sort%20Algorithm.md)

---

## Contact

For questions or collaboration, feel free to reach out:

* **GitHub**: [github.com/iRemaF](https://github.com/iRemaF)  
* **LinkedIn**: [linkedin.com/in/your-profile](https://linkedin.com/in/your-profile)

---
