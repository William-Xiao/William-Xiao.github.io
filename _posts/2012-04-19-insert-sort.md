---
layout: post
title: 七大基本排序算法之插入排序
description: 插入排序算法
keywords: 数据结构与算法
---

```java
import java.io.IOException;
import Input.InputString;
 
/**
 * 插入排序
 * @author xiaomi
 * 2012.3.29
 */
public class InsertSort {
    public static void main(String[] args) throws IOException{
        String s = InputString.getString();
        String[] str = s.split(" ");
        int[] a = new int[str.length];
        for(int i = 0;i < str.length;i++){
            a[i] = Integer.parseInt(str[i]);
        }
        insertSort(a);
        insertSort_i(a);
        for(int i = 0;i < a.length;i++){
            System.out.print(a[i]+" ");
        }
    }
     
    //method1
    public static void insertSort(int[] a){
        int out,in;
        for(out = 1;out < a.length;out++){
            for(in = 0;in<out;in++){
                if(a[out]<a[in]){
                    break;
                }
            }
            int temp = a[out];
            for(int i = out;i > in;i--){
                a[i] = a[i-1];
            }
            a[in] = temp;
        }
    }
     
    //method2
    public static void insertSort_i(int[] a){
        int out,in;
        for(out = 1;out < a.length;out++){
            int temp = a[out];
            in = out;
            while(in>0&&a[in-1]>=temp){
                a[in] = a[in-1];
                in--;
            }
            a[in] = temp;
        } 
    }
    
    //method3
    public static void insertsort(int[] a){
        for(int out = 0; out < a.length; out++){
            for(int in = out; in > 1; in--){
                if(a[in] < a[in-1]){
                    int temp = a[in];
                    a[in] = a[in-1];
                    a[in-1] = temp;
                }
            }
        }
    }
}
```
   