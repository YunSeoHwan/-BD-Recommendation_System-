# Project Title
This project was conducted during the BigData Processing and Applications class in the second semester of 2023.
<br><br>

# Project Background 
This project was conducted in collaboration with [**Finda Inc**](https://finda.co.kr/), aiming to develop a personalized recommendation system based on large-scale data. The implementation approach was Item-based Collaborative Filtering using dot product, and the [**MovieLens**](https://grouplens.org/datasets/movielens/)   dataset was employed.
We sought to develop the optimal recommendation system through a variety of approaches, including preprocessing, vectorization, and similarity analysis.
<br><br>

# Project Process  

## Stack
### Language & Library
<div>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/PySpark-E25A1C?style=flat&logo=apachespark&logoColor=white"/>
  <img src="https://img.shields.io/badge/Numpy-013243?style=flat&logo=Numpy&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pandas-150458?style=flat&logo=Pandas&logoColor=white"/>
<img src="https://img.shields.io/badge/Scikit learn-F7931E?style=flat&logo=Scikitlearn&logoColor=white"/>
</div>

### Recommendation System 
<div>
  <img src="https://img.shields.io/badge/Item genre-000000?style=flat&logo=&logoColor=white"/>
  <img src="https://img.shields.io/badge/Item user-000000?style=flat&logo=&logoColor=white"/>

<br><br>

## Pipeline
![image](https://github.com/YunSeoHwan/DM_TeamProject/assets/48356954/9b7acf9d-e2c2-444e-9c80-f2558802dd55)

### Preprocessing
#### **Missing Value**
There were missing values in the genre data. These were replaced with data obtained through **web crawling** from [**IMDB**](https://www.imdb.com/). While KNN was used, the missing values could be perfectly filled using domain knowledge. Therefore, we opted to handle this through web crawling. <br>

#### **Duplication**
There were approximately 300 duplicate entries with identical titles, despite being different movies. This was addressed by processing it as **'title + Number'**.
<br><br>
![image](https://github.com/YunSeoHwan/DM_TeamProject/assets/48356954/8f925536-6a47-4ac7-8e8c-c8a4cee213ac) <br><br>

#### **Final Dataset**
![image](https://github.com/YunSeoHwan/DM_TeamProject/assets/48356954/8e779d02-2c11-4c69-b100-9694fe9409e6) <br><br>
### Recommendation System 
#### Item - genre
##### **Baseline**
The presence of genres was encoded using one-hot encoding with 0 and 1. For similarity, Pearson and cosine similarities were used. <br><br>
![image](https://github.com/YunSeoHwan/DM_TeamProject/assets/48356954/c3637473-c33c-436d-b068-081c3b9ba8f2)<br>

##### **TF-IDF**
After encoding as with the baseline, TF-IDF was applied. Similarly, Pearson and cosine similarities were used for similarity. <br><br>
![image](https://github.com/YunSeoHwan/DM_TeamProject/assets/48356954/43cd46a8-9e7f-4b7d-9a02-3cf88041cf1f) <br><br>

#### Item - user

### Role
#### [**YunSeoHwan**](https://github.com/YunSeoHwan) : Preprocessing, Recommendation System, Interpretation<br>
#### YunSeongHo : Preprocessing, Recommendation System, Interpretation
#### SinWooHyean : Preprocessing, Recommendation System, Interpretation <br>
## Result & Suggestion
### Item-genre Results
Overall, the performance was better when cosine similarity was utilized, and among the methods, TF-IDF showed the highest performance. <br><br>
![image](https://github.com/YunSeoHwan/DM_TeamProject/assets/48356954/8fd77d2c-9120-4142-8e38-1e355e016ab3) <br><br>
