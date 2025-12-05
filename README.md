# Merge_Sort

#include<bits/stdc++.h>

using namespace std;
int a[1001],b[1001];

void MergeSort(int a[],int low,int high){
    int mid;
    if(low<high){
        mid=(high+low)/2;
        MergeSort(a,low,mid);
        MergeSort(a,mid,high);
        Merge(a,low,mid,high);
    }
}

void Merge(int a[],int low,int mid,int high){
    int i=low,j=m+1,k=0;
    while((i<=mid)&&(j<=high)){
        if(a[i]<=a[j])
        b[k++]=a[i++];
        else
        b[k++]=a[j++];
    }
    while(i<=mid)b[k++]=a[i++];
    while(j<=high)b[k++]=a[j++];
    for(i=low,k=0;i<=high;i++)a[i]=b[k++];
}

int main(){
    int n;
    scanf("%d",&n);
    for(int i=0;i<n;i++)
    scanf("%d",&a[i]);
    MergeSort(a,0,n-1);
    for(int i=0;i<n;i++)
    printf("%d ",a[i]);
    return 0;
}
  
