# Java Misc Interview Programs


1. Fibonacci series (solution)
Write a simple Java program which will print Fibonacci series e.g. 1 1 2 3 5 8 13 ... . up to a given number. Be prepare for cross questions like using iteration over recursion and how to optimize the solution using caching and memoization.

2. Prime number (solution)
Write a Java program to check if a given number is prime or not. Remember, a prime number is a number which is not divisible by any other number e.g. 3, 5, 7, 11, 13, 17 etc. Be prepared for cross e.g. checking till the square root of a number etc.

3. String Palindrome (solution)
You need to write a simple Java program to check if a given String is palindrome or not. A Palindrome is a String which is equal to the reverse of itself e.g. "Bob" is a palindrome because of the reverse of "Bob" is also "Bob".  Though be prepared with both recursive and iterative solution of this problem. The interviewer may ask you to solve without using any library method e.g. indexOf() or subString() so be prepared for that.


4. Integer Palindrome (solution)
This is generally asked as follow-up or alternative of the previous program. This time you need to check if given Integer is palindrome or not. An integer is called palindrome if its equal to its reverse e.g. 1001 is a palindrome but 1234 is not because the reverse of 1234 is 4321 which is not equal to 1234. You can use divide by 10 to reduce the number and modulus 10 to get the last digit. This trick is used to solve this problem.

5. Armstrong number (solution)
A number is called an Armstrong number if it is equal to the cube of its each digit. for example, 153 is an Armstrong number because 153= 1+ 125+27 which is equal to 1^3+5^3+3^3. You need to write a program to check if given number is Armstrong number or not.


6. Avoiding deadlock in Java (solution)
This is one of the interesting programs from Java Interviews, mostly asked to 2 to 3 years of experienced programmers or higher. Interviewer simply asked you to write code where a resource is accessed by multiple threads. You need to write code in such a way that no deadlock should occur. The trick to solving this problem is acquiring resources in an order and release them in reverse order e.g. first acquire resource R1 and only if you have got R1 go for R2. This way you can avoid deadlock.


7. Factorial (solution)
This is one of the simplest programs you can expect on interviews. It is generally asked to see if you can code or not. Sometimes interviewer may also ask about changing a recursive solution to iterative one or vice-versa.

8. Reverse a String (solution)
This problem is similar to the String Palindrome problem we have discussed above. If you can solve that problem you can solve this as well. You can use indexOf() or substring() to reverse a String or alternatively, convert the problem to reverse an array by operating on character array instead of String.

9. Remove duplicates from array (solution)
Write a program to remove duplicates from an array in Java without using the Java Collection API. The array can be an array of String, Integer or Character, your solution should be independent of the type of array. If you want to practice more array based questions then see this list of top 30 array interview questions from Java interviews.

10. Printing patterns (solutions)

11. Print repeated characters of String? (solution)

12. GCD of two numbers (solution)

13. Square root of number (solution)
You need to write a program to calculate the square root of a number without using the Math.sqrt() function of JDK. You need to write your logic and method to calculate the square root. You can though use popular algorithm e.g. Newton's method.

14. Reverse array in place (solution)

15. Reverse words of sentence (solution)

16. Leap year (solution)

17. Binary search (solution)

18. String Anagram (solution)
Write a program to check if two given String is Anagram of each other. Your function should return true if two Strings are Anagram, false otherwise. A string is said to be an anagram if it contains same characters and same length but in different order e.g. army and Mary are anagrams. You can ignore cases for this problem but you should clarify that from your interview.



19. Design a Vending Machine (solution)
This one of the popular OOAD (object oriented analysis and design) question from Java Interviews. You will be given 3 hours to design and code a vending machine satisfying some of the business requirements. You also need to write unit tests to prove your code satisfy those requirements. You can see this article for more object oriented analysis questions.

20. Reverse a number (solution)

21. The first non-repeated character of String (solution)

22. Finding Middle element of linked list in one pass (solution)

23. Pre-order traversal (solution)

