# minimunLengthSubarray-ngonnguC
#include <stdio.h>
#define MIN(a,b) ((a) < (b) ? (a) : (b))
int minimunLengthSubarray(int a[], int n, int target){
    int left = 0;
    
    int ans = n+1;
    int sum = 0;
    for(int right = 0;right<n;right++){
        sum+=a[right];
        while (sum >= target){
            ans = MIN(ans,right - left + 1);
            sum -= a[left];
            left++;
        }
    }
    return ans;
}


