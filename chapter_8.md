_Man is an intelligent species, but still cannot perform all of life’s
tasks all alone. He has to rely on others. You may call a mechanic
to fix up your bike, hire a gardener to mow your lawn, or rely on a store
to supply you groceries every month. A computer program (except for
the simplest one) finds itself in a similar situation. It cannot handle all
the tasks by itself. Instead, it requests other program-like entities—
called ‘functions’ in C—to get its tasks done._

## Functions:
Every C program can be thought of as a
collection of these functions. As we noted earlier, using a function is
something like hiring a person to do a specific job for you.
It is aself-contained block of statements that perform a
specific task.  
Functions are of two types:
- Library functions.
- user defined functions.

### User defined functions.
In a program, while making a function and then using it, we come accross the following three things:  
➡️ Function decleration (prototype)  
➡️ Function call  
➡️ function definition.  

#### Function Declaration:
We declare the return type, name of the function, and it's type of arguments.  
Declaration is done globally, before the function where we are gonna call it.  

*__syntax:__*
 return_type Name_of function(arguments types separated by ,);   
this is a necessary thing to do for using our own functions. Here , we may or may not name the argument variables.

#### Function Definition:
 In a Function definition, we have the full function with its body containing all the operations to be done on arguments or any statement to be executed when the function runs.    
 *__syntax:__*  
 return_type Name_of function(arguments types separated by ,)  
 {
 // function body with all its required statements and return statement when the retuen type isn't void  
 }
 Note: function can be definied right after its declaration also. 
 #### Function call:
When we call a function, the control passes to the function.
*__syntax:__* 
function name(arguments);
When function runs out of statements to execute, the control returns to where it was called.  
Note: function calls can be done within outside the function or within itself too. 🤓 Function calling itself is a separate interesting topic(called recursion).
### Libraary functions: 
As the name suggests, library functions are nothing but commonly
required functions grouped together and stored in a Library file on
the disk.The procedure for calling both types of functions is exactly
same.Example: printf(), scanf() etc.  frequently used libraries: stdio.h , stdlib.h , math.h etc.  
note: To use a library function, Its header file must be included at the top of the program.

### main() :
C program is a collection of programs. If a C program contains only one function, it must be main( ).If a C program contains more than one function, then one (and only
one) of these functions must be main( ), because program execution
always begins with main( ).After each function has done its thing, control returns to main( ).
When main( ) runs out of statements and function calls, the program
ends. Yes, from this we can conclude that main() is a necessity of a c program.  
note: the program execution always begins with
main( ). Except for this fact, all C functions enjoy a state of perfect
equality. No precedence, no priorities, nobody is nobody’s boss.  

**Note: Trace carefully the way control passes from one function to
another. Since the compiler always begins the program execution with
main( ), every function in a program must be called directly or indirectly
by main( ).**  So, The order in which the functions are defined in a program and the
order in which they get called need not necessarily be same.

### Why use Functions?
Why to make a separate function at all? why don't we pu teverything inside main() itself?
some of the reasons to use functions are:

-Writing functions avoids rewriting the same code over and over.
Suppose you have a section of code in your program that calculates
area of a triangle. If later in the program you want to calculate the
area of a different triangle, you won’t like it if you are required to
write the same instructions all over again. Instead, you would prefer
to jump to a ‘section of code’ that calculates area and then jump
back to the place from where you left off. This section of code is
nothing but a function.
- By using functions it becomes easier to write programs and keep
track of what they are doing. If the operation of a program can be
divided into separate activities, and each activity placed in a
different function, then each could be written and checked more or
less independently. Separating the code into modular functions also
makes the program easier to design and understand.

to cram the entire logic in one
function. It is a very bad style of programming. Instead, break a program
into small units and write functions for each of these isolated
subdivisions. 

