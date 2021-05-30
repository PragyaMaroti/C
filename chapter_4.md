### More Complex decision making:

Everytime, the decisions maynot be as simple as to be answered in yes or no, we may have multiple conditions to carry-out an action.
In programming too
action performed may be based on result of multiple conditions. Such
programming situations can be handled elegantly using Logical
Operators.  
consider this Example problem:
The marks obtained by a student in 5 different subjects are
input through the keyboard. The student gets a division as per the
following rules:  
Percentage above or equal to 60 - First division  
Percentage between 50 and 59 - Second division  
Percentage between 40 and 49 - Third division  
Percentage less than 40 - Fail  
Write a program to calculate the division obtained by the student.  

We would tend to use the if-else statements as follows:

#include <stdio.h>  
int main( )  
{  
int m1, m2, m3, m4, m5, per ;  
printf ( "Enter marks in five subjects " ) ;  
scanf ( "%d %d %d %d %d", &m1, &m2, &m3, &m4, &m5 ) ;  
per = ( m1 + m2 + m3 + m4 + m5 ) * 100 / 500 ;  
if ( per >= 60 )  
printf ( "First division\n" ) ;  
else  
{  
if ( per >= 50 )  
printf ( "Second division\n" ) ;  
else  
{  
if ( per >= 40 )  
printf ( "Third division\n" ) ;  
else  
printf ( "Fail\n" ) ;  
}  
}  
return 0 ;  
}  

This is a straight-forward program. Observe that the program uses
nested if-elses. Though the program works fine, it can be a bit tedious work to:
- Care needs to be exercised to match the corresponding ifs and elses.
- Care needs to be exercised to match the corresponding pair of braces.

Let us now introduce ourselves to the **__logical operators :__**
C allows usage of three logical operators, namely, &&, || and !. These
are to be read as ‘AND’, ‘OR’ and ‘NOT’, respectively. Their working is similar to the logical and and logical or that we come across in maathematics.
These operators return true or false.  These are also Binary operators, implying they require two arguments.
 Note that: two of them are composed of double symbols: || and &&.
Don’t use the single symbol | and &. These single symbols also have a
meaning. They are bitwise operators.  
The first two operators, && and ||, allow two or more conditions to be
combined in an if statement. 

Now, Let us use logical operators to solve the above question.  

#include <stdio.h>  
int main( )  
{  
int m1, m2, m3, m4, m5, per ;  
printf ( "Enter marks in five subjects " ) ;  
scanf ( "%d %d %d %d %d", &m1, &m2, &m3, &m4, &m5 ) ;  
per = ( m1 + m2 + m3 + m4 + m5 ) / 500 * 100 ;  
if ( per >= 60 )  
printf ( "First division\n" ) ;  
if ( ( per >= 50 ) && ( per < 60 ) )  
printf ( "Second division\n" ) ;  
if ( ( per >= 40 ) && ( per < 50 ) )  
printf ( "Third division\n" ) ;  
if ( per < 40 )  
printf ( "Fail\n" ) ;  
return 0 ;  
}  
As can be seen from the second if statement, the && operator is used to
combine two conditions. ‘Second division’ gets printed if both the
conditions evaluate to true. **If one of the conditions evaluate to false
then the whole thing is treated as false.**  
The matching (or do I say mismatching) of the ifs with their
corresponding elses gets avoided, since there are no elses in this
program.  

There is a negative side to the program too. Even if the first condition
turns out to be true, still all other conditions are checked. This will increase the time of execution of the program. This can be avoided using
the **else if clause.**  

We shall now make use of the "else if" clause to solve tthe other problem:  
#include <stdio.h>  
int main( )  
{  
int m1, m2, m3, m4, m5, per ;  
per = ( m1+ m2 + m3 + m4+ m5 ) / 500 * 100 ;  
if ( per >= 60 )  
printf ( "First division\n" ) ;  
else if ( per >= 50 )  
printf ( "Second division\n" ) ;  
else if ( per >= 40 )  
printf ( "Third division\n" ) ;  
else  
printf ( "fail\n" ) ;  
return 0 ;  
}  
In this case, every else is associated with its previous if. The
last else goes to work only if all the conditions fail. Also, if a condition is
satisfied, other conditions below it are not checked. Even in else if
ladder, the last else is optional.
Note that the else if clause is nothing different. It is just a way of
rearranging the else with the if that follows it.


