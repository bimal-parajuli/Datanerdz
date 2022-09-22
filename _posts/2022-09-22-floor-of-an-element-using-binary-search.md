---
layout: post
title:  "Calculating the Floor using Binary Search."
categories: [ Coding, Problem-Solving ]
image: assets/images/logo.png
---


```
    public static int floor(int[] arr, int target){

        // Edge Cases.
        if(arr.length == 0 || arr[0] > target) 
            return -1;

        int start = 0, end = arr.length -1;
        int result = -1;
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

```