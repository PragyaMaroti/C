## Data types :
Data types can be of following types:  
- Primary data type:      int, char, float, void
- derived data type:      array, strings, pointer. 
- user-defined data type: structure, union, enum  

### Integers , long and short
the range of an Integer constant depends upon
the compiler. For a 16-bit compiler like Turbo C or Turbo C++ the range
is –32768 to 32767. For a 32-bit compiler like Visual Studio or gcc the
range would be –2147483648 to +2147483647.  
Note : A 32-bit processor provides support for programs compiled using 16-bit compilers. If this backward compatibility support is not provided the 16-bit program
would not run on it. This is precisely what happens on the new Intel
Itanium processors (64-bit), which have withdrawn support for 16-bit
code.  
Remember that out of the two/four bytes used to store an integer, the
highest bit (16th/32nd bit) is used to store the sign of the integer. This bit
is 1 if the number is negative and 0 if the number is positive.  
Each compiler can decide appropriate sizes
depending on the operating system and hardware, for which it is being
written, subject to the following rules:
1.  shorts are at least 2 bytes big.
1.  longs are at least 4 bytes big.
1.  shorts are never bigger than ints.
1.  ints are never bigger than longs.  

Declaration of long variables:  
long int i ;  
Note: long integers cause the program to run a bit slower, but the range of
values that we can use is expanded tremendously. The value of a long
integer typically can vary from -2147483648 to +2147483647

Short variables are declared as:  
short int i;  
C allows the abbreviation of short int to short and of long int to long. therefore, following declarations are valid:  
long i;
short a;  
 Sometimes, we come across situations where the constant is small
enough to be an int, but still we want to give it as much storage as a
long. In such cases, we add the suffix ‘L’ or ‘l’ at the end of the number,
as in 23L.   
Use of suffixes in C:  
Suffixes: They are represented in many ways according to their data types.
- int:- No suffix are required because integer constant are by default assigned as int data type.
- unsigned int: character u or U at the end of integer constant.
- long int: character l or L at the end of integer constant.
- unsigned long int: character ul or UL at the end of integer constant.
- long long int: character ll or LL at the end of integer constant.
- unsigned long long int: character ull or ULL at the end of integer constant.  

### Signed and unsigned integer: 
By default, int is taken as signed int. At times, we already know in advance if the integer will be always positive. In this case we can specify during the declaration as "unsigned". It's benifit is that we get double the original range.  
Ex:  unsigned int num_students ;  
unsigned i;
With such a declaration, the range of permissible integer values (for a
32-bit compiler) will shift from the range –2147483648 to +2147483647
to the range 0 to 4294967295. Thus, declaring an integer as unsigned
almost doubles the size of the largest possible value that it can
otherwise take. This so happens because on declaring the integer as
unsigned, the left-most bit is now free and is not used to store the sign
of the number. Note that an unsigned integer still occupies two bytes  
Note: Like an unsigned int, there also exists a short unsigned int and a long
unsigned int. By default, a short int is a signed short int and a long int is
a signed long int.  
### float and double
A float occupies four bytes in memory and can range from -3.4e38 to
+3.4e38. If this is insufficient, then C offers a double data type that
occupies 8 bytes in memory and has a range from -1.7e308 to +1.7e308.
A variable of type double can be declared as:  
double a;  
If the situation demands usage of real numbers that lie even beyond the
range offered by double data type, then there exists a *long double* that
can range from -1.7e4932 to +1.7e4932. A long double occupies 10
bytes in memory.

