# Mayank-kptncook-data-challenge
Python code for updating data when user listened to new music and recommending artist to user


I first took the input from the user about the song that he/she listened. In this code, user 33 has listened to an artist 'abba' so I open the excel file and ask for updation of new artist if a user  listened to the song. If a user listened new song then I update the excel file with 1 in the designated cell of data. 

After doing the updation, I used Collaborative filtering method for recoomending songs to user.


Collaborative filtering is another technique that can be used for recommendation.
This technique's core premise is as follows:

Assume that Person A and Person B both enjoy oranges.
Assume that Person A like apples.
Individual B is more likely to agree with A on Apples than any other random person.

The benefits of collaborative filtering are self-evident: We can forecast and offer goods to users based on comparable preferences. Collaborative filtering is classified into two types: user-based and item-based.

*Item Based: which takes similarities between items’ consumption histories
*User Based: that considers similarities between user consumption histories and item similarities


The data collection includes information about users, such as their gender, age, and the artists they have listened to on Last.FM. each row will represent a user, and each column represents and artist.


First, I used Item-Based collaborative Filtering on the data to calculate the similarity of each song with the rest of the songs. That is, we want to compare each column in our "data.germany.ibs" data set to every other column in the data set. We will specifically compare what is called as "Cosine Similarity."

In essence, the cosine similarity divides the sum product of the first and second columns by the product of the square root of the sum of squares of each column. In Python, the Scipy library has a function that allows us to do this without customization.

With our similarity matrix completed, we can search for each item's "neighbor" by looping over 'data ibs,' sorting each column in decreasing order, and obtaining the names of the top ten songs.


The following is the procedure for developing a User Based Recommendation System:

1) Have an Item Based Similarity Matrix handy 
2) Examine which things the user has consumed.
3) Obtain the top X neighbors for each item consumed by the user.
4) Get the user's consumption record for each neighbor.
5) Using a formula, compute a similarity score.
6) Recommend the song with the highest similarity.

First I define the function to get similarity scores ("def getScore")- I multiply the total of the product two vectors carrying history and similarity statistics by the sum of the similarities in the corresponding vector.

![image](https://user-images.githubusercontent.com/43773641/172162256-7ef56bd6-e27f-4ecc-a26a-8dbbde7f9df6.png)

The rest is a matter of applying this function to the data frames in the right way. We will now cycle through the rows and columns, filling in the blanks with similarity scores. It is worth noting that we rate goods that the consumer has previously consumed as 0, as there is little purpose in recommending them again.

After that, I produce a matrix of User Based recommendations as follows:

<img width="1002" alt="Screenshot 2022-06-06 at 2 43 04 PM" src="https://user-images.githubusercontent.com/43773641/172162824-782950b1-2e07-44f8-8b8c-d04165de57b5.png">
Now, I sort  the user’s purchase history for the top 10 songs. I saved the list of top 10 reccomended songs to user in "data_recommend". 

Finally, I call the function "data_reccomend" which will give the reccomendation on thier likeness of the songs.

<img width="665" alt="Screenshot 2022-06-06 at 2 47 42 PM" src="https://user-images.githubusercontent.com/43773641/172163507-e7fd60dc-ae33-4111-99f1-acfe6667b386.png">
