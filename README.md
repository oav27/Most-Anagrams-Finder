# Most-Anagrams-Finder In Java
Final Project Created Based on Learnings of Abstract Data Structures.

### Preview:


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

### - **Parsing Command Line Arguments**

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

### - **Parsing the Input File**

After validating the command line arguments, you’ll need to instantiate either a BSTreeMap, RBTreeMap, or MyHashMap. You must create a reference to the interface rather than the class itself, as in:  
``MyMap<String, Integer> map = new BSTreeMap<>();``  
**No credit** will be given if your map variable is not of type MyMap. The key-to-value mapping is String-to-MyList<String>. The key must be the sorted, lowercase spelling of the word. You **must use/modify** the insertion sort method given in class to sort the character of the string. Strings are immutable, so use an array of chars. As an example, when processing the word “Tea”, the key should be “aet”, since all characters have been made lowercase and the characters within the word have been sorted lexicographically. The value is MyList<String>, a MyLinkedList of all the words that are anagrams of the key. The elements in the MyLinkedList may be stored in any order and must be the word with its original capitalization.

The dictionary file contains a list of all the words to process. The file is stored in Unix/Mac format, where each line ends with a single '\n' character. No word will appear twice in the dictionary with the same exact capitalization. The order of the words in the file is random; it may or may not be sorted. For each word in the file, convert it to lowercase characters, sort the characters, and then insert the key-value pair into the map. If an I/O error occurs as the reading takes place, the program must print the message  
``"Error: An I/O error occurred reading '" + args[0] + "'."``  
and a newline character to stderr, where args[0] contains the name of the file the user is attempting to process, and exit in failure.
