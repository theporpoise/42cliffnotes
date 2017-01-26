# Online testing site provided:

http://ftprintf.com/
42filechecker

# Suggested execution order:

### Before getting started
1. Read.  Assignment in full + man pages for printf and stdarg.
2. Understand how va_list works.  Play with this and see that you can pass args
successfully with va_list, va_arg function to read them, and va_end to end.
3. Look at edge cases for print f.  like %%.  lots of others
* see list of interesting printf edge cases
* understand there are some edge cases that will generate compiler warnings, but
still work.  dont get fooled.

### High Level Strat

Parse
Pause when you hit a conversion specifier
Calculate proper type and output from all the modifiers (flags)
Print that conversion specifier out
Repeat until you hit the end


### Architecting - Break out project into major components

1. Parsing the const char *format string

* Each conversion specification is introducted by the char %, and ends with
a conversion specifier.
* In between there may be:
  * %[flags][width][.precision][length][specifier]
  * 0 or more flags
  * optional min field width
  * optional precision
  * optional length modifier

 Parsing Strat
-take in the string.
-go until you see a %
-handle the % case properly
-once you find a %, go until you hit something that is not a "special char"
or hit a specifier.  If you hit something thats unexpected have an error.
// when you see something that says "this flag is ignored" just think to yourself
this is later on down in an if else statement!

## **Side Note: va_arg - How to call it properly?**

So, notice how you have to pass a type to va_arg?  Or at least, hopefully you caught that. 
Where do you get this function type?
wait for it . . . 
The format string!

That's right, you'll need to match up the type you found in the format string to properly call va_arg.
Yes, you will likely have a very large if-else statement!

* type (va_list) is automatically declared when you include <stdarg.h>
Must declare a variable (object) of type va_list which is used by the macros va_start(), va_arg(), va_copy(), and va_end().

### STDARG FUNCTION / MACROS:
* void va_start(va_list ap, last);
** last here is the name of the var right before the variable params
* type va_arg(va_list ap, type);
** this is a type finder?
* void va_copy(va_list dest, va_list src);
* void va_end(va_list ap);

2. Handling interaction between flags
* See interesting table in man 3 printf.  it's the only table in the whole thing, so yes, it's important.

3. Formatting the output for each var
* Substituting in correct type from va_list
* Precision
* Field Width
* Lenght Modifier
* blah.

Suggested Strat:
Start with the numbers, 'd' and 'i' specifiers.  Just get those done first.  After that everything else will make more 
sense.

4. Repeat process over the entire string.

5. DONE!


### STDARG VARIABLE:

# More Notes:

## discover the dif kinds of flags
-how many total?
-how many categories of flags?
-how do they interact?
-how do you break this down into a step by step process, if this, then that.
-what things are certain?  build those functions first.

## print out the output
-dif print functions for dif output,
ex: putnbr for numbers, putstr for string, 

print it a piece at a time?  Or construct the whole string and then print?  Extra bonus if you can return the string :-).

## keep track of how many chars the thing printed out. . .
-have some sort of running counter.
-printf does have a return value - so play around with it.  it's pretty straightforward.  hint -> strlen is your friend.  
-Upon successful return, these functions return the number of characters printed 
(excluding the null byte used to end output to strings).

# Printf Function Standards - Know when it errors:
That you have the right number of parameters and arguements, otherwise it just goes over and prints garbage.

If an output error is encountered, a negative value is returned.


# Printf Assumptions that may impact things (reading from man page):
The functions vprintf(), vfprintf(), vsprintf(), vsnprintf() are equivalent to the functions printf(), fprintf(), sprintf(), snprintf(), respectively, except that they are called with a va_list instead of a variable number of arguments. 
**These functions do not call the va_end macro. Because they invoke the va_arg macro, the value of ap is undefined after the call. S: stdarg(3).**





