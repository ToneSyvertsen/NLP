1. ☼ Create a variable phrase containing a list of words. Review the operations described in the previous chapter, including addition, multiplication, indexing, slicing, and sorting.

``` 
list= ['This', 'is', 'my', 'life', '!']

list + list
Out[86]: ['This', 'is', 'my', 'life', '!', 'This', 'is', 'my', 'life', '!']

list * 3
Out[87]: 
['This',
 'is',
 'my',
 'life',
 '!',
 'This',
 'is',
 'my',
 'life',
 '!',
 'This',
 'is',
 'my',
 'life',
 '!']
 
list[:2]
Out[89]: ['This', 'is']

list[:-2]
Out[90]: ['This', 'is', 'my']

list[-2:]
Out[91]: ['life', '!']

list[2:4]
Out[92]: ['my', 'life']

sorted(list)
Out[94]: ['!', 'This', 'is', 'life', 'my']

```

2. ☼ Use the corpus module to explore austen-persuasion.txt. How many word tokens does this book have? How many word types?

```
len(gutenberg.raw('austen-persuasion.txt'))
Out[96]: 466292

#not sure what they want to know here distinct words?

len(set(gutenberg.words('austen-persuasion.txt')))
Out[108]: 6132

#or classes of words? I do belive that's in chapter 5..

```

3. ☼ Use the Brown corpus reader nltk.corpus.brown.words() or the Web text corpus reader nltk.corpus.webtext.words() to access some sample text in two different genres.

```

from nltk.corpus import brown

print(brown.categories())
['adventure', 'belles_lettres', 'editorial', 'fiction', 'government', 'hobbies', 'humor', 'learned', 'lore', 'mystery', 'news', 'religion', 'reviews', 'romance', 'science_fiction']

mystery=brown.words(categories='mystery')

learned=brown.words(categories='learned')

#I don't know if I was suppose to take out some text? But well then I know I can access it

mystery[4:20]
Out[118]: 
['on',
 'the',
 'bus',
 'the',
 'morning',
 'I',
 'left',
 'for',
 'Hanover',
 ',',
 'most',
 'of',
 'them',
 'disturbed',
 'and',
 'hallucinating']

learned[0:10]
Out[119]: 
['1',
 '.',
 'Introduction',
 'It',
 'has',
 'recently',
 'become',
 'practical',
 'to',
 'use']

```

4. ☼ Read in the texts of the State of the Union addresses, using the state_union corpus reader. Count occurrences of men, women, and people in each document. What has happened to the usage of these words over time?

5. ☼ Investigate the holonym-meronym relations for some nouns. Remember that there are three kinds of holonym-meronym relation, so you need to use: member_meronyms(), part_meronyms(),  substance_meronyms(), member_holonyms(), part_holonyms(), and substance_holonyms().

6. ☼ In the discussion of comparative wordlists, we created an object called translate which you could look up using words in both German and Spanish in order to get corresponding words in English. What problem might arise with this approach? Can you suggest a way to avoid this problem?

7. ☼ According to Strunk and White's Elements of Style, the word however, used at the start of a sentence, means "in whatever way" or "to whatever extent", and not "nevertheless". They give this example of correct usage: However you advise him, he will probably do as he thinks best. (http://www.bartleby.com/141/strunk3.html) Use the concordance tool to study actual usage of this word in the various texts we have been considering. See also the LanguageLog posting "Fossilized prejudices about 'however'" at  http://itre.cis.upenn.edu/~myl/languagelog/archives/001913.html

8. ◑ Define a conditional frequency distribution over the Names corpus that allows you to see which initial letters are more frequent for males vs. females (cf. 4.4).

9. ◑ Pick a pair of texts and study the differences between them, in terms of vocabulary, vocabulary richness, genre, etc. Can you find pairs of words which have quite different meanings across the two texts, such as monstrous in Moby Dick and in Sense and Sensibility?

10. ◑ Read the BBC News article: UK's Vicky Pollards 'left behind' http://news.bbc.co.uk/1/hi/education/6173441.stm. The article gives the following statistic about teen language: "the top 20 words used, including yeah, no, but and like, account for around a third of all words." How many word types account for a third of all word tokens, for a variety of text sources? What do you conclude about this statistic? Read more about this on LanguageLog, at http://itre.cis.upenn.edu/~myl/languagelog/archives/003993.html.

11. ◑ Investigate the table of modal distributions and look for other patterns. Try to explain them in terms of your own impressionistic understanding of the different genres. Can you find other closed classes of words that exhibit significant differences across different genres?

12. ◑ The CMU Pronouncing Dictionary contains multiple pronunciations for certain words. How many distinct words does it contain? What fraction of words in this dictionary have more than one possible pronunciation?

13. ◑ What percentage of noun synsets have no hyponyms? You can get all noun synsets using wn.all_synsets('n').

14. ◑ Define a function supergloss(s) that takes a synset s as its argument and returns a string consisting of the concatenation of the definition of s, and the definitions of all the hypernyms and hyponyms of s.

15. ◑ Write a program to find all words that occur at least three times in the Brown Corpus.

16. ◑ Write a program to generate a table of lexical diversity scores (i.e. token/type ratios), as we saw in 1.1. Include the full set of Brown Corpus genres (nltk.corpus.brown.categories()). Which genre has the lowest diversity (greatest number of tokens per type)? Is this what you would have expected?

17. ◑ Write a function that finds the 50 most frequently occurring words of a text that are not stopwords.

18. ◑ Write a program to print the 50 most frequent bigrams (pairs of adjacent words) of a text, omitting bigrams that contain stopwords.

19. ◑ Write a program to create a table of word frequencies by genre, like the one given in 1 for modals. Choose your own words and try to find words whose presence (or absence) is typical of a genre. Discuss your findings.

20. ◑ Write a function word_freq() that takes a word and the name of a section of the Brown Corpus as arguments, and computes the frequency of the word in that section of the corpus.

21. ◑ Write a program to guess the number of syllables contained in a text, making use of the CMU Pronouncing Dictionary.

22. ◑ Define a function hedge(text) which processes a text and produces a new version with the word 'like' between every third word.
