# 📘 Notes on Merge Sort

## 🔹 What is Merge Sort?

- **Merge Sort** is a **divide-and-conquer sorting algorithm**.
- It works by **splitting the array into smaller parts**, sorting each part, and then merging them back together.
- Unlike Bubble Sort, Selection Sort, or Insertion Sort, Merge Sort has better performance on large datasets.

---

## 🔹 Steps of Merge Sort

1. **Divide**
    - Split the array into two halves until each subarray contains only **1 element**.
    - A single element is already "sorted".
2. **Conquer (Sort subarrays)**
    - Recursively apply Merge Sort on the left half and the right half.
3. **Merge**
    - Combine two sorted halves into a single sorted array.
    - This merging is done by comparing elements one by one.

---

## 🔹 Example (Array: [5, 2, 8, 1])

1. Split into two halves → [5, 2] and [8, 1]
2. Split further → [5], [2], [8], [1]
3. Merge pairs:
    - [5] + [2] → [2, 5]
    - [8] + [1] → [1, 8]
4. Merge final:
    - [2, 5] + [1, 8] → [1, 2, 5, 8]

✅ Sorted array = [1, 2, 5, 8]

---

## 🔹 Pseudocode

```
mergeSort(arr, l, r):
    if l < r:
        m = (l + r) / 2
        mergeSort(arr, l, m)
        mergeSort(arr, m+1, r)
        merge(arr, l, m, r)

merge(arr, l, m, r):
    copy left half to temp array L[]
    copy right half to temp array R[]
    merge L[] and R[] back into arr[l...r]

```
---

## 🔹 Time Complexity

- **Best Case:** O(n log n)
- **Worst Case:** O(n log n)
- **Average Case:** O(n log n)  
    👉 Always efficient compared to Bubble, Selection, and Insertion Sort (O(n²)).

---

## 🔹 Space Complexity

- **O(n)** (extra space for temporary arrays during merge).
- Not in-place (needs additional memory).

---

## 🔹 Advantages

✅ Always runs in O(n log n).  
✅ Works well for large datasets.  
✅ Stable sort (does not change the relative order of equal elements).

---

## 🔹 Disadvantages

❌ Needs extra space (O(n)).  
❌ Slower than Insertion Sort for small datasets.  
❌ Not in-place (makes temporary arrays).

---

## 🔹 Implementation Languages

- ✅ Python (simple list handling).
- ✅ C++ (arrays with temporary subarrays).
- ✅ Java (arrays with `copyOfRange` or loops).

```embed
title: "CS50 Shorts - Merge Sort"
image: ""
description: "Enjoy the videos and music you love, upload original content, and share it all with friends, family, and the world on YouTube."
url: "https://youtu.be/Pr2Jf83_kG0"
favicon: ""
```

```embed
title: "Merge sort in 3 minutes"
image: ""
description: "Step by step instructions showing how to run merge sort.Code: https://github.com/msambol/dsa/blob/master/sort/merge_sort.py (different than video, I added th..."
url: "https://youtu.be/4VqmGXwpLqc"
favicon: ""
```

## 🐍 Python (simple arrays/lists)

```python
def merge(leftArr, rightArr, arr):
    leftSize = len(leftArr)
    rightSize = len(rightArr)
    i = l = r = 0
    while l < leftSize and r < rightSize:
        if leftArr[l] < rightArr[r]:
            arr[i] = leftArr[l]
            l += 1
        else:
            arr[i] = rightArr[r]
            r += 1
        i += 1
    while l < leftSize:
        arr[i] = leftArr[l]
        l += 1
        i += 1
    while r < rightSize:
        arr[i] = rightArr[r]
        r += 1
        i += 1
def mergeSort(arr):
    length = len(arr)
    if length <= 1:
        return
    middle = length // 2
    leftArr = arr[:middle]
    rightArr = arr[middle:]
    mergeSort(leftArr)
    mergeSort(rightArr)
    merge(leftArr, rightArr, arr)


# Driver Code
arr = [8, 3, 5, 6, 7, 3, 4, 1, 9]
mergeSort(arr)
print(*arr)

```

---

## 💻 C++ (without `vector`, using plain arrays)

```cpp
#include <iostream>
using namespace std;

void merge(int arr[], int left[], int right[], int leftSize, int rightSize) {
    int i = 0, l = 0, r = 0;
    while (l < leftSize && r < rightSize) {
        if (left[l] < right[r]) {
            arr[i++] = left[l++];
        } else {
            arr[i++] = right[r++];
        }
    }
    while (l < leftSize) {
        arr[i++] = left[l++];
    }
    while (r < rightSize) {
        arr[i++] = right[r++];
    }
}
void mergeSort(int arr[], int n) {
    if (n <= 1) return;
    int middle = n / 2;
    int* left = new int[middle];
    int* right = new int[n - middle];
    for (int i = 0; i < middle; i++) {
        left[i] = arr[i];
    }
    for (int i = middle; i < n; i++) {
        right[i - middle] = arr[i];
    }
    mergeSort(left, middle);
    mergeSort(right, n - middle);
    merge(arr, left, right, middle, n - middle);
    delete[] left;
    delete[] right;
}
int main() {
    int arr[] = {8, 3, 5, 6, 7, 3, 4, 1, 9};
    int n = sizeof(arr) / sizeof(arr[0]);
    mergeSort(arr, n);
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}

```

---

## ☕ Java (arrays, no extra libraries)

```java
public class SortMerge{
	public static void main(String args[]){
		int[] arr = {8,3,5,6,7,3,4,1,9};
		int n=arr.length;
		mergeSort(arr);
		for(int i=0;i<n;i++){
			System.out.print(arr[i]+" ");
		}
	}
	public static void mergeSort(int[] arr){
		int len=arr.length;
		if(len<=1){
			return;
		}
		int middle= len/2;
		int[] leftArr =new int[middle];
		int[] rightArr= new int[len-middle];
		int i=0;
		int j=0;
		for(;i<len;i++){
			if(i<middle){
				leftArr[i]=arr[i];
			}
			else{
				rightArr[j]=arr[i];
				j++;
			}
		}
		mergeSort(leftArr);
		mergeSort(rightArr);
		merge(leftArr, rightArr, arr);
	}

	private static void merge(int[] leftArr, int[] rightArr, int[] arr){
		int leftSize= arr.length/2;
		int rightSize=arr.length -leftSize;
		int i=0, l=0, r=0;
		while(l<leftSize && r<rightSize){
			if(leftArr[l]<rightArr[r]){
				arr[i]=leftArr[l];
				i++;
				l++;
			}
			else{
				arr[i]=rightArr[r];
				i++;
				r++;
			}
		}
		while(l<leftSize){
			arr[i]=leftArr[l];
			i++;
			l++;
		}
		while(r<rightSize){
			arr[i]=rightArr[r];
			i++;
			r++;
		}
	}
}
```