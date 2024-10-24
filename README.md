![alt text](images\box_office_banner.jpg)
# Box Office Statistical Analysis
Author: Elijah Lopez


## Overview
This analysis utilizes public data from Internet Movie Database (IMDb) and The Numbers to determine which factors make a movie a box office success. Success was defined by average reviews, return on investment (ROI), and gross revenue.

The goal of this analysis is to provide data-driven insights to help an emerging movie studio produce a box office hit! This movie studio will be able to use our findings to determine which genre to focus for their first film, a budget for the film, and when to release their movie to achieve the greatest ticket sales.


## Business Problem
Emerging movie studios are inundated with choices regarding how to grow credibility with their target audience, deciding on a genre, establishing a production budget, and determining when to premiere their new film.


## Data
This data comes from [Internet Movie Database](https://www.imdb.com/) (IMDb) and [The Numbers](https://thenumbers.com/).

* The [data](data\im.db) from IMDb was stored in a SQLite database which includes movie  ID, title (including alternate titles), genre, and average rating, among other things. Initially there were 146,144 movies with 331,703 alternate titles. Only 73,856 of which had average ratings figures.
* [Data](data\tn.movie_budgets.csv) from The Numbers includes movie titles, release date, production budget, and domestic/worldwide gross sales. There were 5,782 movies listed.


## Methods
Data from The Numbers was first matched by title or alternate title and assigned a movie ID. From there the data was merged into one dataframe that consisted of 2,508 unique titles. Further analysis focused:
1. Ratings by Genre
    * Genres with less than 30 movies were excluded.
2. ROI by Budget
    * Revenue was the higher of Domestic Gross and Worldwide Gross. Movies generating $0 in revenue were excluded.
    * Budget levels defined as:
        * Low: < $5M
        * Medium: $5-50M
        * High: > $50M.
3. Revenue by Release Month
    * Revenue was the higher of Domestic Gross and Worldwide Gross with movies generating $0 in revenue were excluded.

After completing descriptive statistics for each these areas of focus, an Analysis of Variance (ANOVA) test with alpha = 0.05 was conducted to determine if there was a statistical difference between categories. Finally, a post-hoc Tukey's Honest Significant Difference (HSD) test with alpha = 0.05 was performed to investigate which categories were causing the significant result observed in the ANOVA test.


## Results


### Ratings by Genre
![alt text](images\rec1.png)

* There are 19 unique genres with average ratings between 5.5 and 7.1 out of 10.
* Documentaries, biographies, and historical movies had highest average ratings.
* Statistical Analysis using an alpha = 0.05 shows that:
    * Documentaries (7.1/10) were rated higher than 10 other genres at a significant level
    * Biographies (7.0/10) were rated higher than 9 other genres at a significant level
    * Historical movies (7.0/10) were rated higher than 4 other genres at a significant level


### ROI by Budget
![alt text](images\rec2.png)

* Budget Levels broken into:
    * Low: < $5M
    * Medium: $5-50M
    * High: > $50M
* ROI by Budget
    * Low: $12.6M
    * Medium: $306.2M
    * High: $525.2M 
* ROI is higher for higher budget films
* Statistical Analysis using an alpha = 0.05 shows that the difference in ROI is significant across all budget levels


### Revenue by Release Month
![alt text](images\rec3.png)
* Across all months May, June, and November recorded the highest gross revenue
* Statistical Analysis using an alpha = 0.05 shows that the difference in revenue is significant between each of these months and September and October but they are not statistically different from each other or the other calendar months.


## Conclusions
This analysis leads to three recommendations.

1. Create a historical movie, a biography, or a documentary. This will likely receive the highest ratings and build credibility with the target audience.

2. Secure a minimum production budget of $5M. This target will set a reasonable goal for an emerging movie studio while capturing the significant increase in ROI that will allow the movie to be profitable and continue future productions.

3. Release the movie in May, June, or November. This will maximize the likelihood of ticket sales as May and June kick off the summer months and November leads into the holiday season, both corresponding to increased family activity.


## Next Steps
* Decide which genre best matches the interest and capability of the production crew.
* Seek funding through banks, private equity, or partnerships.
* Time production (casting, filming, and editing) so that the movie can premiere at the optimal time.


## For More Information
See the full analysis in the [Jupyter Notebook](box_office_statistical_analysis.ipynb) or review this [presentation](https://docs.google.com/presentation/d/1ifef1BkZikxRSQKQzS0ZgQe31FlO3s7aLYEzw0WZeGE/edit#slide=id.p).

For additional info, contact the author at:

Elijah Lopez | elijahlopez94@gmail.com