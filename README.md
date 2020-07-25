# AlgorithmLab
This repository will have all the lab tasks in the Algorithm. The code templates will be given. You have to tweak it by yourself.
#include<bits/stdc++.h>
using namespace std;
int knapSack(int W, int wt[], int val[], int n)
{
    int i, w;
    int K[n + 1][W + 1];
    for (i = 0; i <= n; i++)
    {
        for (w = 0; w < W; w++)
        {
            if (i == 0 || w == 0)
                K[i][w] = 0;
            else if (wt[i-1] <=w)
            {
                K[i][w] = max( val[i - 1] + K[i - 1][w - wt[i - 1]],K[i - 1][w]);
            }
            else
            {
                K[i][w] = K[i - 1][w];
            }
            printf("%d    ",K[i][w]);
        }
        printf("\n")     ;
    }
    return K[n][W-1];
}
int max(int a, int b)
{
(a>b)?a:b;
}
int main()
{
    int weight[] = { 3,4,5,6 };
    int value[] = { 4,5,6,7 };
    int MaxWeight = 7;
    int Size = sizeof(value) / sizeof(value[0]);
    int highest=knapSack(MaxWeight, weight, value, Size);
    cout<<"The max possible value  is "<<highest<<endl;
    return 0;
}

//Robiul islam
//191-15-2611