24. Pre-order traversal without recursion (solution)

25. In order traversal (solution)

26. In order traversal without recursion (solution)

27. Post-order traversal (solution)

28. Post order traversal without recursion (solution)

29. Print all leaves of binary tree (solution)


30. Sort array using quicksort (solution)
You need to write a Java program to sort an array of integers using quick sort algorithm. You cannot use any library method e.g. JDK or a third party library, which means, you need to first implement the quicksort algorithm and then sort the array.


31. Insertion sort (solution)
Write a program to implement the insertion sort algorithm in Java. The program should take an unsorted array and sort it using insertion sort algorithm Also explain the best case and worst case time and space complexity of Insertion sort algorithm.

32. Bubble sort (solution)
Write a program to implement the bubble sort algorithm in Java. You can use basic operators and functions but sorting functions from Java API is not allowed.

33. Transpose a matrix (solution)

34. Print all permutations of String (solution)
Write a Java program to print all permutations of a given String. For example, if given String is "GOD" then your program should print all 6 permutations of this string e.g. "GOD", "OGD", "DOG", "GDO", "ODG", and "DGO".

Java Programming Interview Questions for 2 to 3 years 


35. Reverse a String in place (solution)

36. Adding two matrices in Java (solution)

37. Matrix multiplication (solution)

38. Removal all white space from String (solution)

39. Reverse a linked list (solution)
Write a program to reverse a singly linked list in Java. You can use iteration and recursion to solve this problem but you should reverse linked list in place.

Java Programming Interview Questions for experienced


40. Find the length of linked list (solution)
Just write a program in Java to find the length of a singly linked list in one pass i.e. in just one iteration of singly linked list.


41. Check if linked list has loop (solution)
Write a program to check if given linked list has a loop or not. Sometimes a linked list get corrupt and two nodes point to the same node, which forms the loop or cycle in the linked list.

42. Find the start of loop in linked list (solution)

43. Find middle element of linked list (solution)

44. Find the 3rd element from the tail linked list (solution)
You need to write a program to find the 3rd element from the tail of a singly linked list. You need to solve this problem without iterating twice. If you want more linked list questions you can see the article about frequently asked linked list interview questions.

Java Coding Interview Questions



44. Convert a linked list to a binary tree (solution)
It's possible to convert a doubly linked list to a binary tree, you need to write a Java program which takes a doubly linked list and returns a binary tree.


45. Sort a linked list (solution)
You need to given an unsorted linked list and you need to write a program in Java to sort them in ascending order of the values in each node.


46. Iterative Quicksort (solution)
You need to write a Java program to implement quicksort sorting algorithm without recursion. You can use essential JDK classes and programming constructs, but recursion is not allowed.


46. Bucket sort (solution)
This program is increasingly getting popular on Java interview because it sorts a given array in linear time. Though there are a lot of prerequisite e.g. you must know the maximum value present in the array, it is a very interesting problem from interview point of view. You need to write a program to implement bucket sort algorithm in Java. If you are not familiar with Bucket sort or any other linear sorting algorithm, I suggest you to first read a good on algorithms e.g. Introduction to Algorithms by Thomas H. Cormen.

Top 50 Java Programs from Coding Interviews



47. Counting sort (solution)
This is another problem which is similar to the previous one because counting sort is also a linear sorting algorithm. Just remember that bucket sort and counting sort are different algorithms, so it's also good to state how they are different.


48. Check if two string rotation of each other
Write a program which accepts two given String and checks if they are the rotation of each. If they then return true otherwise return false. A String is said to be a rotation of other string if they contain same characters and the sequence is rotated across any character e.g "dabc" is a rotation of "abcd" but "dbac" is not.  If you want to practice more string based questions, you can also see my list of 20 String based algorithm questions from Java interviews.


49. LRU cache in Java (solution)
Write a program to implement an LRU cache in Java.  An LRU cache means Least Recently Used Cache which removes the least recently used element if the cache is full. You can use LinkedHashMap to implement LRU cache in Java.

