# Handling Multiple Strings:  
often we are required to deal with a set of strings rather an isolated
string.  
Example program : to check out the name entered in the exsisting list of names:  
(Using a 2-D character array) : 

--------------------------------------------
#include<stdio.h>  
#include <string.h>  
#define FOUND 1  
#define NOTFOUND 0  
int main( )  
{  
char masterlist[ 6 ][ 10 ] = {  
"akshay",  
"parag",  
"raman",  
"srinivas",  
"gopal",  
"rajesh"  
} ;  
int i, flag, a ;  
char yourname[ 10 ] ;  
printf ( "Enter your name " ) ;  
scanf ( "%s", yourname ) ;  
flag = NOTFOUND ;  
for ( i = 0 ; i <= 5 ; i++ )  
{  
a = strcmp ( &masterlist[ i ][ 0 ], yourname ) ;  
if ( a == 0 )  
{  
printf ( "Welcome, you can enter the palace\n" ) ;  
flag = FOUND ;  
break ;  
}  
}  
if ( flag == NOTFOUND )  
printf ( "Sorry, you are a trespasser\n" ) ;  
return 0 ;  
}  

-----------------------------------------------------

And here is the output for two sample runs of this program: 

-----------------------------
Enter your name dinesh  
Sorry, you are a trespasser  
Enter your name raman  
Welcome, you can enter the palace  

---------------------

Notice how the two-dimensional character array has been initialized.
The order of the subscripts in the array declaration is important. The
first subscript gives the number of names in the array, while the second
subscript gives the length of each item in the array.  
Instead of initializing names, had these names been supplied from the
keyboard, the program segment would have looked like this:  
for ( i = 0 ; i <= 5 ; i++ )  
scanf ( "%s", &masterlist[ i ][ 0 ] ) ;  
     
 pictorial representation of the stored list :  
 ![image](https://user-images.githubusercontent.com/64036955/122178121-ed3b2700-cea3-11eb-819e-9ff1c305c637.png)  
 Note: there's wastage of memory with every name that we stored.  
 
 We could avoid this wastage by using the :  
 ### Array of Pointers to Strings:  
 a pointer variable always contains an address. Therefore, if
we construct an array of pointers, it would contain a number of
addresses.  
Using array of pointers we could store the names_list as follows:  
char *names[ ] = {
"akshay",
"parag",
"raman",
"srinivas",
"gopal",
"rajesh"
} ;
 
 Pictorial representation looks like:  
 ![image](https://user-images.githubusercontent.com/64036955/122179135-d943f500-cea4-11eb-9fbd-a2a7ef0e8eb5.png)  
 In the two-dimensional array of characters, the strings occupied 60
bytes. As against this, in array of pointers, the strings occupy only 41
bytes—a net saving of 19 bytes.  
Another reason to use an array of pointers to store strings is to obtain
greater ease in manipulation of the strings. Using the characteer array, the manipulation is done character by character, using the pointer array, we do manipulation on the string using thier addresses.  
For Example:  
        
        # include <stdio.h>
        int main( )
        {
        char names[ ][ 10 ] = {
        "akshay",
        "parag",
        "raman",
        "srinivas",
        "gopal",
        "rajesh"
        } ;
        int i ;
        char t ; 
        printf ( "Original: %s %s\n", &names[ 2 ][ 0 ], &names[ 3 ][ 0 ] ) ;
        for ( i = 0 ; i <= 9 ; i++ )
        {
        t = names[ 2 ][ i ] ;
        names[ 2 ][ i ] = names[ 3 ][ i ] ;
        names[ 3 ][ i ] = t ;
        }
        printf ( "New: %s %s\n", &names[ 2 ][ 0 ], &names[ 3 ][ 0 ] ) ;
        return 0 ;
        }
        
        
  Output:  
  
      Original: raman srinivas
      New: srinivas raman
      
In this program to exchange the names, we are required to
exchange corresponding characters of the two names. In effect, 10
exchanges are needed to interchange two names.    


another program:  
  
        #include <stdio.h>
        int main( )
        {
        char *names[ ] = {
        "akshay",
        "parag",
        "raman",
        "srinivas",
        "gopal",
        "rajesh"
        } ;
        char *temp ;
        printf ( "Original: %s %s\n", names[ 2 ], names[ 3 ] ) ;
        temp = names[ 2 ] ;
        names[ 2 ] = names[ 3 ] ;
        names[ 3 ] = temp ;
        printf ( "New: %s %s\n", names[ 2 ], names[ 3 ] ) ;
        return 0 ;}  
        
 The output is same as the earlier program. In this program, all that we
are required to do is to exchange the addresses (of the names) stored in
the array of pointers, rather than the names themselves. Thus, by
effecting just one exchange, we are able to interchange names. This
makes handling strings very convenient.



## Limitations of array to pointer to strings:
Limitation of Array of Pointers to Strings
When we are using a two-dimensional array of characters, we are at
liberty to either initialize the strings where we are declaring the array, or
receive the strings using scanf( ) function.  




    # include <stdio.h>
    int main( )
    {
    char *names[ 6 ] ;
    int i ;
    for ( i = 0 ; i <= 5 ; i++ )
    {
    printf ( "Enter name " ) ;
    scanf ( "%s", names[ i ] ) ;
    }
    return 0 ;
    
The program doesn’t work because; when we are declaring the array, it
is containing garbage values. And it would be definitely wrong to send
these garbage values to scanf( ) as the addresses where it should keep
the strings received from the keyboard.   

We can have a clumsy solution to this problem:  

 
    # include <stdio.h>
    # include <stdlib.h>
    # include <string.h>
    int main( )
    {
    char *names[ 6 ] ;
    char n[ 50 ] ;
    int len, i ;
    char *p ;
    for ( i = 0 ; i <= 5 ; i++ )
    {
    printf ( "Enter name " ) ;
    scanf ( "%s", n ) ;
    len = strlen ( n ) ;
    p = ( char * ) malloc ( len + 1 ) ; /* +1 for accommodating \0 */
    strcpy ( p, n ) ;
    names[ i ] = p ;
    }
    for ( i = 0 ; i <= 5 ; i++ )
    printf ( "%s\n", names[ i ] ) ;
    return 0 ;
    }

    }
    
 Note:  A void * means a pointer which is a

legal address but it is not address of a char, or address of an int, or
address of any other datatype. Hence it has been converted into char *
using a C language feature called typecasting.   
But why did we not use array to allocate memory? This is because, with
arrays, we have to commit to the size of the array at the time of writing
the program. Moreover, there is no way to increase or decrease the
array size during execution of the program. In other words, when we use
arrays, static memory allocation takes place. Unlike this, using malloc( ),
we can allocate memory dynamically, during execution.  
__*This solution suffers in performance because we need to allocate
memory and then do the copying of string for each name received
through the keyboard.*__

