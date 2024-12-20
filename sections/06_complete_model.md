# The complete model

What makes a movie a blockbuster? In this final chapter we will finally try to give an answer to this compelling question. After all the analysis on individual aspects, countries, genres, cast, and production companies, it’s time to bring everything together. Here, we’ll finally try to give an answer to this big question by combining all the insights we’ve gathered throughout the project.

To do so, we’ll take a two-step approach. First, we’ll try to answer this question using a decision tree model. This is because decision trees are great at giving us an intuitive, easy-to-interpret picture of how different factors interact and contribute to a movie’s success. Then, we’ll move to a more traditional OLS regression model, which will give us a detailed, quantitative breakdown of how each covariate contributes to a movie’s performance.

For both models we focussed on the following covatiates:
- **Log Budget**.
- **Countries**: only those that produced at least 50 movies, as above.
- **Genres**.
- **Cast statistics**: only the ones that we discovered to be relevant, so *cast_country_count*, *age_std*, *actor_fame_bool*, and *director_fame_bool*.
- **Production companies**: we included only companies that produced at least 70 movies. This way, we avoided overfitting with smaller players.

As for the dependent variable, we classified movies into low success and high success groups based on average popularity. This binary classification allowed us to clearly delineate between blockbusters and less successful films.

We split the dataset into a training set and a test set, trained the model on the training set, and evaluated its performance on the test set. The results are very encouraging: the decision tree achieved an accuracy of 79% on the test set with only 5 levels, proving to be really good at recognising real blockbusters.

So let’s dive into the details and see what our models have to say about what truly makes a movie successful. The plot below illustrates the first three layers of the decison three.
<figure class="center">
  <img src="./assets/img/05_tree.png" class = "center" width="1000"> 
</figure>
If we examine the tree, we notice that the most important variable for predicting a movie’s popularity is its budget. The decision tree uses budget as the primary discriminator for all the first two levels of depth. This finding is intuitive: larger budgets often mean better production quality, higher-profile marketing, and greater audience appeal. The more a production invests, the more likely it is to attract viewers.

The next most significant factors are *std_age* (the standard deviation of cast age) and *cast_country_count* (the number of nationalities within the cast). This reinforces the idea that internationally diverse casts resonate better with global audiences, while a wider age range increases a movie’s appeal across different generations.

Finally, the decision tree highlights the impact of genre, with thrillers and family movie standing out as particularly influential genres.

Using the same set of covariates, we built an OLS regression model to predict movie popularity as a continuous variable. To make the results more interpretable, we normalized all numeric covariates, such as log budget and cast statistics. This ensured that the coefficients represented the relative impact of each variable on movie popularity, measured on a comparable scale.

The results are visualized in the plot below, which shows the regression coefficients for each variable.

<div style="display: flex; justify-content: center; margin-top: -40px;">
    {% include plots/05_complete_ols.html %}
</div>

As in the decision tree, the budget stands out as the most significant factor influencing a movie's popularity. The large positive coefficient reinforces the idea that bigger budgets lead to higher-quality movies and wider audience reach.

Another notable factor is cast diversity, measured by the *cast_country_count* variable. This metric reflects the variety of countries represented in a movie’s cast. The positive impact of this variable indicates that a diverse cast broadens a movie’s appeal, particularly in global markets, where representation and relatability play key roles in attracting audiences.

Production companies also emerge as important contributors to movie success. Established players like Paramount Pictures, Columbia Pictures, and United Artists are associated with strong positive coefficients. These findings underscore the advantage of working with experienced studios that have the resources, networks, and expertise to consistently produce good movies. The influence of genres also aligns with expectations: genres such as sci-fi, horror, and thrillers are significant predictors of popularity. 

Finally, the country of production plays a significant role, with movies produced in the USA showing a substantial positive impact. This reflects Hollywood's global dominance, with its unparalleled production infrastructure and audience reach. In contrast, countries like Russia and Argentina show slightly negative coefficients, indicating that movies produced there face challenges in achieving the same levels of success on a global scale.

Together, these two models provide a comprehensive picture of what makes a movie successful. The decision tree offers a clear and interpretable recipe for success, while the OLS model quantifies the individual contributions of each factor. Both approaches underline the importance of budget, country of production, and genre in defining blockbuster potential. By combining these perspectives, we gain a richer understanding of the elements that really make a movie successful.