1.InItIalIzatIon of malloc() functIon Into zero.
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
int main()
{
int n=5;
int*arr=(int *)malloc(n*sizeof(int));
if(arr==NULL) 
{
printf("Memory allocation failed\n");
return 1;
}
memset(arr,0,n*sizeof(int));
for (int i = 0; i < n; i++) 
{
printf("%d ",arr[i]);
}
free(arr);
printf("program output:success\n");
system("getmac");
return 0;
}
