
Exercises

1. ☼ Try using the Python interpreter as a calculator, and typing expressions like 12 / (4 + 1).
``` 
12 / (4+1)
Out[811]: 2.4

``` 

2. ☼ Given an alphabet of 26 letters, there are 26 to the power 10, or 26 ** 10, ten-letter strings we can form. That works out to 141167095653376. How many hundred-letter strings are possible?

``` 
26**100
Out[810]: 3142930641582938830174357788501626427282669988762475256374173175398995908420104023465432599069702289330964075081611719197835869803511992549376

``` 

3. ☼ The Python multiplication operation can be applied to lists. What happens when you type ['Monty', 'Python'] * 20, or 3 * sent1?

```
['Monty', 'Python'] * 6
Out[816]: 
['Monty',
 'Python',
 'Monty',
 'Python',
 'Monty',
 'Python',
 'Monty',
 'Python',
 'Monty',
 'Python',
 'Monty',
 'Python'
]
 
```

```
sent1 ='Hello'
3 * sent1
Out[817]: 'HelloHelloHello'

```
4. ☼ Review 1 on computing with language. How many words are there in text2? How many distinct words are there?

All words
``` 
len(text2)
Out[820]: 141576

```
Distinct words

```
len(set(text2))
Out[821]: 6833

```

5. ☼ Compare the lexical diversity scores for humor and romance fiction in 1.1. Which genre is more lexically diverse?

```
def lexical_diversity(text):
    return len(set(text)) / len(text)

from nltk.corpus import brown
brown.categories()

lexical_diversity(brown.words(categories='humor'))
Out[829]: 0.23125144042406084

lexical_diversity(brown.words(categories='romance'))
Out[830]: 0.12070492131044529

```
The text in humor seems to have the highest lexical_diversity, this can be because it's a smaller text but also that the author have used a wider vocabulary.

6. ☼ Produce a dispersion plot of the four main protagonists in Sense and Sensibility: Elinor, Marianne, Edward, and Willoughby. What can you observe about the different roles played by the males and females in this novel? Can you identify the couples?