![image](https://user-images.githubusercontent.com/64036955/121327343-fcb0f200-c930-11eb-8930-f80fe1bc3771.png)



## Storage classes: 
To fully define a variable, one needs to
mention not only its ‘type’ but also its ‘storage class’.  
We have not mentioned storage classes yet, though we have written
several programs in C. We were able to get away with this because
storage classes have defaults. If we don’t specify the storage class of a
variable in its declaration, the compiler will assume a storage class
depending on the context in which the variable is used.  
From C compiler’s point of view, a variable name identifies some
physical location within the computer where the string of bits
representing the variable’s value is stored. There are basically two kinds
of locations in a computer where such a value may be kept:—  
- Memory :
- CPU registers : A value stored in a CPU register can always be accessed faster than the
one that is stored in memory. Therefore, if a variable is used at many
places in a program, it is better to declare its storage class as register.  

It is the variable’s storage class that determines in
which of these two types of locations, the value is stored.
There are 4 storage classes in C: 
1. automatic storage class (auto)
2. static storage class (static)
3. register storage class
4. external storage class

![image](https://user-images.githubusercontent.com/64036955/121482894-33e3d980-c9eb-11eb-858a-66612ae9b429.png)  

Consider the following example: 

---------------------------------------------------
#include <stdio.h>  
int main( )  
{  
auto int i = 1 ;  
{  
auto int i = 2 ;  
{  
auto int i = 3 ;  
printf ( "%d ", i ) ;  
}  
printf ( "%d ", i ) ;  
}  
printf ( "%d\n", i ) ;  
return 0 ;  
}  

-------------------------------------------

Note that the Compiler treats the three i’s as totally different variables,
since they are defined in different blocks. All three i’s are available to
the innermost printf( ). This is because the innermost printf( ) lies in all
the three blocks (a block is all statements enclosed within a pair of
braces) in which the three i’s are defined. This printf( ) prints 3 because
when all three i’s are available, the one which is most local (nearest to
printf( )) is given a priority.   

Note (for register class):  even though we have declared the storage class of i as register,
we cannot say for sure that the value of i would be stored in a CPU
register. Why? Because the number of CPU registers are limited, and
they may be busy doing some other task. What happens in such an
event... the variable works as if its storage class is auto.  
Not every type of variable can be stored in a CPU register. For example,
if the microprocessor has 16-bit registers then they cannot hold a float
value or a double value, which require 4 and 8 bytes respectively.
However, if you use the register storage class for a float or a double
variable, you won’t get any error messages. All that would happen is the
compiler would treat the variables to be of auto storage class.  

Understanding difference between static and auto :  
![image](https://user-images.githubusercontent.com/64036955/121483746-29760f80-c9ec-11eb-8c7c-c2d8e8af3840.png)  
   __if the storage class is static, then the statement
static int i = 1 is executed only once, irrespective of how many times the
same function is called.__   
word of advice—avoid using static variables
unless you really need them. Because their values are kept in memory
when the variables are not active, which means they take up space in
memory that could otherwise be used by other variables.    
Note(for extern) : External variables are declared outside all
functions, yet are available to all functions that care to use them.

Note: a static variable can also be declared outside all the
functions. For all practical purposes it will be treated as an extern
variable. However, the scope of this variable is limited to the same file in
which it is declared. This means that the variable would not be available
to any function that is defined in a file other than the file in which the
variable is defined.  

👉All variables that are defined inside a function are normally created
on the stack each time the function is called. These variables die as
soon as control goes back from the function. However, if the
variables inside the function are defined as static then they do not
get created on the stack. Instead they are created in a place in
memory called ‘Data Segment’. Such variables die only when
program execution comes to an end.  
👉 If a variable is defined outside all functions, then not only is it
available to all other functions in the file in which it is defined, but is
also available to functions defined in other files. In the other files
the variable should be declared as extern.  
👉 In the following statements the first three are definitions, whereas,
the last one is a declaration:  
auto int i ;  
static int j ;  
register int k ;  
extern int l ;  

### Which to Use When 🤔

We decide which memory has to be used, keeping in mind the following points: 
- economise the memory space consumed by the variables
- improve the speed of execution of the program  
**Some ground rules to Decide the memory:**  
1. Use static storage class only if you want the value of a variable to persist between different function calls.
2. Use register storage class for only those variables that are being used very often in a program. (because it is limited) A typical application of register storage class is loop counters, which get used a number of times in a program.
3. Use extern storage class for only those variables that are being used by almost all the functions in the program. This would avoid unnecessary passing of these variables as arguments when making a function call. Declaring all the variables as extern would amount to a lot of wastage of memory space because these variables would remain active throughout the life of the program.
4. If you don’t have any of the express needs mentioned above, then
use the auto storage class. In fact, most of the times, we end up
using the auto variables. This is because once we have used the
variables in a function and are returning from it, we don’t mind
losing them.
