# Recursion
It is one important feature associated with functions in C.Though a bit difficult to understand, it is often
the most direct way of programming a complicated logic.  
In C, it is possible for the functions to call themselves. A function is
called ‘recursive’ if a statement within the body of a function calls the
same function.  
Following is the recursive version of the function to calculate the
factorial value:
#include <stdio.h>  
int rec ( int ) ;  
int main( )  
{  
int a, fact ;  
printf ( "Enter any number " ) ;  
scanf ( "%d", &a ) ;  
fact = rec ( a ) ;  
printf ( "Factorial value = %d\n", fact ) ;  
return 0 ;  
}  
int rec ( int x )  
{  
int f ;   
if ( x == 1 )  
return ( 1 ) ;  
else  
f = x * rec ( x - 1 ) ;  
return ( f ) ;  
}  
And here is the output for four runs of the program…  
Enter any number 1  
Factorial value = 1  
Enter any number 2  
Factorial value = 2  
Enter any number 3  
Factorial value = 6  
Enter any number 5  
Factorial value = 120  

In the first run when the number entered through scanf( ) is 1, let us see what
action does rec( ) take. The value of a (i.e., 1) is copied into x. Since x
turns out to be 1, the condition if ( x == 1 ) is satisfied and hence 1
(which indeed is the value of 1 factorial) is returned through the return
statement. When the number entered through scanf( ) is 2, the ( x == 1 ) test fails,
so we reach the statement,  
f = x * rec ( x - 1 ) ;  
And here is where we meet recursion. How do we handle the expression
x * rec ( x - 1 )? We multiply x by rec ( x - 1 ). Since the current value of x
is 2, it is same as saying that we must calculate the value (2 * rec ( 1 )).
We know that the value returned by rec ( 1 ) is 1, so the expression
reduces to (2 * 1), or simply 2. Now perhaps you can see what would happen if the value of a is 3, 4, 5
and so on.   
These successive invocations of the same
function are possible because the C compiler keeps track of which
invocation calls which. These recursive invocations end finally when the
last invocation gets an argument value of 1, which the preceding
invocation of rec( ) now uses to calculate its own f value and so on up
the ladder.  
### Recursion and stack
