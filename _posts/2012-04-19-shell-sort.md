---
layout: post
title: 七大基本排序算法之希尔排序
description: 希尔排序算法
keywords: 数据结构与算法
---

```java
import java.io.IOException;
import Input.InputString;
  
/**
 * 希尔排序
 * @author xiaomi
 * 2012.3.29
 */
public class ShellSort {
    public static void main(String[] args) throws IOException{
        String s = InputString.getString();
        String[] str = s.split(" ");
        int[] a = new int[str.length];
        for(int i = 0;i < str.length;i++){
            a[i] = Integer.parseInt(str[i]);
        }
        shellSort(a);
        for(int i = 0;i < a.length;i++){
            System.out.print(a[i]+" ");
        }
    }
      
    public static void shellSort(int[] a){
        for(int step = a.length/2;step > 0;step /= 2){
            for(int begin = 0;begin<a.length;begin++){
                for(int out = begin+step;out < a.length;out+=step){
                    int in = out;
                    int temp = a[out];
                    while(in>=step&&a[in-step]>temp){
                        a[in] = a[in-step];
                        in-=step;
                    }
                    a[in] = temp;
                }
            }       
        }
    }
}
```
   