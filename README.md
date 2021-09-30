# Automated Syntax Error Correction

## Problem Statement
Given a code having some syntax error, we have to predict the error free version of that code.

### Input:

```
#include<stdio.h>

int check_prime(int num)
{
    int i;
    
    for(i=2;i<=num-1;i++)
   
   {
       if(num%i!==0)        //*****ERROR*********
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

### Output:

```
#include<stdio.h>

int check_prime(int num)
{
    int i;
    
    for(i=2;i<=num-1;i++) 
   
   {
       if(num%i==0)           //*****ERROR FIX*********
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

Dataset consist of following main features:
* sourceText
* targetText
* sourceLineText
* targetLineText

Handling complete code will require high computational resources, therefore I have used sourceLineText and targetLineText instead. These two contains error line in the code and its corrected version. 

## ML Model:

* Developed a sequence to sequence translation model to remove syntactic errors in C programs.
* Performed line-to-line error ﬁxing using the Encoder Decoder model with teacher forcing method.
* Obtained 22% and 27% accuracy using LSTMs and Bi-directional LSTMs respectively.