Java Programming Interview Questions



50. Merge sort
Implement the merge sort algorithm in Java. You can write a recursive or iterative solution, whichever you like. You also need to explain the time and space complexity for the best, worst, and average case.

20) How to check whether user input is number or not in java?

Write a java program to check whether user has entered a number or not. [Solution]

24) Decimal To Binary, Decimal To Octal And Decimal To HexaDecimal In Java
26) Reverse and add until you get a palindrome

29) Roman equivalent of a decimal number

31) Launch external applications through java code
33) String immutable program
How to sort a text file in java?
Finding the most repeated word in a text file.
 
 1. How to find the missing number in given integer array of 1 to 100? (solution)

2. How to find the duplicate number on a given integer array? (solution)

3. How to find the largest and smallest number in an unsorted integer array? (solution)

4. How to find all pairs of integer array whose sum is equal to a given number? (solution)

5. How to find duplicate numbers in an array if it contains multiple duplicates? (solution)

6. How to remove duplicates from given array in Java? (solution)

7. How to sort an integer array in place using QuickSort algorithm? (solution)

8. How to remove duplicates from an array in place? (solution)

9. How to reverse an array in place in Java? (solution)

10. How to find multiple missing numbers in given integer array with duplicates? (solution)

I have linked to all the solution but you should try to solve them by yourself before looking at the solution, especially if you have time. That's the only sure way to learn to programme by solving these coding questions.

If you think these 10 questions from the array is not enough and you are interested in solving more array-based programming problems then you can also check out this 30 array based coding questions for more practice.




 



2. String-based Coding Interview Questions
After array, String is the next popular topic on Programming job interviews, but if you have a good understanding of array then you can easily deal with String programming questions because String is nothing but a character array.

The string is implemented differently in different programming language e.g. in C it's a NULL terminated character array but in Java, it's an object. Though, you can still get access to the underlying array to apply your logic.

Here is a list of some of the frequently asked coding questions which are based on String. Though some of them are quite old, you can still expect this in your programming job interview in 2018.

11. How to Print duplicate characters from String? (solution)

12. How to check if two Strings are anagrams of each other? (solution)

13. How to print first non repeated character from String? (solution)

14. How to reverse a given String using recursion? (solution)

15. How to check if a String contains only digits? (solution)

16. How to find duplicate characters in a String? (solution)

17. How to count a number of vowels and consonants in a given String? (solution)

18. How to count the occurrence of a given character in String? (solution)

19. How to find all permutations of String? (solution)

20. How to reverse words in a given sentence without using any library method? (solution)

21. How to check if two String is a rotation of each other? (solution)

22. How to check if given String is Palindrome? (solution)

Similar to an array, I have also linked to a solution for all of these String problems but if you want to get most of this article, you better solve these questions without looking at the answers.

Only when you stuck and running out-of-time, you can look at the solution. You can also learn from it by comparing your solution with the solution I have given. It's not necessarily to be same but you can learn a lot by comparing them and if you need more practice, here is another list of 20 String algorithm questions.


Top 50 Coding Interview Questions



3. Linked list based Programming Interview Questions
Along with array and string, a linked list is another popular data structure in programming world as well as on coding interviews. You will find a lot of questions on linked list e.g. reversing a linked list, adding a new element, removing an element from middle etc.

It's also the counterpart of array data structure. While array stores elements on contiguous memory location, the linked list stored them at different locations and find them by storing there address. a linked list is made of nodes, an internal data structure which holds the value as well as the address of next node.

Becuase of its structure, it's easier to add and remove elements from the linked list e.g. on O(1) time if you are adding or removing from the head but the search is equally difficult and takes O(n) time, as you have to literally walk through each element.

Anyway, here is a collection of some of the simple and tricky linked list based coding question for your practice:

23. How to find middle element of a singly linked list in one pass? (solution)

24. How to check if a given linked list contains cycle? How to find the starting node of the cycle?(solution)

