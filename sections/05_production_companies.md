# Investigating the Role of Production Companies in Movie Popularity

Next, we examine whether the production company has an impact on a movie's popularity, with popularity measured by the number of votes received. To investigate this, we analyze the frequency of movies produced by each company, using it as a proxy for the company's prominence or influence within the industry. The underlying assumption is that more prolific production companies may be linked to higher average popularity for their films.

To begin, we visualized the Top 20 production companies based on the number of movies they have released. The results are as follows:

<br>
<div style="display: flex; justify-content: center; margin-top: -40px;">
    {% include plots/03_prod_companies_count.html %}
</div>

We observe that the movie industry is largely dominated by major production companies, which produce significantly more movies than others (e.g., Metro-Goldwyn-Mayer, Paramount, etc.).

For the top ten production companies, we analyze the average popularity of their movies, measured as the logarithm of the number of ratings. To explore this, we use boxplots to visualize the distributions of popularity for each company's produced movies.

<br>
<div style="display: flex; justify-content: center; margin-top: -40px;">
    {% include plots/03_prod_companies_boxplots.html %}
</div>

Here, we do not observe any clear trend in popularity, as it appears that for the ten most productive companies, production volume does not heavily influence movie popularity.

To further investigate, we will use a barplot to examine how popularity is distributed among the most "popular" production companies—those that produce movies with the highest average popularity.

<br>
<div style="display: flex; justify-content: center; margin-top: -40px;">
    {% include plots/03_prod_companies_barplots.html %}
</div>

Although the average popularity appears relatively stable for the first seven companies, the high variance observed for all of them prevents us from drawing any significant conclusions about a clear trend.

To gain a broader perspective, we use a scatterplot to compare a company's importance—measured by the number of movies produced—with the average popularity of its movies, expressed as the logarithm of the number of ratings. Given the highly unbalanced distribution of company importance, we apply a logarithmic transformation for better visualization.

<br>
<div style="display: flex; justify-content: center; margin-top: -40px;">
    {% include plots/03_prod_companies_scatterplot.html %}
</div>

From the scatter plot, there is no clear trend linking production frequency to average movie popularity. However, variability in popularity tends to decrease as production frequency increases, suggesting that high-frequency companies produce movies with more stable popularity. In contrast, low-frequency companies show greater variability, possibly due to focusing on specific genres or producing a mix of successful and unpopular movies. This variability can be seen as a measure of the 'risk' of producing movies.

However, after performing an F-test on the ratio of variances, the results do not support our intuition, as the p-value is nearly 100%. This indicates that there is no significant difference in the 'risk' associated with producing movies at high or low frequencies.