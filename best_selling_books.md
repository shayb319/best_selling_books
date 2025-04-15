# Analyzing Best Selling Books - Data Visualization Portfolio Project

## Introduction

This project explores the information on the 100 top-selling books, ranked by their worldwide sales, using a range of visualizations. We will discover trends and gain insights into authors, genres, publishing trends, and reader behaviors.

#### Source

The dataset that we will use was obtained from Kaggle, Bestsellers Unveiled: Global Top Selling Books by Maria Nadeem. This dataset contains information about the world's best-selling books, with a focus on sales volume and other related details. 

#### Questions

We will be working with this list of world best-selling books to answer the following questions:
- Which publishers have the most books on the list?
- What are the most popular genres?
- Do some genres tend to sell more copies on average than others?
- Is there a correlation between the number of best-selling books an author or publishers has and their total sales?

## Import Libraries

#### Data Manipulation & Analysis

#### Data Visualization

#### Statistical Analysis

#### Text Annotation & Adjustment

## Load and Inspect Data

The dataset containing the list of best-selling books is located in the 'datasets' folder.

Let's load and inspect the data of the top 100 best-selling books.

#### Load Dataset

#### Inspect Dataset

#### Initial Observations

- The data includes the name of the book, the author, the publisher, the genre, total number of sales and it's rank in the top 100 list.
- The `Volume Sales` column is currently of type `object` when it should be of type `int`.
- There are 21 unique `Genre` categories, which can be reduced down to broader groups to help with analysis.
- There are a handful of publishers listed that are owned by the same parent company.
- There is one book record for 'The Beano Annual' that is written by various authors, but currently lists the author as `0`.
- Some of the publisher names are very long and may make some of our visualizations difficult to read.
- Author names are currently listed in last name, first name format.

## Data Cleaning & Preparation

Before we start looking at the data, we need to clean and prepare the dataset.

Here are some updates we will be making:
- Replace any space characters in the column names with an underscore and lowercase all characters to provide easier access to columns.
- Change the data type of the `Volume Sales` column from `object` to `int`.
- Create an additional column called 'general_genre' to consolidate the number of unique genre categories into larger groups.  This will improve trend analysis while maintaining meaningful distinctions between groups.
- Create an additional column named `parent_company`, which will group together publishers that are owned by the same company and list them as `Independent` if there is no parent company.
- Replace any instances where `Author` is `0` to have a value of `Various Authors`.
- Create a new column that includes an abbreviated version of the publishers name to make it more concise for use in our visualizations.
- Extract the first and last name from the `author` column to create new columns called `first_name` and `last_name`. Use those new columns to concatenate the values to create a `full_name` column. This will help with visualizations.
- Create individual dataframes that group by the following columns; `general_genre`, `publisher_abbrev`, `parent_company`, and `author`. Each dataframe will include the total number of books, the sum of volume sales, and some additional features that pertain to each individual topic.
- Create color palettes to use on our charts and graphs to make them visually engaging. 

#### Optimizing Features

#### Generating New Features

#### Developing Color Schemes for Graphs

#### Group and Aggregate Data

#### Evaluating Cleaned DataFrames

Now that we have cleaned and prepped our book dataset, we can start answering our initial questions through data visualization.

## Data Visualizations

### What are the most popular genres?

In order to figure out which genres are most common in the top 100 bestsellers, we need to look at the genres of each book on the list. We'll group the books by genre and count how many titles there are for each genre. Then, we'll present this information in a horizontal bar graph, displaying the number of books in each genre.

The bar graph above clearly shows that fiction novels make up the largest percentage of the top 100 bestsellers, accounting for almost one-third of all titles. Following closely behind are children's novels, thrillers, and mysteries, which have similar popularity rates. Interestingly, science fiction and fantasy seem to be less popular, with only two titles on the list.

### Do some genres tend to generate more total sales than others?

Some book genres may not appear often on bestseller lists but could still generate significant sales. To find out, we will examine the total number of copies sold within each general genre. We will use a horizontal bar graph to display the results, similar to the previous graph showing the number of books by genre. This consistency will make it easier to compare both graphs and notice any pattern changes, such as genres that sell well despite having fewer titles or those that are common on the list but contribute less to overall sales.

The genre rankings remain largely consistent between our graph of 'Most Popular Book Genres' and 'Books Sold by Genre'. *Fiction*, *Children's Books*, *Thriller & Mystery*, and *Science Fiction & Fantasy* retained their original placements, while the remaining genres shifted by only one or two spots. 

However, the gap between the top two genres, *Fiction* and *Children's Books*, is less pronounced in the sales graph. *Fiction* led with 38.5 million, while *Children's Books* followed closely with 33.8 million, a difference of just 5 million. This suggests that while *Children's Books* had fewer entries on the list, some individual titles were exceptionally successful. 
~
### Which publishers have the most books on the list?

To effectively answer this question, we can visualize the number of books contributed by each publisher using a bar graph. 

According to the data, Random House is the most dominant publisher, accounting for 19 of the top 100 best-sellers. Notably, the top three publishers, all subsidiaries of Penguin Random House, collectively account for 48 books on this list.

### Which authors have the highest total sales?

The top 100 best-seller book rankings are determined by the total volume sales of a book. Is the same true when looking at the total volume sales by an author, does their highest rank correlate with the total number of books they've sold?

We'll look at the top performing authors in terms of total sales and how they compare to some of the other authors on the list, while also listing the peak rank that an author was able to obtain from a single book.

In the graph above, the top 15 authors in terms of total book sales appear. There are 6 authors whose sales have totaled more than 5 million books. As highlighted in blue, they are J.K. Rowling, Dan Brown, E.L. James, Stephanie Meyer, Stieg Larsson, and Jamie Oliver. We can see that the difference in sales between J.K. Rowling and the runner up, Dan Brown, is close to 15 million, almost double the number of sales. 

J.K. Rowling's success is undeniable, but this begs us to ask the question, was their large number of books sales due to a single book or multiple releases? Are other authors not recognized as much despite having high sales relative to the number of books on this list? 

Another interesting point to make is that the best ranks for each author do not 




Let's look at a similar graph, but instead of looking at the total volume sales, we'll use the average number of sales per book, while continuing to highlight the same authors with the highest total sales so we can see if there are any shifts.





The top 4 authors maintained their rankings, although the difference between the top 2 authors is much less. For each book they have released, J.K. Rowling sells an average of 3.2 million and Dan Brown sell... There was a fairly large shift after that. Stieg Larsson originally ranked 5th, but when it comes to average sales per book, his placement reduced to 7th. Alice Sebold and Mark Haddon were toward the bottom of the top 15 best-sellers

Let's look at the relationship between the number of books on the top 100 best-sellers list and the total volume of sales for each books. We will highlight authors with high average sales per book



### Is there a correlation between the number of books an publisher or author has in the top 100 and their total sales?

To determine the relationship between the number of books a publisher or author has in the top 100 and their total sales, we will calculate the correlation coefficient and visualize the data using scatterplots with regression lines.



A high correlation would suggest that having multiple bestsellers significantly impacts total sales, while a low correlation might indicate that sales depend more on other factors



### Sales Distribution across Books

### Top-selling Books by Publisher




### Sales Trend by Genre




### Author Contribution to Sales




### Cumulative Sales by Rank


