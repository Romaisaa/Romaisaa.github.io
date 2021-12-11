# Const Keyword and & Operator Report
## A- Const Keyword: 
<img src="https://github.com/Romaisaa/Romaisaa.github.io/blob/main/Const%20usage%20Diagram.png" align="center" width="700" height="400">
As shown in diagram const keyword has 6 different usage.

### ***1- Declaring a constant variable:*** 
 
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
  
  
  
  ### ***2- Declaring a constant Pointer:*** 
  Pointers can be declared as const by 3 ways
  
**i**-	Pointer to a const variable : 

```
const int* u;   
```
it’s used to make any string or array immutable


**ii**-	Const pointer: 

```
int x = 1;
int* const w = &x;  //Change the order of const keyword and make it to the right of the data type. 
```
This declaration allow us to change the value of the variable x but not the value of the pointer


**iii**-	Both Const var with const pointer:
```
const int* const x;
```
This declaration to make both pointer(memory location) and value of varaible constant 



 ### ***3- Declaring a constant const function arg and return types:*** 
 
 **i** - when an argument in a function declared as const, its value cannot be changed in the function body 
 
 Example
 ```
 void conFun(const int x)
{
    i++;    // error
}

 ```
 
 **ii** - the return value of a const function is always const value
 ```
 const int C()
{
    return 5;    
}

 ```
 
 
 
### ***4- Class Data Members:*** 
There are data members declared in the class as constant but not intialized at their declaration. They can be intialized in the constructor for each object

```
class animal
{
    const String voice;
    public:
    Test(String V):voice(V)
    {
        voice = V;  // for this object the value of voice cannot be changed
    }
};

```



### ***5- Class Member Functions:*** 
The functions which are declared as const. if an object is called by them, this means that this obiect cannot be modified 
their declartion goes as follows: 

```
datatype function_name const();
```
*Example:* 

```
Class Animals{
int getValue() const {
      return val;
   }
   int main() {
   Animals A1();
   A1.getValue(); // this line forces that object A1 cannot be modified
   }
   };
```



### ***6- Constant objects:*** 

Also, objects can be declared as const.
When an object is declared or created using the const keyword, its data members can never be changed, during the object's lifetime.
Syntax:

```
const class_name object;
```







## B- & Operator:
*it has many usages depending on its syntax and this chart shows these usage with syntax:*
<img /src="https://github.com/Romaisaa/Romaisaa.github.io/blob/main/%26%20usage%20chart.png" align="center" width="700" height="400">



 
### ***1-  &*** 
***i- Getting the address of a variable*** 

if used at the left side of a variable, it means that the new varibale point to its location
*Example:*
```
int x = 10; // declartion of variable 
int* y = &x;  // declartion of refrence y to the variable x
```



***ii- Declaring a reference to a type:*** 

```
string& R = X; // Here, R is a reference to X    
```

***iii- Bitwise AND Operator*** 
it's used to campare each bit of a var by logic AND
*Eaxmple:*
```
int main() {  
   int X = 14 & 42;  // where 14 is equivalant to 	0 0	1	1	1 0
                      //  42 is equivalant to 1	0	1	0	1	0
                      // then x is 0	0	1	0	1	0 which is eq to 10 decimal

}
```

***iv- Function Overloading*** 
There is a type of function that are decalred by word operator followed by the operator symbol 
in this example, it's used to add 2 objects together. so, the parameters are sent y refrence.

*Example:*
```
class Box {
   public:
      double getVolume(void) {
         return length * breadth * height;
      }
      void setLength( double len ) {
         length = len;
      }
      void setBreadth( double bre ) {
         breadth = bre;
      }
      void setHeight( double hei ) {
         height = hei;
      }
      
      // Overload + operator to add two Box objects.
      Box operator+(const Box& b) {
         Box box;
         box.length = this->length + b.length;
         box.breadth = this->breadth + b.breadth;
         box.height = this->height + b.height;
         return box;
      }
   ```   

      


### ***2-  &&*** 

***i- Declaring Universal References*** 
first, we should know the difference of rvalue and lvalue in cpp. An lvalue is an expression e that may appear on the left or on the right hand side of an assignment, whereas an rvalue is an expression that can only appear on the right hand side of an assignment.
&& is used for declaring rvalue.
*Examples:*
```
template<typename T>
void f(std::vector<T>&& param);     // “&&” means rvalue reference
```
```
template<typename T>
void f(const T&& param); 

```



***ii- Logic AND Operator*** 

 used for expression of logical AND 
 
 
***iii- Function Overloading*** 

*Same usage as mentioned in **B.1.iv***

### ***3-  &=*** 
***i- Bitwise And*** 
It's the same of what mention in usage of & but it only differs in its syntax.
***Difference:***

```
x = 0 1 0 1 1 0;
y = 1 0 1 0 0 1;
x &= y ; 
x = x & y  //Two expressions are both equivalnt

```

