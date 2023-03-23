# spotify_moods

The libraries used for this project are listed below: 

1)Pandas 
2)Numpy 
3)Matplotlib 
4)Seaborn 
5)SkLearn 
6)SKImage 

We are using spotify_mood.csv file. Number of rows is 686 and number of columns is 19.

If we observe there is a column called "Mood" which has categorical value. We will use OneHotEncoder Technique which will assign numerical value to the moods of the song. 


*OneHotEncoder*: It is the one-hot numeric array. Here the categorical data gets converted to numerical data for the use in machine learning. They are turned into binary features meaning it recieves a "1" otherwise a "0". 

Understanding the OneHotEncoder class : 

from sklearn.preprocessing import OneHotEncoder 


OneHotEncoder( 

      categories='auto', 
      
      drop = None, #to see if we have to drop any features 
      
      sparse= true, 
      
      dtype= <class> 
      
output

)
      

eg: one= OneHotEncoder(dtype=int)
mood_columns = one.fit_transform(df[['mood']]).toarray()

lets see what we did here:
we initialised a OneHotEncoder object to one and later we fiited and transformed our data using the .fit_transform() method and returned the array version of the transformed data using the .toarray() method. 


![image](https://user-images.githubusercontent.com/22547288/227235936-fd280700-44fc-4715-b563-81debb36df55.png)
 

