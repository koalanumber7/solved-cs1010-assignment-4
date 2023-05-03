Download Link: https://assignmentchef.com/product/solved-cs1010-assignment-4
<br>
# Question 1: SelectionSort————————————–

You have implemented counting sort, a simple and fastsorting algorithm that works on integers with a limitedrange.  But if the range of possible values to be sortedis huge or unlimited, then, counting sort does not workso well, and we need a different kind of sorting algorithm.

In this question, you are asked to implement the selectionsort algorithm.  The idea behind selection sort is simple,and we will illustrate with the sequence `15 23 16 4 42 8`.To sort an array with n values in increasing order,selection sort first finds the maximum value, then movesit into its proper place, that is, the last position.This move is achieved by swapping the value currently inthe last position with the maximum value.  For instance,for `15 23 16 4 42 8`, `42` is the maximum value and `8`wrongly occupies the position reserved for the maximumvalue.  After the first step, the array becomes`15 23 16 4 8 42`.

We now focus on sorting the first n-1 values in the array(since the maximum is in place).  To do this, we findthe second largest value and move it to the second lastposition.  The array becomes `15 8 16 4 23 48` after thissecond step.

The algorithm continues, moving the third largest valueinto place, the fourth largest value into place, etc.,until the array is sorted.  The table below shows theevolution of the array.

|Step| Array            | Remarks|—-|——————|———————————–| 0  | 15 23 16 4 42 8  | Input Array| 1  | 15 23 16 4  8 42 | Swap 42 and 8| 2  | 15 8 16 4  23 42 | Swap 23 and 8| 3  | 15 8 4 16 23 42  | Swap 16 and 4| 4  | 4 8 15 16 23 42  | Swap 15 and 4| 5  | 4 8 15 16 23 42  | 8 happens to already be in position| 6  | 4 8 15 16 23 42  | 4 must already be in position

Write a program `selectionsort` that, reads the following,from the standard input,

– n, the number of integers to sort– followed by n integers

into an array, and prints, to the standard output, n –1 lines, each line showing the array after moving thelargest or the next largest element into position.

You can assume that the input list of n integers to besorted are unique — i.e., no repetition.}

### Sample Run“`<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="791616100e0d39091c484840">[email protected]</a>:~/as04-skeleton$ ./selectionsort6 15 23 16 4 42 815 23 16 4 8 4215 8 16 4 23 4215 8 4 16 23 424 8 15 16 23 424 8 15 16 23 42<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="0768686e707347776236363e">[email protected]</a>:~/as04-skeleton$ ./selectionsort3 0 4 80 4 80 4 8<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="6708080e101327170256565e">[email protected]</a>:~/as04-skeleton$ ./selectionsort5 1 3 5 4 21 3 2 4 51 3 2 4 51 2 3 4 51 2 3 4 5“`

# Question 2: Mastermind———————————–

Mastermind is a board game played by two players, a_coder_ and a _codebreaker_.  The coder creates a codethat consists of four color pegs, chosen from pegs ofsix different colors (cyan, green, red, blue, purple,orange).  Repetition of the same colors is allowed.The codebreaker’s task is to guess the colors of the pegsand the order their appears in the code.

The game proceeds in rounds.  In each round, thecodebreaker tries to guess the code by specifying thecolors and the order of the colors.  The coder thenprovides feedback to the codebreaker, with two smaller pegsof black and white color.  A black color peg is placed ifthe codebreaker guesses correctly a peg in both positionand color.  A white color peg is placed if the codebreakerguesses correctly a peg in color but not in the position.Based on the feedback, the codebreaker guesses again in thenext round.  In the actual board game, the codebreaker winsif he guesses correctly every color in the correct order.The coder wins if the codebreaker failed to guess correctlyafter 8 guesses.

Write a program called `mastermind` that simulates theMastermind game.  The program first reads in the codefrom the standard inputs.  We denote the colors withtheir initials, `c`, `g`, `r`, `b`, `p`, `o`.  Hence,the code is a 4-letter word.  For instance, the code`prob` corresponds the pegs purple, red, orange, blue,in that order.  It then reads in a sequence of guesses,each is a 4-letter word consists of the letter `c`, `g`,`r`, `b`, `p`, `o`.  For each guess, the program printsout two numbers, the first is the number of pegs that arecorrect in both position and color.  The second is thenumber of pegs that are correct in color but not position.Note that we do not double count, so the total of thesetwo numbers is at most 4.

For example,  if the code is `prob` and the guess is`borg`, the program prints `0 3`.  Since none of theguesses is correct in both color and position.  The threecolors `b`, `o`, `r`, however, appear in the code, albeitin a different position.  Suppose the guess is `rrrr`,the program prints `1 0`.  The third `r` is the guess thatappears in the correct position and correct color.  Thereis no other `r` in the code, so the second number is 0.This example illustrates that we do not double count.We do not match the other `r`s in the guess to the `r`in the code, once the `r` in the code has been matched.

The program terminates when the guess is the same asthe code.

## Sample Run————-“`<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="b0dfdfd9c7c4f0c0d5818189">[email protected]</a>:~/as04-skeleton$ ./mastermindprobborg0 3rrrr1 0bbbb1 0oorr0 2prob4 0<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="8fe0e0e6f8fbcfffeabebeb6">[email protected]</a>:~/as04-skeleton$ ./mastermindcccpborg0 0prob0 1oooc0 1crrc1 1pcpc1 2cpcp3 0cccp4 0“`