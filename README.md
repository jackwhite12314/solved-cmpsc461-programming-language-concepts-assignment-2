Download Link: https://assignmentchef.com/product/solved-cmpsc461-programming-language-concepts-assignment-2
<br>
For this assignment, you need to submit your solution as one single file named as “code.rkt” to Gradescope. You may NOT use any of Schemes imperative features (assignment/loops) or anything else not covered in class. You should use Racket (https://racket-lang.org) for your implementation. For all problems, you can assume all inputs obey the types as specified in a problem.

Testing and Auto Grading We will use the Gradescope Autograder feature to grade the assignment. So it is important to start from the code template “code.rkt” on Canvas, which only has dummy implementations, but is nevertheless useful since it obeys a few important requirements for auto grading, such as file name, function names etc. For you submission, just replace the dummy definitions with your implementations.

Before the submission deadline, you can see your partial score based on a public set of tests on Gradescope. You can debug your code and resubmit any time before the deadline. After the deadline, a final grade will be assigned based on the entire testsuite, including the public and a few extra private tests.

Debug Hint: if the autograder hangs for <em>&gt; </em>5 minutes, or you see an error message like “The results uploaded

to Gradescope were not formatted correctly.”, that means your submitted code fails to terminate on at least one of the public or hidden private tests. Carefully check your code to avoid non-terminating cases.

Problem 1 [20pt] In lecture, we define Church number <em><u>n </u></em>as <em>λf n. </em>(<em>f<sup>n </sup>z</em>), where (<em>f<sup>n </sup>z</em>) represents the n-fold composition of function f applied to z (i.e., <em>f</em>(<em>f</em>(<em>…</em>(<em>f z</em>))) where <em>f </em>is repeated for <em>n </em>times).

<ol start="2">

 <li>(5pt) Implement a function funPower, which takes a function <em>f</em>, an integer <em>n </em>and returns the function <em>f<sup>n</sup></em>. For example, ((funPowersqrt2)16) should return 2.</li>

 <li>(5pt) Implement a function encode, which takes a natural number <em>n </em>and returns the church encoding of</li>

 <li><em>n</em>. For example, (encode2) should return <u>2 </u>(i.e., the function <em>λf. λz. f </em>(<em>f z</em>)).</li>

 <li>(5pt) Implement a function decode, which takes <em><u>n </u></em>(the church encoding of some natural number <em>n</em>) and returns <em>n</em>. For example, (decode(encode2)) should return 2.</li>

 <li>(5pt) Implement a function MULT, which takes two church numbers <em>n</em><a href="#_ftn1" name="_ftnref1"><u><sup>[1]</sup></u></a>, <em>n</em><u><sub>2 </sub></u>and returns the church number of <em>n</em><sub>1</sub>× <em>n</em><sub>2 </sub>(i.e., <em>n</em><u><sub>1</sub></u><u>× </u><em>n</em><u><sub>2</sub></u>). For example, (decode(MULT(encode2)(encode3))) should be 6.</li>

</ol>

Problem 2 [5pt] Define a recursive function merge, which takes two sorted lists of numbers, and returns one merged list where all numbers are sorted. Assume that all elements are sorted in the increasing order.

For example,

(merge ’(2 7) ’()) ; returns (2 7)

(merge ’(1 1 2) ’(1 3 5)) ; returns (1 1 1 2 3 5)

(merge ’(1 1 6 8) ’(2 7)) ; returns (1 1 2 6 7 8)

Problem 3 [5pt] Define a recursive function findMax to return the largest element from a list of nonnegative numbers (note that the list may contain nested lists). If the list is empty, your implementation should return 0. For example,

(findMax ’(4 5 1))                                         ; returns 5

(findMax ’(5 1 (3 (4 8)))) ; returns 8

(findMax ’(1 3 (3 3) () 6 (1))) ; returns 6

Problem 4 [5pt] Define a recursive function lstEvenSum, which when given a list of numbers, it returns the sum of numbers at <em>even </em>positions in the list. Your implementation should return 0 if the list is empty or has length 1. You can assume that the input is a list of numbers without nested lists. For example,

(lstEvenSum ’(1)) ; returns 0

(lstEvenSum ’(1 2 3)) ; returns 2

(lstEvenSum ’(1 2 3 4)) ; returns 6

Problem 5 [15pt] Implement the following functions in Scheme using map and foldl. DO NOT use recursive definition for this problem.

<ol>

 <li>(5pt) Define a function trunc, which takes a lower bound <em>a</em>, an upper bound <em>b </em>and a list of numbers, and replaces all numbers that are <em>&lt; a </em>with <em>a </em>and all numbers that are <em>&gt; b </em>with <em>b</em>. For example,</li>

</ol>

(trunc 0 1 ’(-2 -1 0 1 2)) ; returns ’(0 0 0 1 1)

(trunc 0.5 1.5 ’(-2 -1 0 1 2)) ; returns ’(0.5 0.5 0.5 1 1.5)

(trunc 1 1 ’(-2 -1 0 1 2)) ; returns ’(1 1 1 1 1)

<ol>

 <li>(5pt) Define a function lstOR, which takes a list of Booleans and returns #f if and only if all of the Booleans are false. For your convenience, (lstOR <sup>0</sup>()) is defined as # For example,</li>

</ol>

(lstOR ’(#t #f)) ; returns #t

(lstOR ’(#f #f)) ; returns #f

(lstOR ’()) ; returns #f

<ol>

 <li>(5pt) Define a function geq, which takes two lists of numbers (<em>x</em><sub>1 </sub><em>x</em><sub>2 </sub><em>… x<sub>n</sub></em>), (<em>y</em><sub>1 </sub><em>y</em><sub>2 </sub><em>… y<sub>n</sub></em>) and returns #t if and if and only if <em>x<sub>i </sub></em>≥ <em>y<sub>i </sub></em>for all 1 ≤ <em>i </em>≤ <em>n</em>. You can assume that both lists have the same length.</li>

</ol>

For example,

(geq ’(5 4 3) ’(2 3 3)) ; returns #t

(geq ’(1 0) ’(0 1)) ; returns #f

(geq ’() ’()) ; returns #t

Assignment 2, Cmpsc 461                                                                                                                                                       2/2

<a href="#_ftnref1" name="_ftn1">[1]</a> /2