Resources:
https://github.com/theporpoise/random_file_gen
42FileChecker


What you will learn:
Managing a buffer properly presents quite a few challenges.  You have to keep track of where you
are in the file, the leftover buffer, and your return value.

Using a static variable allows you to maintain data inside a buffer between function calls.
Allowing you to access the data on the next call.

If you decide to tackle Get Next Line using memory, you will quickly learn the importance of
b_zero, and making sure that you pass clean memory to your functions.

#Suggested Execution Order
1. Create a main to take in the file and pass it to your function.
2. Have your function

#Headers you will need and why


#Architecture

You should be able to solve the basic Get Next Line (no bonus) with 3 or less functions.
A typical 3 function structure to solve is:

1. Main Get Next Line Function
* Checks if there is anything from previous call of Get Next Line saved in static buffer
** Checks to see if this has a newline in it
* Reads in additional buffer - assuming no newline found so far - and continues reading until
a newline is found
* Calls function (#3) to append all the pieces of the buffer together to the provided pointer.
* returns the correct integerr to indicate end of file, error, or keep reading.

2. A function to find the newline and save the leftover / remaining buffer for the next call
to get next line.

3. A function to properly append everything together.  The thing to remember here is you are
NOT returning a newline at the end of each string, so skip over the newlines and return the
correct thing!

Up to two additional functions can be added to handle multiple file descriptors:

4. Creates a list item that contains a file descriptor and its previous remaining buffer.

5. Looks up the correct list item and the remaining buffer.


#Interesting Test Cases
What if your file does not end in a newline?
What if your buffer is really really big (in particular, what if there are multiple, 2+, newlines
inside your buffer?
What if your buffer is the EXACT size as your line?







