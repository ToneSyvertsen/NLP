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

```
from nltk.corpus import state_union

state_union.fileids()
Out[123]: 
['1945-Truman.txt',
 '1946-Truman.txt',
 '1947-Truman.txt',
 '1948-Truman.txt',
 '1949-Truman.txt',
 '1950-Truman.txt',
 '1951-Truman.txt',
 '1953-Eisenhower.txt',
 '1954-Eisenhower.txt',
 '1955-Eisenhower.txt',
 '1956-Eisenhower.txt',
 '1957-Eisenhower.txt',
 '1958-Eisenhower.txt',
 '1959-Eisenhower.txt',
 '1960-Eisenhower.txt',
 '1961-Kennedy.txt',
 '1962-Kennedy.txt',
 '1963-Johnson.txt',
 '1963-Kennedy.txt',
 '1964-Johnson.txt',
 '1965-Johnson-1.txt',
 '1965-Johnson-2.txt',
 '1966-Johnson.txt',
 '1967-Johnson.txt',
 '1968-Johnson.txt',
 '1969-Johnson.txt',
 '1970-Nixon.txt',
 '1971-Nixon.txt',
 '1972-Nixon.txt',
 '1973-Nixon.txt',
 '1974-Nixon.txt',
 '1975-Ford.txt',
 '1976-Ford.txt',
 '1977-Ford.txt',
 '1978-Carter.txt',
 '1979-Carter.txt',
 '1980-Carter.txt',
 '1981-Reagan.txt',
 '1982-Reagan.txt',
 '1983-Reagan.txt',
 '1984-Reagan.txt',
 '1985-Reagan.txt',
 '1986-Reagan.txt',
 '1987-Reagan.txt',
 '1988-Reagan.txt',
 '1989-Bush.txt',
 '1990-Bush.txt',
 '1991-Bush-1.txt',
 '1991-Bush-2.txt',
 '1992-Bush.txt',
 '1993-Clinton.txt',
 '1994-Clinton.txt',
 '1995-Clinton.txt',
 '1996-Clinton.txt',
 '1997-Clinton.txt',
 '1998-Clinton.txt',
 '1999-Clinton.txt',
 '2000-Clinton.txt',
 '2001-GWBush-1.txt',
 '2001-GWBush-2.txt',
 '2002-GWBush.txt',
 '2003-GWBush.txt',
 '2004-GWBush.txt',
 '2005-GWBush.txt',
 '2006-GWBush.txt']

#Counting occurrences of men, women, and people
cfd = nltk.ConditionalFreqDist(
        (target, fileid[:4])
        for fileid in state_union.fileids()
        for w in state_union.words(fileid)
        for target in ['men', 'women', 'people']
        if w.lower().startswith(target)) [1]

cfd.plot()
``` 

Today it dosen't work(neither does the example in the book, but did work last time.


![somethings wrong...](https://puu.sh/xCd7f/428b554610.png)



![CCounting occurrences of men, women, and people](https://puu.sh/xCd4p/60a3720464.png)


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
