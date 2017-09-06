20. ◑ Write code to access a favorite webpage and extract some text from it. 
For example, access a weather site and extract the forecast top temperature for your town or city today.
Since I did not choose weather (Norwegian forcastes is really not that interesting in September :P) I had to try out some other things


I startede by counting the words

```

    In [89]: import nltk, re, pprint
        ...: from nltk import word_tokenize
        ...: from urllib import request
        ...: from bs4 import BeautifulSoup
        ...: import feedparser
        ...: 
        ...: url = "http://cvnerden.no/eksempler-pa-cv-og-soknad-2/"
        ...: html = request.urlopen(url).read().decode('utf8')
        ...: raw = BeautifulSoup(html, "lxml").get_text()
        ...: tokens = word_tokenize(raw)
        ...: len(tokens)
    Out[89]: 2872

```

Rename tokens to text

```python

text = nltk.Text(tokens)

```

Trying collocation

```python

text.collocations()
Slik får; flaks trenger; jobbsoking.com says; Med litt; lenge før;
litt flaks; har landet; før den; jobb lenge; landet jobb; aller
viktigste; dem ikke; FANTASTISK søknad; senere Slik; søknadOg senere;
ung person; vet hva; den tid.Se; tid.Se mer; *Relevant annonse

```
Seems like it finds the links on the page??

Then I try to find and name the title

```python

title = text[:5]
title
Out[115]: ['Eksempler', 'på', 'CV', 'og', 'søknad']

```

I dont like the title to be a list so try to make it look like a string

```python

title2 = " ".join(title)
title2
Out[116]: 'Eksempler på CV og søknad'

```

Is it possible to find the position of words in the text so you don't have to guess the position?
I try to find a codesnippet for that


```python

word="Ting"
if word in text:
    print( word, " is in the sentence")
    for i, j in enumerate(text):
        if j == word:
            print("'"+word+"'","is in position",i+1)
Ting  is in the sentence
'Ting' is in position 1132
'Ting' is in position 1397

```
Then I want to locate the first bulletpoint in the text, and wants to fint it's location

```python

word="Søkeren"
if word in text:
    print( word, " is in the sentence")
    for i, j in enumerate(text):
        if j == word:
            print("'"+word+"'","is in position",i+1)
Søkeren  is in the sentence
'Søkeren' is in position 1402
'Søkeren' is in position 1422
'Søkeren' is in position 1662

```
Then I try to show the intire bulletpoint

```python

text = nltk.Text(tokens)
text = text[1401:1420]
text
Out[129]: 
['Søkeren',
 '(',
 'jeg',
 ')',
 'bruker',
 'bulletpoints',
 'når',
 'han',
 'skal',
 'beskrive',
 'arbeidsoppgavene',
 '–',
 'dette',
 'kan',
 'gjøre',
 'CV-en',
 'tydelig',
 'og',
 'lettlest']
 
```

Don't want it to be a list so use .join

```python

text2 = " ".join(text)
text2
Out[130]: 'Søkeren ( jeg ) bruker bulletpoints når han skal beskrive arbeidsoppgavene – dette kan gjøre CV-en tydelig og lettlest'

```
