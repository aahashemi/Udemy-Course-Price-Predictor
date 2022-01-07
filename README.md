# Project Description

### Database
The database contains data of 10000 Udemy courses. Such as *id, title, is_paid, price, currency, and course URL*. There are two types of databases in this repository
1. `raw_udemy_databse.csv`
   

2. `cleaned_udemy_databse.csv`
    * The only differnce of this csv file with *raw_udemy_databse.csv* file is that the stop words in the **title** coloumn are removed.

````
STOP WORDS: They are commonly used in Text Mining and Natural Language Processing (NLP) to 
eliminate words that are so commonly used that they carry very little useful information.

Examples of stop words in English are “a”, “the”, “is”, “are” and etc. 
````
<br>

The two tables below illustrate the diffrence bwtween `raw_udemy_databse.csv`  and  `cleaned_udemy_databse.csv`:

#### raw_udemy_databse.csv
|id| `title`|is_paid|price|curreny|price_string|
|:------:| :------:|:------:|:------:|:------:|:------:|
|567828| 2022 Complete Python Bootcamp From Zero to Hero in Python|1|89.99|EUR|€89.99|

#### cleaned_udemy_database.csv
|id| `title`|is_paid|price|curreny|price_string|
|:------:| :------:|:------:|:------:|:------:|:------:|
|567828| complete python bootcamp zero hero python|1|89.99|EUR|€89.99|

Stop words “2022”, “From”, “to”, “in” are removed
- - - -
### Word2Vec Model

The `word2vec_udemy.model` is the vector representation model for the udemy courses titles. This model computes the similarity between the courses' title in the dataset



# How To Use It?
To use this tool all you need to do is to call the **predictPrice()** function in the `Udemy_Course_Price_Predictor.ipynb`. 
<br>
Note: Make sure the DATABSE_PATH (cleaned_udemy_databse.csv) and MODEL_PATH (word2vec_udemy.model) are set correctly


### Example 1 - single keyword ###
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



