---
layout: post
title: 七大基本排序算法之归并排序
description: 归并排序算法
keywords: 
category: 数据结构与算法
---

```java
import java.io.IOException;
import Input.InputString;
 
/**
 * 快速排序
 * @author xiaomi
 * 2012.04.02
 */
public class MergeSort {
 
    public static void main(String[] args) throws IOException{
        String s = InputString.getString();
        String[] str = s.split(" ");
        int[] a = new int[str.length];
        for(int i = 0;i < str.length;i++){
            a[i] = Integer.parseInt(str[i]);
        }
        mergeSort(a,0,a.length-1);
        for(int i = 0;i < a.length;i++){
            System.out.print(a[i]+" ");
        }
    }
 
    public static void mergeSort(int[] a,int low,int high){
        if(low == high){
            return;
        }
        int mid = (low+high)/2;
        mergeSort(a,low,mid);
        mergeSort(a,mid+1,high);
        merge(a,low,mid,high);
    }
     
    public static void merge(int[] a,int low,int mid,int high){
        int i,j,k;
        i = low;
        j = mid+1;
        k = low;
        int[] temp = new int[a.length];
        while(i<=mid&&j<=high){
            if(a[i]<a[j]){
                temp[k++] = a[i++];
            }else{
                temp[k++] = a[j++];
            }
        }
        while(i<=mid){
            temp[k++] = a[i++];
        }
        while(j<=high){
            temp[k++] = a[j++];
        }
        for(i = low;i <= high;i++){
            a[i] = temp[i];
        }
    }
}
```
   