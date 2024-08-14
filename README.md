# Most-Anagrams-Finder In Java
Final Project Created Based on Learnings of Data Structures.

---

## Preview:
This was the capstone project of my Data Structures in Java class at Columbia. It was a project that was meant to utilize almost all of our learnings over the semester. While I am very proud of my code, as I say with absolute honesty and humility that  

### ***I recieved a perfect grade on this project***,   

I cannot publicly share my code for this project. Posting my code would be violating my school's Academic Honesty Policy, as this project could be a future assignment for students taking this class in the future.

With all that being said, if you are a recruiter or company that would like to see or go over my code with me, I would be more than estatic to share it with you privately. Please message me on [LinkedIn]([www.linkedin.com/in/olivia-a-494759269](https://www.linkedin.com/in/olivia-a-494759269/)) or right here on GitHub. Thank you!

### Below is the specification guide given to me from my professor on what exactly my project was supposed to accomplish. It gives the do's and do nots, example outputs, etc. I will also include the test files they gave us. Please enjoy!

---

### Objective

Your goal is to use several data structures and a sorting algorithm you developed this semester to develop a program that finds the word or words with the most anagrams. Insertion sort works well on small amounts of data, which is perfect for this task. BSTreeMap, RBTreeMap, and MyHashMap implement the MyMap interface. So, with proper
object-oriented programming techniques, specifically the use of polymorphism, you can create any one of these data structures and refer to it from a MyMap reference. Though all
three classes implement the same interface, their methods are implemented very differently, leading to different execution times on the computer. You will time your
program’s execution to see how each of the data structures performs.

---

### Problem

You will develop a command line Java application to find the word or words with the most anagrams. An anagram is another word that uses all the characters of the given word, just in
a different order or with a different capitalization. For instance, “tea” and “eat” are anagrams; “tae” and “aet” are merely permutations of the characters of the word and are
not considered anagrams because they are not words provided in the dictionary file. “Tea” and “Eat” are anagrams even though they have different capital letters. The name of the
public class **must be MostAnagramsFinder**, and it must reside in a file named **MostAnagramsFinder.java**.

### - Parsing Command Line Arguments

The program will take in two command line arguments. If the number of arguments supplied is incorrect, the program will print the usage message  
``"Usage: java MostAnagramsFinder <dictionary file> <bst|rbt|hash>"``  
and a newline character to stderr and exit in failure.

If the number of command line arguments is correct, the program will then verify that the
dictionary file exists. If it does not, the program will print the message  
``"Error: Cannot open file '" + args[0] + "' for input."``  
and a newline character to stderr, where args[0] contains the name of the dictionary file the user is attempting to open, and exit in failure.

The program will then try to parse the command line for which data structure the user wishes to use. Valid strings are “bst”, “rbt”, and “hash”. Any other string including those with
different capitalization is considered invalid, causing the program to print the message  
``"Error: Invalid data structure '" + args[1] + "' received."``  
and a newline character to stderr, where args[1] contains the data structure string name, and exit in failure.

### - Parsing the Input File

After validating the command line arguments, you’ll need to instantiate either a BSTreeMap, RBTreeMap, or MyHashMap. You must create a reference to the interface rather than the class itself, as in:  
``MyMap<String, Integer> map = new BSTreeMap<>();``  
***No credit*** will be given if your map variable is not of type MyMap. The key-to-value mapping is String-to-MyList<String>. The key must be the sorted, lowercase spelling of the word. You ***must use/modify*** the insertion sort method given in class to sort the character of the string. Strings are immutable, so use an array of chars. As an example, when processing the word “Tea”, the key should be “aet”, since all characters have been made lowercase and the characters within the word have been sorted lexicographically. The value is MyList<String>, a MyLinkedList of all the words that are anagrams of the key. The elements in the MyLinkedList may be stored in any order and must be the word with its original capitalization.

The dictionary file contains a list of all the words to process. The file is stored in Unix/Mac format, where each line ends with a single '\n' character. No word will appear twice in the dictionary with the same exact capitalization. The order of the words in the file is random; it may or may not be sorted. For each word in the file, convert it to lowercase characters, sort the characters, and then insert the key-value pair into the map. If an I/O error occurs as the reading takes place, the program must print the message  
``"Error: An I/O error occurred reading '" + args[0] + "'."``  
and a newline character to stderr, where args[0] contains the name of the file the user is attempting to process, and exit in failure.

### - Displaying the Output

If no anagrams are found in the input file, the output is the string literal  
``"No anagrams found."``  
and a newline character.

If anagrams are present, the first line of output displays the number of groups of anagrams and the anagram count. Sometimes, there is one group of words of maximal length, but sometimes, there are ties, and several groups of anagrams are of maximal length. Always print  
``"Groups: " + groupCount + ", Anagram count: " + anagramCount``  
followed by a newline character.

Each group is enclosed in square brackets []. The words in the group are sorted lexicographically. That means that words beginning with a capital letter will appear in the output before words beginning with a lowercase letter. The groups themselves are sorted lexicographically by the first word in the list.

There ***must never be any whitespace characters***, such as extra spaces or tabs, at the end of a line of output. After the last visible character on a line, the cursor must be placed on the next line.

---

### Sample Input / Output

For the supplied dictionary.txt file, the command:  
```
java MostAnagramsFinder dictionary.txt hash
```
produces:  
```
Groups: 1, Anagram count: 8
[Stael, Tesla, least, slate, stale, steal, tales, teals]
```

For the supplied words.txt file, the command:
```
java MostAnagramsFinder words.txt hash
```
produces:  
```
Groups: 5, Anagram count: 15
[Acres, Cesar, Cresa, acers, arces, cares, carse, caser, ceras, escar, races, sacre, scare, scrae, serac]
[Andrel, Erland, Ernald, Lander, Landre, Larned, Lenard, Nadler, Randel, Randle, aldern, darnel, enlard, ladner, reland]
[Salter, Slater, alerts, alters, artels, estral, laster, lastre, rastle, ratels, relast, resalt, staler, stelar, talers]
[Tersina, anestri, antsier, asterin, eranist, nastier, ratines, resiant, restain, retains, retinas, retsina, stainer, starnie, stearin]
[Tresa, arest, aster, astre, rates, reast, resat, serta, stare, strae, tares, tarse, tears, teras, treas]
```  
All words between [ and ] are on one line, despite it appearing on two above. The document is simply not wide enough to fit all the characters. Print the newline character after the ] at the end of a group of anagrams.

---

### Requirements

You must use the supplied implementations of the BSTreeMap, RBTreeMap, and MyHashMap. You ***must not modify*** these files in any way. You must write all your code in MostAnagramsFinder.java. We will copy the source for the data structures into the same folder as your source code when grading your submission. If you wish to write additional
classes to help you encapsulate the data you process, put the non-public class inside MostAnagramsFinder.java.

You are permitted only to import from the following packages:
```
java.io.*;
java.util.Arrays;
java.util.Iterator;
```

You ***must not import*** any other packages from the Java API. They will be stripped away before grading, and your code will not compile.  

Any method implementing the insertion sort algorithm must be named "insertionSort". The argument list and return type is left to your discretion. You ***must use/modify*** the insertion sort method given in class. It is acceptable and even necessary to have several overloaded versions of the method with different input arguments.

---

### Timing Your Work and Evaluating the Results

After you are confident you are getting the correct output for smaller files, try processing the words.txt supplied in Canvas. It contains 466,550 words. Time it from the command line as follows:
```
time java MostAnagramsFinder words.txt bst
time java MostAnagramsFinder words.txt rbt
time java MostAnagramsFinder words.txt hash
```
Take the average of 5 executions for each data structure

### - Answer the following questions in a readme.txt file.

How long does your program take to produce the answer when using the bst, rbt, and hash flags? Copy the results into this readme file.  
What data structure do you expect to have the best (fastest) performance? Which one do you expect to be the slowest? 
Do the results of timing your program’s execution match your expectations? If so, briefly explain the correlation. If not, what run times deviated and briefly explain why you think this is the case.
