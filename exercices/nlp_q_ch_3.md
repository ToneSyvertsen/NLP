# Exercises Chapter 3

1. ☼ Define a string s = 'colorless'. Write a Python statement that changes this to "colourless" using only the slice and concatenation operations.

```
s = 'colorless'
s
Out[131]: 'colorless'

```

```
s = 'colorless'
s= s.split("r") 
s.insert(1, 'ur')
s= ''.join(s)

s
Out[204]: 'colourless'

```

this next one is just to show whats going on inbetween
```
s = 'colorless'
s= s.split("r") 
print (s)         #this is just to se whats going on
s.insert(1, 'ur')
print (s)         #this is just to se whats going on
s= ''.join(s)
s
['colo', 'less']             #print1
['colo', 'ur', 'less']       #print2
Out[200]: 'colourless'
```


This was my fist thought, but by using this I will not use slice and concatenation operations..

```
s = s.replace('colorless', "colourless")
s
Out[206]: 'colourless'

```

2. ☼ We can use the slice notation to remove morphological endings on words. For example, 'dogs'[:-1] removes the last character of dogs, leaving dog. Use slice notation to remove the affixes from these words (we've inserted a hyphen to indicate the affix boundary, but omit this from your strings): dish-es, run-ning, nation-ality, un-do, pre-heat.

I don't know if I interpreted this question correct..

```
w = 'dishes'
w = w[:4]
print (w)

w2 = 'running'
w2 = w2[:3]
print(w2)

w3 = 'nationality'
w3 = w3[:6]
print(w3)

w4 = 'undo'
w4 = w4[:2]
print(w4)

w5 = 'preheat'
w5 = w5[:3]
print(w5)
dish
run
nation
un
pre

```


3. ☼ We saw how we can generate an IndexError by indexing beyond the end of a string. Is it possible to construct an index that goes too far to the left, before the start of the string?

If I interpreted the question right I belive this is the answere.
Because I ask for letters before = index

```
w[:0]
Out[219]: ''

```


4. ☼ We can specify a "step" size for the slice. The following returns every second character within the slice: monty[6:11:2]. It also works in the reverse direction: monty[10:5:-2] Try these for yourself, then experiment with different step values.

```
monty = 'Monty Python'

monty[6:11:2]
Out[227]: 'Pto'
monty[10:5:-2]
Out[228]: 'otP'
monty[11:5:-2]
Out[229]: 'nhy'

monty[4:-1:-3]
Out[230]: ''

monty[2:-1:-3]
Out[231]: ''
monty[2:10:-3]
Out[232]: ''
monty[2:10:3]
Out[233]: 'n t'
monty[11:5:-3]
Out[234]: 'nt'

```


5. ☼ What happens if you ask the interpreter to evaluate monty[::-1]? Explain why this is a reasonable result.

6. ☼ Describe the class of strings matched by the following regular expressions.

[a-zA-Z]+
[A-Z][a-z]*
p[aeiou]{,2}t
\d+(\.\d+)?
([^aeiou][aeiou][^aeiou])*
\w+|[^\w\s]+
Test your answers using nltk.re_show().

7. ☼ Write regular expressions to match the following classes of strings:

A single determiner (assume that a, an, and the are the only determiners).
An arithmetic expression using integers, addition, and multiplication, such as 2*3+8.

8. ☼ Write a utility function that takes a URL as its argument, and returns the contents of the URL, with all HTML markup removed. Use from urllib import request and then  request.urlopen('http://nltk.org/').read().decode('utf8') to access the contents of the URL.

9. ☼ Save some text into a file corpus.txt. Define a function load(f) that reads from the file named in its sole argument, and returns a string containing the text of the file.

Use nltk.regexp_tokenize() to create a tokenizer that tokenizes the various kinds of punctuation in this text. Use one multi-line regular expression, with inline comments, using the verbose flag (?x).
Use nltk.regexp_tokenize() to create a tokenizer that tokenizes the following kinds of expression: monetary amounts; dates; names of people and organizations.

10. ☼ Rewrite the following loop as a list comprehension:

 	
>>> sent = ['The', 'dog', 'gave', 'John', 'the', 'newspaper']
>>> result = []
>>> for word in sent:
...     word_len = (word, len(word))
...     result.append(word_len)
>>> result
[('The', 3), ('dog', 3), ('gave', 4), ('John', 4), ('the', 3), ('newspaper', 9)]

11. ☼ Define a string raw containing a sentence of your own choosing. Now, split raw on some character other than space, such as 's'.

12. ☼ Write a for loop to print out the characters of a string, one per line.

13. ☼ What is the difference between calling split on a string with no argument or with ' ' as the argument, e.g. sent.split() versus sent.split(' ')? What happens when the string being split contains tab characters, consecutive space characters, or a sequence of tabs and spaces? (In IDLE you will need to use '\t' to enter a tab character.)

14. ☼ Create a variable words containing a list of words. Experiment with words.sort() and sorted(words). What is the difference?

15. ☼ Explore the difference between strings and integers by typing the following at a Python prompt: "3" * 7 and 3 * 7. Try converting between strings and integers using int("3") and str(3).

16. ☼ Use a text editor to create a file called prog.py containing the single line monty = 'Monty Python'. Next, start up a new session with the Python interpreter, and enter the expression monty at the prompt. You will get an error from the interpreter. Now, try the following (note that you have to leave off the .py part of the filename):

 	
>>> from prog import monty
>>> monty
This time, Python should return with a value. You can also try import prog, in which case Python should be able to evaluate the expression prog.monty at the prompt.

17. ☼ What happens when the formatting strings %6s and %-6s are used to display strings that are longer than six characters?

18. ◑ Read in some text from a corpus, tokenize it, and print the list of all wh-word types that occur. (wh-words in English are used in questions, relative clauses and exclamations: who, which, what, and so on.) Print them in order. Are any words duplicated in this list, because of the presence of case distinctions or punctuation?

19. ◑ Create a file consisting of words and (made up) frequencies, where each line consists of a word, the space character, and a positive integer, e.g. fuzzy 53. Read the file into a Python list using open(filename).readlines(). Next, break each line into its two fields using split(), and convert the number into an integer using int(). The result should be a list of the form:  [['fuzzy', 53], ...].

20. ◑ Write code to access a favorite webpage and extract some text from it. For example, access a weather site and extract the forecast top temperature for your town or city today.

 [see my answere here] (ex20chap3.md) 

21. ◑ Write a function unknown() that takes a URL as its argument, and returns a list of unknown words that occur on that webpage. In order to do this, extract all substrings consisting of lowercase letters (using re.findall()) and remove any items from this set that occur in the Words Corpus (nltk.corpus.words). Try to categorize these words manually and discuss your findings.

22. ◑ Examine the results of processing the URL http://news.bbc.co.uk/ using the regular expressions suggested above. You will see that there is still a fair amount of non-textual data there, particularly Javascript commands. You may also find that sentence breaks have not been properly preserved. Define further regular expressions that improve the extraction of text from this web page.

23. ◑ Are you able to write a regular expression to tokenize text in such a way that the word don't is tokenized into do and n't? Explain why this regular expression won't work: «n't|\w+».

24. ◑ Try to write code to convert text into hAck3r, using regular expressions and substitution, where e → 3, i → 1, o → 0, l → |, s → 5, . → 5w33t!, ate → 8. Normalize the text to lowercase before converting it. Add more substitutions of your own. Now try to map s to two different values: $ for word-initial s, and 5 for word-internal s.

25. ◑ Pig Latin is a simple transformation of English text. Each word of the text is converted as follows: move any consonant (or consonant cluster) that appears at the start of the word to the end, then append ay, e.g. string → ingstray, idle → idleay.  http://en.wikipedia.org/wiki/Pig_Latin

Write a function to convert a word to Pig Latin.
Write code that converts text, instead of individual words.
Extend it further to preserve capitalization, to keep qu together (i.e. so that quiet becomes ietquay), and to detect when y is used as a consonant (e.g. yellow) vs a vowel (e.g. style).

26. ◑ Download some text from a language that has vowel harmony (e.g. Hungarian), extract the vowel sequences of words, and create a vowel bigram table.


27. ◑ Python's random module includes a function choice() which randomly chooses an item from a sequence, e.g. choice("aehh ") will produce one of four possible characters, with the letter h being twice as frequent as the others. Write a generator expression that produces a sequence of 500 randomly chosen letters drawn from the string "aehh ", and put this expression inside a call to the ''.join() function, to concatenate them into one long string. You should get a result that looks like uncontrolled sneezing or maniacal laughter: he  haha ee  heheeh eha. Use  split() and join() again to normalize the whitespace in this string.

28. ◑ Consider the numeric expressions in the following sentence from the MedLine Corpus: The corresponding free cortisol fractions in these sera were 4.53 +/- 0.15% and 8.16 +/- 0.23%, respectively. Should we say that the numeric expression 4.53 +/- 0.15% is three words? Or should we say that it's a single compound word? Or should we say that it is actually nine words, since it's read "four point five three, plus or minus zero point fifteen percent"? Or should we say that it's not a "real" word at all, since it wouldn't appear in any dictionary? Discuss these different possibilities. Can you think of application domains that motivate at least two of these answers?

29. ◑ Readability measures are used to score the reading difficulty of a text, for the purposes of selecting texts of appropriate difficulty for language learners. Let us define μw to be the average number of letters per word, and μs to be the average number of words per sentence, in a given text. The Automated Readability Index (ARI) of the text is defined to be: 4.71 μw + 0.5 μs - 21.43. Compute the ARI score for various sections of the Brown Corpus, including section f (lore) and j (learned). Make use of the fact that nltk.corpus.brown.words() produces a sequence of words, while nltk.corpus.brown.sents() produces a sequence of sentences.

30. ◑ Use the Porter Stemmer to normalize some tokenized text, calling the stemmer on each word. Do the same thing with the Lancaster Stemmer and see if you observe any differences.

31. ◑ Define the variable saying to contain the list ['After', 'all', 'is', 'said', 'and', 'done', ',', 'more',
'is', 'said', 'than', 'done', '.']. Process this list using a for loop, and store the length of each word in a new list lengths. Hint: begin by assigning the empty list to lengths, using  lengths = []. Then each time through the loop, use append() to add another length value to the list. Now do the same thing using a list comprehension.

32. ◑ Define a variable silly to contain the string: 'newly formed bland ideas are inexpressible in an infuriating
way'. (This happens to be the legitimate interpretation that bilingual English-Spanish speakers can assign to Chomsky's famous nonsense phrase, colorless green ideas sleep furiously according to Wikipedia). Now write code to perform the following tasks:

Split silly into a list of strings, one per word, using Python's split() operation, and save this to a variable called bland.
Extract the second letter of each word in silly and join them into a string, to get 'eoldrnnnna'.
Combine the words in bland back into a single string, using join(). Make sure the words in the resulting string are separated with whitespace.
Print the words of silly in alphabetical order, one per line.

33. ◑ The index() function can be used to look up items in sequences. For example, 'inexpressible'.index('e') tells us the index of the first position of the letter e.

What happens when you look up a substring, e.g. 'inexpressible'.index('re')?
Define a variable words containing a list of words. Now use words.index() to look up the position of an individual word.
Define a variable silly as in the exercise above. Use the index() function in combination with list slicing to build a list phrase consisting of all the words up to (but not including) in in  silly.

34. ◑ Write code to convert nationality adjectives like Canadian and Australian to their corresponding nouns Canada and Australia (see  http://en.wikipedia.org/wiki/List_of_adjectival_forms_of_place_names).

35. ◑ Read the LanguageLog post on phrases of the form as best as p can and as best p can, where p is a pronoun. Investigate this phenomenon with the help of a corpus and the findall() method for searching tokenized text described in 3.5. http://itre.cis.upenn.edu/~myl/languagelog/archives/002733.html

36. ◑ Study the lolcat version of the book of Genesis, accessible as nltk.corpus.genesis.words('lolcat.txt'), and the rules for converting text into lolspeak at http://www.lolcatbible.com/index.php?title=How_to_speak_lolcat. Define regular expressions to convert English words into corresponding lolspeak words.

37. ◑ Read about the re.sub() function for string substitution using regular expressions, using help(re.sub) and by consulting the further readings for this chapter. Use re.sub in writing code to remove HTML tags from an HTML file, and to normalize whitespace.
