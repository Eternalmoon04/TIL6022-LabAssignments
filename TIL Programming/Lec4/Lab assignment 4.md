# 1. Read and write simple text files

A text file `addition.txt` contains a number in each line. Write a python code that

## 1.1. Reads all numbers


```python
# YOUR CODE HERE
# Hint: Use the .strip() function to remove whitespaces and newlines characters from a string
file_path = 'addition.txt'
with open(file_path,'r') as fp:
    lines = fp.readlines()
    for line in lines:
        line = line.strip()
        print(line)
        

        
    
    
```

    2
    3
    5
    
    

## 1.2. Calculats their sum


```python
# YOUR CODE HERE
file_path = 'addition.txt'
summ = int()
list1 =[]
with open(file_path,'r') as fp:
    lines = fp.readlines()
    for line in lines:
        line = line.strip()
        list1.append(line)
    while '' in list1:
        list1.remove('')
    list1 = list(map(int,list1))
    for line in list1:
        summ = summ + line
    print(summ)
        
```

    10
    

## 1.3 Writes the sum at the bottom of the text file


```python
# YOUR CODE HERE
# Hint: 
# - You might want to opne the file in the "Append" mode
# - Add \n characters to start a new line before writing the sum value
with open('addition.txt', 'a') as f:
    f.write('\n')
    f.write(summ)

```

# 2. Pandas

In this part, you will practice loading and exploring a data set from Netflix.

## 2.1. Dataset

