Array rotation
In this Article we’ll be learning about program for array rotation of elements of array – left and right to a specified number of times. An array is said to be right rotated if all the selected elements were  moved towards right by one position.

Array Rotation In C
Method Discussed :
Method 1 : Using Temporary array.
Method 2 : Rotate one by one.
Method 1 :
In this method we will declare an extra array to store some k elements. Here, k refers to number of rotations.

Declare a temporary array of size k.
Store the first k elements in temp[] array.
Now, shift the remaining elements.
After, shifting the elements add the elements of temp[] in the array.
Array Rotation In C
DSA desktop gif
Related Pages
Introduction to 2-D Arrays

Reverse an array or string

Find pairs in array with given sum

Sort the array in Waveform

Majority Element in Array

Method 1 : Code in C
Run
//Write a program for array rotation in C
#include<stdio.h>
 
/* Driver program to test above functions */
int main()
{
    int arr[] = { 10, 20, 30, 40, 50, 60, 70};
    int n = sizeof(arr)/sizeof(arr[0]);
    int k = 3;
    
    int temp[k];
    for(int i=0; i<k; i++)
      temp[i] = arr[i];
    
    int x = k;
    for(int i=0; x < n; i++){
        arr[i] = arr[x++];
    }
    x = 0;
    
    for(int i=n-k; i<n; i++)
       arr[i] = temp[x++];
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);

    return 0;
}
Output
40 50 60 70 10 20 30
Method 2 :
In this method, we will rotate the elements one by one by shifting them.

Method 2 : Code in C
Run
//Write a program for array rotation in C
#include<stdio.h>
 
void leftRotatebyOne(int arr[], int n)
{
    int temp = arr[0], i;
    for (i = 0; i < n - 1; i++)
        arr[i] = arr[i + 1];
    arr[n-1] = temp;
}

void leftRotate(int arr[], int k, int n)
{
    for (int i = 0; i < k; i++)
        leftRotatebyOne(arr, n);
}
 
/* Driver program to test above functions */
int main()
{
    int arr[] = { 10, 20, 30, 40, 50, 60, 70};
    int n = sizeof(arr)/sizeof(arr[0]);
    
    leftRotate(arr, 3, n);
    
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);

    return 0;
}
Output
40 50 60 70 10 20 30
