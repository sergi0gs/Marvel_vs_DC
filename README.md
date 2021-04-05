# Table of Contents
- [Introduction](#introduction)
- [Resources](#resources)
- [What do we want to know?](#what-do-we-want-to-know-)
- [Data Exploration](#data-exploration)
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
- [Questions](#questions)

# INTRODUCTION

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

# RESOURCES
We are going to use the next 3 datasets 👇:
1. [SuperHero.csv](https://github.com/sergi0gs/Marvel_vs_DC/blob/main/datasets/SuperheroDataset.csv)
2. [heroes_information.csv](https://github.com/sergi0gs/Marvel_vs_DC/blob/main/datasets/heroes_information.csv)
3. [super_hero_powers.csv](https://github.com/sergi0gs/Marvel_vs_DC/blob/main/datasets/super_hero_powers.csv)

# WHAT DO WE WANT TO KNOW? ❓❓❓❓
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

# DATA EXPLORATION
### IMPORT LIBRARIES
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
%matplotlib inline

```
--------------------------------------------------------

### READ FILES
In this case we are going to use the raw version of github.
```
superhero = pd.read_csv('https://raw.githubusercontent.com/sergi0gs/Marvel_vs_DC/main/datasets/SuperheroDataset.csv')
heroes_information = pd.read_csv('https://raw.githubusercontent.com/sergi0gs/Marvel_vs_DC/main/datasets/heroes_information.csv')
super_hero_powers = pd.read_csv('https://github.com/sergi0gs/Marvel_vs_DC/blob/main/datasets/super_hero_powers.csv')
```
--------------------------------------------------------

### DATA SHAPE
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

### INFORMATION
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

### NULL VALUES
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

### DUPLICATES
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

# DATA CLEANING
In this part we are going to filter the data about Marvel Comics and DC Comics
##### SuperHero.csv
Remember the last notes:
- shape: (743,29)
- Lots of null values in "Skin color"
- We won't use some columns
- We don't have duplicate rows
- We can filter with the "Creator" column.
- 
**Step 1:** Eliminate unnecessary columns like: "Skin color","Unnamed: 0", "Unnamed: 0.1",'Url','Full name,'Alter Egos','Aliases','Place of birth','Eye color','Hair color','Occupation','Base','Team Affiliation','Relatives'
```
superhero_clean = superhero.copy(deep = True)
superhero_clean.drop(columns = ['Skin color','Unnamed: 0', 'Unnamed: 0.1','Url','Full name','Alter Egos','Aliases',
                                'Place of birth','Height','Weight','Eye color','Hair color','Occupation','Base','Team Affiliation','Relatives','First appearance'], inplace=True)
superhero_clean
```

![super_hero_clean_1](https://user-images.githubusercontent.com/71573671/113637000-361b6780-9639-11eb-9a37-471a7c19d131.PNG)

Remember: 743 rows x 12 columns

**Step 2:** Count the number of values in Marvel Comics and DC Comics

```
superhero_clean['Creator'].value_counts()
```

![superhero_value_counts](https://user-images.githubusercontent.com/71573671/113464635-c7999800-93f3-11eb-9d09-34ec8bd45832.png)

The number of Marvel Comics + DC Comics = 614. We must remember it.

**Step 3: filter by comics.
```
filter_sh = (superhero_clean['Creator'] == 'Marvel Comics') | (superhero_clean['Creator'] == 'DC Comics') 
superhero_clean = superhero_clean[filter_sh]
superhero_clean
```

![superhero_filter](https://user-images.githubusercontent.com/71573671/113637234-b8a42700-9639-11eb-8b45-de046ca6a0b7.PNG)

We can see that the number of columns is 614 so we did it well.
--------------------------------------------------------

##### heroes_information_csv
Remember the last notes:
- Shape: (734,11)
- "Unnamed: 0" is unnecesarry
- We can filter with the "Publisher" column.
- There are not null values and duplicates.

**Step 1:** Eliminate 'Unnamed: 0','Hair color','Height','Skin color','Height','Weight'
```
heroes_information_clean = heroes_information.copy(deep = True)
heroes_information_clean.drop(columns = ['Unnamed: 0','Eye color','Hair color','Height','Skin color','Height','Weight'], inplace = True)
heroes_information_clean
```

![heros_information_drop](https://user-images.githubusercontent.com/71573671/113637348-fd2fc280-9639-11eb-9cdd-c74c0bfbbd87.PNG)

It is Okey.

**Step 2** : Filter by comics.
```
filter_hi = (heroes_information_clean['Publisher'] == 'Marvel Comics') | (heroes_information_clean['Publisher'] == 'DC Comics') 
heroes_information_clean = heroes_information_clean[filter_hi]
heroes_information_clean
```

![heros_information_filter](https://user-images.githubusercontent.com/71573671/113637400-20f30880-963a-11eb-85ca-87f56b9d35e2.PNG)

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

We need to transform the data in a long format to visualize it better.

**Step 1:** Obtain all the columns as a list
```
super_hero_powers_clean = super_hero_powers.copy(deep = True)
shpc_columns = list(super_hero_powers_clean.columns)
shpc_columns
```

**Step 2:** Eliminate the first value
```
shpc_columns.remove('hero_names')
shpc_columns
```
**Step 3:** Melt the data to transform it to a long format
```
sphc_melt = pd.melt(super_hero_powers_clean, id_vars='hero_names',value_vars = shpc_columns)
sphc_melt
```

![super_hero_power_melt](https://user-images.githubusercontent.com/71573671/113637563-7f1feb80-963a-11eb-85d1-09e5d8efdb0f.PNG)

**Step 4:** Filter with True Value
```
filter_sphc = sphc_melt['value'] == True
sphc_melt = sphc_melt[filter_sphc]
sphc_melt
```

![super_hero_power_melt_true](https://user-images.githubusercontent.com/71573671/113637625-abd40300-963a-11eb-90f7-1a4d4ca8dac0.PNG)

New shape: (5874,3)

**Step 5:** Group by "hero_names"
```
sphc_melt = sphc_melt.groupby('hero_names')['variable'].apply(list).reset_index()
sphc_melt
```

![super_hero_power_groupby](https://user-images.githubusercontent.com/71573671/113637689-d920b100-963a-11eb-9033-be81bf30175a.PNG)

New shape: (667,2)

**Step 6:** Change name columns "variable" to "super_power"
```
sphc_melt.rename(columns={'variable':'super_powers'},inplace=True)
sphc_melt
```

![super_hero_power_groupby_rename](https://user-images.githubusercontent.com/71573671/113637774-05d4c880-963b-11eb-95da-6f3d390abd1d.PNG)

--------------------------------------------------------

### CROSS THE DATAFRAMES IN ONLY ONE
#### Join SuperHero and Heroes information
Left: SuperHero (614 rows)

Right: heroes_information (603 rows)

Use Left Join because superhero_clean have more rows

```
data_join = pd.merge(superhero_clean, heroes_information_clean, how = 'left', left_on= 'Name', right_on= 'name')
data_join
```

![join_sh_hi](https://user-images.githubusercontent.com/71573671/113638135-c3f85200-963b-11eb-931a-2df06460fb10.PNG)

#### Check null values and drop unnecessary columns
```
data_join.isnull().sum()
```

![join_null_values](https://user-images.githubusercontent.com/71573671/113638215-f3a75a00-963b-11eb-86c5-251ec6f4ddb9.PNG)

Drop: 'name','Gender_y','Race_y','Publisher','Alignment_y'
```
data_join.drop(columns=['name','Gender_y','Race_y','Publisher','Alignment_y'], inplace=True)
data_join
```

![join_sh_hi_drop](https://user-images.githubusercontent.com/71573671/113638308-2a7d7000-963c-11eb-9ca6-139bc26af20d.PNG)

Change the name of columns with "_x" in its names.
```
data_join.rename(columns={'Alignment_x':'Alignment','Gender_x':'Gender','Race_x':'Race'}, inplace= True)
data_join
```

--------------------------------------------------------

#### Left join between "data_join" and "super_hero_powers_clean"

Left: data_join (653 rows)

Right: shpc_melt (667 rows)

```
data_join_2 = pd.merge(data_join,sphc_melt,how='left',left_on='Name',right_on='hero_names')
data_join_2
```

![join_2](https://user-images.githubusercontent.com/71573671/113638456-821bdb80-963c-11eb-9aab-45e4c417db6d.PNG)


Check null values and drop unnecessary columns
```
data_join_2.isnull().sum()
```

![join_2_null_values](https://user-images.githubusercontent.com/71573671/113638534-b0012000-963c-11eb-8d29-7fa41a851f66.PNG)

Compare between Name and null values of hero_names
```
data_join_2[data_join_2['hero_names'].isnull()]
```

We can see that there 89 rows of Null values in the columns "hero_names", but it is the opposite in the column "Name" so we are going to Drop the column "hero_names"
```
data_join_2.drop(columns=['hero_names'], inplace = True)
data_join_2
```

![join_2_null__drop](https://user-images.githubusercontent.com/71573671/113638801-50efdb00-963d-11eb-901b-6b5ce6f2c412.PNG)

Replace null values of "super_powers" by a "Empty"
```
data_join_2.fillna(data_join_2.median(),inplace = True)
data_join_2
```
Check null values
```
data_join_2.isnull().sum()
```

![join_2_null_fillna_num](https://user-images.githubusercontent.com/71573671/113638945-af1cbe00-963d-11eb-9b76-1e370c5c2b4a.PNG)

The replace was ok.

Now, change null values of superpowers for "Empty"
```
data_join_2.fillna("Empty",inplace = True)
data_join_2
```

Check null values

```
data_join_2.isnull().sum()
```

![join_2_null_values_ok](https://user-images.githubusercontent.com/71573671/113639137-1c305380-963e-11eb-980f-42a5c47cfa7e.PNG)


![join_2_null_fillna_category](https://user-images.githubusercontent.com/71573671/113639074-002cb200-963e-11eb-8043-6dedf9d83158.PNG)

--------------------------------------------------------

### OUR FINAL DATAFRAME
Make a copy of "data_join_2"
```
final_df = data_join_2.copy(deep=True)
final_df
```

# Questions 
### 1.How many heroes are there in DC Comics and Marvel Comics?
**Step 1:** Use Column "Creator"
```
q1 = final_df['Creator']
q1.value_counts()
```
**Step 2:** Plot
```
fig,ax = plt.subplots()
ax.bar(q1.value_counts().index, q1.value_counts())
ax.set_title('Characters by comics')
ax.set_xlabel('Comic')
ax.set_ylabel('Nro.')

plt.show()
```

![q1_plot](https://user-images.githubusercontent.com/71573671/113639338-8b0dac80-963e-11eb-9d3f-c9a8d46dd715.png)



### 2.What is the predominant gender in the characters of DC Comics and Marvel Comics?
**Step 1:** Use only "Creator" and "Gender" columns
```
q2 = final_df.loc[:,['Creator','Gender']]
q2
```
**Step 2:** Check the value_counts()
```
q2.value_counts()
```

![q2_value_counts](https://user-images.githubusercontent.com/71573671/113639421-c4461c80-963e-11eb-89c5-af989fbb6cb8.PNG)

**Step 3:** We see that there are 28 values whit this 👉 ' - '. It means that there are characters which can not be considered a Gender. Remember that the Gender depends of the Race so in order to not confused you we are going to change it by 'Without Gender"
```
q2.replace({'-':'Without Gender'}, inplace=True)
q2_values = q2.value_counts()
q2_values= q2_values.reset_index()
q2_values
```

![q2_new_df](https://user-images.githubusercontent.com/71573671/113639493-e93a8f80-963e-11eb-8ce6-f13b0e7804b2.PNG)

**Step 4:** Change '0' by 'Values'
```
q2_values.rename(columns={0:'Values'},inplace = True)
q2_values
```

**Step 5:** Create a Pivot Table:

values='Values.

index='Creator'.

columns='Gender'
```
q2_pivot_table = q2_values.pivot_table(values='Values',index='Creator',columns='Gender')
q2_pivot_table
```

![q2_pivot_table](https://user-images.githubusercontent.com/71573671/113639606-299a0d80-963f-11eb-82a2-9f480e9a9abf.PNG)

**Step 6:** Plot the Pivot Table:
```
labels = list(q2_pivot_table.index)
female_means = list(q2_pivot_table['Female'])
male_means = list(q2_pivot_table['Male'])
without_gender_means = list(q2_pivot_table['Without Gender'])

x=np.arange(len(labels))
width=0.2

fig, ax = plt.subplots()

female_bar = ax.bar(x-width/2 , female_means, width, label = 'Female')
male_bar = ax.bar(x+width/2, male_means ,width, label = 'Male')
without_gender_bar = ax.bar(x+3*(width/2), without_gender_means ,width, label = 'Without Gender')

ax.set_title('Predominant Gender by Comics')
ax.set_xlabel('Comic')
ax.set_ylabel('Number')
ax.set_xticks(x)
ax.set_xticklabels(labels)
ax.legend()

def autolabel(bar):
  width=0.2
  for p in ax.patches:
      ax.annotate(str(p.get_height()), (p.get_x()+0.05, p.get_height()))
    
autolabel(female_bar)
autolabel(male_bar)

fig.tight_layout()
plt.show()
```

![q2_plot](https://user-images.githubusercontent.com/71573671/113639661-48989f80-963f-11eb-8418-5e698ea0b19f.png)





### 3.What is the predominant race in both comics?
### 4.Which has more Heroes or Villains?
### 5.Realize a comparative between the character abilites of both comics.
### 6.Who are the most intelligent characters?
### 7.Who are the strongest characters?
### 8.Who are the fastest characters?
### 9.Who are the characters with more power?
### 10.What superpowers predominate in the characters of DC Comics and Marvel Comics?