### Passing values between function:
It's the way of communication between the ‘calling’ and the ‘called’ functions.
The mechanism used to convey information to the function is the
‘argument’. We have unknowingly used the arguments in the printf( )
and scanf( ) functions; the format string and the list of variables used
inside the parentheses in these functions are arguments. The arguments
are sometimes also called ‘parameters’.
- Arguments are passed to function when it is called. __they must have the same type as declared in the function prototype or the definition__.
- Areguments are written inside the brackets follwed by the function name.
- Arguments names(if mentioned ) in declaration or in function definition are called Formal arguments, while the ones which are passed during the calles are callled actual argument
- the type, order and number of the actual and formal arguments must always be same.
- actual and formal parameters may have same name as the compiler treat them differently because they are in different functions.


#### Return Statements:
Basic syntax: return _whatever to be returned_;  
these are used in a function to return as per the specified return type of a function. Some valid Examples of return statements are:
- return 0;
- return;
- return 250;
- return a;
 When a return statement is encountered , the control is passed to the place where the function was called.  
 Whenever the control returns from a function, the sum being
returned is collected in the calling function by assigning the called
function to some variable. For example:  
x = sum(a,b);  

The return statement serves two purposes:
1. On executing the return statement, it immediately transfers
the control back to the calling function.
1.  It returns the value present in the parentheses after return, to
the calling function. In the above program, the value of sum of
two numbers is being returned.

A function can return only one value at a time. Thus, the following
statements are invalid:  
return ( a, b ) ;  
return ( x, 12 ) ;   

If the value of a formal argument is changed in the called function,
the corresponding change does not take place in the calling
function. for example:  

      #include <stdio.h>  
      void fun ( int ) ;  
      int main( )  
      {  
      int a = 30 ;  
      fun ( a ) ;  
      printf ( "%d\n", a ) ;  
      return 0 ;  
      }  
      void fun ( int b )  
      {  
      b = 60 ;  
      printf ( "%d\n", b ) ;  
      }  
      Output:  
      60  
      30  
      through htis we can understand that we have only passed the information of what value was stored in a. We do not have access to the actual memory location of a. B only has the same value as a.  
      Adding further to this , we have 
      #### The scope rule of a function:

      scope of a variable is local to
      the function in which it is defined. For example:  
      #include <stdio.h>  
      void display ( int ) ;  
      int main( )  
      {   
      int i = 20 ;  
      display ( i ) ;  
      return 0 ;  
      }  
      void display ( int j )  
      {  
      int k = 35 ;    
      printf ( "%d\n", j ) ;  
      printf ( "%d\n", k ) ;  
      }  
is it necessary to pass the value of the variable i to the
function display( )? Will it not become automatically available to the
function display( )? No. Because, by default, the scope of a variable is
local to the function in which it is defined.  
### Order of passing variable:
It is passed right to left. It generally doesn't effect the results, but it is necessary to know .  
consider the example:  
int a = 1 ;  
printf ( "%d %d %d\n", a, ++a, a++ ) ;  
It appears that this printf( ) would output 1 2 2.
This however is not the case. Surprisingly, it outputs 3 3 1. This is
because, in C during a function call the arguments are passed from right
to left. That is, firstly 1 is passed through the expression a++ and then a
is incremented to 2. Then result of ++a is passed. That is, a is
incremented to 3 and then passed. Finally, latest value of a, i.e., 3, is
passed. Thus in right to left order, 1, 3, 3 get passed. Once printf( )
collects them, it prints them in the order in which we have asked it to
get them printed (and not the order in which they were passed).  

### One Dicey Issue
Now consider the following program:
#include <stdio.h>  
int main( )  
{  
int i = 10, j = 20 ;  
printf ( "%d %d %d\n", i, j ) ;  
printf ( "%d\n", i, j ) ;  
return 0 ;  
}  
This program gets successfully compiled, even though there is a
mismatch in the format specifiers and the variables in the list used in
printf( ). This is because, printf( ) accepts variable number of arguments
(sometimes 2 arguments, sometimes 3 arguments, etc.), and even with
the mismatch above, the call still matches with the prototype of printf( )
present in ‘stdio.h’. At run-time, when the first printf( ) is executed,
since there is no variable matching with the last specifier %d, a garbage
integer gets printed. Similarly, in the second printf( ), since the format
specifier for j has not been mentioned, its value does not get printed.
