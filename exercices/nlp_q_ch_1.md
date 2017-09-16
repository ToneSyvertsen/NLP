
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
