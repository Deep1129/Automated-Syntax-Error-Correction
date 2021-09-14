# Automated Syntax Error Correction

## Problem Statement
Given a code having some syntax error, we have to predict the error free version of that code.

### Input:
Input:
```
#include<stdio.h>

int check_prime(int num)
{
    int i;
    
    for(i=2;i<=num-1;i++)
   
   {
       if(num%i!==0)
       {
           return 0;
       }
      
   }
   return 1;
}

int main()
{
    int i,n1,n2;
    scanf("%d%d",n1,n2);
    for(i=n1;i<=n2;i++)
    {
    if(check_prime(i))

     printf("%d",i);        
        
    }
     return 0;
}
```

## Dataset

Dataset consist of following features:
* 
