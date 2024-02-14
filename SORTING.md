BUBBLE SORT:
Bubble sort is a simple sorting algorithm that repeatedly steps through the list of items, compares adjacent items and swaps them if they are in the wrong order. 

Program of Bubble Sort in C++:

#include <iostream>
using namespace std;
void bubbleSort(int arr[], int n) {
    for (int i = 0; i < n-1; i++) {
        for (int j = 0; j < n-i-1; j++) {
            if (arr[j] > arr[j+1]) {
                swap(arr[j], arr[j+1]);
            }
        }
    }
}

int main() {
    int arr[] = {64, 34, 25, 12, 22, 11, 90};
    int n = sizeof(arr)/sizeof(arr[0]);
    bubbleSort(arr, n);
    cout << "Sorted array is: \n";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }
    return 0;
}



SELECTION SORT:
Selection sort is a simple comparison-based sorting algorithm. The algorithm iterates through the array multiple times, each time finding the smallest (or largest) element and swapping it with the element in the first unsorted position.

Program of Selection Sort in C++:

#include<iostream>
using namespace std;

void selectionSort(int arr[], int size){
for(int step = 0; step < size-1; step++){
     int min = step;
     for(int i = step+1 ; i < size ; i++) {
          if(arr[i] < arr[min])
           min = i;
           }
           swap(arr[step], arr[min]);
        }
      }

    int main()
    {
    int size = sizeof(data) / sizeof(data[0]);
    selectionSort(data, size);
    for(int i = 0; i<size; i++)
    cout<<data[i]<<" ";
    cout << endl;
    return 0;
    }


INSERTION SORT:
Insertion sort is a simple comparison-based sorting algorithm that builds a sorted array one item at a time. It starts by assuming that the first element of the array is already sorted, and then iteratively adds each of the remaining elements to the sorted portion of the array.

Program of insertion sort in C++ :

#include <iostream>
#include <vector>
using namespace std;

void insertionSort(vector<int>& arr) {
    for (int i = 1; i < arr.size(); i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}
int main() {
    vector<int> arr = {12, 11, 13, 5, 6};

    insertionSort(arr);

    for (int i = 0; i < arr.size(); i++) {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}


QUICK SORT:
QuickSort is a fast sorting algorithm that uses a divide-and-conquer strategy to sort an array. It works by selecting a pivot.

Program of quick sort in C++ :

#include <iostream>
#include <vector>
using namespace std;

void quickSort(vector<int>& arr, int left, int right) {
    if (left < right) {
        int pivotIndex = partition(arr, left, right);
        quickSort(arr, left, pivotIndex - 1);
        quickSort(arr, pivotIndex + 1, right);
    }
}

int partition(vector<int>& arr, int left, int right) {
    int pivot = arr[right];
    int i = left - 1;
    for (int j = left; j < right; j++) {
        if (arr[j] <= pivot) {
            i++;
            swap(arr[i], arr[j]);
        }
    }
    swap(arr[i + 1], arr[right]);
    return i + 1;
}

int main() {
    vector<int> arr = {12, 11, 13, 5, 6};

    quickSort(arr, 0, arr.size() - 1);

    for (int i = 0; i < arr.size(); i++) {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}

MERGE SORT:
MergeSort is a fast and efficient sorting algorithm that uses a divide-and-conquer strategy to sort an array. It works by dividing the array into smaller subarrays, sorting each subarray, and then merging the sorted subarrays back together.

Program of Merge sort in C++:

#include <iostream>
using namespace std;

void merge(int arr[], int l, int m, int r) {
    int n1 = m - l + 1;
    int n2 = r - m;

    int L[n1], R[n2];

    for (int i = 0; i < n1; i++)
        L[i] = arr[l + i];
    for (int j = 0; j < n2; j++)
        R[j] = arr[m + 1 + j];

    int i = 0;
    int j = 0;
    int k = l;

    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) {
            arr[k] = L[i];
            i++;
        } else {
            arr[k] = R[j];
            j++;
        }
        k++;
    }

    while (i < n1) {
        arr[k] = L[i];
        i++;
        k++;
    }

    while (j < n2) {
        arr[k] = R[j];
        j++;
        k++;
    }
}

void mergeSort(int arr[], int l, int r) {
    if (l >= r)
        return;

    int m = l + (r - l) / 2;
    mergeSort(arr, l, m);
    mergeSort(arr, m + 1, r);
    merge(arr, l, m, r);
}

int main() {
    int arr[] = {12, 11, 13, 5, 6, 7};
    int n = sizeof(arr) / sizeof(arr[0]);

    mergeSort(arr, 0, n - 1);

    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    cout << endl;

    return 0;
}


