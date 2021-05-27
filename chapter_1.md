### Introduction to C

C is one of the languages which we use in the process of communivating with the computers.
Communicating with a computer involves speaking the language the
computer understands, which immediately rules out English as the
language of communication with computer.
#### Origin of C:
It was developed at Bell Labs, by Dennis Ritchie, Ken Thompson and others. It was a by-product of the UNIX operating system. Like other operating systems of that time, UNIX was written in assembly level language. \
programs written in assembly level language are hard to debug and enhance, and UNIX wwas no exception.
Ken Thompson then decided that a higher level language was needed for further development of UNIX , so he designed a language named "B".

Soon, Dennis Ritchie joined the UNIX project and started programming in B. In 1970, Bell Labs acquired  a PDP 11 for the UNIX project. Once unix was up and running on PDP 11, Thompson, rewrote a portion of UNIX in B.
and it became apparent that B wasn't well suited for PDP 11, So Ritchie began to develop an "extended version of B". He named it as NB at first, nbut upon more developments, when it diverted more from B, name was changed to "C". \
By 1973, the language was stable enough that UNIX could be written in C.
It provided an important benifit : **portability**.  By writing compilers in C for other computers at Bell Labs, it couldb be used on other machines as well!

#### Standardization:
C continued to involved during the 1970 specially between 1977 and 1979.Iit was during this period the first book of C appeared, “ the C programming language” by Brian kernighan and Dennis Ritchie which was published in 1978 but in the absence of this official standard book for C this book known as the K & R or the “white book “, served as a standard reference.
 During 1977, relatively few C programs and most of them were UNIX users. By the 1980s, however, C expanded beyond the narrow confines of the Unix world. C compilers became available on a variety of Machines, running a different operating system. In particular, C began to establish itself on the fast-growing IBM PC platform .

Programmers who wrote new C compilers relied on K and R as a reference. Unfortunately it was not clear about many of the features and it did not have a clear distinction which features belong to C and which were a part of Unix. Also, C continued to change after K&R  was published, with new features being added and a few older ones being removed. Need of a thorough, precise and up-to-date description of the language soon became Apparent.  Without such a standard numerous dialects would have ryzen 13 the portability of the C programs.
The development of US standard for C began in 1983, under the auspices of the ANSI. After many revisions, the standard was completed in 1988 and formally approved in December 1989 as ANSI standard. In 1998, it  was approved by international organisation for standardization (ISO).
This is reffered to as the *C89 version.

-------------------
Well,We got to know that it's one of the older generation of the programming languages still using it when we have We have many more modern languages?
Not and languages are also based on C like C++, Java etc.

There are several reasons which make us study C even now, those are:
👉C++, C# or java Make use of a principal is called object oriented programming to organise the program. This principle has a lot of advantages to offer but even while using this organising principle we should need a good holdover the language elements of sea and the basic programming skills. So we still have to learn C and then migrate to C++ or java through this two step learning process may take more time but at the end it will definitely find worth it. 
👉Part of popular operating system like Windows Unix Linux and Android are written in C because even today when it comes to performance nothing beats C.
👉 these days the common consumer devices like microwave ovens washing machines digital cameras are getting smarter day by day and this partners comes from a microprocessor and operating system and a program embedded in these devices. These programs are not only have to run fast but also have to work in Limited amount of memory so again we we make use of C.
👉Times when it required to interact with the hardware devices C is used for faster interaction Not compromising with the performance. 

Four important aspects of any language are:
the way it stores data 
The way it operates upon this data
how it accomplishes input and output
how it lets you control the sequence of execution of instructions in a program.
We shall learn about these aspects of C.



#### Getting started with c
there is a close analogy between learning English language and learning C language. The
classical method of learning English is to first learn the alphabets used in
the language, then learn to combine these alphabets to form words,
which, in turn, are combined to form sentences and sentences are
combined to form paragraphs.  Learning C is similar and easier. Instead of straight-away learning how to
write programs,we should:
1. first know what alphabets, numbers and special symbols are used in C and how to use them,
2.  know how  constants, variables and keywords are constructed
3.  know how are these combined to form an instruction.
 A group of instructions would be combined later on
to form a program.

### The C Character Set:
A character denotes any alphabet, digit or special symbol used to
represent information.
The alphabets, digits and special symbols when properly combined form constants, variables and keywords. \
 
### constants and variables:

A constant is an entity that doesn’t change, whereas, a
variable is an entity that may change
In programming languages, constants are often called literals, whereas,
variables are called identifiers.





![image](https://user-images.githubusercontent.com/64036955/119832942-4c002700-bf1c-11eb-9f79-aea36f349ba9.png)

Rules for Constructing Integer Constants
(a) An integer constant must have at least one digit.
(b) It must not have a decimal point.
(c) It can be either positive or negative.
(d) If no sign precedes an integer constant, it is assumed to be positive.
(e) No commas or blanks are allowed within an integer constant. \

the range of an Integer constant depends upon the
compiler.
For compilers like Visual Studio, gcc, it is -2147483648 to
+214748364 \

Rules for creating a Float constant:
The mantissa part and the exponential part should be separated by
a letter e or E.
(b) The mantissa part may have a positive or negative sign.
(c) Default sign of mantissa part is positive.
(d) The exponent must have at least one digit, which must be a positive
or negative integer. Default sign is positive.
(e) Range of real constants expressed in exponential form is -3.4e38 to 3.4e38. \


A character constant is a single alphabet, a single digit or a single
special symbol enclosed within single inverted commas.
(b) Both the inverted commas should point to the left. For example, ’A’
is a valid character constant whereas ‘A’ is not.



