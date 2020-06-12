# Tweet Sentiment Extraction
Repo for Tweet sentiment extraction Challenge. https://www.kaggle.com/c/tweet-sentiment-extraction

# Problem

Given a tweet and sentiment extract the 'phrase' leading to a sentiment.

input = {'sentence': 'soo sad I missed you here in san diego', 'sentiment':'negative'}
expected output = {'target':'soo sad'}

# Evaluation

Jaccard similarity between phrases of target and prediction.

```def jaccard(str1, str2): 

    a = set(str1.lower().split()) 
    b = set(str2.lower().split())
    c = a.intersection(b)
    return float(len(c)) / (len(a) + len(b) - len(c))
 ```
    

# Approach

Straight forward way to approach this problem is to `use a recurrent neural network on char-level emebedding to predict the characters which appear in output.`

NER approach:
Formulate this task as named entity recognition task. All the words in the output are marked as entities to be recognized from the input. Instead of characters we predict words here.

QA approach: We can formulate this problem Question answering problem with 

1. `sentiment`     as question.
1. `text`          as context.
1. `selected_text` as answer

and apply BERT-based models like RoBERTa, ALBERT models. (Current state-of-art models)


Judging by the notebooks in the competition page, BERT-based models seem to outperform other approaches. Based 

TODO
- [ ] Apply ALBERT model and record cv-score
- [ ] Apply BERT model and record cv-score