25. How to reverse a linked list? (solution)

26. How to reverse a singly linked list without recursion? (solution)

27. How to remove duplicate nodes in an unsorted linked list? (solution)

28. How to find the length of a singly linked list? (solution)

29. How to find the 3rd node from the end in a singly linked list? (solution)

30. How do you find the sum of two linked list using Stack? (program)

Similar to array and string, I have also linked to all the solutions but you should only look them once you solved the problem on your own or you feel stuck.

A key to solving linked list is a good understanding of recursion because a linked list is a naturally recursive data structure, for example, if you take one node out of the linked list, the result is another linked list.

This means most of the linked list based problems has an easy recursive solution than their iterative version. And if you need more practice, here is another list of 30 linked list programming questions for your reference.

Top 75 Programming Interview Questions and Solutions



4. Binary Tree based Coding Interview Questions
A tree is another popular data structure in the programming world and coding interviews. Unlike array and linked list, which are considered linear data structure, a tree is considered a hierarchical data structure and used to arrange information in hierarchical order.

There are a lot of different types of tree e.g. binary tree, binary search tree, AVL tree, Red Black tree etc but Binary and Binary search tree are also known as BST are two of the most popular ones and most of the question are based upon them.

Some questions are also based upon theoretical knowledge of tree data structure e.g. finding the height of the tree, finding leaf nodes, checking if the tree is balanced or not etc, hence you should also spend some time to learn the basics, along with practicing coding questions.

Anyway, here is a list of popular binary tree and binary search tree based coding question to practice before your job interview:

30. Can you write a program to implement a binary search tree?  (solution)

31. How do you perform Pre-order traversal in given binary tree? (solution)

32. Write a Program to traverse a given binary tree in Pre-order without recursion (solution)

33. How to perform an In order traversal in given binary tree? (solution)

34. How to print all nodes of given binary tree using inorder traversal without recursion (solution)

35. How to implement Post-order traversal algorithm? (solution)

36. How to traverse a binary tree in Post order traversal without recursion (solution)

37. How to Print all leaves of a binary search tree? (solution)

38. How to count a number of leaf nodes in given binary tree? (solution)

39. How to perform a binary search in given array? (solution)

Like an array, linked list and string questions, I have also linked to all solution for binary tree questions but you should only look them once you have tried it yourself.

One trick I would like to share with you while solving tree questions is to remember that, similar to a linked list, the tree is also a recursive data structure and most of the tree based problems has an easy recursive solution.

For example, a subtree is also a tree which means you can apply same steps to subtree can devise a recursive solution. In above list, many popular tree algorithms e.g. pre-order, post-order, in-order are implemented recursively as well as iterative.

If you don't feel confident to solve these problems and want to refresh your knowledge of binary tree and other data structure before attempting these questions, then you should check out Data Structures and Algorithms: Deep Dive Using Java from Udemy.

Top 75 Essential Programming Interview Questions to Crack Any Coding Interview



5. Miscellaneous Programming Interview Questions
Even though data structure based questions makes the bulk of Coding Interview, there are always some questions from topics like sorting algorithms, bit manipulation, software design, Dynamic Programming, and other logical and tricky questions.

In this list below, you will find most of the common searching and sort questions as well as a couple of design and bit manipulation questions.

40. How to implement Bubble Sort algorithm? (solution)

41. How to implement Iterative QuickSort Algorithm? (solution)

42. How to implement Insertion Sort Algorithm? (solution)

43. How to implement Merge Sort Algorithm? (solution)

44. How to implement Bucket Sort Algorithm? (solution)

45. How to implement Counting Sort Algorithm? (solution)

46. How to implement Radix Sort Algorithm? (solution)

47. How to swap two numbers without using the third variable? (solution)

48. How to check if two rectangles overlap with each other? (solution)

49. How to design a Vending Machine? (solution)

50. How to implement an LRU Cache in your favorite programming language? (solution)

51. How to check if a given number is a Palindrome? (solution)

