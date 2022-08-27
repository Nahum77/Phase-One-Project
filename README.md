
# Phase-One-Project

# MICROSOFT FILM PROJECT
## Author: Nahum Odemba


## BUSINESS UNDERSTANDING

### 1.1 Project Overview  
My client, Microsoft Company, is planning to join the fun-filled movie industry. Apart from adding fun to the mix, this is also part of generating more profits for the company. Unfortunately, Microsoft has no knowledge about movie production, leave alone where to start. My goal in this project was to conduct data analysis using datasets from IMBD, Box Office Mojo, Rotten Tomatoes, The MovieDB, and The Numbers to explore what genres of movies generated the most revenue. Second, the analysis also focused on budgeting to see whether high budgets on movies yielded high returns. Finally, the project examined seasonality of movies and revenue generation. At the end of the project, I provided recommendations on where Microsoft’s new movie industry should focus on. The motivation of the recommendations was to help Microsoft invest in the right movies that will generate the highest income, at the least cost. 
 
### 1.2 Understanding the Problem
 
The movie industry is booming. This multi-billion-dollar industry is getting even bigger every year. Investing in the movie industry sounds fun and also a good business opportunity for a large company like Microsoft. Microsoft is thus willing to jump into the mix and have a market share. Investing in a new industry may not be easy, especially when you lack insight into the market. Microsoft has no knowledge of the movie industry. Therefore, rush decision may lead to low return on investment or losses. By analyzing movie trends in the industry, I am capable of recommending the right genre Microsoft should focus on and also how the company should spend on movie production. To come up with the best recommendations, I based my analysis on the following factors:
Movie genre vs ratings and number of votes: Which is the best movie genre to invest in depending on ratings and votes?
Movie budget vs movie income (gross): Does high budget translate to high income?
Movie income vs genre: Does the movie genre determine its income?


## DATA UNDERSTANDING 
### 2.1 Data Collection
Data used in this project had already been provided on a GitHub repository. My work involved forking the repository from GitHub, cloning it to my computer and then using different technologies to access the most useful dataframes. The available data was collected from IMBD, Box Office Mojo, Rotten Tomatoes, The MovieDB, and The Numbers. 
The tn.movie_budgets.csv: Provides data on production budget of a movie and the domestic and foreign gross of that movie.
The im.db is a relational database with tables containing information such as movie directors.  
### 2.2 	Data preparation
I started preparing data by first loading the tn.movie_budgets.csv and im.db to my jupyter notebook. 
Second, I joined the movie_ratings and the movie_basics tables from the im.db file.
### 2.3. Data Cleaning  
Data cleaning is an important step done to ensure clarity, validity and consistency of data being used in the subsequentb steps. Another important role of this step is to remove outliers, NaN values, and ensure data used fully addresses the business question.

The first thing i did was to check for duplicates in the movie_ratings table. I did this using the primary_title column. This column was chosen because two movies cannot have a shared primary title, according to the data set that i was working with. I used the primary_title as the primary key.

The next step was to drop all the duplicates in the movie_ratings table. Just to be certain, I went ahead to confirm if there were any duplicates left. I saved the filtered table to movie_ratings_no_duplicates.

The movie_ratings_no_duplicates was filtered further by dropping movies with average ratings less than 6 and numvotes less than 100 and saving the results to filtered2.

The purpose of this was to ensure taht I only work with top rated movies with many number of votes.
Next after reading tn.movie_budgets.csv and saving it in the variable budget_df, I went ahead and checked its datatype. I learned that the columns I wanted to use: production_budget, worldwide_gross, and domestic_gross, were object types. Which I then converted to integer type. 
Using inner join, I joined filtered2 and the budget_df table and named the reultimng table joined_df. Joining was important because it enabled me to have all the columns and rows that I wanted to use in answering my business question.
### 3.Data Analysis
### 3.1 Exploratory Data Anslysis
My first business question was to see which movie genres had higher ratings with high number of votes. 

I plotted a bar graph of genres vs. numvotes, for movies with ratings above 6 and numvotes above 100. The graph showed that the following movie genres have high ratings and number of votes:
Adventure, Animation, Comedy
Action, Adventure, Sci-Fi
Action, Drama, Family

The second business question was to answer the question of whether high production cost translates to high movie income. I plotted a scatter plot to show the relationship between production budget and the worldwide gross. 
The graph showed that correlation between production budget and worldwide gross. There are movies with high production budget taht do not translate to high worldwide gross. Also, there are movies with low production budget but high worldwide gross. 
Another scatter plot was also plotted to show the relationship between production budget and domestic gross.

Just like the plot on the relationship between production budget and worldwide gross, this plot confirms that high production budget does not guarantee high movie income.

Genre was another variable I used to determine the most profitable movies. The business question i was trying to answer was whether movie income depends with its genre. Therefore, in the joined_df dataframe, I added another column ‘Profit’ which I calculated by subtracting production budget from the worldwide gross. After plotting genres against profits, I got the following chart. 

The chart showed that the following genres make the highest profits:
Thriller
Action, Drama, Family
Action, Adventure, Thriller
Crime, Drama, Thriller
## 4. Conclusion 
This data analysis proved wrong certain hypothesis about movie industry. For instance, it is hypothesised that high production budget translates to high movie income. From the analysis, it is proven that high production cost does not guarantee high income. Second, this analysis finds high movie rating does not translate into high income. For instance, Adventure, Animation, Comedy genre has a very high rating but low income compared to Thriller which has very low rating but high income. Action, Adventure, Sci-Fi is another example of genres with high ratings but average income. This conclusion, however, may be affected by the number of movies in said genres 
## 5. Recommendations
First, using the graphs that I have presented, I would recommend that Microsoft’s new movie studio kicks off with Thriller movies. Thrillers have the potential of making more money for the studio and the company. 
This recommendation has been arrived because Thrillers have high profits from the analysis that I did with the available data. 

Second, the production budget should be kept at the possible minimum because high production cost does not translate into high income. However, this should not be done at the expense of the movie quality.
  



