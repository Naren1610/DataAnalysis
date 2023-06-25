```python
import pandas as pd
import numpy as np

```


```python
df=pd.read_csv("bestSellingGames.csv")
```


```python
df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 33 entries, 0 to 32
    Data columns (total 6 columns):
     #   Column           Non-Null Count  Dtype 
    ---  ------           --------------  ----- 
     0   Game             33 non-null     object
     1   Copies sold      33 non-null     object
     2   Release date[a]  33 non-null     object
     3   Genre(s)         33 non-null     object
     4   Developer(s)     33 non-null     object
     5   Publisher(s)     33 non-null     object
    dtypes: object(6)
    memory usage: 1.7+ KB
    


```python
df.shape
```




    (33, 6)




```python
df.head()
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
      <th>Game</th>
      <th>Copies sold</th>
      <th>Release date[a]</th>
      <th>Genre(s)</th>
      <th>Developer(s)</th>
      <th>Publisher(s)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Marvel's Spider-Man</td>
      <td>20 million</td>
      <td>September 7, 2018</td>
      <td>Action-adventure</td>
      <td>Insomniac Games</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
    <tr>
      <th>1</th>
      <td>God of War</td>
      <td>19.5 million</td>
      <td>April 20, 2018</td>
      <td>Action-adventure hack and slash</td>
      <td>Santa Monica Studio</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Uncharted 4: A Thief's End</td>
      <td>16 million</td>
      <td>May 10, 2016</td>
      <td>Action-adventure</td>
      <td>Naughty Dog</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
    <tr>
      <th>3</th>
      <td>The Witcher 3: Wild Hunt</td>
      <td>10.8 million</td>
      <td>May 18, 2015</td>
      <td>Action role-playing</td>
      <td>CD Projekt Red</td>
      <td>CD Projekt</td>
    </tr>
    <tr>
      <th>4</th>
      <td>The Last of Us Part II</td>
      <td>10 million</td>
      <td>June 19, 2020</td>
      <td>Action-adventure survival horror</td>
      <td>Naughty Dog</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
  </tbody>
</table>
</div>




```python
import matplotlib.pyplot as plt # data visualization
import seaborn as sns # data visualization
```


```python
df.isnull()
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
      <th>Game</th>
      <th>Copies sold</th>
      <th>Release date[a]</th>
      <th>Genre(s)</th>
      <th>Developer(s)</th>
      <th>Publisher(s)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>5</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>6</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>7</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>8</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>9</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>10</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>11</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>12</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>13</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>14</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>15</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>16</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>17</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>18</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>19</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>20</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>21</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>22</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>23</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>24</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>25</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>26</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>27</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>28</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>29</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>30</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>31</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>32</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.describe()
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
      <th>Game</th>
      <th>Copies sold</th>
      <th>Release date[a]</th>
      <th>Genre(s)</th>
      <th>Developer(s)</th>
      <th>Publisher(s)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>33</td>
      <td>33</td>
      <td>33</td>
      <td>33</td>
      <td>33</td>
      <td>33</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>33</td>
      <td>24</td>
      <td>32</td>
      <td>15</td>
      <td>23</td>
      <td>12</td>
    </tr>
    <tr>
      <th>top</th>
      <td>Marvel's Spider-Man</td>
      <td>2 million</td>
      <td>November 15, 2013</td>
      <td>Action role-playing</td>
      <td>Square Enix</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>1</td>
      <td>4</td>
      <td>2</td>
      <td>11</td>
      <td>4</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['Copies sold'] = df['Copies sold'].str.replace(' million', '').astype(float)
```


```python
df.describe()
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
      <th>Copies sold</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>33.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>5.445152</td>
    </tr>
    <tr>
      <th>std</th>
      <td>5.291126</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>2.500000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>8.420000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>20.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
df['Release date[a]'] = df['Release date[a]'].astype('datetime64[ns]')
```


