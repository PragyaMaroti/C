### C instructions:
A program is nothing but a set of instructions. The program behaves
as per the instructions that we give in it. Different instructions help
us achieve different tasks in a program.  
__Types of instructions:__
There are basically three types of instructions in C:
- Type Declaration Instruction
- Arithmetic Instruction
- Control Instruction

The elementary C programs would usually contain only the type
declaration and the arithmetic instructions.  

#### Type Declaration instruction:
Any variable used in the program must be declared before
using it in any statement. As a good habbit, it is declared usually in the begining of  function for local variables.

While declaring a variable, we must specify it's type and name Basic syntax:
**data_type variable_name**
Optionally, we can initiaalize it while declaring it.

We can use a a predefined variable in initialization of another variable.  

* int a=10;  
 int b = a+10;

* int a, b, c, d ;  
a = b = c = 10 ;

however, it won't work here:

int a = b = c = d = 10 ;

#### Arithmetic Instruction:

A C arithmetic instruction consists of a variable name on the left hand
side of = and variable names and constants on the right hand side of =.
The variables and constants appearing on the right hand side of = are
connected by arithmetic operators like +, -, *, %, and /.
Here,
*,%, /, -, + are the arithmetic operators and 
'=' is the assignment operator.

Arithmetic instruction can be of 3 types: 
- Integer mode arithmetic statement – In this statement all operands are either integer variables or integer constants.
- Real mode arithmetic statement – In this statement all operands are either real constants or real variables.
- Mixed mode arithmetic statement – In this statement some operands are integers and some operands are real.

Points to be noted for an arithematic operartion:
- C allows only one variable on left-hand side of =.
- the modulus operator (%) cannot be applied on a float. Also note that on using % the sign of the remainder is always same as the sign of the numerator. Thus -5 % 2 yields –1, whereas, 5 % -2 yields 1.
- An arithmetic instruction is at times used for storing character constants in character variables.

Note : When we do this, the ASCII values of the characters are stored in
the variables. ASCII codes are used to represent any character in
memory. For example, ASCII codes of ‘F’ and ‘G’ are 01000110 and
01000111. ASCII values are nothing but the decimal equivalent of
ASCII codes.

-------------

Rules that are used for the implicit conversion of floating
point and integer values in C, are mentioned below:

- An arithmetic operation between an integer and integer always yields an integer result.
- An operation between a real and real always yields a real result.
- An operation between an integer and real always yields a real result. In this operation the integer is first promoted to a real and then the operation is performed. Hence the result is real.

----------------
Heirarch of operations:

![image](https://user-images.githubusercontent.com/64036955/119967249-c5a21e80-bfc9-11eb-9b48-d0c4a3a63e9d.png)
Note: if there is any parenthesis in the expressionn, the operation inside the parenthesis is done first. 

Just as for performing mathematical operations, we follow a priority rule, called BODMS, here too we follow this priority order to avoid ambiguity.

-
-
-

#### Associativity of operators:
When an expression contains two operators of equal priority the tie
between them is settled using the associativity of the operators.
