# SORT-AGAIN

SORT AGAIN

Problem Description

给你N个整数,x1,x2...xn，任取两个整数组合得到|xi-xj|,(0<i,j<=N,i!=j)。

现在请你计算第K大的组合数是哪个（一个组合数为第K大是指有K-1个不同的组合数小于它）。

Input

输入数据首先包含一个正整数C，表示包含C组测试用例.

每组测试数据的第一行包含两个整数N，K。(1<N<=1000,0<K<=2000)

接下去一行包含N个整数，代表x1,x2..xn。(0<=xi<=2000)

Output

对于每组测试数据，请输出第K大的组合数，每个输出实例占一行。

Sample Input

3 3 2 4 0 7 4 2 1 2 3 4 2 1 2 9

Sample Output

4 2 7

代码：

#include<iostream>
  
#include<math.h>

using namespace std;

int main()

{

    int n,m,t,a[1001],b[2002],w,i,j;
    
    scanf("%d",&n);
    
    while(n--)
    
    {
    
        scanf("%d%d",&m,&t);
        
        memset(b,-1,sizeof(b));
        
        w=0;
        
        for(i=0;i<m;i++)
        
            scanf("%d",&a[i]);
            
        for(i=m-1;i>=0;i--)
        
            for(j=0;j<i;j++)
            
                b[abs(a[i]-a[j])]=abs(a[i]-a[j]);
                
        for(i=0;i<2002;i++)
        
        {
        
            if(b[i]!=-1)
            
            {
            
                w++;
                
                if(w==t)
                
                {
                
                    printf("%d\n",b[i]);
                    
                    break;
                    
                }
                
            }
            
        }
        
    }
    
    return 0;
    
}
