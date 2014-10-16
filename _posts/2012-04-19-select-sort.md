---
layout: post
title: 七大基本排序算法之选择排序
description: 选择排序算法
keywords: 数据结构与算法
---

```java
import java.io.IOException;
import Input.InputString;
 
/**
 * 选择排序
 * @author xiaomi
 * 2012.3.29
 */
public class SelectSort {
    public static void main(String[] args) throws IOException{
        String s = InputString.getString();
        String[] str = s.split(" ");
        int[] a = new int[str.length];
        for(int i = 0;i < str.length;i++){
            a[i] = Integer.parseInt(str[i]);
        }
        selectSort(a);
        for(int i = 0;i < a.length;i++){
            System.out.print(a[i]+" ");
        }
    }
     
    public static void selectSort(int[] a){
        for(int i = 0;i < a.length;i++){
            int pos = i;
            for(int j = i;j < a.length;j++){
                if(a[pos]>a[j]){
                    pos = j;
                }
            }
            int temp = a[i];
            a[i] = a[pos];
            a[pos] = temp;
        }
    }
}
```
   