# About The Project
In this project, you can predict a Udemy course price by providing a list of keywords (words that may be used in the course title).
Follow the [Project Description](#ProjectDescription) to see what each of the files in this repository are used for. Or else, go to the
[How To Use It?](#HowToUseIt) section to use the AI tool.

<br>

1. [Project Description](#ProjectDescription)
   * [Database](#Database)
      * [raw_udemy_databse.csv](#raw_udemy_databse.csv)
      * [raw_udemy_databse.csv](#raw_udemy_databse.csv)
   * [word2vec_udemy.model](#word2vec_udemy.model)
   * [Ceate_Word2Vec_Model_From_Scratch.ipynb](#Ceate_Word2Vec_Model_From_Scratch.ipynb)
   * [Udemy_Course_Price_Predictor.ipynb](#Udemy_Course_Price_Predictor.ipynb)
   
   
  
2. [How To Use It?](#HowToUseIt)



<a id="ProjectDescription"></a> 
# Project Description
<a id="Database"></a>  
### Database
The database contains data of 10000 Udemy courses. Such as *id, title, is_paid, price, currency, and course URL*. There are two types of databases in this repository.
1. `raw_udemy_databse.csv`
   
2. `cleaned_udemy_databse.csv`
    * The only difference between this CSV file and the *raw_udemy_databse.csv* file is that the stop words in the **title** column are removed.

````
STOP WORDS: They are commonly used in Text Mining and Natural Language Processing (NLP) to 
eliminate words that are so commonly used that they carry very little useful information.

Examples of stop words in English are “a”, “the”, “is”, “are” and etc. 
````
<br>

The two tables below illustrate the difference between  `raw_udemy_databse.csv`  and  `cleaned_udemy_databse.csv`:
<a id="raw_udemy_databse.csv"></a> 
#### raw_udemy_databse.csv
|id| `title`|is_paid|price|curreny|price_string|
|:------:| :------:|:------:|:------:|:------:|:------:|
|567828| 2022 Complete Python Bootcamp From Zero to Hero in Python|1|89.99|EUR|€89.99|

<a id="cleaned_udemy_database.csv"></a>  
#### cleaned_udemy_database.csv
|id| `title`|is_paid|price|curreny|price_string|
|:------:| :------:|:------:|:------:|:------:|:------:|
|567828| complete python bootcamp zero hero python|1|89.99|EUR|€89.99|

Stop words “2022”, “From”, “to”, “in” are removed
- - - -
<a id="word2vec_udemy.model"></a>  
### word2vec_udemy.model

The `word2vec_udemy.model` is the vector representation model for the Udemy courses titles. This model computes the similarity between the courses' titles in the dataset. This model will be used for price prediction.

- - - -

<a id="Ceate_Word2Vec_Model_From_Scratch.ipynb"></a>  
### Ceate_Word2Vec_Model_From_Scratch.ipynb
A notebook **tutorial** to build a Word2Vec model from scratch in order to predict the keyword similarities in the Udemy course titles.
This tutorial is designed for those who are interested in how I came up with the `word2vec_udemy.model`. 


- - - -
<a id="Udemy_Course_Price_Predictor.ipynb"></a>  
### Udemy_Course_Price_Predictor.ipynb
A notebook **tutorial** that uses the pre-trained word2vec_udemy.model in order to predict the price of a Udemy course based on a list of keywords. Follow this tutorial for the step-by-step guide through.


<a id="HowToUseIt"></a>  
# How To Use It?
To use this tool all you need to do is to call the **predictPrice()** function in the `Udemy_Course_Price_Predictor.ipynb`. 
<br>
Follow the **`Udemy_Course_Price_Predictor.ipynb`** tutorial to learn how to use the function
<br>



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

### Example 3 - error keyword ###

```python
predictPrice(keyWords=['instagram','hamburger'],topn=2)
```

**`Output:`**
```bash
Error message: "word 'hamburger' not in vocabulary"
```



