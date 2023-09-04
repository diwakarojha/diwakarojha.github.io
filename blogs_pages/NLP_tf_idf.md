## Count Vectorise and Tfidf in NLP

From out previous experience, we know that Computers can only understand number not text informations. If we go back to our college days we, we know that
characters have ascii value stored in computers. So now when we want to apply machine learnign models, which are nothing but equations like y =mx +c,  on natural text,
we have to find a way to convert these english sentences to a numerical vector representation. or in other words a vector which presents the sentence.
So we will start with very basic idea on how can we convert a english sentence to a vector.
Lets assume a sentence like: "I like cheese pizza and pan pizza " and we have a english vocab of 7 words [ I, like, pizza, cold, hot, cheese, pan].

Now if we try to represent above sentence in vector form we can simply use a 5(length of dict) dimentional vector by placing 1 for the word which are
present in the sentence and 0 where word is not present in sentence.
| Vocab word | I | like | pizza | cold | hot | cheese | pan |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Sent1 | 1 | 1 | 1 | 0 | 0 | 1 | 0|

So now We can say that for sent1 = [ 1,1,1,0,0,1,0] is a vector representation.

But if we see carefully here "pizza" has come two times in sentence but in vector representation does not convey this information. so to overcome this problem we can use countVectorizer.

**CountVectorizer(Bag of words(BOW))** : In Count Vectorizer, in place of placing 0,1 we note down word frequencies.
| Vocab word | I | like | pizza | cold | hot | cheese | pan |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Sent1 | 1 | 1 | 2 | 0 | 0 | 1 | 0|


Vector form is: [ 1,1,2,0,0,1,0]
So now we have started capturing word frequencies. But when we start dealing with english sentences we know there are many word which are used just for grammatical reason and does not actualy convey any information.
and above vector form does not tell anything about such words. So to overcome these type of challenges we can use tf-idf.

**tf-idf**: <br>
tf - Term frequency: count of word in the current sentence(Document).
df: Document Frequency : count of documents which has same word.
N: Total no. of documents

$$tfidf = tf * log(\frac{N}{df})$$

But in above way, A collection of unigrams (what bag of words is) cannot capture phrases and multi-word expressions, effectively disregarding any word order dependence.

so to capture word dependence we use N grams. where if n=2 , we use 2 word combination and find out vector representation.


