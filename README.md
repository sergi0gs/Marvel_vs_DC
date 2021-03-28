# Table of Contents
- [Introduction](#introduction)
- [What do we want to know?](#what-do-we-want-to-know)
- [Data Exploratory](#data-exploratory)
  - [Import libraries](#import-libraries)
  - [Read files](#read-files)
  - [Data shape](#data-shape)
  - [Print information about the dataframes](#print-information-about-the-dataframes)
  - [Lookinf for null values](#lookinf-for-null-values)
- [Data Cleaning](#data-cleaning)
- [Questions](#questions)



# Introduction

In this project we will try to analyse the information about the heroes of Marvel and DC comics learning about the different types of techniques that we have in Python to analyse, clean, transform and visualize data.

The information comes from these datasets in kaggle:
https://www.kaggle.com/thec03u5/complete-superhero-dataset, 
https://www.kaggle.com/claudiodavi/superhero-set

Which was constructed using web scrapping tecniques from the next website: https://www.superherodb.com/.

Alse we use as a guide the next example maked in R from: https://cosmoduende.medium.com/dc-comics-vs-marvel-comics-an%C3%A1lisis-exploratorio-y-visualizaci%C3%B3n-de-datos-con-r-b0cf565e44e2

You can execute this project in the link 👇: 
https://colab.research.google.com/drive/10FLK0zI3RWUyMDFuFGhjRH1ImmZWYKKO?authuser=2#scrollTo=JJq8smoyAiU_

# What do we want to know?
1. [How many heroes are there in DC Comics and Marvel Comics?](#1how-many-heroes-are-there-in-dc-comics-and-marvel-comics) 
2. [What is the predominant gender in the characters of DC Comics and Marvel Comics?](#2what-is-the-predominant-gender-in-the-characters-of-dc-comics-and-marvel-comics)
3. [What is the predominant race in both comics?](#3what-is-the-predominant-race-in-both-comics)
4. [Which has more Heroes or Villains?](#4which-has-more-heroes-or-villains)
5. [Realize a comparative between the character abilites of both comics.](#5realize-a-comparative-between-the-character-abilites-of-both-comics)
6. [Who are the most intelligent characters?](#6who-are-the-most-intelligent-characters)
7. [Who are the strongest characters?](#7who-are-the-strongest-characters)
8. [Who are the fastest characters?](#8who-are-the-fastest-characters)
9. [Who are the characters with more power?](#9who-are-the-characters-with-more-power)
10. [What superpowers predominate in the characters of DC Comics and Marvel Comics?](#10what-superpowers-predominate-in-the-characters-of-dc-comics-and-marvel-comics)

# Data Exploratory
### Import libraries

![import_libraries](https://user-images.githubusercontent.com/71573671/112564400-3306b880-8da9-11eb-9208-3664d6660664.PNG)

### Read files
In this case we are going to use the raw version of github.

![2_read_files](https://user-images.githubusercontent.com/71573671/112565235-ba086080-8daa-11eb-9e37-8d39bd040ba2.PNG)

### Data shape

![3_data_shape](https://user-images.githubusercontent.com/71573671/112565180-a0671900-8daa-11eb-87a2-3497b985000d.PNG)

### Print information about the dataframes

![4_information_df_1](https://user-images.githubusercontent.com/71573671/112566123-639c2180-8dac-11eb-8bc0-fb12578c5307.PNG)



![5_information_df_2](https://user-images.githubusercontent.com/71573671/112566122-639c2180-8dac-11eb-871b-05a58c23b9e7.PNG)



We see in this example that there are too many columns so later we will change it to a long format.

![6_information_df_3](https://user-images.githubusercontent.com/71573671/112566121-63038b00-8dac-11eb-9f53-c9d1c9e034ef.PNG)


### Lookinf for null values

![7_null_values](https://user-images.githubusercontent.com/71573671/112567241-82031c80-8dae-11eb-9b1d-8b995ef6b94f.PNG)

![8_nulls_values_super_hero_powers](https://user-images.githubusercontent.com/71573671/112567240-816a8600-8dae-11eb-8f41-1db2afd4b37a.PNG)

In this case, we can not see the total number of nulls so we are going tu "sum()" the result to know if there are any null in the whole dataframe.

![10_total_nulls_super_hero_powers](https://user-images.githubusercontent.com/71573671/112567446-db6b4b80-8dae-11eb-9aa0-3d85e4dbc370.PNG)

We can see that there are not any null value in this dataframe.

![9_nulls_values_super_heroes](https://user-images.githubusercontent.com/71573671/112567237-80d1ef80-8dae-11eb-9418-929a79c4aff0.PNG)


# Data Cleaning
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