```python
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
      <th>Game</th>
      <th>Copies sold</th>
      <th>Release date[a]</th>
      <th>Genre(s)</th>
      <th>Developer(s)</th>
      <th>Publisher(s)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Marvel's Spider-Man</td>
      <td>20.00</td>
      <td>2018-09-07</td>
      <td>Action-adventure</td>
      <td>Insomniac Games</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
    <tr>
      <th>1</th>
      <td>God of War</td>
      <td>19.50</td>
      <td>2018-04-20</td>
      <td>Action-adventure hack and slash</td>
      <td>Santa Monica Studio</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Uncharted 4: A Thief's End</td>
      <td>16.00</td>
      <td>2016-05-10</td>
      <td>Action-adventure</td>
      <td>Naughty Dog</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
    <tr>
      <th>3</th>
      <td>The Witcher 3: Wild Hunt</td>
      <td>10.80</td>
      <td>2015-05-18</td>
      <td>Action role-playing</td>
      <td>CD Projekt Red</td>
      <td>CD Projekt</td>
    </tr>
    <tr>
      <th>4</th>
      <td>The Last of Us Part II</td>
      <td>10.00</td>
      <td>2020-06-19</td>
      <td>Action-adventure survival horror</td>
      <td>Naughty Dog</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Horizon Zero Dawn</td>
      <td>10.00</td>
      <td>2017-02-28</td>
      <td>Action role-playing</td>
      <td>Guerrilla Games</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
    <tr>
      <th>6</th>
      <td>The Last of Us Remastered</td>
      <td>10.00</td>
      <td>2014-07-29</td>
      <td>Action-adventure survival horror</td>
      <td>Naughty Dog</td>
      <td>Sony Computer Entertainment</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Ghost of Tsushima</td>
      <td>9.73</td>
      <td>2020-07-17</td>
      <td>Action-adventure stealth</td>
      <td>Sucker Punch Productions</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Star Wars Battlefront</td>
      <td>8.42</td>
      <td>2015-11-17</td>
      <td>First-person shooter third-person shooter</td>
      <td>EA DICE</td>
      <td>Electronic Arts</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Gran Turismo Sport</td>
      <td>8.00</td>
      <td>2017-10-17</td>
      <td>Racing</td>
      <td>Polyphony Digital</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Infamous Second Son</td>
      <td>6.00</td>
      <td>2014-03-21</td>
      <td>Action-adventure</td>
      <td>Sucker Punch Productions</td>
      <td>Sony Computer Entertainment</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Detroit: Become Human</td>
      <td>5.50</td>
      <td>2018-05-25</td>
      <td>Adventure</td>
      <td>Quantic Dream</td>
      <td>Sony Interactive Entertainment</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Final Fantasy VII Remake</td>
      <td>5.00</td>
      <td>2020-04-10</td>
      <td>Action role-playing</td>
      <td>Square Enix</td>
      <td>Square Enix</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Monster Hunter: World</td>
      <td>4.67</td>
      <td>2018-01-26</td>
      <td>Action role-playing</td>
      <td>Capcom</td>
      <td>Capcom</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Cyberpunk 2077</td>
      <td>3.83</td>
      <td>2020-12-10</td>
      <td>Action role-playing</td>
      <td>CD Projekt Red</td>
      <td>CD Projekt</td>
    </tr>
    <tr>
      <th>15</th>
      <td>FIFA 17</td>
      <td>3.12</td>
      <td>2016-09-27</td>
      <td>Sports</td>
      <td>EA Canada EA Bucharest</td>
      <td>EA Sports</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Crash Bandicoot N. Sane Trilogy</td>
      <td>2.50</td>
      <td>2017-06-30</td>
      <td>Platform</td>
      <td>Vicarious Visions</td>
      <td>Activision</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Final Fantasy XV</td>
      <td>2.50</td>
      <td>2016-11-29</td>
      <td>Action role-playing</td>
      <td>Square Enix Business Division 2</td>
      <td>Square Enix</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Persona 5 Royal</td>
      <td>2.30</td>
      <td>2019-10-31</td>
      <td>Role-playing social simulation</td>
      <td>P-Studio</td>
      <td>Atlus</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Killzone: Shadow Fall</td>
      <td>2.10</td>
      <td>2013-11-15</td>
      <td>First-person shooter</td>
      <td>Guerrilla Games</td>
      <td>Sony Computer Entertainment</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Grand Theft Auto V</td>
      <td>2.02</td>
      <td>2014-11-18</td>
      <td>Action-adventure</td>
      <td>Rockstar North</td>
      <td>Rockstar Games</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Bloodborne</td>
      <td>2.00</td>
      <td>2015-03-24</td>
      <td>Action role-playing</td>
      <td>FromSoftware</td>
      <td>Sony Computer Entertainment</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Driveclub</td>
      <td>2.00</td>
      <td>2014-10-07</td>
      <td>Racing</td>
      <td>Evolution Studios</td>
      <td>Sony Computer Entertainment</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Knack</td>
      <td>2.00</td>
      <td>2013-11-15</td>
      <td>Platform beat 'em up</td>
      <td>Japan Studio</td>
      <td>Sony Computer Entertainment</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Minecraft: PlayStation 4 Edition</td>
      <td>2.00</td>
      <td>2014-09-04</td>
      <td>Sandbox survival</td>
      <td>4J Studios</td>
      <td>Sony Computer Entertainment</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Nier: Automata</td>
      <td>1.60</td>
      <td>2017-02-23</td>
      <td>Action role-playing</td>
      <td>PlatinumGames</td>
      <td>Square Enix</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Nioh 2</td>
      <td>1.40</td>
      <td>2020-03-12</td>
      <td>Action role-playing</td>
      <td>Team Ninja</td>
      <td>WW: Sony Interactive Entertainment JP: Koei Tecmo</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Battlefield 1</td>
      <td>1.30</td>
      <td>2016-10-21</td>
      <td>First-person shooter</td>
      <td>EA DICE</td>
      <td>Electronic Arts</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Dragon Quest XI: Echoes of an Elusive Age</td>
      <td>1.30</td>
      <td>2017-07-29</td>
      <td>Role-playing</td>
      <td>Square Enix</td>
      <td>Square Enix</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Metal Gear Solid V: The Phantom Pain</td>
      <td>1.10</td>
      <td>2015-09-01</td>
      <td>Action-adventure stealth</td>
      <td>Kojima Productions</td>
      <td>Konami</td>
    </tr>
    <tr>
      <th>30</th>
      <td>Final Fantasy XII: The Zodiac Age</td>
      <td>1.00</td>
      <td>2017-07-11</td>
      <td>Role-playing</td>
      <td>Square Enix</td>
      <td>Square Enix</td>
    </tr>
    <tr>
      <th>31</th>
      <td>Kingdom Hearts III</td>
      <td>1.00</td>
      <td>2019-01-25</td>
      <td>Action role-playing</td>
      <td>Square Enix</td>
      <td>Square Enix</td>
    </tr>
    <tr>
      <th>32</th>
      <td>Nioh</td>
      <td>1.00</td>
      <td>2017-02-07</td>
      <td>Action role-playing</td>
      <td>Team Ninja</td>
      <td>WW: Sony Interactive Entertainment JP: Koei Tecmo</td>
    </tr>
  </tbody>
</table>
</div>




```python
plt.figure(figsize=(10, 7))

