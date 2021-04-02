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
- [Data Cleaning](#data-cleaning)
  - [SuperHero.csv](#superherocsv-3)
  - [heroes_information_csv](#heroes_information_csv-3)
  - [Super_hero_powers.csv](#super_hero_powerscsv-3)
- [Data Wrangling](#data-wrangling)
  - [SuperHero.csv](#superherocsv-4)
  - [heroes_information_csv](#heroes_information_csv-4)
  - [Super_hero_powers.csv](#super_hero_powerscsv-4)
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
--------------------------------------------------------

![superhero_shape](https://user-images.githubusercontent.com/71573671/112911245-9dc23780-90ba-11eb-9091-b8f43e1de6e1.PNG)

##### heroes_information_csv
```
heroes_information.shape
```
--------------------------------------------------------

![heroes_information_shape](https://user-images.githubusercontent.com/71573671/112911418-fe517480-90ba-11eb-8fc2-9252b53a4d25.PNG)


##### Super_hero_powers.csv
```
super_hero_powers.shape
```
--------------------------------------------------------

![super_hero_powers_shape](https://user-images.githubusercontent.com/71573671/112911460-13c69e80-90bb-11eb-8f3c-5c2ffc06c283.PNG)


### Information
##### SuperHero.csv
```
superhero.info()
```
--------------------------------------------------------

![superhero_info](https://user-images.githubusercontent.com/71573671/112911953-11187900-90bc-11eb-8403-20dc4fc3d5b9.png)

👀 We see that "Skin color" have very little information. It's important notice that because we are going to do something with it later.

Visualize 5 random rows
```
superhero.sample(5)
```

![superhero_sample](https://user-images.githubusercontent.com/71573671/113387005-09bdcd80-9351-11eb-9dd9-25f313675e15.png)

--------------------------------------------------------

👀 We can see that there are some columns that we probably we are not going to use so we must remember this information to use it later. Also we can not see all the columns because there are a lot of its.

##### heroes_information_csv
```
heroes_information.info()
```

![heroes_information_info](https://user-images.githubusercontent.com/71573671/113387386-d891cd00-9351-11eb-91aa-f705c5c752a8.PNG)

It is Okey👆.

Visualize 5 random rows 👇

```
heroes_information.sample(5)
```

![heroes_information_sample](https://user-images.githubusercontent.com/71573671/113387554-260e3a00-9352-11eb-9d5b-02d0215f2aaf.PNG)

It is Okey👆.

--------------------------------------------------------

##### Super_hero_powers.csv
```
super_hero_powers.info()
```

![super_hero_powers_info](https://user-images.githubusercontent.com/71573671/113387724-7c7b7880-9352-11eb-8dc6-d76ff8c02cd7.PNG)

Notice that we cannot see the information about it because it have a lot of columns so we are going to see 5 rows of it to understand it better
```
super_hero_powers.sample(5)
```

![super_hero_powers_sample](https://user-images.githubusercontent.com/71573671/113388110-3a9f0200-9353-11eb-919b-ce6fa17eb71a.PNG)

👀 We can see that there are 168 columns. This is the reasons why we cannot see it so probably we are going to transform it in a long data format to solve it later.

### Null Values
##### SuperHero.csv
##### heroes_information_csv
##### Super_hero_powers.csv


# Data Cleaning
##### SuperHero.csv
##### heroes_information_csv
##### Super_hero_powers.csv

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
