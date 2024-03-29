Project 1 -- Autocomplete
=========================

In this project, you will write a fast implementation of the autocomplete functionality.

You will work with files that contain a large number of terms, along with the importance weight associated with those terms.

The autocomplete task is to quickly retrieve the top terms that match a query string. For example, if the query string is "Eng", you matches might be "English",
"Engineering", and "EngSci".

To accomplish the task, you will:

* Read in the entire file of terms, and sort the terms in lexicographic ordering. This sorted list will be reused for multiple queries.

* Use binary search to find the location of the first term in lexicographic ordering that matches the query string, as well as the last term in lexicographic oredering that matches the query string.

* Extract the terms that match the query string, and sort them by weight.

* Extract the top matching terms by weight

Throughtout, you will use the following struct:
struct term{
    char term[200]; // assume terms are not longer than 200
    double weight;
};


Part 1
======
Write a function with the signature 

void read_in_terms(struct term **terms, int *pnterms, char *filename);

The function takes in a pointer to a pointer to struct term, a pointer to an int, and the name of a file that is formatted like cities.txt.

The function allocates memory for all the terms in the file and stores a pointer to the block in *terms. The function stores the number of terms in *pnterms. The function reads in all the terms from filename, and places them in the block pointed to by *terms.

The terms should be sorted in lexicographic order.

Part 2(a)
=========
Write a function with the signature
int lowest_match(struct term *terms, int nterms, char *substr);

The function returns the index in terms of the first term in lexicographic ordering that matches the string substr.

This function must run in O(log(nterms)) time, where nterms is the number of terms in terms.

You can assume that terms is sorted in ascending lexicographic ordering.

Part 2(b)
=========
Write a function with the signature
int highest_match(struct term *terms, int nterms, char *substr);

The function returns the index in terms of the last term in lexicographic order that matches the string substr.

This function must run in O(log(nterms)) time, where nterms is the number of terms in terms.

You can assume that terms is sorted in ascending lexicographic ordering.

Part 3
======
Write a function with the signature 

void autocomplete(struct term **answer, int *n_answer, struct term *terms, int nterms, char *substr);

The function takes terms (assume it is sorted lexicographically), the number of terms nterms, and the query string substr, and places the answers in answer, with *n_answer being the number of answers. The answer should be sorted by weight.


Reading in files
================
The following code can be used to read in N lines of a text file line-by-line.

char line[200];
FILE *fp = fopen(filename, "r");
for(int i = 0; i < N; i++){
    fgets(line, sizeof(line), fp); //read in at most sizeof(line) characters
                                   //(including '\0') into line.
}

Sorting with qsort
==================
See here: https://www.tutorialspoint.com/c_standard_library/c_function_qsort.htm


Compilation instructions
========================
You should use the provided autocomplete.h. Your code should compile without errors with

gcc -Wall autocomplete.c main.c

with autocomplete.h placed in the same folder as the C files. You should modify your main.c to test your work, but we will be compiling your autocomplete.c with our version of autocomplete.h (which is the same as yourse) and our own main.c.

Submission instructions
=======================
TBA



Credit: the assignment was designed by Kevin Wayne, and adapted to C by Michael Guerzhoy