# Table of Contents
- [Introduction](#introduction)
- [Resources](#resources)
- [What do we want to know?](#what-do-we-want-to-know-)
- [Data Exploratory](#data-exploratory)
  - [Import libraries](#import-libraries)
  - [Read files](#read-files)
  - [Data shape](#data-shape)
    - [SuperHero.csv](#superherocsv)
    - [heroes_information_csv](#heroes_information_csv)
    - [Super_hero_powers.csv](#super_hero_powerscsv)
  - [Information](#information)
    - [SuperHero.csv](#superherocsv-1)
    - [heroes_information_csv](#heroes_information_csv-1)
    - [Super_hero_powers.csv](#super_hero_powerscsv-1)
  - [Null values](#null-values)
    - [SuperHero.csv](#superherocsv-2)
    - [heroes_information_csv](#heroes_information_csv-2)
    - [Super_hero_powers.csv](#super_hero_powerscsv-2) 
  - [Duplicates](#duplicates)
    - [SuperHero.csv](#superherocsv-3)
    - [heroes_information_csv](#heroes_information_csv-3)
    - [Super_hero_powers.csv](#super_hero_powerscsv-3)
- [Data Cleaning](#data-cleaning)
  - [SuperHero.csv](#superherocsv-4)
  - [heroes_information_csv](#heroes_information_csv-4)
  - [Super_hero_powers.csv](#super_hero_powerscsv-4)
- [Data Wrangling](#data-wrangling)
  - [SuperHero.csv](#superherocsv-5)
  - [heroes_information_csv](#heroes_information_csv-5)
  - [Super_hero_powers.csv](#super_hero_powerscsv-5)
- [Questions](#questions)

# Introduction

In this project we will try to analyse the information about the heroes of Marvel and DC comics 🤩 learning about the different types of techniques that we have in Python to analyse, clean, transform and visualize data 📊

The information comes from these datasets in kaggle:
https://www.kaggle.com/thec03u5/complete-superhero-dataset, 
https://www.kaggle.com/claudiodavi/superhero-set

Which was constructed using web scrapping tecniques from the next website 👇: 
https://www.superherodb.com/.

Alse we use as a guide the next example maked in R from 👇: 
https://cosmoduende.medium.com/dc-comics-vs-marvel-comics-an%C3%A1lisis-exploratorio-y-visualizaci%C3%B3n-de-datos-con-r-b0cf565e44e2

You can execute this project in the link 👇: 
https://colab.research.google.com/drive/10FLK0zI3RWUyMDFuFGhjRH1ImmZWYKKO?authuser=2#scrollTo=JJq8smoyAiU_

# Resources
We are going to use the next 3 datasets 👇:
1. [SuperHero.csv](https://github.com/sergi0gs/Marvel_vs_DC/blob/main/datasets/SuperheroDataset.csv)
2. [heroes_information.csv](https://github.com/sergi0gs/Marvel_vs_DC/blob/main/datasets/heroes_information.csv)
3. [super_hero_powers.csv](https://github.com/sergi0gs/Marvel_vs_DC/blob/main/datasets/super_hero_powers.csv)

# What do we want to know? ❓❓❓❓
1. [How many heroes are there in DC Comics and Marvel Comics?](#1how-many-heroes-are-there-in-dc-comics-and-marvel-comics) 
2. [What is the predominant gender in the characters of DC Comics and Marvel Comics?](#2what-is-the-predominant-gender-in-the-characters-of-dc-comics-and-marvel-comics)
3. [What is the predominant race in both comics?](#3what-is-the-predominant-race-in-both-comics)
4. [Which has more Heroes or Villains?](#4which-has-more-heroes-or-villains)
5. [Realize a comparative between the character abilites of both comics.](#5realize-a-comparative-between-the-character-abilites-of-both-comics)
6. [Who are the most intelligent characters?](#6who-are-the-most-intelligent-characters)
7. [Which comic have the strongest characters?](#7who-are-the-strongest-characters)
8. [Which comic have the fastest characters?](#8who-are-the-fastest-characters)
9. [Which comic have the characters with more power?](#9who-are-the-characters-with-more-power)
10. [What superpowers predominate in the characters of DC Comics and Marvel Comics?](#10what-superpowers-predominate-in-the-characters-of-dc-comics-and-marvel-comics)

# Data Exploratory
### Import libraries
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline

```
--------------------------------------------------------

### Read files
In this case we are going to use the raw version of github.
```
superhero = pd.read_csv('https://raw.githubusercontent.com/sergi0gs/Marvel_vs_DC/main/datasets/SuperheroDataset.csv')
heroes_information = pd.read_csv('https://raw.githubusercontent.com/sergi0gs/Marvel_vs_DC/main/datasets/heroes_information.csv')
super_hero_powers = pd.read_csv('https://github.com/sergi0gs/Marvel_vs_DC/blob/main/datasets/super_hero_powers.csv')
```
--------------------------------------------------------

### Data shape
##### SuperHero.csv
```
superhero.shape
```

![superhero_shape](https://user-images.githubusercontent.com/71573671/112911245-9dc23780-90ba-11eb-9091-b8f43e1de6e1.PNG)

--------------------------------------------------------

##### heroes_information_csv
```
heroes_information.shape
```

![heroes_information_shape](https://user-images.githubusercontent.com/71573671/112911418-fe517480-90ba-11eb-8fc2-9252b53a4d25.PNG)

--------------------------------------------------------

##### Super_hero_powers.csv
```
super_hero_powers.shape
```

![super_hero_powers_shape](https://user-images.githubusercontent.com/71573671/112911460-13c69e80-90bb-11eb-8f3c-5c2ffc06c283.PNG)

--------------------------------------------------------

### Information
##### SuperHero.csv
```
superhero.info()
```

![superhero_info](https://user-images.githubusercontent.com/71573671/112911953-11187900-90bc-11eb-8403-20dc4fc3d5b9.png)

- We see that "Skin color" have very little information. It's important notice that because we are going to do something with it later.

Visualize 5 random rows
```
superhero.sample(5)
```

![superhero_sample](https://user-images.githubusercontent.com/71573671/113387005-09bdcd80-9351-11eb-9dd9-25f313675e15.png)

- We can see that there are some columns that we probably we are not going to use so we must remember this information to use it later. Also we can not see all the columns because there are a lot of its.

--------------------------------------------------------

##### heroes_information_csv
```
heroes_information.info()
```

![heroes_information_info](https://user-images.githubusercontent.com/71573671/113387386-d891cd00-9351-11eb-91aa-f705c5c752a8.PNG)

- It is Okey👆.

Visualize 5 random rows.

```
heroes_information.sample(5)
```

![heroes_information_sample](https://user-images.githubusercontent.com/71573671/113387554-260e3a00-9352-11eb-9d5b-02d0215f2aaf.PNG)

- We see that "Unnamed: 0" is unnecessary so probably we are going to do drop it later.

--------------------------------------------------------

##### Super_hero_powers.csv
```
super_hero_powers.info()
```

![super_hero_powers_info](https://user-images.githubusercontent.com/71573671/113387724-7c7b7880-9352-11eb-8dc6-d76ff8c02cd7.PNG)

- Notice that we cannot see the information about it because it have a lot of columns so we are going to see 5 rows of it to understand it better

Visualize 5 random rows.
```
super_hero_powers.sample(5)
```

![super_hero_powers_sample](https://user-images.githubusercontent.com/71573671/113388110-3a9f0200-9353-11eb-919b-ce6fa17eb71a.PNG)

- We can see that there are 168 columns. This is the reasons why we could not see it before so probably we are going to transform it in a long data format to solve it later.
--------------------------------------------------------

### Null Values
##### SuperHero.csv
```
superhero.isnull().sum()
```

![superhero_isnull_sum](https://user-images.githubusercontent.com/71573671/113388732-61116d00-9354-11eb-8af9-96bd51894bd2.PNG)

- We can see better about null values. In this case there are 669 null values in "Skin color" so we definetly are going to drop it later.
--------------------------------------------------------

##### heroes_information_csv
```
heroes_information.isnull().sum()
```

![heroes_information_isnull](https://user-images.githubusercontent.com/71573671/113388973-d1b88980-9354-11eb-81b6-162f82d43d36.PNG)

- It is Okey.

--------------------------------------------------------

##### Super_hero_powers.csv
```
super_hero_powers.isnull().sum()
```
![super_hero_powers_isnull](https://user-images.githubusercontent.com/71573671/113389117-15ab8e80-9355-11eb-9122-f0dad72071b0.PNG)

- There are a lot of columns so we are goint to calcule the sum() about the last sum().

```
super_hero_powers.isnull().sum().sum()
```

![super_hero_powers_isnull_sum_sum](https://user-images.githubusercontent.com/71573671/113389539-d6ca0880-9355-11eb-99ff-ac4595ccd349.PNG)

- There are not any null value.

--------------------------------------------------------

### Duplicates
##### SuperHero.csv
```
superhero.duplicated().sum()
```

![superhero_duplicate](https://user-images.githubusercontent.com/71573671/113389744-2c9eb080-9356-11eb-814a-b10068519df9.PNG)

- There are not any duplicate row.

--------------------------------------------------------

##### heroes_information_csv
```
heroes_information.duplicated().sum()
```

![heroes_information_duplicate](https://user-images.githubusercontent.com/71573671/113389922-6ff91f00-9356-11eb-811b-4278d117cc0b.PNG)

- There are not any duplicate row.
--------------------------------------------------------

##### Super_hero_powers.csv
```
super_hero_powers.duplicated().sum()
```

![super_hero_powers_duplicate](https://user-images.githubusercontent.com/71573671/113390081-a767cb80-9356-11eb-80ae-19767e5f894e.PNG)

- There are not any duplicate row.
--------------------------------------------------------

# Data Cleaning
In this part we are going to filter the data about Marvel Comics and DC Comics
##### SuperHero.csv
Remember the last notes:
- shape: (743,29)
- Lots of null values in "Skin color"
- We won't use "Unnamed: 0" and "Unnamed: 0.1"
- We don't have duplicate rows
- We can filter with the "Creator" column.
**Step 1:** Eliminate unnecessary columns like: "Skin color","Unnamed: 0" and "Unnamed: 0.1"
```
superhero_clean = superhero.copy(deep = True)
superhero_clean.drop(columns = ['Unnamed: 0','Unnamed: 0.1','Url','First appearance','Skin color'], inplace=True)
superhero_clean.head()
```

![superhero_drop_columns](https://user-images.githubusercontent.com/71573671/113464597-6d98d280-93f3-11eb-843e-028d4db8e59b.PNG)

Remember: 743 rows x 24 columns

**Step 2:** Filter by comics
Count the number of values in Marvel Comics and DC Comics
```
superhero_clean['Creator'].value_counts()
```

![superhero_value_counts](https://user-images.githubusercontent.com/71573671/113464635-c7999800-93f3-11eb-9d09-34ec8bd45832.png)

The number of Marvel Comics + DC Comics = 614. We must remember it.
Now, filter by comics.
```
filter_sh = (superhero_clean['Creator'] == 'Marvel Comics') | (superhero_clean['Creator'] == 'DC Comics') 
superhero_clean = superhero_clean[filter_sh]
superhero_clean
```
![superhero_filter](https://user-images.githubusercontent.com/71573671/113464666-25c67b00-93f4-11eb-924c-7ae00985c887.png)

We can see that the number of columns is 614 so we did it well.
--------------------------------------------------------

##### heroes_information_csv
Remember the last notes:
- Shape: (734,11)
- "Unnamed: 0" is unnecesarry
- We can filter with the "Publisher" column.
- There are not null values and duplicates.

**Step 1:** Eliminate "Unnamed: 0"
```
heroes_information_clean = heroes_information.copy(deep = True)
heroes_information_clean.drop(columns = ['Unnamed: 0'], inplace = True)
heroes_information_clean
```

![heores_information_drop](https://user-images.githubusercontent.com/71573671/113464818-290e3680-93f5-11eb-84ec-56229c6a64d3.PNG)

It is Okey.

**Step 2** : Filter by comics.
```
filter_hi = (heroes_information_clean['Publisher'] == 'Marvel Comics') | (heroes_information_clean['Publisher'] == 'DC Comics') 
heroes_information_clean = heroes_information_clean[filter_hi]
heroes_information_clean
```

![heores_information_filter](https://user-images.githubusercontent.com/71573671/113464963-3677f080-93f6-11eb-9ec8-6bd36d8fce64.PNG)

**Step 3:** Check the filter
```
heroes_information_clean['Publisher'].unique()
```

![heores_information_check_filter](https://user-images.githubusercontent.com/71573671/113464981-5c04fa00-93f6-11eb-9279-8cb036fb687d.PNG)

It is Okey.

--------------------------------------------------------

##### Super_hero_powers.csv
Remember the last notes:
- Shape: (667,168)
- The data format is wide so we must transform it
- There are not null values and duplicates.

In this case we do not need to clean something, only transform it in a longo format and then clean.

# Data Wrangling
##### SuperHero.csv
##### heroes_information_csv
##### Super_hero_powers.csv


# Questions 
### 1.How many heroes are there in DC Comics and Marvel Comics?
### 2.What is the predominant gender in the characters of DC Comics and Marvel Comics?
### 3.What is the predominant race in both comics?
### 4.Which has more Heroes or Villains?
### 5.Realize a comparative between the character abilites of both comics.
### 6.Who are the most intelligent characters?
### 7.Who are the strongest characters?
### 8.Who are the fastest characters?
### 9.Who are the characters with more power?
### 10.What superpowers predominate in the characters of DC Comics and Marvel Comics?
