# Mayank-kptncook-data-challenge
Python code for updating data when user listened to new music and recommending artist to user

-----------------------------------------------

First I created a 2D array copy of csv file. If user 33 has listened to an artist 'abba' so the excel file will be updated accordingly. If the user didn't heard any new songs then it will not be updated in the excel file. 

----------------------------------------

After doing the updation, I used Collaborative filtering method for recoomending songs to user.

-------------------------------------

The data represents each row as a user, and each column as an artist. Data contains whether a
user has listened to artist, if he has heard a particular artist then data[user][artist]=1, otherwise 0

--------------------------------------

First, I use Item-Based collaborative Filtering on the data to calculate the similarity of each song with the rest of the songs. That is, we want to compare each column in our "data.germany.ibs" to every other column in the data set. We will specifically compare what is called as "Cosine Similarity."

With our similarity matrix completed, we can search for each item's "neighbor" by looping over 'data ibs,' sorting each column in decreasing order, and obtaining the names of the top ten songs.

---------------------------------------------

The following is the procedure for developing a User Based Recommendation System:

1) Have an Item Based Similarity Matrix
2) Examine which things the user has listened
3) Obtain the top 10 neighbors for each item listened by the user
4) Get the user's listening record for each neighbor
5) Using a formula, compute a similarity score
6) Recommend the song with the highest similarity

I define the function to get similarity scores ("def getScore")- I multiply the total of the product two vectors carrying history and similarity statistics by the sum of the similarities in the corresponding vector.

![image](https://user-images.githubusercontent.com/43773641/172162256-7ef56bd6-e27f-4ecc-a26a-8dbbde7f9df6.png)

The rest is a matter of applying this function to the data frames in the right way.We start by creating a variable to hold our similarity data. This is basically the same as our original data but with nothing filled in except the headers. We now loop through the rows and columns filling in empty spaces with similarity scores.

Note that we score items that the user has already listened as 0, because there is no point of recommending it again.


After that, I produce a matrix of User Based recommendations as follows:

<img width="1002" alt="Screenshot 2022-06-06 at 2 43 04 PM" src="https://user-images.githubusercontent.com/43773641/172162824-782950b1-2e07-44f8-8b8c-d04165de57b5.png">
Now, I sort  the user’s purchase history for the top 10 songs. I saved the list of top 10 reccomended songs to user in "data_recommend". 

Finally, I call the function "data_recommend" which will give the reccomendation on thier likeness of the songs.

<img width="665" alt="Screenshot 2022-06-06 at 2 47 42 PM" src="https://user-images.githubusercontent.com/43773641/172163507-e7fd60dc-ae33-4111-99f1-acfe6667b386.png">