Read the [Netflix dataset](https://www.kaggle.com/datasets/luiscorter/netflix-original-films-imdb-scores)


```python
# import
import pandas as pd
```

Solution to the encoding problem [here](https://www.kaggle.com/code/paultimothymooney/how-to-resolve-a-unicodedecodeerror-for-a-csv-file/notebook)


```python
# YOUR CODE HERE
file_path = 'NetflixOriginals.csv'
df = pd.read_csv(file_path,encoding = 'Windows-1252')
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Title</th>
      <th>Genre</th>
      <th>Premiere</th>
      <th>Runtime</th>
      <th>IMDB Score</th>
      <th>Language</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Enter the Anime</td>
      <td>Documentary</td>
      <td>August 5, 2019</td>
      <td>58</td>
      <td>2.5</td>
      <td>English/Japanese</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Dark Forces</td>
      <td>Thriller</td>
      <td>August 21, 2020</td>
      <td>81</td>
      <td>2.6</td>
      <td>Spanish</td>
    </tr>
    <tr>
      <th>2</th>
      <td>The App</td>
      <td>Science fiction/Drama</td>
      <td>December 26, 2019</td>
      <td>79</td>
      <td>2.6</td>
      <td>Italian</td>
    </tr>
    <tr>
      <th>3</th>
      <td>The Open House</td>
      <td>Horror thriller</td>
      <td>January 19, 2018</td>
      <td>94</td>
      <td>3.2</td>
      <td>English</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Kaali Khuhi</td>
      <td>Mystery</td>
      <td>October 30, 2020</td>
      <td>90</td>
      <td>3.4</td>
      <td>Hindi</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>579</th>
      <td>Taylor Swift: Reputation Stadium Tour</td>
      <td>Concert Film</td>
      <td>December 31, 2018</td>
      <td>125</td>
      <td>8.4</td>
      <td>English</td>
    </tr>
    <tr>
      <th>580</th>
      <td>Winter on Fire: Ukraine's Fight for Freedom</td>
      <td>Documentary</td>
      <td>October 9, 2015</td>
      <td>91</td>
      <td>8.4</td>
      <td>English/Ukranian/Russian</td>
    </tr>
    <tr>
      <th>581</th>
      <td>Springsteen on Broadway</td>
      <td>One-man show</td>
      <td>December 16, 2018</td>
      <td>153</td>
      <td>8.5</td>
      <td>English</td>
    </tr>
    <tr>
      <th>582</th>
      <td>Emicida: AmarElo - It's All For Yesterday</td>
      <td>Documentary</td>
      <td>December 8, 2020</td>
      <td>89</td>
      <td>8.6</td>
      <td>Portuguese</td>
    </tr>
    <tr>
      <th>583</th>
      <td>David Attenborough: A Life on Our Planet</td>
      <td>Documentary</td>
      <td>October 4, 2020</td>
      <td>83</td>
      <td>9.0</td>
      <td>English</td>
    </tr>
  </tbody>
</table>
<p>584 rows × 6 columns</p>
</div>



## 2.2 Show the first 3 rows


```python
# YOUR CODE HERE
df.head(3)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Title</th>
      <th>Genre</th>
      <th>Premiere</th>
      <th>Runtime</th>
      <th>IMDB Score</th>
      <th>Language</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Enter the Anime</td>
      <td>Documentary</td>
      <td>August 5, 2019</td>
      <td>58</td>
      <td>2.5</td>
      <td>English/Japanese</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Dark Forces</td>
      <td>Thriller</td>
      <td>August 21, 2020</td>
      <td>81</td>
      <td>2.6</td>
      <td>Spanish</td>
    </tr>
    <tr>
      <th>2</th>
      <td>The App</td>
      <td>Science fiction/Drama</td>
      <td>December 26, 2019</td>
      <td>79</td>
      <td>2.6</td>
      <td>Italian</td>
    </tr>
  </tbody>
</table>
</div>



## 2.3. Show the last 5 rows


```python
# YOUR CODE HERE
df.tail(5)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Title</th>
      <th>Genre</th>
      <th>Premiere</th>
      <th>Runtime</th>
      <th>IMDB Score</th>
      <th>Language</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>579</th>
      <td>Taylor Swift: Reputation Stadium Tour</td>
      <td>Concert Film</td>
      <td>December 31, 2018</td>
      <td>125</td>
      <td>8.4</td>
      <td>English</td>
    </tr>
    <tr>
      <th>580</th>
      <td>Winter on Fire: Ukraine's Fight for Freedom</td>
      <td>Documentary</td>
      <td>October 9, 2015</td>
      <td>91</td>
      <td>8.4</td>
      <td>English/Ukranian/Russian</td>
    </tr>
    <tr>
      <th>581</th>
      <td>Springsteen on Broadway</td>
      <td>One-man show</td>
      <td>December 16, 2018</td>
      <td>153</td>
      <td>8.5</td>
      <td>English</td>
    </tr>
    <tr>
      <th>582</th>
      <td>Emicida: AmarElo - It's All For Yesterday</td>
      <td>Documentary</td>
      <td>December 8, 2020</td>
      <td>89</td>
      <td>8.6</td>
      <td>Portuguese</td>
    </tr>
    <tr>
      <th>583</th>
      <td>David Attenborough: A Life on Our Planet</td>
      <td>Documentary</td>
      <td>October 4, 2020</td>
      <td>83</td>
      <td>9.0</td>
      <td>English</td>
    </tr>
  </tbody>
</table>
</div>



## 2.4. Show the title and the genre of the 100th movie in the database?


```python
# YOUR CODE HERE
df.loc[99,['Title','Genre']]
```




    Title    Game Over, Man!
    Genre      Action/Comedy
    Name: 99, dtype: object



## 2.5. Set the column Title as index for the dataset.


```python
# YOUR CODE HERE
df.index
df.set_index('Title',inplace=True)

```

Show the first 5 rows


```python
df.head(5)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Genre</th>
      <th>Premiere</th>
      <th>Runtime</th>
      <th>IMDB Score</th>
      <th>Language</th>
    </tr>
    <tr>
      <th>Title</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Enter the Anime</th>
      <td>Documentary</td>
      <td>August 5, 2019</td>
      <td>58</td>
      <td>2.5</td>
      <td>English/Japanese</td>
    </tr>
    <tr>
      <th>Dark Forces</th>
      <td>Thriller</td>
      <td>August 21, 2020</td>
      <td>81</td>
      <td>2.6</td>
      <td>Spanish</td>
    </tr>
    <tr>
      <th>The App</th>
      <td>Science fiction/Drama</td>
      <td>December 26, 2019</td>
      <td>79</td>
      <td>2.6</td>
      <td>Italian</td>
    </tr>
    <tr>
      <th>The Open House</th>
      <td>Horror thriller</td>
      <td>January 19, 2018</td>
      <td>94</td>
      <td>3.2</td>
      <td>English</td>
    </tr>
    <tr>
      <th>Kaali Khuhi</th>
      <td>Mystery</td>
      <td>October 30, 2020</td>
      <td>90</td>
      <td>3.4</td>
      <td>Hindi</td>
    </tr>
  </tbody>
</table>
</div>



## 2.6. How many movies are there in the dataset?


```python
# YOUR CODE HERE
information=df.shape
print(information[0])
```

    584
    

## 2.7. For each movie, what information are available?


```python
# YOUR CODE HERE
df.columns
```




    Index(['Genre', 'Premiere', 'Runtime', 'IMDB Score', 'Language'], dtype='object')



## 2.8. What is the highest IMDB score in the dataset?


```python
# YOUR CODE HERE
df['IMDB Score'].max()
```




    9.0



## 2.9. Which movies are scored the highest?


```python
# YOUR CODE HERE
df = df.rename(columns=lambda x:x.replace(' ',''))
df[
    df.IMDBScore == 9.0
]

```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Genre</th>
      <th>Premiere</th>
      <th>Runtime</th>
      <th>IMDBScore</th>
      <th>Language</th>
    </tr>
    <tr>
      <th>Title</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>David Attenborough: A Life on Our Planet</th>
      <td>Documentary</td>
      <td>October 4, 2020</td>
      <td>83</td>
      <td>9.0</td>
      <td>English</td>
    </tr>
  </tbody>
</table>
</div>



## 2.10. What is the lowest IMDB score?


```python
df['IMDBScore'].min()
```




    2.5



## 2.11. What movies are scored the lowest?


```python
df[
    df.IMDBScore == 2.5
]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Genre</th>
      <th>Premiere</th>
      <th>Runtime</th>
      <th>IMDBScore</th>
      <th>Language</th>
    </tr>
    <tr>
      <th>Title</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Enter the Anime</th>
      <td>Documentary</td>
      <td>August 5, 2019</td>
      <td>58</td>
      <td>2.5</td>
      <td>English/Japanese</td>
    </tr>
  </tbody>
</table>
</div>



## 2.12. Consider only-English-language movies, find those that are scored above their average score


```python
# YOUR CODE HERE
dfinEng=df[
    df.Language == 'English'
]
# print the average IMDB score
avscore = dfinEng['IMDBScore'].mean()
print('the average IMDB score of English movies is',avscore)
# show all those score higher than the average
dfinEng[
    dfinEng.IMDBScore > avscore
]
```

    the average IMDB score of English movies is 6.380049875311723
    




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Genre</th>
      <th>Premiere</th>
      <th>Runtime</th>
      <th>IMDBScore</th>
      <th>Language</th>
    </tr>
    <tr>
      <th>Title</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Ariana Grande: Excuse Me, I Love You</th>
      <td>Concert Film</td>
      <td>December 21, 2020</td>
      <td>97</td>
      <td>6.4</td>
      <td>English</td>
    </tr>
    <tr>
      <th>ARQ</th>
      <td>Science fiction/Thriller</td>
      <td>September 16, 2016</td>
      <td>88</td>
      <td>6.4</td>
      <td>English</td>
    </tr>
    <tr>
      <th>First Match</th>
      <td>Sports-drama</td>
      <td>March 30, 2018</td>
      <td>102</td>
      <td>6.4</td>
      <td>English</td>
    </tr>
    <tr>
      <th>Fractured</th>
      <td>Thriller</td>
      <td>October 11, 2019</td>
      <td>100</td>
      <td>6.4</td>
      <td>English</td>
    </tr>
    <tr>
      <th>Irreplaceable You</th>
      <td>Drama</td>
      <td>February 16, 2018</td>
      <td>96</td>
      <td>6.4</td>
      <td>English</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>Dancing with the Birds</th>
      <td>Documentary</td>
      <td>October 23, 2019</td>
      <td>51</td>
      <td>8.3</td>
      <td>English</td>
    </tr>
    <tr>
      <th>Ben Platt: Live from Radio City Music Hall</th>
      <td>Concert Film</td>
      <td>May 20, 2020</td>
      <td>85</td>
      <td>8.4</td>
      <td>English</td>
    </tr>
    <tr>
      <th>Taylor Swift: Reputation Stadium Tour</th>
      <td>Concert Film</td>
      <td>December 31, 2018</td>
      <td>125</td>
      <td>8.4</td>
      <td>English</td>
    </tr>
    <tr>
      <th>Springsteen on Broadway</th>
      <td>One-man show</td>
      <td>December 16, 2018</td>
      <td>153</td>
      <td>8.5</td>
      <td>English</td>
    </tr>
    <tr>
      <th>David Attenborough: A Life on Our Planet</th>
      <td>Documentary</td>
      <td>October 4, 2020</td>
      <td>83</td>
      <td>9.0</td>
      <td>English</td>
    </tr>
  </tbody>
</table>
<p>210 rows × 5 columns</p>
</div>



## 2.13. (Optional) Is there a correlation between runtime and IMDB score?


```python
cornum = df.corr()
cornum = cornum.iloc[0,1]
if cornum>-0.05:
    if cornum<0.05:
        print('There is no correlation between runtime and IMDB score')
    else:
        print('There is a correlation between runtime and IMDB score')
else:
    print('There is a correlation between runtime and IMDB score')

```

    There is no correlation between runtime and IMDB score
    

## 2.14 How many languages available?


```python
# YOUR CODE HERE
df['Language'].unique()
```




    array(['English/Japanese', 'Spanish', 'Italian', 'English', 'Hindi',
           'Turkish', 'Korean', 'Indonesian', 'Malay', 'Dutch', 'French',
           'English/Spanish', 'Portuguese', 'Filipino', 'German', 'Polish',
           'Norwegian', 'Marathi', 'Thai', 'Swedish', 'Japanese',
           'Spanish/Basque', 'Spanish/Catalan', 'English/Swedish',
           'English/Taiwanese/Mandarin', 'Thia/English', 'English/Mandarin',
           'Georgian', 'Bengali', 'Khmer/English/French', 'English/Hindi',
           'Tamil', 'Spanish/English', 'English/Korean', 'English/Arabic',
           'English/Russian', 'English/Akan', 'English/Ukranian/Russian'],
          dtype=object)



## 2.15. Extract all action movies. Save them into a csv file 'action_movies.csv'


```python
# YOUR CODE HERE
df['isAction'] = (df['Genre'].str.contains('Action'))
action_movies=df[
    df.isAction == True
]
action_movies.to_csv('action_movies.csv')

```

## 2.16. For each genre of movies, answer the following question
- How many movies are available in the dataset?


```python
# YOUR CODE HERE
df_genre=df.groupby('Genre')
df_genre_number=df_genre.count()
df_genre_number['Premiere']
```




    Genre
    Action              7
    Action comedy       5
    Action thriller     1
    Action-adventure    1
    Action-thriller     3
                       ..
    War                 2
    War drama           2
    War-Comedy          1
    Western             3
    Zombie/Heist        1
    Name: Premiere, Length: 115, dtype: int64




- What are their average score?


```python
# YOUR CODE HERE
df_genre_avscore=df_genre['IMDBScore'].mean()
df_genre_avscore
```




    Genre
    Action              5.414286
    Action comedy       5.420000
    Action thriller     6.400000
    Action-adventure    7.300000
    Action-thriller     6.133333
                          ...   
    War                 6.750000
    War drama           7.100000
    War-Comedy          6.000000
    Western             6.066667
    Zombie/Heist        5.900000
    Name: IMDBScore, Length: 115, dtype: float64



## 2.17. On average, what type of movies scores the highest?


```python
df_genre_avscore = pd.DataFrame(df_genre_avscore)
df_genre_avscore[
    df_genre_avscore.IMDBScore == df_genre_avscore.IMDBScore.max()]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>IMDBScore</th>
    </tr>
    <tr>
      <th>Genre</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Animation/Christmas/Comedy/Adventure</th>
      <td>8.2</td>
    </tr>
  </tbody>
</table>
</div>


