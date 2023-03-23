# spotify_moods

I have done this project in google colab. 

The libraries used for this project are listed below: 

1)Pandas 
2)Numpy 
3)Matplotlib 
4)Seaborn 
5)SkLearn 
6)SKImage 

We are using spotify_mood.csv file. Number of rows is 686 and number of columns is 19.

If we observe there is a column called "Mood" which has categorical value. We will use OneHotEncoder Technique which will assign numerical value to the moods of the song. 


1) *OneHotEncoder*: It is the one-hot numeric array. Here the categorical data gets converted to numerical data for the use in machine learning. They are turned into binary features meaning it recieves a "1" otherwise a "0". 

Understanding the OneHotEncoder class : 

from sklearn.preprocessing import OneHotEncoder 


OneHotEncoder( 

      categories='auto', 
      
      drop = None, #to see if we have to drop any features 
      
      sparse= true, 
      
      dtype= <class> 
      
output

)
      

eg: 
one= OneHotEncoder(dtype=int)

mood_columns = one.fit_transform(df[['mood']]).toarray()


lets see what we did here:
we initialised a OneHotEncoder object to one and later we fiited and transformed our data using the .fit_transform() method and returned the array version of the transformed data using the .toarray() method. 


![image](https://user-images.githubusercontent.com/22547288/227235936-fd280700-44fc-4715-b563-81debb36df55.png)

2) *StandardScaler* : its used to standardised the data values intot a standard format. 

Syntax: object = StandardScaler()
        
        object.fit_transform(data) 
        
We first initialise StandardScaler() function to object and later use fit.transform() to transform the data and standardize it. 

3) PCA_Pipeline: Principle component analysis is a dimentional reduction technique. It compresses the data set into a smaller data set with fewer features. Pca will help improve regression and classification algorithm by preventing over fitting and reduction noise. It can also be used to craete visualisations with two or three features instead of original data. 

Syntax: pca = PCA()
        
        pca.fit_transform(X)
        
 we first do StandardScaler and later Pca 
 
 
 3) n_cluster Validation : procedure of evaluating the goodness of clustering algorithm results. 
 we use silhouette score to calculate the clustering technique. It ranges from -1 to 1. 
 where 1 means clusters are well apart from each other and clearly distinguished. 
 
 0 means cluster are indifferent or we can say that the distance between clsuter is not significant.
 
 -1 means clusters are assigned in the wrong way.
 
 from sklearn.metrics import silhouette_socre 
 
 for k in range(2, 11):
 
   ...:     kmeans = KMeans(n_clusters=k, **kmeans_kwargs)
   
   ...:     kmeans.fit(scaled_features)
   
   ...:     score = silhouette_score(scaled_features, kmeans.labels_)
   
   ...:     silhouette_coefficients.append(score)
   
Euclidean Distances: 
its the shortest between the 2 points irrespective of the dimentions.We use the numpy library. 

from sklearn.metrics import euclidean_distances


 We have connected the spotify using the client id and client secret. 
   to install the spotipy library use: 
   
   %pip install spotipy
   
   to find the credentials go to 
   
   https://developer.spotify.com/dashboard/login
   
   clink on create my app and accept the terms and conditions and you will find your client id and client secret. 
   
   
   


  
  
 
 
 

