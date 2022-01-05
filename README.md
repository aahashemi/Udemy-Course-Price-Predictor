# Project Description

|id| title|is_paid|price|curreny|price_string|
|:------| :------|:------|:------|:------|:------|
|567828| 2022 Complete Python Bootcamp From Zero to Hero in Python|1|89.99|EUR|€89.99|


|id| title|is_paid|price|curreny|price_string|
|:------| :------|:------|:------|:------|:------|
|567828| complete python bootcamp zero hero python|1|89.99|EUR|€89.99|





# How To Use It?


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



