A buffer flush is the transfer of computer data from a temporary storage area to the computer’s permanent memory. For instance, 
if we make any changes in a file, the changes we see on one computer screen are stored temporarily in a buffer. 
Usually, a temporary file comes into existence when we open any word document and is automatically destroyed when we close our main file.
Thus when we save our work, the changes that we’ve made to our document since the last time we saved it are flushed from the buffer to permanent storage on the hard disk.

In C++, we can explicitly be flushed to force the buffer to be written. Generally, the std::endl function works the same by inserting a new-line character and flushes the stream.
stdout/cout is line-buffered that is the output doesn’t get sent to the OS until you write a newline or explicitly flush the buffer.
=========================================================================================================================================================================================================================

In C++, the output buffer is a temporary storage used to hold data before sending it to the console (or other output destinations). The buffer is flushed (i.e., its contents are sent to the output) in several cases:

1. When Using std::endl
std::endl inserts a newline (\n) and flushes the buffer immediately.
This ensures that everything before std::endl is printed right away.

std::cout << "Line 1" << std::endl; // Newline + buffer flush


2. When the Buffer Fills Up
The buffer automatically flushes when it reaches its capacity.


3. When Using std::flush
std::flush forces a buffer flush without adding a newline

std::cout << "Processing..." << std::flush; // Flush buffer but stay on the same line

4. When Using \n (Without Explicit Flush)
\n only adds a newline but does not flush the buffer.
The buffer may remain unflushed until it's full or flushed explicitly

5. When std::cout is Interacting with std::cin
The buffer flushes automatically before any std::cin input to ensure output appears before the user types.

6. When the Program Exits Normally
The output buffer is flushed before the program terminates.
