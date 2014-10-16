---
layout: post
title: 七大基本排序算法之快速排序
description: 快速排序算法
keywords: 数据结构与算法
---

```java
/**
 * 快速排序
 * @author xiaomi
 * 2012.4.2
 */
public class QuickSort {
    public static void main(String[] args) throws IOException{
        String s = InputString.getString();
        String[] str = s.split(" ");
        int[] a = new int[str.length+1];
        for(int i = 0;i < str.length;i++){
            a[i+1] = Integer.parseInt(str[i]);
        }
        quickSort(a,1,a.length-1);
        for(int i = 1;i < a.length;i++){
            System.out.print(a[i]+" ");
        }
    }
   
    public static void quickSort(int[] a,int low,int high){
        if(low < high){
            int pivot = partion_1(a, low, high);
            quickSort(a, low, pivot-1);
            quickSort(a, pivot+1, high);
        }
    }
    //method1   
    public static int partion_1(int[] a,int low,int high){
        a[0] = a[low];
        int pivot = a[low];
        while(low<high){
            while(low < high && a[high] >= pivot){
                high--;
            }
            a[low] = a[high];
            while(low < high && a[low] <= pivot){
                low++;
            }
            a[high] = a[low];
        }
        a[low] = a[0];
        return low;
    }
    //method2   
    public static int partion_2(int[] a,int low,int high){
        int pivot = a[low];
        while(low<high){
            while(low < high && a[high] >= pivot){
                high--;
            }
            while(low < high && a[low] < pivot){//不能都加‘=’号，否则可能high跑到low前面
                low++;
            }
            int temp = a[high];
            a[high] = a[low];
            a[low] = temp;
        }
        return low;
    }
}
```

补充两个全面介绍排序算法的链接：
wiki
王汝金
   