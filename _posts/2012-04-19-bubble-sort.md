---
layout: post
title: 七大基本排序算法之冒泡排序
description: 冒泡排序算法
keywords: 
category: 数据结构与算法
---

```java
import java.io.IOException;
import Input.InputString;
 
/**
 * 冒泡排序
 * @author xiaomi
 * 2012.3.29
 */
public class BubbleSort {
    public static void main(String[] args) throws IOException{
        String s = InputString.getString();
        String[] str = s.split(" ");
        int[] a = new int[str.length];
        for(int i = 0;i < str.length;i++){
            a[i] = Integer.parseInt(str[i]);
        }
        bubbleSort(a);
        for(int i = 0;i < a.length;i++){
            System.out.print(a[i]+" ");
        }
    }
     
    public static void bubbleSort(int[] a){
        for(int i = 0;i < a.length;i++){
            for(int j = a.length-1;j > i;j--){
                if(a[j]<a[j-1]){
                    int temp = a[j];
                    a[j] = a[j-1];
                    a[j-1] = temp;
                }
            }
        }
    }
}
```
   