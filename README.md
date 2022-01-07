# Project Description

### Database

1. `raw_udemy_databse.csv`
              1. A nested numbered list
              2. Which is numbered
2.`cleaned_udemy_databse.csv`

The only difference between `raw_udemy_databse.csv` and `cleaned_udemy_databse.csv` is that the stop words in the **title** coloumn  are removed in `cleaned_udemy_databse.csv`

````
Stop words are commonly used in Text Mining and Natural Language Processing (NLP) to 
eliminate words that are so commonly used that they carry very little useful information.

Examples of stop words in English are “a”, “the”, “is”, “are” and etc. 
````

#### raw_udemy_databse.csv
|id| `title`|is_paid|price|curreny|price_string|
|:------:| :------:|:------:|:------:|:------:|:------:|
|567828| 2022 Complete Python Bootcamp From Zero to Hero in Python|1|89.99|EUR|€89.99|

<br>


#### cleaned_udemy_database.csv
|id| `title`|is_paid|price|curreny|price_string|
|:------:| :------:|:------:|:------:|:------:|:------:|
|567828| complete python bootcamp zero hero python|1|89.99|EUR|€89.99|

Stop words “2022”, “From”, “to”, “in” are removed

### Word2Vec

word2vec_udemy.model

# How To Use It?


###Example 1 - single keyword ###
```python
predictPrice(keyWords='english',topn=4)
```

**`Output:`**
```bash
Top 4 key words with the highest similarity:  ['speaking', 'language', 'start', 'writing']
Predicted price:  74 Euro
```

### Example 2 - multiple keywords ###

```python
predictPrice(keyWords=['machine','learning'],topn=6)
```

**`Output:`**
```bash
Top 6 key words with the highest similarity: ['data', 'python', 'r', 'deep', 'science', 'tableau'] 
Predicted price:  76 Euro
```

### Example 3 - error keywork ###

```python
predictPrice(keyWords=['instagram','hamburger'],topn=2)
```

**`Output:`**
```bash
Error message: "word 'hamburger' not in vocabulary"
```



