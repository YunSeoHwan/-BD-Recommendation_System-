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
![image](https://github.com/YunSeoHwan/BD_Recommendation_System/assets/48356954/1bc992c1-4ea9-403d-9909-546704e29c0b) <br><br>

#### **Final Dataset**
![image](https://github.com/YunSeoHwan/BD_Recommendation_System/assets/48356954/bf7e0595-a7b8-49cd-9181-dfc4fff82e7f) <br><br>
### Recommendation System 
#### **Item - genre**
##### **Baseline**
The presence of genres was encoded using one-hot encoding with 0 and 1. For similarity, Pearson and cosine similarities were used. <br><br>
![image](https://github.com/YunSeoHwan/BD_Recommendation_System/assets/48356954/8831a8cf-9efc-4c09-8d7f-ff37277f3f99)<br>

##### **TF-IDF**
After encoding as with the baseline, TF-IDF was applied. Similarly, Pearson and cosine similarities were used for similarity. <br><br>
![image](https://github.com/YunSeoHwan/BD_Recommendation_System/assets/48356954/3ab0ff95-e9e5-4364-a291-393872b170f0) <br><br>

#### **Item - user**
##### **Baseline**
We used rating scores, and missing values were treated as zeros. For similarity, Pearson and cosine similarities were used. <br><br>
![image](https://github.com/YunSeoHwan/BD_Recommendation_System/assets/48356954/8506f265-2abc-4c7c-a69b-18abef079952)

##### **KNN**
Missing values in the rating scores were handled using KNN. Comparative experiments were conducted with **K set to 1, 3, and 5**. For similarity, Pearson and cosine similarities were used.
![image](https://github.com/YunSeoHwan/BD_Recommendation_System/assets/48356954/06613f39-191b-492f-92cd-636a13a28f83)
##### **SVD**
Missing values were addressed using **SVD** **Normalization**. Additionally, we conducted SVD, adjusting the n_components to **10%, 25%, and 50%** for comparative experiments. For similarity, Pearson and cosine similarities were used. <br><br>
![image](https://github.com/YunSeoHwan/BD_Recommendation_System/assets/48356954/eb8b87ff-a43d-422e-b54a-14e5f585ce99)<br><br>
### Role
#### [**YunSeoHwan**](https://github.com/YunSeoHwan) : Preprocessing, Recommendation System, Interpretation<br>
#### YunSeongHo : Preprocessing, Recommendation System, Interpretation
#### SinWooHyean : Preprocessing, Recommendation System, Interpretation <br>

# Result & Suggestion
## Item-genre Results
Overall, the performance was better when cosine similarity was utilized, and among the methods, TF-IDF showed the highest performance. <br><br>
![image](https://github.com/YunSeoHwan/DM_TeamProject/assets/48356954/8fd77d2c-9120-4142-8e38-1e355e016ab3) <br><br>

## Item-user Results
The **Baseline** and **SVD** generally exhibited good performance. Among them, **Baseline Pearson** achieved the best performance, demonstrating superiority over the item-genre comparison.
<br><br>
![image](https://github.com/YunSeoHwan/BD_Recommendation_System/assets/48356954/6cc9ed06-03c1-491d-8db3-43e763c2a25e)<br><br>

## Recommandation System
We implemented a system for movie recommendations. If a user inputs their information and preferred genres, the system will recommend 10 movies. <br><br>
![image](https://github.com/YunSeoHwan/BD_Recommendation_System/assets/48356954/07e9d841-f93c-440e-96ad-994cd2f16e6d)

# Limitation
- There were limitations in tuning model hyperparameters with various combinations.
- We were unable to implement distributed processing using PySpark.
- We did not utilize tag data.