52. How do you check if a given number is an Armstrong number? (solution)

53. How do find all prime factors of a given number? (solution)

54. How do check if a given number is a positive or negative in Java? (solution)

55. How to find the largest prime factor of a given integral number? (solution)

56. Write a Program to print all prime numbers up to a given number? (solution)

57. Write a Program to print Floyd's triangle? (solution)

58. Write a Program to print Pascal's triangle? (solution)

59. How to calculate the square root of a given number? (solution)

60. How to check if given number is a prime number? (solution)

61. How to implement Sieve of Eratosthenes Algorithm? (solution)

62. How to add two numbers without using plus operator in Java? (solution)

63. Write a Program to subtract two binary numbers? (solution)

64. Write a Program to transpose a Matrix? (solution)

65. Write a Program to add or subtract two Matrices? (solution)

66. Write a Program to multiply two Matrices in Java? (solution)

67. How to calculate the average of all numbers in given array? (solution)

68. How to check if a given number is even/odd without using Arithmetic operator? (solution)

69. Write a Program to find GCD of two numbers using Euclid's Algorithm? (solution)

70.  How to find the number of 1s (the Set bit) in a given Bit Sequence? (solution)

71. Write a Program to given Pyramid structure? (solution)

72. How to find the highest repeating world from a given file in Java? (solution)

73. How to reverse given Integer in Java? (solution)

74. How to convert a decimal number to binary in Java? (solution)

75. How to check if a given year is a leap year in Java? (solution)

