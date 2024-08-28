1. **Bubble Algorithm:**
   - **Core Thinking: **Take sort from smallest to biggest as an example, pairwise comparison between two adjacent numbers from left to right, thus get the largest number at the rightmost at each round, run n rounds like this then get the sort.
   - Java Codes:
```java
public void bubbleSort(int[] nums){
    for(int i=1;i<nums.length;i++){
        for(int j=0;j<nums.length-i;j++){
            if(nums[j]>nums[j+1]){
                int temp=nums[j];
                nums[j]=nums[j+1];
                nums[j+1]=temp;
            }
        }
    }
}
```

2. **Selection Algorithm:**
   - **Core Thinking:** Assuming the first number is the minimum number, then log its index to a variable "min", and compare this number with other numbers one by one, if there is a number smaller than the assumed minimum number, change the variable "min" to this index of the number, and go on comparing this new minimum number with the remaining numbers, thus get the index of the minimum number of all. If the index has been changed, exchange the first number and the number with the minimum number. Then deal with the second number and others just like this.
   - Java Codes:
```java
public void selectionSort(int[] nums){
    int min;//the index of the minimum number
    for(int i=0;i<nums.length-1;i++){
        min=i;
        for(int j=i+1;j<nums.length;j++){
            if(nums[min]>nums[j])min=j;
        }
        if(min!=i){//determinate if the index has been changed
            int temp=nums[i];
            nums[i]=nums[min];
            nums[min]=temp;
        }
    }
}
```

3. **Insertion Algorithm:**
   - **Core Thinking: **Divide the array into two parts, the first part is the orderly array, and the other part is an unorderly array. Select a number from the unorderly array to compare with the numbers in the orderly array one by one, if the number is bigger than the selected number, move it behind, until finding a smaller number, then insert the number here.
   - the GIF of the demonstration:![insertionSort.gif](https://cdn.nlark.com/yuque/0/2024/gif/47471281/1724138174482-f6ae3db7-8ab4-4d3b-8645-1918d263191e.gif#averageHue=%23ececec&clientId=u7eba3fdd-0874-4&from=drop&id=u1cdfe25a&originHeight=505&originWidth=811&originalType=binary&ratio=2&rotation=0&showTitle=false&size=368273&status=done&style=none&taskId=u9cb77d00-5098-40d2-aa18-ad15c1c2c75&title=)
   - **For an array, the cost is as much as the bubble algorithm, since it always has to move positions one by one. So for a list, the cost will be super low, since there's no need to move the positions of all the numbers when doing an insertion. Because at the insertion position, we just need to designate the next of the prior node to the inserted node; and designate the next of the inserted node to the after node.**
4. **Quick Algorithm:**
   - **Core Thinking: **
      1. assume a number of an array to be the pivot;
      2. Compare the pivot with other numbers one by one, set the numbers smaller than the pivot aside, and set other numbers to another side, which is named "partition".
      3. Recursively do this to both sides until only one number remains.
   - **Java Codes:**
```java
public int[] sort(int[] sourceArrArray){
    int[] arr = Arrays.copyOf(sourceArray, sourceArray.length);
    return quickSort(arr, 0, arr.length);
}
public int[] quickSort(int[] arr, int left, int right){
    if(left<right){
        int partitionPivot = partition(arr,left,right);
        quickSort(arr,left,partitionPivot-1);
        quickSort(arr,partitionPivot+1,right);
    }
    return arr;
}
public int[] partition(int[] arr, int left, int right){
    int pivot=left;
    int index=pivot+1;
    for(int i = index+1; i<=right; i++){
        if(arr[i]<arr[pivot]){
            swap(arr, i, index);
            index++
        }
    }
    swap(arr,pivot,index);
    return arr;
}
public void swap(int[] arr， int i, int j){
    int temp=arr[i];
    arr[i]=arr[j];
    arr[j]=temp;
}
```

1. Heap Algorithm:
2. Hill Algorithm:
3. Reduction Algorithm:
4. Bucket Algorithm:
5. Counting Algorithm:
6. Basic Algorithm:
