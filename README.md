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
  - [1.How many heroes are there in DC Comics and Marvel Comics?](#1how-many-heroes-are-there-in-dc-comics-and-marvel-comics)
    - [Plot](#step-2-plot)
  - [2.What is the predominant gender in the characters of DC Comics and Marvel Comics?](#2what-is-the-predominant-gender-in-the-characters-of-dc-comics-and-marvel-comics)
    - [Plot](#step-6-plot-the-pivot-table)
  - [3.What is the predominant race in both comics?](#3what-is-the-predominant-race-in-both-comics)
    - [Plot](#step-5-plot)
  - [4.Which has more Heroes or Villains?](#4which-has-more-heroes-or-villains)
    - [Plot](#step-7-plot-pivot-table)
  - [5.What superpowers predominate in the characters of DC Comics and Marvel Comics?](#5what-superpowers-predominate-in-the-characters-of-dc-comics-and-marvel-comics)
    - [Plot]()
  - [6.Who are the most intelligent characters?](#6who-are-the-most-intelligent-characters)
    - [Plot]()
  - [7.Which comic have the strongest characters?](#7who-are-the-strongest-characters)
    - [Plot]()
  - [8.Which comic have the fastest characters?](#8who-are-the-fastest-characters)
     - [Plot]()
  - [9.Which comic have the characters with more power?](#9who-are-the-characters-with-more-power)
     - [Plot]()

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
5. [What superpowers predominate in the characters of DC Comics and Marvel Comics?](#5what-superpowers-predominate-in-the-characters-of-dc-comics-and-marvel-comics)
6. [Who are the most intelligent characters?](#6who-are-the-most-intelligent-characters)
7. [Which comic have the strongest characters?](#7who-are-the-strongest-characters)
8. [Which comic have the fastest characters?](#8who-are-the-fastest-characters)
9. [Which comic have the characters with more power?](#9who-are-the-characters-with-more-power)

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
In this part we are going to clean and correct the data about Marvel Comics and DC Comics
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

**Step 3:** filter by comics.
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

Replace null values of "super_powers" with the median.
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

![join_2_null_fillna_category](https://user-images.githubusercontent.com/71573671/113639074-002cb200-963e-11eb-8043-6dedf9d83158.PNG)

Check null values

```
data_join_2.isnull().sum()
```

![join_2_null_values_ok](https://user-images.githubusercontent.com/71573671/113639137-1c305380-963e-11eb-980f-42a5c47cfa7e.PNG)


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
#### **Step 2:** Plot
```
fig,ax = plt.subplots()
ax.bar(q1.value_counts().index, q1.value_counts())
ax.set_title('Characters by comics')
ax.set_xlabel('Comic')
ax.set_ylabel('Nro.')

plt.show()
```

![q1_plot](https://user-images.githubusercontent.com/71573671/113639338-8b0dac80-963e-11eb-9d3f-c9a8d46dd715.png)

--------------------------------------------------------

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

#### **Step 6:** Plot the Pivot Table:
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

--------------------------------------------------------

### 3.What is the predominant race in both comics?
**Step 1:** Use "Creator" and "Race" columns
```
q3_df = final_df.loc[:,['Creator','Race']]
q3_df
```

![q3](https://user-images.githubusercontent.com/71573671/113937664-2037af00-97bf-11eb-9348-9f262b3f7b13.PNG)

**Step 2:** Replace '-' by 'Without Race' and counts de values.
```
q3_df.replace({'-':'Witout Race'}, inplace=True)
q3_df = q3_df.value_counts().reset_index()
q3_df
```

![q3_replace_vc](https://user-images.githubusercontent.com/71573671/113937886-6f7ddf80-97bf-11eb-9019-f432aca7a903.PNG)

**Step 3:** Rename '0' by 'values'
```
q3_df.rename(columns={0:'Values'}, inplace=True)
q3_df
```

**Step 4:** Filter and separate in two dataframes by comics
```
q3_marvel = q3_df[q3_df['Creator'] == 'Marvel Comics']
q3_dc = q3_df[q3_df['Creator'] == 'DC Comics']
```

#### **Step 5:** Plot
```
fig, (ax1,ax2) = plt.subplots(1,2)
fig.set_size_inches(12,10)

ax1_values = list(q3_marvel['Values'])
ax1_labels = list(q3_marvel['Race'])

sns.barplot(x = ax1_values, y=ax1_labels , ax = ax1, orient = 'h', palette='Blues_d')
ax1.set_xticks(range(0,200,50))

ax1.set_title('Marvel Race',fontsize=16) 

for text_n, rect in zip(ax1_values, ax1.patches):
    width = rect.xy
    width, height = rect.get_width(), rect.get_height()
    x, y = rect.get_xy() 
    ax1.text(x = x + width , 
             y = y + height , 
             s =text_n)

fig.tight_layout()
plt.show()
```

![q3_plot](https://user-images.githubusercontent.com/71573671/113938860-cb953380-97c0-11eb-91b2-076632c286fb.png)

--------------------------------------------------------

### 4.Which has more Heroes or Villains?

**Step 1:** Use columns "Alignment" and "Creator"
```
q4_df = final_df.loc[:,['Creator','Alignment']]
q4_df
```

![q4_df](https://user-images.githubusercontent.com/71573671/114604383-6d53cf00-9c5e-11eb-8e1b-6bbae15ffefd.PNG)

**Step 2:** Check the value_counts()
```
q4_df.value_counts()
```

![q4_df_vañue_count](https://user-images.githubusercontent.com/71573671/114604486-8d838e00-9c5e-11eb-931d-fce3f1870a5d.PNG)

It's Ok. Rememer that the values in "blank" in "Creator" is the same of the value which is above of it.

**Step 3:** Replace "good" by "Hero" , "bad" by "Villains" ad '-' by 'Doubt'
```
q4_df.replace({'good':'Hero','bad':'Villain','-':'Doubt'}, inplace=True)
q4_df
```

**Step 4:** Compare with the value counts. Then make it in a dataframe
```
q4_df.value_counts()
```

![q4_df_replace](https://user-images.githubusercontent.com/71573671/114604760-ece19e00-9c5e-11eb-8358-21b239d7c310.PNG)

```
q4_df=q4_df.value_counts().reset_index()
q4_df
```

![q4_new_df](https://user-images.githubusercontent.com/71573671/114604889-17335b80-9c5f-11eb-9eb1-65ce78b4dc23.PNG)

**Step 5:** Change '0' by 'Values'
```
q4_df.rename(columns={0:'Values'}, inplace = True)
q4_df
```

**Step 6:** Create a Pivot Table

values='Values.

index='Creator'.

columns='Alignment'
```
q4_df = q4_df.pivot_table(index = 'Creator',columns='Alignment',values='Values')
q4_df
```

![q4_pivot](https://user-images.githubusercontent.com/71573671/114605052-49dd5400-9c5f-11eb-9340-616283db9a99.PNG)

#### **Step 7:** Plot pivot table
```
labels = list(q4_df.index)
doubt_data = list(q4_df['Doubt'])
hero_data = list(q4_df['Hero'])
villain_data = list(q4_df['Villain'])
neutral_data = list(q4_df['neutral'])

x=np.arange(len(labels))
width=0.2

fig, ax = plt.subplots()
doubt_bar = ax.bar(x-width/2, doubt_data, width, label = 'Doubt')
hero_bar = ax.bar(x+width/2, hero_data, width, label = 'Heroes')
villian_bar = ax.bar(x-3*(width/2), villain_data, width, label = 'Villains')
neutral_bar = ax.bar(x-5*(width/2), neutral_data, width, label = 'Neutrals')

ax.set_title('Heroes and Villians')
ax.set_xlabel('Comics')
ax.set_ylabel('Values')
ax.set_xticks(x)
ax.set_xticklabels(labels)
ax.legend()

def autolabel(bar):
  width=0.2
  for p in ax.patches:
      ax.annotate(str(p.get_height()), (p.get_x()+0.05, p.get_height()*1.01))

autolabel(doubt_bar)
autolabel(hero_bar)
autolabel(villian_bar)
autolabel(neutral_bar)

fig.tight_layout()
plt.show
```

![q4_plot](https://user-images.githubusercontent.com/71573671/114605375-a3458300-9c5f-11eb-9db6-1864d77508b4.png)

--------------------------------------------------------
### 5.What superpowers predominate in the characters of DC Comics and Marvel Comics?
**Step 1:** Use "Creator" and "super_powers"
```
q5_df = final_df.loc[:,['Creator','super_powers']]
q5_df
```

![q5_df](https://user-images.githubusercontent.com/71573671/114606437-df2d1800-9c60-11eb-84d8-ae09108e5376.PNG)

**Step 2:** Transform it in a long format
```
q5_df = q5_df.explode('super_powers')
q5_df
```

![q5_df_long_format](https://user-images.githubusercontent.com/71573671/114606602-156a9780-9c61-11eb-8917-9f5154381753.PNG)

**Step 3:** Verify unique values of "Creator"
```
q5_df['Creator'].unique()
```
It's Ok.

**Step 4:** Count the values and reset the index
```
q5_df = q5_df.value_counts().reset_index()
q5_df
```

![q5_df_new_df](https://user-images.githubusercontent.com/71573671/114606754-4d71da80-9c61-11eb-879f-8285844cc149.PNG)

**Step 5:** Rename column 0 by 'Values'
```
q5_df.rename(columns={0:'Values'}, inplace = True)
q5_df
```

**Step 6:** Filter by comics
```
q5_marvel = q5_df[(q5_df['Creator'] == 'Marvel Comics') & (q5_df['Values'] > np.median(q5_df['Values']))]
q5_dc = q5_df[(q5_df['Creator'] == 'DC Comics') & (q5_df['Values'] > np.median(q5_df['Values']))]
```

**Step 7:** Plot
```
fig, (ax1,ax2) = plt.subplots(1,2)
fig.set_size_inches(18,17)

# Marvel #
ax1_values = list(q5_marvel['Values'])
ax1_labels = list(q5_marvel['super_powers'])

sns.barplot(x = ax1_values, y = ax1_labels, ax = ax1, orient = 'h')
ax1.set_xticks(range(0,250,50))
ax1.set_title('Marvel super powers', fontsize = 16)


for text, rect in zip(ax1_values, ax1.patches):
  width, height = rect.get_width(), rect.get_height()
  x,y = rect.get_xy()
  ax1.text(x = x+width,
          y = y+height,
          s=text)

ax1.set_xlabel('Numbers of characters')
ax1.set_ylabel('Super Powers')
  
# DC #
ax2_values = list(q5_dc['Values'])
ax2_labels = list(q5_dc['super_powers'])

sns.barplot(x = ax2_values, y = ax2_labels, ax = ax2, orient = 'h')
ax2.set_xticks(range(0,250,50))
ax2.set_title('DC super powers', fontsize = 16)


for text_dc, rect_dc in zip(ax2_values, ax2.patches):
  width_dc, height_dc = rect_dc.get_width(), rect_dc.get_height()
  x_dc,y_dc = rect_dc.get_xy()
  ax2.text(x = x_dc + width_dc,
          y = y_dc + height_dc,
          s = text_dc)

ax2.set_xlabel('Numbers of characters')
ax2.set_ylabel('Super Powers')
      
fig.tight_layout()
plt.show()
```

![q5_plot](https://user-images.githubusercontent.com/71573671/114607376-164ff900-9c62-11eb-8c9f-55f5e24fd823.png)

--------------------------------------------------------
### 6.Who are the most intelligent characters?
**Step 1:** Use the next columns: "Name", "Creator" and "Intelligence".
```
q6_df = final_df.loc[:,['Name','Creator','Intelligence']]
q6_df
```

![q6_df](https://user-images.githubusercontent.com/71573671/114607656-6a5add80-9c62-11eb-89b1-5c9d128c71db.png)

**Step 2:** Separate by comics and filter with data > 4th quintil
```
# Quintil
q_val = [0,20,40,60,80,100]
quintiles = np.percentile(q6_df['Intelligence'], q = q_val)

q6_marvel = q6_df[(q6_df['Creator'] == 'Marvel Comics') & (q6_df['Intelligence'] > quintiles[4])]
q6_dc = q6_df[(q6_df['Creator'] == 'DC Comics') & (q6_df['Intelligence'] > quintiles[4])]
```

**Step 3:** Plot
```
fig, (ax1,ax2) = plt.subplots(1,2)
fig.set_size_inches(13,10)

def barplot(df,title,x_label,y_label,min_val,max_val,step,ax):
  ax_labels = list(df['Name'])
  ax_values = list(df['Intelligence'])
  sns.barplot(x = ax_values, y = ax_labels, ax = ax, orient='h')
  ax.set_xticks(range(min_val,max_val,step))
  ax.set_title(title, fontsize = 16)
  ax.set_xlabel(x_label)
  ax.set_ylabel(y_label)

def autolabel(df,ax):
  ax_labels = list(df['Name'])
  ax_values = list(df['Intelligence'])
  for text, rect in zip(ax_values, ax.patches):
    width, height = rect.get_width(), rect.get_height()
    x,y = rect.get_xy()
    ax.text(x = x+width,
            y = y+height,
            s=text)

# Marvel
barplot(q6_marvel,'Marvel','Values','Characters',0,150,20,ax1)
autolabel(q6_marvel,ax1)

# DC
barplot(q6_dc,'DC','Values','Characters',0,150,20,ax2)
autolabel(q6_dc,ax2)

fig.tight_layout()
plt.show()
```

![q6_plot_1](https://user-images.githubusercontent.com/71573671/114607805-94ac9b00-9c62-11eb-84b1-89b7f8d53f45.png)

This plot is not enough because there are lots of characters who have 100 points in "Intelligence" so we are going to campare between them with another graphic focus on their comics

**Step 4:** Use column "Creator" and "Intelligence"
```
q6_df = q6_df.loc[:,['Creator','Intelligence']]
q6_df
```

**Step 5:** Check the value counts of intelligence and make it in a new dataframe.
```
q6_df = q6_df.value_counts().reset_index()
q6_df
```

**Step 6:** Rename 0 by 'Values'
```
q6_df.rename(columns={0:'Values'}, inplace = True)
q6_df
```

![q6_df_2](https://user-images.githubusercontent.com/71573671/114608500-611e4080-9c63-11eb-83da-5f7006d104e5.PNG)

**Step 7:** Create a Pivot table to make the plot easier.
```
q6_pivot = q6_df.pivot_table(index = 'Creator', columns = 'Intelligence', values = 'Values')
q6_pivot
```

**Step 8:** Replace Null values by 0.
```
q6_pivot = q6_pivot.fillna(0)
q6_pivot
```

![q6_pivot](https://user-images.githubusercontent.com/71573671/114608672-8a3ed100-9c63-11eb-91db-1a430d9981da.PNG)

**Step 9:** Plot
Star from the column "75" because before it there are very little information.
```
q6_pivot = q6_pivot.iloc[:,6:12]
q6_pivot
```

code:
```
labels = list(q6_pivot.index)
data_75 = list(q6_pivot[75.0])
data_80 = list(q6_pivot[80.0])
data_85 = list(q6_pivot[85.0])
data_90 = list(q6_pivot[90.0])
data_95 = list(q6_pivot[95.0])
data_100 = list(q6_pivot[100.0])

x=np.arange(len(labels))
width=0.1

fig, ax = plt.subplots()
bar_75 = ax.bar(x-width/2, data_75, width, label = '75')
bar_80 = ax.bar(x+width/2, data_80, width, label = '80')
bar_85 = ax.bar(x-3*(width/2), data_85, width, label = '85')
bar_90 = ax.bar(x-5*(width/2), data_90, width, label = '90')
bar_95 = ax.bar(x-7*(width/2), data_95, width, label = '95')
bar_100 = ax.bar(x-9*(width/2), data_100, width, label = '100')


ax.set_title('Comics that has more intelligent characters')
ax.set_xlabel('Comics')
ax.set_ylabel('Values')
ax.set_xticks(x)
ax.set_xticklabels(labels)
ax.legend()

fig.tight_layout()
plt.show
```

![q6_plto_2](https://user-images.githubusercontent.com/71573671/114608978-e1dd3c80-9c63-11eb-8917-b557abf65291.png)

--------------------------------------------------------
### 7.Who are the strongest characters?
**Step 1:** Use the next columns: "Name", "Creator" and "Intelligence".
```
q7_df = final_df.loc[:,['Name','Creator','Strength']]
q7_df
```

![q7_df](https://user-images.githubusercontent.com/71573671/114632774-fa118380-9c84-11eb-96ce-16d48b7eda76.PNG)

**Step 2:** Separate by comics and filter with data > 4th quintil
```
# Quintiles
q_val = [0,20,40,60,80,100]
quintiles = np.percentile(q7_df['Strength'], q = q_val)

q7_marvel = q7_df[(q7_df['Creator'] == 'Marvel Comics') & (q7_df['Strength'] > quintiles[4])].fillna(0)
q7_dc = q7_df[(q7_df['Creator'] == 'DC Comics') & (q7_df['Strength'] > quintiles[4])].fillna(0)
```

**Step 3:** Plot
```
fig, (ax1,ax2) = plt.subplots(1,2)
fig.set_size_inches(13,17)

def barplot(df,title,x_label,y_label,min_val,max_val,step,ax):
  ax_labels = list(df['Name'])
  ax_values = list(df['Strength'])
  sns.barplot(x = ax_values, y = ax_labels, ax = ax, orient='h')
  ax.set_xticks(range(min_val,max_val,step))
  ax.set_title(title, fontsize = 16)
  ax.set_xlabel(x_label)
  ax.set_ylabel(y_label)

def autolabel(df,ax):
  ax_labels = list(df['Name'])
  ax_values = list(df['Strength'])
  for text, rect in zip(ax_values, ax.patches):
    width, height = rect.get_width(), rect.get_height()
    x,y = rect.get_xy()
    ax.text(x = x+width,
            y = y+height,
            s=text)

# Marvel
barplot(q7_marvel,'Marvel','Values','Characters',0,150,20,ax1)
autolabel(q7_marvel,ax1)

# DC
barplot(q7_dc,'DC','Values','Characters',0,150,20,ax2)
autolabel(q7_dc,ax2)

fig.tight_layout()
plt.show()
```

![q7_df_plot_1](https://user-images.githubusercontent.com/71573671/114632921-32b15d00-9c85-11eb-9a1f-2aca90fc6110.PNG)

This plot is not enough because there are lots of characters who have 100 points in "Strength" so we are going to campare between them with another graphic focus on their comics

**Step 4:** Use "Creator" and "Strength"
```
q7_df = q7_df.loc[:,['Creator','Strength']]
q7_df
```

![q7_df_2](https://user-images.githubusercontent.com/71573671/114632993-5e344780-9c85-11eb-9f02-d19ac2858682.PNG)

**Step 5:** Check the value counts of strength and make it in a new dataframe
```
q7_df = q7_df.value_counts().reset_index()
q7_df
```

**Step 6:** Rename 0 by 'Values'
```
q7_df.rename(columns={0:'Values'}, inplace = True)
q7_df = q7_df[q7_df['Values']>np.median(q7_df['Values'])] 
q7_df
```

![q7_rename](https://user-images.githubusercontent.com/71573671/114633100-90de4000-9c85-11eb-899b-9397d2396e88.PNG)

**Step 7:** Create a Pivot table to make the plot easier.
```
q7_pivot = q7_df.pivot_table(index = 'Creator', columns = 'Strength', values = 'Values')
q7_pivot
```

**Step 8:** Replace Null values by 0.
```
q7_pivot = q7_pivot.fillna(0)
q7_pivot
```

![q7_pivot](https://user-images.githubusercontent.com/71573671/114633466-22e64880-9c86-11eb-807b-bb0e2fa23e07.PNG)

**Step 9:** Plot
```
labels = list(q7_pivot.index)

x=np.arange(len(labels))
width=0.05

def plot(df,column_i, x , width, label, count):
  data = list(df[column_i])
  bar = ax.bar(x-width/2 + count*width, data, width, label = label)

fig, ax = plt.subplots()
fig.set_size_inches(10,6)
count = 0
for column_i in q7_pivot.columns:
  plot(q7_pivot, column_i, x, width, str(column_i), count)
  count += 1

ax.set_title('Comics that has the stronger characters')
ax.set_xlabel('Comics')
ax.set_ylabel('Values')
ax.set_xticks(x)
ax.set_xticklabels(labels)
ax.legend()

fig.tight_layout()
plt.show
```

![q7_plot](https://user-images.githubusercontent.com/71573671/114633511-3d202680-9c86-11eb-985d-0d6c71e5d00a.png)

--------------------------------------------------------
### 8.Who are the fastest characters?
**Step 1:** Use the next columns: "Name", "Creator" and "Speed".
```
q8_df = final_df.loc[:,['Name','Creator','Speed']]
q8_df
```

![q8_df](https://user-images.githubusercontent.com/71573671/114633558-57f29b00-9c86-11eb-9fd2-8f292ee4f533.PNG)

**Step 2:** Separate by comics and filter with data > 4th quintil
```
q_val = [0,20,40,60,80,100]
quintiles = np.percentile(q8_df['Speed'], q = q_val)

q8_marvel = q8_df[(q8_df['Creator'] == 'Marvel Comics') & (q8_df['Speed'] > quintiles[4])].fillna(0)
q8_dc = q8_df[(q8_df['Creator'] == 'DC Comics') & (q8_df['Speed'] > quintiles[4])].fillna(0)
```

**Step 3:** Plot
```
fig, (ax1,ax2) = plt.subplots(1,2)
fig.set_size_inches(13,17)

def barplot(df,title,x_label,y_label,min_val,max_val,step,ax):
  ax_labels = list(df['Name'])
  ax_values = list(df['Speed'])
  sns.barplot(x = ax_values, y = ax_labels, ax = ax, orient='h')
  ax.set_xticks(range(min_val,max_val,step))
  ax.set_title(title, fontsize = 16)
  ax.set_xlabel(x_label)
  ax.set_ylabel(y_label)

def autolabel(df,ax):
  ax_labels = list(df['Name'])
  ax_values = list(df['Speed'])
  for text, rect in zip(ax_values, ax.patches):
    width, height = rect.get_width(), rect.get_height()
    x,y = rect.get_xy()
    ax.text(x = x+width,
            y = y+height,
            s=text)

# Marvel
barplot(q8_marvel,'Marvel','Values','Characters',0,150,20,ax1)
autolabel(q8_marvel,ax1)

# DC
barplot(q8_dc,'DC','Values','Characters',0,150,20,ax2)
autolabel(q8_dc,ax2)

fig.tight_layout()
plt.show()
```

![q8_plot_1](https://user-images.githubusercontent.com/71573671/114633618-807a9500-9c86-11eb-9ae7-b1ccdae5dd36.png)

This plot is not enough because there are lots of characters who have 100 points in "Speed" so we are going to campare between them with another graphic focus on their comics.

**Step 4:** Use "Creator" and "Speed"
```
q8_df = q8_df.loc[:,['Creator','Speed']]
q8_df
```

![q8_df_2](https://user-images.githubusercontent.com/71573671/114633674-9be5a000-9c86-11eb-8fac-c64e735763be.PNG)

**Step 5:** Check the value counts of speed and make it in a new dataframe
```
q8_df = q8_df.value_counts().reset_index()
q8_df
```

**Step 6:** Rename 0 by 'Values' and filter using median
```
q8_df.rename(columns={0:'Values'}, inplace = True)
q8_df = q8_df[q8_df['Values']>np.median(q8_df['Values'])] 
q8_df
```

![q8_2_value_c](https://user-images.githubusercontent.com/71573671/114633829-e7984980-9c86-11eb-9116-b63850566fef.PNG)

**Step 7:** Create a Pivot table to make the plot easier.
```
q8_pivot = q8_df.pivot_table(index = 'Creator', columns = 'Speed', values = 'Values')
q8_pivot
```

**Step 8:** Replace Null values by 0.
```
q8_pivot = q8_pivot.fillna(0)
q8_pivot
```

![q8_2_pivot](https://user-images.githubusercontent.com/71573671/114633917-11ea0700-9c87-11eb-8bbb-f9f12422e07d.PNG)

**Step 9:** Plot
```
labels = list(q8_pivot.index)

x=np.arange(len(labels))
width=0.05

def plot(df,column_i, x , width, label, count):
  data = list(df[column_i])
  bar = ax.bar(x-width/2 + count*width, data, width, label = label)

fig, ax = plt.subplots()
fig.set_size_inches(10,6)
count = 0
for column_i in q8_pivot.columns:
  plot(q8_pivot, column_i, x, width, str(column_i), count)
  count += 1

ax.set_title('Comics that has the fastest characters')
ax.set_xlabel('Comics')
ax.set_ylabel('Values')
ax.set_xticks(x)
ax.set_xticklabels(labels)
ax.legend()

fig.tight_layout()
plt.show
```

![q9_plot_2](https://user-images.githubusercontent.com/71573671/114633967-275f3100-9c87-11eb-97bc-fd7591cc5551.png)

--------------------------------------------------------
### 9.Who are the characters with more power?

**Step 1:** Use the next columns: "Name", "Creator" and "Power".
```
q9_df = final_df.loc[:,['Name','Creator','Power']]
q9_df
```

![q9_df](https://user-images.githubusercontent.com/71573671/114635577-9be79f00-9c8a-11eb-8860-0e6b92fef2c8.PNG)

**Step 2:** Separate by comics and filter with data > 4th quintil
```
q_val = [0,20,40,60,80,100]
quintiles = np.percentile(q9_df['Power'], q = q_val)

q9_marvel = q9_df[(q9_df['Creator'] == 'Marvel Comics') & (q9_df['Power'] > quintiles[3])].fillna(0)
q9_dc = q9_df[(q9_df['Creator'] == 'DC Comics') & (q9_df['Power'] > quintiles[3])].fillna(0)
```

**Step 3:** Plot
```
fig, (ax1,ax2) = plt.subplots(1,2)
fig.set_size_inches(13,20)

def barplot(df,title,x_label,y_label,min_val,max_val,step,ax):
  ax_labels = list(df['Name'])
  ax_values = list(df['Power'])
  sns.barplot(x = ax_values, y = ax_labels, ax = ax, orient='h')
  ax.set_xticks(range(min_val,max_val,step))
  ax.set_title(title, fontsize = 16)
  ax.set_xlabel(x_label)
  ax.set_ylabel(y_label)

def autolabel(df,ax):
  ax_labels = list(df['Name'])
  ax_values = list(df['Power'])
  for text, rect in zip(ax_values, ax.patches):
    width, height = rect.get_width(), rect.get_height()
    x,y = rect.get_xy()
    ax.text(x = x+width,
            y = y+height,
            s=text)

# Marvel
barplot(q9_marvel,'Marvel','Values','Characters',0,150,20,ax1)
autolabel(q9_marvel,ax1)

# DC
barplot(q9_dc,'DC','Values','Characters',0,150,20,ax2)
autolabel(q9_dc,ax2)

fig.tight_layout()
plt.show()
```

![q9_df_1](https://user-images.githubusercontent.com/71573671/114635650-c5082f80-9c8a-11eb-81dd-7358a2313d29.PNG)

This plot is not enough because there are lots of characters who have 100 points in "Power" so we are going to campare between them with another graphic focus on their comics.

**Step 4:** Use "Creator" and "Power"
```
q9_df = q9_df.loc[:,['Creator','Power']]
q9_df
```

![q9_df_2](https://user-images.githubusercontent.com/71573671/114635720-eec15680-9c8a-11eb-8b51-196993546337.PNG)

**Step 5:** Check the value counts of power and make it in a new dataframe
```
q9_df = q9_df.value_counts().reset_index()
q9_df
```

**Step 6:** Rename 0 by 'Values' and filter using median
```
q9_df.rename(columns={0:'Values'}, inplace = True)
q9_df = q9_df[q9_df['Values']>np.median(q9_df['Values'])] 
q9_df
```

**Step 7:** Create a Pivot table to make the plot easier.
```
q9_pivot = q9_df.pivot_table(index = 'Creator', columns = 'Power', values = 'Values')
q9_pivot
```

**Step 8:** Replace Null values by 0.
```
q9_pivot = q9_pivot.fillna(0)
q9_pivot
```

![q9_pivot](https://user-images.githubusercontent.com/71573671/114635855-48c21c00-9c8b-11eb-801e-d822cf514183.PNG)

**Step 9:** Plot
```
labels = list(q9_pivot.index)

x=np.arange(len(labels))
width=0.05

def plot(df,column_i, x , width, label, count):
  data = list(df[column_i])
  bar = ax.bar(x-width/2 + count*width, data, width, label = label)

fig, ax = plt.subplots()
fig.set_size_inches(10,6)
count = 0
for column_i in q9_pivot.columns:
  plot(q9_pivot, column_i, x, width, str(column_i), count)
  count += 1

ax.set_title('Comics that has the powerest characters')
ax.set_xlabel('Comics')
ax.set_ylabel('Values')
ax.set_xticks(x)
ax.set_xticklabels(labels)
ax.legend()

fig.tight_layout()
plt.show
```

![q9_plot_2_real](https://user-images.githubusercontent.com/71573671/114635897-64c5bd80-9c8b-11eb-96a5-034455ff5b5a.png)

# Conclusions
1. There are more characters in Marvel Comics than DC Comics.
2. The predominat gender in both comics is "Male".
3. The predominat race in Marvel Comics is "Human" as a second place and "Without Race" as the first. In DC comics the predominant race is "Human" as a 1st place and "Without Race" as a 2nd.
4. There are more Heroes in both comics than Villains.
5. The predominant super power in both comics is "Super Strength"
6. We can not define one character as the most intelligent but we can say that Marvel Comics have more intelligent characters than DC Comics.
7. We can not define one character as the strongest but we can say that Marvel Comics have more strong characters than DC Comics.
8. We can not define one character as the fastest but we can say that Marvel Comics have more fast characters than DC Comics.
9. We can not define one character as the powerest but we can say that Marvel Comics have more powerful characters than DC Comics.