--------------------------------------------------------------------
Java Program To Check Whether User Input Is Number Or Not
How To Launch External Applications Through Java Program
Java Program To Reverse A String
How To Find Trigonometric Values Of An Angle?
Java Program To Find Common Elements Between Two Arrays
Java Puzzle – Find Missing Number In An Array
How To Check The Equality Of Two Arrays In Java?
Check Whether One String Is Rotation Of Another?
Java Program To Check Whether Given Number Is Binary Or Not
How To Find An Armstrong Number In Java?
Anagram Program In Java – Four Methods
How To Generate Random Numbers In Java?
How To Find Second Largest Number In An Integer Array?
How To Find Largest Number Less Than Given Number And Without Given Digit?
How To Count Occurrences Of Each Character In String In Java?
How To Find Duplicate Characters In A String In Java?
How To Find Sum Of All Digits Of A Number In Java?
How To Find All Pairs of Elements In An Array Whose Sum Is Equal To A Given Number?
How To Find All The Leaders In An Integer Array?
How To Separate Zeros From Non-Zeros In An Array?
21 Frequently Asked Java Interview Programs On Strings
Java Program To Implement Selection Sort
How To Find Continuous Sub Array Whose Sum Is Equal To Given Number?
How To Create Pyramid Of Numbers In Java?
How To Remove Duplicate Elements From ArrayList In Java?
How To Reverse The String With Preserving The Position Of Spaces?
How To Find Percentage Of Uppercase Letters, Lowercase Letters, Digits And Special Characters In String?
How To Find Roman Equivalent Of A Decimal Number In Java?
Decimal To Binary, Decimal To Octal And Decimal To HexaDecimal In Java
How To Perform Matrix Operations In Java?
How To Reverse And Add A Number Until You Get A Palindrome?
How To Reverse Each Word Of A String In Java?
85+ Popular Java Interview Programs With Solutions
String To Integer And Integer To String Conversion In Java
How To Create Spiral Of Numbers (Spiral Matrix) In Java?
How To Find First Repeated And Non-Repeated Character In A String?
How To Print Floyd’s Triangle In Java?
How To Check If Number Belongs To Fibonacci Series Or Not?
How To Find All Permutations Of String In Java?
How To Sort An ArrayList In Java With Examples?
How To Convert HashMap To ArrayList In Java?
How To Find Number Of Characters, Words And Lines In File In Java?
How To Synchronize ArrayList, HashSet And HashMap In Java?
How To Append Text To A File In Java?
How To Remove Duplicate Elements From An Array In Java?
How To Stop A Thread In Java?
How To Find The Most Repeated Word In Text File In Java?
How To Swap Two String Variables Without Using Third OR Temp Variable In Java?
How To Reverse An Array In Java?
How To Count Occurrences Of Each Element In An Array?
How To Find Longest Substring Without Repeating Characters In Java?
Array To ArrayList And ArrayList To Array In Java With Examples
How To Sort A Text File In Java? – Example Program
Diamond Pattern Program In Java
How To Reverse An ArrayList In Java?
20 Different Number Pattern Programs In Java
How To Format Date In Java?
How To Set File Permissions In Java With Examples?
Symmetric Matrix Program In Java
How To Find Frequency Of All Digits In Number In Java?
Difference Between Two Dates In Java – Years, Days, Hours, Minutes, Seconds
How To Compare Two Text Files In Java?
How To Read And Write Images In Java? – ImageIO Example
How To Find Union And Intersection Of Multiple Arrays In Java?
How To Find Saddle Point Of A Matrix In Java?
How To Check Harshad Number (Niven Number) In Java?
How To Replace Specific String In Text File In Java?
How To Find The Most Frequent Element In Array In Java?
How To Remove All Vowels From String In Java?
Frequently Asked Java Array Interview Programs
How To Make Text File Read-Only In Java?
How To Reverse A Sentence Word By Word In Java?
10 Prime Number Programs In Java
Array Rotation Program In Java
Palindrome Program In Java
Array Element Removal Programs In Java
How To Remove White Spaces from String In Java?
How To Find Duplicates In Array In Java?
List All Files In Directory – With Java 8 Examples
--------------------------------------------
List Of All Interview Programs:
How to reverse Singly Linked List?
Find out duplicate number between 1 to N numbers.
Find out middle index where sum of both ends are equal.
Write a singleton class.
Write a program to create deadlock between two threads.
Write a program to reverse a string using recursive algorithm.
Write a program to reverse a number.
Write a program to convert decimal number to binary format.
Write a program to find perfect number or not.
Write a program to implement ArrayList.
Write a program to find maximum repeated words from a file.
Wrie a program to find out duplicate characters in a string.
Write a program to find top two maximum numbers in a array.
Write a program to sort a map by value.
Write a program to find common elements between two arrays.
How to swap two numbers without using temporary variable?
Write a program to print fibonacci series.
Write a program to find sum of each digit in the given number using recursion.
Write a program to check the given number is a prime number or not?
Write a program to find the given number is Armstrong number or not?
Write a program to convert binary to decimal number.
Write a program to check the given number is binary number or not?
Write a program for Bubble Sort in java.
Write a program for Insertion Sort in java.
Write a program to implement hashcode and equals.
How to get distinct elements from an array by avoiding duplicate elements?
Write a program to get distinct word list from the given file.
Write a program to get a line with max word count from the given file.
Write a program to convert string to number without using Integer.parseInt() method.
Write a program to find two lines with max characters in descending order.
Write a program to find the sum of the first 1000 prime numbers.
Find longest substring without repeating characters.
Write a program to remove duplicates from sorted array.
How to sort a Stack using a temporary Stack?
Write a program to print all permutations of a given string.
Implement Binary Search Tree (BST)
Find min and max value from Binary Search Tree (BST)
Find height of a Binary Search Tree (BST)
Implement Binary Search Tree (BST) Level order traversal (breadth first).
Implement Binary Search Tree (BST) pre-order traversal (depth first).
Implement Binary Search Tree (BST) in-order traversal (depth first).
Implement Binary Search Tree (BST) post-order traversal (depth first).
How to check the given Binary Tree is Binary Search Tree (BST) or not?
How to delete a node from Binary Search Tree (BST)?
Write a program to find common integers between two sorted arrays.


https://www.softwaretestinghelp.com/core-java-interview-questions/
https://java2blog.com/introduction-to-aws-certifications/
