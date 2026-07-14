class Solution {
   // Function to count inversions in the array.
   public int inversionCount(int[] arr) {
       int n = arr.length;
       return mergeSort(arr, 0, n - 1);
   }


   private int mergeSort(int[] arr, int low, int high) {
       int count = 0;
       if (low < high) {
           int mid = (low + high) / 2;
           count += mergeSort(arr, low, mid);
           count += mergeSort(arr, mid + 1, high);
           count += merge(arr, low, mid, high);
       }
       return count;
   }


   private int merge(int[] arr, int low, int mid, int high) {
       int n1 = mid - low + 1;
       int n2 = high - mid;


       int[] left = new int[n1];
       int[] right = new int[n2];


       for (int i = 0; i < n1; i++) {
           left[i] = arr[low + i];
       }
       for (int i = 0; i < n2; i++) {
           right[i] = arr[mid + 1 + i];
       }


       int i = 0, j = 0, k = low, count = 0;


       while (i < n1 && j < n2) {
           if (left[i] <= right[j]) {
               arr[k++] = left[i++];
           } else {
               arr[k++] = right[j++];
               count += (n1 - i); // Count inversions
           }
       }


       while (i < n1) {
           arr[k++] = left[i++];
       }


       while (j < n2) {
           arr[k++] = right[j++];
       }
       return count;
   }
}



