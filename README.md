Download Link: https://assignmentchef.com/product/solved-csci2500-homework-1-matrix-multiplication
<br>
In this first individual homework assignment, you will implement matrix multiplication. (For you Math dual majors, you’re welcome.) If you need a refresher in how matrix multiplication works, look in a math textbook or check out Wikipedia. Note that we will revisit this topic in the future, but for now you will implement your algorithm in C.

Command-Line Arguments

Four command-line arguments are required (i.e., argv[1] through argv[4]). The first two commandline arguments specify how many rows and columns are in the first matrix, and the second two command-line arguments specify how many rows and columns are in the second matrix. To properly translate the command-line arguments, use the atoi() function, which you can learn more about by checking out the man page.

Once the pair of matrix dimensions are identified and validated, prompt the user to enter the values (non-negative integers) of each matrix. Use scanf() to read in the appropriate values.

<h2>Example Program Execution</h2>

On the next page are example program executions that you can use to better understand how your program should work and how you can begin to test your code. Note that your program must properly return either EXIT_SUCCESS or EXIT_FAILURE, which you can verify via echo$?.

Also, be sure to match the output formatting exactly as shown (to ensure full credit on Submitty). In particular, when displaying a matrix, each line must start with ‘[’ and end with ‘]’ (as shown below). Further, right justify and vertically line up your columns as follows:

[12 34 5567]

[ 8 9 123]

[45 67              8]

[ 9 10             11]

Example program executions are shown below:

bash$ ./a.out 2 3 3 1

Please enter the values for the first matrix (2×3):

1 2 3

4 5 6

Please enter the values for the second matrix (3×1):

7

8

9

[1 2 3]

[4 5 6]

multiplied by

[7]

[8] [9] equals

[ 50]

[122] bash$ echo $?

0

bash$ ./a.out 4 5 6 7 ERROR: Invalid inputs! bash$ echo $?

1

bash$ ./a.out 2 2 2 2

Please enter the values for the first matrix (2×2):

1 2

3 4

Please enter the values for the second matrix (2×2):

5 6

7 8

[1 2] [3 4] multiplied by [5 6]

[7 8]

equals [19 22] [43 50] bash$ echo $? 0

2

<h2>Starting Point</h2>

Below is a starting point for your code (e.g., hw1.c):

/* hw1.c */

/* NAME: &lt;your-name-here&gt; */

#include &lt;stdio.h&gt;

#include &lt;stdlib.h&gt; #include &lt;math.h&gt;

int main( int argc, char * argv[] )

{

/* Ensure we have the correct number of command-line arguments */ if ( argc != 5 )

{ fprintf( stderr, “ERROR: Invalid inputs!
” ); return EXIT_FAILURE;

}

return EXIT_SUCCESS;

}

Note that if an error occurs, use either perror() or fprintf( stderr, “…” ), depending on whether the global errno is set.