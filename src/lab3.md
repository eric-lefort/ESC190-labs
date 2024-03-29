# Lab 3
1. The function strcat in <string.h> appends a source string to a destination
   string. It returns the destination string. Write a version of the function
   char *my_strcat(char *dest, char *src)

2. Write a recursive version of strcmp. The signature must be
   int my_strcmp_rec(char *str1, char *str2).
   The function should return 0 if the contents of str1 and str2
   are the same.
   If the contents of str1 and str2 are not the same, and the first
   character that doesn't match is at location i, the function
   should return str1[i]-str2[i].
   Each character corresponds to an integer value. For example,
   'A' corresponds to 65, 'B' corresponds to 66, ..., 'Z' 
   corresponds to 90, 'a' corresponds to 97, 'b' corresponds to
   98, ... 
   https://simple.wikipedia.org/wiki/ASCII#/media/File:ASCII-Table-wide.svg
   Returning the difference between the first pair of unmatched characters
   makes it so that strcmp returns a negative value if str1 comes before
   str2 in a lexicographic order.

3. The C library function atoi converts a string to an integer. Write
   your own version of the function, with the signature
   int atoi(char *str)
   Hints:
   * The function isdigit (defined in <ctype.h>) can be used to tell if 
   a character is a digit
   * You can convert a digit c to an integer value using c-'0'

4. Implement Floyd's cycle-finding algorithm for a linked list in C
   https://en.wikipedia.org/wiki/Cycle_detection#Floyd's_tortoise_and_hare
   Your function should return 1 if there is a cycle in the linked list,
   and 0 otherwise. (Note that the linked code does more than that).

   Test your algorithm./**/