```
text2.dispersion_plot(["Elinor", "Marianne", "Edward", "Willoughby"])

```
![text2.dispersion_plot](https://puu.sh/xAGuv/bf18d0f060.png)

I do believe Elinor is the main character and that she has a good friend, Marianne.
Based on those compared to when the men appears I would guess Elinor + Edward and Marianne + Willoughby J


7. ☼ Find the collocations in text5.

``` 
text5.collocations()
wanna chat; PART JOIN; MODE #14-19teens; JOIN PART; PART PART;
cute.-ass MP3; MP3 player; JOIN JOIN; times .. .; ACTION watches; guys
wanna; song lasts; last night; ACTION sits; -...)...- S.M.R.; Lime
Player; Player 12%; dont know; lez gurls; long time

```

8. ☼ Consider the following Python expression: len(set(text4)). State the purpose of this expression. Describe the two steps involved in performing this computation.

**len** count the words in text 4, then **set** take away all the duplicates and you get a number of distinct words in text 4.
If you don’t use len in the expression all the words will appear instead of the count

9. ☼ Review 2 on lists and strings.

Define a string and assign it to a variable, e.g., my_string = 'My String' (but put something more interesting in the string). Print the contents of this variable in two ways, first by simply typing the variable name and pressing enter, then by using the print statement.
Try adding the string to itself using my_string + my_string, or multiplying it by a number, e.g., my_string * 3. Notice that the strings are joined together without any spaces. How could you fix this?

```
my_string='Hello there!'
my_string
Out[834]: 'Hello there!'
print(my_string)
Hello there!

```

```
my_string + my_string
Out[836]: 'Hello there!Hello there!'
my_string * 3
Out[837]: 'Hello there!Hello there!Hello there!

```

```
my_string + ' ' + my_string
Out[838]: 'Hello there! Hello there!'


(my_string + ' ') * 3
Out[839]: 'Hello there! Hello there! Hello there! '

```

10. ☼ Define a variable my_sent to be a list of words, using the syntax my_sent = ["My", "sent"] (but with your own words, or a favorite saying).

```
my_sent= ["Æ", "æ", "a", "å",  "edår"]
my_sent
Out[841]: ['Æ', 'æ', 'a', 'å', 'edår']

```

Use ' '.join(my_sent) to convert this into a string.
```
' '.join(my_sent)
Out[842]: 'Æ æ a å edår'

```

Use split() to split the string back into the list form you had to start with.

```
'Æ æ a å EDÅR'.split()
Out[845]: ['Æ', 'æ', 'a', 'å', 'EDÅR']

```

11. ☼ Define several variables containing lists of words, e.g., phrase1, phrase2, and so on. Join them together in various combinations (using the plus operator) to form whole sentences. What is the relationship between len(phrase1 + phrase2) and len(phrase1) + len(phrase2)?

```
As string
>>> phrase1=['the sun is allways shining']
>>> phrase2=['on mondays']
 
>>> phrase1 + phrase2
['the sun is allways shining', 'on mondays']
>>> phrase2 + phrase1
['on mondays', 'the sun is allways shining']
 
As list
>>> phrase1 + phrase2
['the', 'sun', 'is', 'allways', 'shining', 'on', 'mondays']
>>> phrase2 + phrase1
['on', 'mondays', 'the', 'sun', 'is', 'allways', 'shining']
 
>>> len(phrase1) + len(phrase2)
7
>>> len(phrase1 + phrase2)
7

```
I believe it gives the same result, but will be easier when you are connecting a lot of lists/strings?

12. ☼ Consider the following two expressions, which have the same value. Which one will typically be more relevant in NLP? Why?

"Monty Python"[6:12]
["Monty", "Python"][1]

```
"Monty Python"[6:12]
Out[846]: 'Python'

["Monty", "Python"][1]
Out[847]: 'Python'

```
That will depend on what type of analysis you are doing.
Sometimes it's best to use list other times strings?

13. ☼ We have seen how to represent a sentence as a list of words, where each word is a sequence of characters. What does sent1[2][2] do? Why? Experiment with other index values.

```
sent1
Out[847]: ['Call', 'me', 'Ishmael', '.']

sent1[2][2]
Out[848]: 'h'
```
It takes the third letter from the third word. Number three because the indexes start at 0.


14. ☼ The first sentence of text3 is provided to you in the variable sent3. The index of the in sent3 is 1, because sent3[1] gives us 'the'. What are the indexes of the two other occurrences of this word in sent3?


```
sent3
Out[850]: 
['In',
 'the', #index 1
 'beginning',
 'God',
 'created',
 'the', #index 5
 'heaven',
 'and',
 'the', #index 8
 'earth',
 '.']

```

15. ☼ Review the discussion of conditionals in 4. Find all words in the Chat Corpus (text5) starting with the letter b. Show them in alphabetical order.

```
sorted(w for w in set(text5) if w.startswith('b'))
Out[851]: 
['b',
 'b-day',
 'b/c',
 'b4',
 'babay',
 'babble',
 'babblein',
 'babe',
 'babes',
 'babi',
 'babies',
 'babiess',
 'baby',
 ...]
 
```



16. ☼ Type the expression list(range(10)) at the interpreter prompt. Now try list(range(10, 20)), list(range(10, 20, 2)), and list(range(20, 10, -2)). We will see a variety of uses for this built-in function in later chapters.

For some reason this don't work in spyder..

```
>>> list(range(10))                                      
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
>>> list(range(10, 20))
[10, 11, 12, 13, 14, 15, 16, 17, 18, 19]
>>> list(range(10, 20, 2))
[10, 12, 14, 16, 18]
>>> list(range(20, 10, -2))
[20, 18, 16, 14, 12]

```

17.◑ Use text9.index() to find the index of the word sunset. You'll need to insert this word as an argument between the parentheses. By a process of trial and error, find the slice for the complete sentence that contains this word.

```
text9.index('sunset')
Out[860]: 629

```
```
***Trying to find the sentens***
text9[600:640]
Out[861]: 
[',',
 'and',
 'you',
 'may',
 'safely',
 'read',
 '.',
 'G',
 '.',
 'K',
 '.',
 'C',
 '.',
 'CHAPTER',
 'I',
 'THE',
 'TWO',
 'POETS',
 'OF',
 'SAFFRON',
 'PARK',
 'THE',
 'suburb',
 'of',
 'Saffron',
 'Park',
 'lay',
 'on',
 'the',
 'sunset',
 'side',
 'of',
 'London',
 ',',
 'as',
 'red',
 'and',
 'ragged',
 'as',
 'a']

text9[622:645]
Out[862]: 
['suburb',
 'of',
 'Saffron',
 'Park',
 'lay',
 'on',
 'the',
 'sunset',
 'side',
 'of',
 'London',
 ',',
 'as',
 'red',
 'and',
 'ragged',
 'as',
 'a',
 'cloud',
 'of',
 'sunset',
 '.',
 'It']
 
text9[621:644]
Out[863]: 
['THE',
 'suburb',
 'of',
 'Saffron',
 'Park',
 'lay',
 'on',
 'the',
 'sunset',
 'side',
 'of',
 'London',
 ',',
 'as',
 'red',
 'and',
 'ragged',
 'as',
 'a',
 'cloud',
 'of',
 'sunset',
 '.']
 
 ```

18. ◑ Using list addition, and the set and sorted operations, compute the vocabulary of the sentences sent1 ... sent8.

```
#collects the sentences
allsents=(sent1 + sent2 + sent3 + sent4 + sent5 + sent6 + sent7 + sent8) 

#Sort all the words, fint only distinct words and then sort out the non alphabetic tokens
Words=sorted(wd for wd in set(allsents) if wd.isalpha())                 

Words
Out[871]: 
['ARTHUR',
 'Call',
 'Citizens',
 'Dashwood',
 'Fellow',
 'God',
 'House',
 'I',
 'In',
 'Ishmael',
 'JOIN',
 'KING',
 'MALE',
 'PMing',
 'Pierre',
 'Representatives',
 'SCENE',
 'SEXY',
 'Senate',
 'Sussex',
 'The',
 'Vinken',
 'Whoa',
 'a',
 'and',
 'as',
 'attrac',
 'been',
 'beginning',
 'board',
 'clop',
 'created',
 'director',
 'discreet',
 'earth',
 'encounters',
 'family',
 'for',
 'had',
 'have',
 'heaven',
 'in',
 'join',
 'lady',
 'lol',
 'long',
 'me',
 'nonexecutive',
 'of',
 'old',
 'older',
 'people',
 'problem',
 'seeks',
 'settled',
 'single',
 'the',
 'there',
 'to',
 'will',
 'wind',
 'with',
 'years']

```


19. ◑ What is the difference between the following two lines? Which one will give a larger value? Will this be the case for other texts?

```

>>> sorted(set(w.lower() for w in text1))
>>> sorted(w.lower() for w in set(text1))

```

The second one gives som duplicates, but i can not tell why. 
??? Do you know why @katekuzmina or @ausken ???

20. ◑ What is the difference between the following two tests: w.isupper() and not w.islower()?
```
sentq='This is a TEST! Can I tell the difference?'

#This argument allso include other tokens as long as they are not lower.
sorted(w for w in set(sentq) if not w.islower())
Out[897]: [' ', '!', '?', 'C', 'E', 'I', 'S', 'T']

#This argument only returns the upper letters
sorted(w for w in set(sentq) if w.isupper())
Out[898]: ['C', 'E', 'I', 'S', 'T']

```

21. ◑ Write the slice expression that extracts the last two words of text2.

```
text2[-2:]
Out[901]: ['THE', 'END']

```

22. ◑ Find all the four-letter words in the Chat Corpus (text5). With the help of a frequency distribution (FreqDist), show these words in decreasing order of frequency.

```
fdist1 = FreqDist(sorted(w for w in (text1) if len(w) == 4 and w.isalpha()))

#If I leave the emty it will return the hole list
fdist1.most_common(20)
Out[922]: 
[('that', 2982),
 ('with', 1659),
 ('this', 1280),
 ('from', 1052),
 ('have', 760),
 ('were', 680),
 ('like', 624),
 ('they', 586),
 ('some', 578),
 ('then', 571),
 ('when', 553),
 ('upon', 538),
 ('into', 520),
 ('ship', 507),
 ('more', 501),
 ('Ahab', 501),
 ('them', 471),
 ('what', 442),
 ('been', 415),
 ('over', 403)]


```

23. ◑ Review the discussion of looping with conditions in 4. Use a combination of for and if statements to loop over the words of the movie script for Monty Python and the Holy Grail (text6) and print all the uppercase words, one per line.

```
sorted(set(w for w in (text6) if w.isupper()))
Out[930]: 
['A',
 'ALL',
 'AMAZING',
 'ANIMATOR',
 'ARMY',
 'ARTHUR',
 'B',
 'BEDEVERE',
 'BLACK',
 'BORS',
 'BRIDE',
 'BRIDGEKEEPER',
 'BROTHER',
 'C',
 'CAMERAMAN',
 'CART',
 'CARTOON',
 'CHARACTER',
 'CHARACTERS',
 'CONCORDE',
 'CRAPPER',
 'CRASH',
 'CRONE',
 'CROWD',
 'CUSTOMER',
 'DEAD',
 'DENNIS',
 'DINGO',
 'DIRECTOR',
 'ENCHANTER',
 'FATHER',
 'FRENCH',
 'GALAHAD',
 'GIRLS',
 [...]

```

24. ◑ Write expressions for finding all words in text6 that meet the conditions listed below. The result should be in the form of a list of words: ['word1', 'word2', ...].

 a. Ending in ize
 I did not get any hits
 ```
 sorted(w for w in text6 if w.endswith('ize'))
Out[17]: []


 ```
 
 b. Containing the letter z
 
 ```
 sorted(w for w in text6 if 'z' in w)
Out[18]: 
['Fetchez',
 'Fetchez',
 'amazes',
 'frozen',
 'zhiv',
 'zone',
 'zoo',
 'zoop',
 'zoosh']
 
 ```
 
 c. Containing the sequence of letters pt

```
sorted(w for w in text6 if 'pt' in w)
Out[19]: 
['Chapter',
 'Thpppppt',
 'Thppppt',
 'Thpppt',
 'Thppt',
 'Thppt',
 'aptly',
 'empty',
 'empty',
 'excepting',
 'ptoo',
 'temptation',
 'temptress']
 
 ```
 d. Having all lowercase letters except for an initial capital (i.e., titlecase)
 
 ```
sorted(set(w for w in text6 if w.istitle()))
Out[22]: 
['A',
 'Aaaaaaaaah',
 'Aaaaaaaah',
 'Aaaaaah',
 'Aaaah',
 'Aaaaugh',
 'Aaagh',
 'Aaah',
 'Aaauggh',
 'Aaaugh',
 'Aaauugh',
 'Aagh',
 'Aah',
 'Aauuggghhh',
 'Aauuugh',
 'Aauuuuugh',
 'Aauuuves',
 'Action',
 'Actually',
 'African',
 'Ages',
 'Aggh',
 'Agh',
 'Ah',
 'Ahh',
 'Alice',
 'All',
 'Allo',
[...]
 
 ```
 
 25. ◑ Define sent to be the list of words ['she', 'sells', 'sea', 'shells', 'by', 'the', 'sea', 'shore']. Now write code to perform the following tasks:
 ```
s_list= ['she', 'sells', 'sea', 'shells', 'by', 'the', 'sea', 'shore']

 ```
 a. Print all words beginning with sh
 
 ``` 
 print([w for w in s_list if w.startswith('sh')])
['she', 'shells', 'shore']

 ```
 
 b. Print all words longer than four characters
 
 ``` 
 print([w for w in s_list if len(w) > 4])
['sells', 'shells', 'shore']

 ```

26. ◑ What does the following Python code do?  sum(len(w) for w in text1) Can you use it to work out the average word length of a text?

It counts all tokens in the text

```
sum(len(w) for w in text1)
Out[28]: 999044

```
```
alltokens= sum(len(w) for w in text1)
allwords=len(text1)

alltokens/allwords
Out[41]: 3.830411128023649

```
or 

```
print(sum(len(w) for w in text1)/len(text1))
3.830411128023649

```



