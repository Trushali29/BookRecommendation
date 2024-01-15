# BookRecommendation

Recommendation systems are widely used to recommend products to the most appropriate end users. Online book-selling websites nowadays are competing with each other by many means. A recommendation system is one of the stronger tools to increase profit and retain buyers. The book recommendation system must recommend books that are of buyer’s interest. This paper presents a book recommendation system based on combined features of content filtering, collaborative filtering, and popularity filtering.
For this, we are proposing a knn algorithm and a hybrid algorithm in which we combine two or more algorithms, so it helps the recommendation system to recommend the book based on the buyer's interest.

**Keywords** 

Content-based, collaborative based, Knn , Hybrid algorithm, popularity based, search by author and publisher, recommendation.


**INTRODUCTION**

The main motive for building a recommendation system is to try various approaches using popularity-based, content-based and collaborative-based based. 
After analysing these filters we are finally approaching a hybrid algorithm that melds content-based and collaborative approaches, which have complementary strengths and weaknesses, thus producing stronger results.


**ABOUT DATASET**

The dataset we have used in this work is the Book-Crossing Dataset which comprises three tables: -
Books: It has 8 columns; ISBN, Book title, Book author, Year of publication, Publisher, and three columns for Book cover Image URLs representing three different versions (small, medium, and large).

Users: Contains the user’s information. It consists of 3 columns: UserID, Location, and age.

Ratings: Contains information on ratings of the books. It consists of 3 columns UserID, ISBN, and Book Rating.

The workflow of the project is:


**PRE-PROCESSING AND CLEANING**

All the pre-processing and cleaning on the dataset is described below:

**Books Table**

Drop all three Image URL features.
Check for the number of null values in each column. There are only 3 null values in the table. Replace these three empty cells with ‘Other’.
Check for the unique years of publications. Two values in the year column are publishers. Also, three tuples have the name of the author of the book merged with the title of the book.
Manually set the values for these three above-obtained tuples for each of their features using the ISBN number of the book.
Convert the type of the years of publications feature to the integer.
By keeping the range of valid years as less than 2022 and, not 0, replace all invalid years with the mode of the publications which is 2002.
Upper-casing all the alphabets present in the ISBN column and removing duplicate rows from the table.


**Users Table**

Check for null values in the table. The Age column has more than 1 lakh null values.
Check for unique values present in the Age column. There are many invalid ages present like 0 or 244.
By keeping the valid age range of readers as 10 to 80, replace null values and invalid ages in the Age column with the mean of valid ages.
Removal of duplicate entries from the table.

**Rating Table**

Check for null values in the table.
Check for the Rating column and User-ID column to be an integer.
Removal of punctuation from ISBN column values and if that resulting ISBN is available in the book dataset only then consider dropping that entity.
Upper-casing all the alphabets present in the ISBN column.
Removal of duplicate entries from the table.


**Merging of all three Tables**

Merging Books, Users and Rating Tables in One Dataset.


**DATA VISUALIZATION**

**1. Top books by author**
**2. Top books by publisher**
**3. Age distribution**
**4. Book ratings given by users: The graph below shows the count of book ratings given by users. We can see most of the books are rated 8 on a scale of 10.**
**5.Explicit and implicit book ratings**
**6. Number of ratings of a book**

**RECOMMENDATION MODELS**

We have implemented 5 basic recommendation systems.  

**1. Popularity in the whole collection**

We have sorted the dataset according to the total ratings each of the books has received in non-increasing order and then recommended the top n books.

**2. Recommend books by author name and publisher name**

For this model, we have sorted the books by rating for the same author and same publisher of the given book and recommended top n books.

**3. Books by author**
**4. Books by Publisher**

**5. Content-based recommendation of books**

Implemented a content-based recommendation system that recommends books by calculating similarities in Book Titles. For this, TF-IDF feature vectors are created for unigrams and bigrams of Book-Titles where only those books' data has been considered that have at least 80 ratings (because of limited resources).

**6. Collaborative-based recommendation of books**

A collaborative Filtering Recommendation System considers user ratings and finds cosine similarities in ratings by several users to recommend books. To implement this, Consider only those books' data that have at least 80 ratings in all (because of limited resources).

**7. Nearest Neighbour-based recommendation system**

To train the Nearest Neighbours model, creating a compressed sparse row matrix by taking ratings of each Book by each User individually. This matrix trains the Nearest Neighbours model and then finds n nearest neighbours using the cosine similarity metric.

**8. Hybrid-based recommendation system (content + collaborative)**

Implementing a hybrid recommendation system using both content-based filtering and collaborative filtering systems. A percentile score is given to the results obtained from both content and collaborative filtering models and is combined to recommend top n books.

 
