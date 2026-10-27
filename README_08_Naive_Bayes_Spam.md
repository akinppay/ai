# 08 Naive Bayes Spam

## Python Code

```python
from sklearn.feature_extraction.text import CountVectorizer
from sklearn.naive_bayes import MultinomialNB
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score

emails = ['Win money now','Free prize claim','Meeting at 10 am',
          'Project update','Claim your reward','Lunch tomorrow']
labels = [1,1,0,0,1,0]
X_train,X_test,y_train,y_test = train_test_split(emails,labels,test_size=0.33,random_state=1)
vector = CountVectorizer()
X_train = vector.fit_transform(X_train)
X_test = vector.transform(X_test)
model = MultinomialNB().fit(X_train,y_train)
print('Accuracy:',accuracy_score(y_test,model.predict(X_test)))
print('Prediction:',model.predict(vector.transform(['free money offer'])))
```
