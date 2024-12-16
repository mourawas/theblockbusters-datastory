# Cast

Having explored the influence of countries and genres on a movie's success, we now turn to another critical aspect of every movie: the cast. The actors and directors behind a film can significantly influence its popularity. For instance, well-known actors and directors can act as a movie's "face," drawing audiences based on their past performances or their reputation.

However, a successful cast is not solely about individual star power. The composition of the cast—their experience, diversity, chemistry, and demographic characteristics—plays an equally important role. A mix of seasoned performers and fresh faces can balance credibility with novelty, while an ensemble cast with varied backgrounds might appeal to wider and more diverse audiences.

But how do these factors work together? What is the statistical relationship between cast composition and a movie’s performance?

To assess the impact of cast composition on a movie's success, we delve into three key groups of metrics: Diversity, Fame, and Anagraphic. These metrics provide a comprehensive view of how diversity, experience, and anagraphic within the cast influence audience reception and popularity for each movie. Let’s explore each of these in detail.

1. **Diversity Measures**
 - **Number of Different Nationalities** (*cast_country_count*): Counts the unique nationalities represented in the cast. A higher count suggests a more internationally diverse ensemble.
 - **Shannon Entropy of Nationalities** (*cast_country_entropy*): Measures the evenness of representation among different nationalities. High entropy indicates a balanced representation across multiple nationalities, rather than dominance by one or two.
 - **Percentage of Females in the Cast** (*female_score*): Calculates the proportion of female members in the cast, reflecting gender representation.
 - **Gender Balance Index** (*gender_score*): Measures how close the gender ratio is to parity (e.g., equal numbers of male and female cast members).

2. **Fame Measures**
 - **Maximum Number of Appearances by Actors** (*actor_fame*): Aggregates the number of other movies for all actors in the cast, focusing on the most experienced individual.
 - **Number of Appearances by Director** (*director_fame*): Evaluates the director's experience by counting how many other movies he/she did. If there are multiple directors, the maximum value is used.
 - **Presence of Experienced Actors or Directors** (*actor_fame_bool* and *director_fame_bool*): Indicate whether any actor or director in the cast has appeared in other movies. This binary metrics highlights whether the film benefits from at least one experienced professional.

3. **Anagraphic Measures**
 - **Average Age of the Cast** (*age_mean*): Captures the mean age of the cast members.
 - **Standard Deviation in Cast Age** (*age_std*): Measures the variation in age among cast members. This could also be classified as a diversity measure.

<div style="display: flex; align-items: flex-start">
    <div style="flex: 1; margin-right: 10px;">
        Having established these key metrics, we now proceed to quantify their influence on movie success. To achieve this, we compute the Pearson correlation between each metric and the popularity of the movies in our dataset. Pearson correlation provides a straightforward measure of the linear relationship between each cast composition factor and audience reception, allowing us to identify which aspects of the cast can be associated with success. The bar plot here on the side visually illustrates our results. <br><br>
		
		The results reveal that diversity metrics, particularly the number of different nationalities and the Shannon entropy of nationalities, exhibit strong positive correlations with movie popularity. This suggests that movies with more internationally diverse and balanced casts tend to resonate better with audiences. Additionally, the presence of experienced actors and
		<span style="display: inline-block; width: 100%;"> </span>
    </div>
    <div style="flex: 1;">
        {% include plots/04_cast_pearson.html %}
    </div>
</div>
<div style="margin-top: -27px;">
    directors shows a notable positive association, emphasizing the value of established talent in driving a movie's success. On the demographic side, the standard deviation of cast age stands out, indicating that a wider age range within the cast can increase a movie's appeal across generations. In contrast, metrics like the average age and gender proportion show weaker correlations, suggesting that their influence on success is relatively limited.
</div>

Before creating a linear model, however, we have to check for colinearities among our metrics. Collinearity occurs when two or more variables are highly correlated, which can distort the results of a linear regression. To address this, we compute the correlation matrix and visualize it using a heatmap here below.

<div style="display: flex; justify-content: center; margin-top: -40px;">
    {% include plots/04_cast_stats_heatmap.html %}
</div>

We notice here that the number of different nationalities is highly correlated with the Shannon entropy of nationalities. This relationship is expected, as both metrics capture similar aspects of cast diversity, one focusing on the count and the other on the distribution balance. Including both in the model could lead to redundancy and inflate variance in coefficient estimates.

Additionally, there are other notable collinearities among variables that aim to describe the same dimension of the cast. For instance, the number of appearances by director is strongly related to the presence of experienced directors (a binary metric). In addition, the percentage of females in the cast is negatively related gender balance index, meaning that on average there are more males than females in movies' casts.

To address these issues and utilizing what we discovered using Pearson's coefficients, we train a OLS model only on the metrics: *cast_country_count*, *age_std*, *actor_fame_bool*, and *director_fame_bool*.

<div style="display: flex; align-items: flex-start">
    <div style="flex: 1; margin-right: 10px;">
        The OLS coefficients plot reveals that the standard deviation in cast age (*age_std*) and the number of different nationalities (*cast_country_count*) have the strongest positive effects on movie popularity, highlighting the importance of multi-generational and international appeal. The presence of an experienced director (*director_fame_bool*) also contributes positively, while the effect of experienced actors (*actor_fame_bool*) appears to be low but consistent. Finally, the model's R² value of 0.107 indicates that while the cast alone does not fully explain movie success, these findings can still be usefull in a broader models that consider more aspects of movies.
    </div>
    <div style="flex: 1;">
        {% include plots/04_cast_ols.html %}
    </div>
</div>