a = sns.barplot(x=df['Game'], y=df['Copies sold'], alpha=1, color='yellow')
a.set_xticklabels(labels=df['Game'], rotation=90)
plt.title('Most selling Games')

plt.show()
```


    
![png](output_12_0.png)
    



```python
genre_counts=df['Genre(s)'].value_counts()
```


```python
import squarify
genres = genre_counts.index.tolist()
counts = genre_counts.values.tolist()

# Set up colors
colors = ['#1f77b4', '#ff7f0e', '#2ca02c', '#d62728', '#9467bd',
          '#8c564b', '#e377c2', '#7f7f7f', '#bcbd22', '#17becf',
          '#aec7e8', '#ffbb78', '#98df8a', '#ff9896', '#c5b0d5']

# Calculate percentages
total_count = sum(counts)
percentages = [(count / total_count) * 100 for count in counts]

# Creating the treemap
plt.figure(figsize=(10, 6))
squarify.plot(sizes=counts, label=[f'{p:.1f}' for p in percentages], color=colors, alpha=0.8)
plt.legend(labels=genres, loc='center left', bbox_to_anchor=(1.02, 0.5))


# Adding labels and titles
plt.axis('off')
plt.title('Genre Distribution')

# Displaying the plot
plt.show()
```


    
![png](output_14_0.png)
    



```python
unique_values = df['Publisher(s)'].value_counts().reset_index()
unique_values.columns = ['Value', 'Count']

# Sort values by count in descending order
unique_values = unique_values.sort_values('Count', ascending=False)

# Create the bar chart
plt.figure(figsize=(10, 6))
plt.bar(unique_values['Value'], unique_values['Count'], color='steelblue')

# Adding labels and titles
plt.xlabel('Publisher')
plt.ylabel('Count')
plt.title('Publisher Distribution')

# Rotating x-axis labels for better readability
plt.xticks(rotation=45, ha='right')

# Displaying the plot
plt.tight_layout()
plt.show()
```


    
![png](output_15_0.png)
    



```python
year= df['Release date[a]'].dt.year
year
```




    0     2018
    1     2018
    2     2016
    3     2015
    4     2020
    5     2017
    6     2014
    7     2020
    8     2015
    9     2017
    10    2014
    11    2018
    12    2020
    13    2018
    14    2020
    15    2016
    16    2017
    17    2016
    18    2019
    19    2013
    20    2014
    21    2015
    22    2014
    23    2013
    24    2014
    25    2017
    26    2020
    27    2016
    28    2017
    29    2015
    30    2017
    31    2019
    32    2017
    Name: Release date[a], dtype: int32




```python
from scipy.stats import norm

# Assuming you have a DataFrame named 'df' with columns 'Year' and 'Copies sold'

# Calculate mean and standard deviation of sales
mean_sales = df['Copies sold'].mean()
std_sales = df['Copies sold'].std()

# Create the bar graph
plt.figure(figsize=(10, 4))
plt.bar(year, df['Copies sold'], color='steelblue')

# Plotting the normal distribution curve
x = np.linspace(year.min(), year.max(), 100)
y = norm.pdf(x, mean_sales, std_sales) * df['Copies sold'].max()  # Scale the curve to match the Copies sold range
plt.plot(x, y, 'r', lw=2)

# Adding labels and titles
plt.xlabel('Year')
plt.ylabel('Copies sold')
plt.title('Copies sold by Year')

# Displaying the plot
plt.tight_layout()
plt.show()

```


    
![png](output_17_0.png)
    



```python

```
