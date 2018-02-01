import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    static long getWays(long n, long[] c){
       long m = c.length;
     long[] Table = new long[(int)n+1];
        Table[0] = 1;
        for(long i=0;i<m;i++){
            for(long j=c[(int)i];j<=n;j++){ //i=0;c[0]=1;j=1
                long k = j-c[(int)i];
                Table[(int)j] += Table[(int)( j-c[(int)i])];
            }
           
        }
        return Table[(int)n];
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        int m = in.nextInt();
        long[] c = new long[m];
        for(int c_i=0; c_i < m; c_i++){
            c[c_i] = in.nextLong();
        }
        // Print the number of ways of making change for 'n' units using coins having the values given by 'c'
        
        long ways = getWays(n, c);
        System.out.print(ways);
    }
}
