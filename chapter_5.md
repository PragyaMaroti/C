### Loop control instructions:
The programs that we have developed so far used either a sequential
or a decision control instruction. In the first one, the calculations
were carried out in a fixed order; while in the second, an appropriate set
of instructions were executed depending upon the outcome of the
condition(s) being tested.  
We frequently need to perform an action over and over, often
with variations in the details each time. The mechanism, which meets
this need, is the ‘Loop Control Instruction’.

#### Loops:
There are three methods by way of which we can repeat a part of a
program. They are:
- using a **while** statement
- using a **for** statement
- using a **do-while** statement

Let's study them 1 by 1:

### While loop:
The basic syntax:  
initialize loop counter ;  
while ( test loop counter using a condition )  
{  
do this ;  
and this ;  
increment loop counter ;  
}  

The statements within the while loop would keep getting executed
till the condition being tested remains true. When the condition
becomes false, the control passes to the first statement that follows
the body of the while loop.  
In place of the condition there can be any other valid expression. So
long as the expression evaluates to a non-zero value the statements
within the loop would get executed.  
The statements within the loop may be a single line or a block of
statements. In the first case, the braces are optional.  

Note:
- It is not necessary that a loop counter must only be an int. It can even be a float. Even floating point loop counters can be decremented.
- No semicolon after while(condition)
- never use n+++ to increment the value of n by 2, since there doesn’t exist an operator +++ in C.
- +=, -=, *=, /= are compound assignment operator. For example, j = j + 10 can also be written as j += 10.

