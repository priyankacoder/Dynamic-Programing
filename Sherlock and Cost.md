import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    static void cost(int[] arr) {
        int low=0,hi = 0;
        for(int i=1;i<arr.length;i++){
            int hitolow = Math.abs(arr[i-1]-1);
            int lowtohi = Math.abs(arr[i]-1);
            int hitohi = Math.abs(arr[i]-arr[i-1]);
            int lowmax = Math.max(low,hi+hitolow);
            int himax = Math.max(hi+hitohi,low+lowtohi);
            low = lowmax;
            hi = himax;
        }
        
        System.out.println(Math.max(low,hi));
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int t = in.nextInt();
        for(int a0 = 0; a0 < t; a0++){
            int n = in.nextInt();
            int[] arr = new int[n];
            for(int arr_i = 0; arr_i < n; arr_i++){
                arr[arr_i] = in.nextInt();
            }
            Solution sc = new Solution();
            sc. cost(arr);
            //int result = cost(arr);
           // System.out.println(result);
        }
        in.close();
    }
}
