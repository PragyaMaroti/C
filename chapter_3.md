### Decision making using if-else

We all make decisions based on circumstances,
if we have this we would react like this or if we get this we might do this etc.  
Till now, We have written the statements in a program in the order we want it to be executed . Many times we want a set of instructions to be executed in one situation and entirely different set of instructions to be executed in another condition this kind of situation is dealt in C program using decision control instruction. 

Most commonly used decision making instructions in C are as follows:
- If statement
- If-else statement
- switch statement
a comaratively less used decision making statement is the one that uses conditional operators.

#### if statement:
C uses the "if keyword" to implement the decision control instruction. It's basic syntax is :  

-------------------------
if(condition_to be checked)  
{  
statements to be executed if the condition is met;  

}

-----------------------------

note: if there is only one statement to be executed for if condition, then braces are not necessary 

The condition following the keyword if is always enclosed in a pair of parentheses .
If the statement is true then the statement following if statement in closed in the brackets are executed if the condition is not true then the statement is not executed and it's skipped. 
As a general rule we Express a condition using C’s relational operators.We can also have arithmetic expressions in the condition statement or even just a number in the conditional statement. 
Treats any of the non-zero value as true and the 0 as false.

Examples:

if ( 3 + 2 % 5 )  
printf ( "This works" ) ;  
if ( a = 10 )  
printf ( "Even this works" ) ;  
if ( -5 )
printf ( "Even this works" ) ;  



"flow chart" is a useful tool to understand / visualize how the the program would work

####  if-else statement:

The if statement by itself will execute a single statement, or a group of
statements, when the expression following if evaluates to true. It does
nothing when the expression evaluates to false. using the else statement following the if statement, we can give instructions for what statements to execute if the if condition is false.
Basic syntax of if-else statement:

------------
if(condition)  
{  
statements to be executed if the condition is true;  
}  
else  
{  
statements to be executed if the condition is false;  
}  
-----------------------------

The group of statements after if excluding the statements after else is called the else block.
note: the else is written just below the if bolck.



#### nested if-else statements:

It is perfectly alright if we write an entire if-else construct within either
the body of the if statement or the body of an else statement. This is
called ‘nesting’of ifs. There are two ways to nest if-else statemnts:

-  if ( condition )  
{  
if ( condition )  
do this ;  
else  
{  
do this ;  
and this ;  
}  
}  
else  
do this ;  

-  if ( condition )  
do this ;  
else  
{  
if ( condition )  
do this ;  
else  
{  
do this ;  
and this ;  
}  
}  
 
 


