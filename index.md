# Const Keyword and & Operator Report
## A- Const Keyword: 
<img src="https://github.com/Romaisaa/Romaisaa.github.io/blob/main/Const%20usage%20Diagram.png" align="center" width="1400" height="800">
As shown in diagram const keyword has 6 different usage.

***1- Declaring a constant variable:*** 
 
 if a variable is declared as const, it should be intialized at declartion with its value that won't be changed along its scope.
  if tried to change its value it will lead to compile error
  
  **Example** : 
  
  ```
  
  int main()
{
    const int x = 100;
    int z = 10;
    const int y = x + 100;     // it work as x is declared as const also.
    const int y = z + 100;     // it doesn’t work as z is not declared as const and then y also is not const
    x++;    // this leads to Compile time error   
}

  ```
  
