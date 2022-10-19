---
layout: post
title:  "Calculating the Floor using Binary Search."
categories: [ Coding, Problem-Solving ]
image: assets/images/post_assets/programming.jpg
---


䷢ **Can you to write code to find the floor of a target element from an array?** 
 
 Note: &nbsp; &nbsp;<sub> Floor of a target = Biggest number which is smaller than or equal to the target.</sub>

 How would you do it? \
 Can you do it in O(logn) time and constant space?




 <!-- Add some explanation and description here. -->


<!-- Code snippet starts here. -->


Naively, We can iterate through the entire and record the element that is less than or equal to the current element. Right?  
 
\- Almost Right. 
 
But the this approach is a bit time consuming because it's a linear time solution.  

Remember having the sorted array? What's the benefit of having a sorted array? Yes, some possibility for **binary search**.
 

Let's see how one can apply binary search to solve it. 
 

Here is one approach using **BINARY SEARCH**.
 
~~~java
    public static int floor(int[] arr, int target){

        if(arr.length == 0 || arr[0] > target) 
            return -1;

        int start = 0, 
            end = arr.length -1, 
            result = -1;
        
        while(start <= end){
            
            int mid = (start + end) /2;

            if(arr[mid] == target){
                result = target;
                break;
            }
            if(arr[mid] < target){
                result = Math.max(arr[mid], result);
                start = mid + 1;
            }
            if(arr[mid] > target){
                end = mid -1;
            }
        }

        return result;
    }
~~~


Time Complexity: **O(log n)**  
Space complexity: **O(1)**
 
 