# ML-DRIVEN: A Clustering-Based Approach of Book Recommendation System

## Exploratory Data Analysis + Data Visualization + Modelling 

### 1 - Abstract

In this project, I made Exploratory Data Analysis, Data Visualisation, and lastly Modelling. The dataset contains 11123 rows in a CSV file. Each example row represents a book with 12 different pieces of information. Before the modeling part I have to check NaN values make some small adjustments for easy use of the dataset and merge a couple of languages into 1 language(en-AUS,en-UK to eng). Later I made a couple of visualizations to understand the dataset better. In the modeling part, I used the unsupervised learning algorithm K-means which groups unlabelled data. For deciding the number of clusters I used the Elbow method and decided to do 5 clusters. Finally, I tested my model with several books and added an input function for searching easily. 

### 2 - Data
<a href="https://www.kaggle.com/jealousleopard/goodreadsbooks">Dataset</a> contains 12 columns and 11123 rows.

Columns Description:
* __bookID__ = contains the unique ID for each book/series
* __title__ = contains the titles of the books
* __authors__ = contains the author of the particular book
* __average_rating__ = the average rating of the books, as decided by the users
* __ISBN ISBN(10)__ = number, tells the information about a book - such as edition and publisher
* __ISBN 13__ = the new format for ISBN, implemented in 2007. 13 digits
* __language_code__ = tells the language for the books
* __Num_pages__ = contains the number of pages for the book
* __Ratings_count__ = contains the number of ratings given for the book
* __text_reviews_count__ = has the count of reviews left by users
* __publication_date__ = date of publication
* __publisher__ = name of the publisher


### 3 - Exploratory Data Analysis

In EDA I visualize language distribution, the Top 20 authors with the number of books, the Top 20 highest-rated books, and the Average rating distribution for all books. 


<p align="center">
  <img width="800" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/languagedistribution.png">
</p>

<p align="center">
  <img width="800" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/authorswithNumberofbooks.png">
</p>

<p align="center">
  <img width="900" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/most_rated_books.png">
</p>

<p align="center">
  <img width="800" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/Average%20rating.png">
</p>

Secondly, I create a list of my favorite authors and visualize their books according to the average rating of books. 
```
authors = ['Gabriel García Márquez', 'Jack London', 'George Orwell', 'Jules Verne', 'Richard P. Feynman']
```
<p align="center">
  <img width="800" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/GabrielGarc%C3%ADaM%C3%A1rquez.png">
</p>

<p align="center">
  <img width="800" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/GeorgeOrwell.png">
</p>

<p align="center">
  <img width="900" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/JackLondon.png">
</p>

<p align="center">
  <img width="800" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/JulesVerne.png">
</p>

<p align="center">
  <img width="900" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/RichardFeynman.png">
</p>

After all these steps, I wanted to investigate the relationship between columns. As you can see below, __Average Rating and Number of Pages, Average Rating and Reviews Counts,Rating Counts and Average Ratings__

<p align="center">
  <img width="500" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/averagerating_numpages.png">
</p>

<p align="center">
  <img width="500" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/averagerating_reviewcount.png">
</p>

<p align="center">
  <img width="500" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/averagerating_ratingscount.png">
</p>

### 4 - Modelling 
In the modeling part, I already decided to use the K-Means Algorithm but I have to decide how many should I use. For deciding this I used the Elbow Method which gives giving very good assumption. In the figure below you can see the graph.

<p align="center">
  <img width="800" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/elbow.png">
</p>

After deciding on 5 clusters, I created plotting and expressing clusters.

<p align="center">
  <img width="800" height="500" src="https://github.com/HalukSumen/Book_Recommender/blob/main/images/cluster1.png">
</p>

Lastly, I implemented a Min-max scaler, to reduce bias. Because some books have a massive amount of features and some of them very few. So, the Min-Max scaler will find the median of all books. 


### 5 - Result & Future Work
```
print_similar_books("Caesar (Masters of Rome  #5)")
```
* The Metaphysical Club
* One Hundred Years of Solitude
* Alice's Adventures in Wonderland and Through the Looking-Glass (Alice's Adventures in Wonderland  #1-2)
* In Cold Blood
* Desperation / The Regulators: Box Set

```
print_similar_books("Lord of the Flies")
```
* Introduction to the Philosophy of History with Selections from The Philosophy of Right
* Marie  Dancing
* The Odyssey
* The Hour Before Dark
* A Philosophical Enquiry into the Origin of our Ideas of the Sublime and Beautiful

As a result, my book recommender gives good results. But still, there is more room for improvement. Such as finding the category of each book makes everything more effective. Increasing the size of data or information(more rows) can help more accurate recommendations.
