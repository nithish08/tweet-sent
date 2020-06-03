# tweet-sent
Repo for Tweet sentiment extraction Challenge. https://www.kaggle.com/c/tweet-sentiment-extraction

# Problem

Given a tweet and sentiment extract the 'phrase' leading to a sentiment.

x = {'sentence': 'soo sad I missed you here in san diego', 'sentiment':'negative'}
y = {'target':'soo sad'}

# Evaluation

Jaccard similarity between phrases of target and prediction.

```def jaccard(str1, str2): 
    a = set(str1.lower().split()) 
    b = set(str2.lower().split())
    c = a.intersection(b)
    return float(len(c)) / (len(a) + len(b) - len(c))```