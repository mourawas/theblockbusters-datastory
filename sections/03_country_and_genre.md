# Countries

Now that we’ve established what "success" really means for us, let's examine the influence of a movie's country of origin on its success. It's no surprise that the country where a film is produced can play a significant role in shaping its trajectory. Some nations have well-established film industries, global distribution networks, and deep cultural influence, while others might struggle to reach international audiences.

In our dataset, we notice that some countries appear much more frequently than others. For instance, the United States alone accounts for nearly 40% of the movies in the dataset, while the U.S., India, and U.K. together represent almost 60%. This stark imbalance suggests a potential sampling bias, which requires caution when analyzing the impact of a movie’s country of origin on its success. Without careful consideration, we could be misled into overstating the influence of these dominant countries simply because they are overrepresented.

The plots below help illustrate this phenomenon. The world map displays the number of movies produced by each country, emphasizing the overwhelming dominance of a few countries that are heavily represented, overshadowing the contributions of smaller film industries across the globe. In contrast, many nations, especially those with emerging or niche film industries, are far less present in the dataset.

<div style="margin-top: -40px;">
    {% include plots/03_map_country_num.html %}
</div>

<div style="margin-top: 20px;">
    {% include plots/03_country_count_bar.html %}
</div>

When considering the average popularity of movies per country, we faced an important decision: whether to include countries with only a handful of movies in our analysis. Although every film industry has value, a country with just a few entries might not provide a reliable measure of average popularity. For instance, a single highly successful movie could skew the average for countries with limited representation, making it appear disproportionately influential. To address this, we decided to exclude countries with fewer than 50 movies in our dataset. Doing so, we were able to compare 56 countries with enough films to reveal patterns that are both meaningful and surprising.

The plots below illustrate the average popularity of movies across countries. The world map shows how popularity varies globally, while the bar plot highlights the "best" 10 and the "worst" 10 countries in term of average pupularity.

<div style="margin-top: -40px;">
    {% include plots/03_map_country_avg.html %}
</div>

<div style="margin-top: 20px;">
    {% include plots/03_country_avg_bar.html %}
</div>

What stands out the most here is the disconnect between volume and quality. If we consider, for example, the United States and India, two of the most prolific film-producing countries, we notice how they occupy opposite ends of the spectrum. While the U.S., in spite of its massive output, maintains relatively high average popularity, India’s huge number of movies struggles to achieve the same audience reception. At the same time, we noticed the impressive performance of relatively small film industries. Countries like Luxembourg, Turkey, and New Zealand, while contributing far fewer films than the cinematic giants, have achieved remarkably high average popularity scores. These contrasts highlights a key insight: producing more movies doesn’t necessarily equate to producing more successful ones. A high volume of films may dilute overall popularity, as not every production can meet the same standards or achieve the same level of audience appeal.

<div style="display: flex; align-items: flex-start">
    <div style="flex: 1; margin-right: 10px;">
        But lets dive deeper and analyze the OLS coefficients. <br><br>
		
		At the top, Turkey takes the spotlight with the highest positive coefficient, showing that films from this country tend to perform exceptionally well. It’s a clear case of quality over quantity, as Turkey might not produce as many movies as the global giants, but the ones they do make really hit the mark. The United States follows closely behind, showing once again that Hollywood’s global influence remains unmatched.<br><br>

		Countries like Serbia, Iran, and New Zealand are also impressive performers. While they produce fewer films overall, their positive coefficients suggest that they’re punching above their weight when it comes to audience reception. <br><br>
		
		On the other hand, countries like India and Indonesia land somewhere near the middle, with coefficients close to zero. India, despite being a massive movie producer, faces a "dilution effect", where a high volume of movies leads to mixed results, with only a fraction achieving significant international success. <br><br>

		At the bottom, countries like Argentina, Sri Lanka, and Pakistan show negative coefficients, indicating that their films struggle more to gain global traction. This isn’t necessarily a comment on the quality of their movies but rather a result of the challenges they face, such as limited international distribution, smaller budgets, and lower overall visibility. <br><br>
    </div>
    <div style="flex: 1;">
        {% include plots/03_country_ols.html %}
    </div>
</div>
These observations naturally raise an important question: What drives this success or struggle? Is it simply about where a film is produced, or are other factors-like budget, genre, and access to global markets-playing a larger role? For instance, does being produced in the United States inherently boost a movie's success, or is Hollywood’s dominance more a reflection of its unparalleled access to resources, talent, and distribution networks?

To answer this question, we turn to causal analysis techniques, which allow us to move beyond correlations and uncover whether being from a specific country—like the United States—causes a movie to perform better. One key method we use is propensity score matching (PSM).

Propensity score matching helps us compare movies from the United States to those from other countries in a way that controls for confounding factors like budget, genre, and runtime. Essentially, PSM creates a "balanced dataset" where movies from the U.S. are matched with movies from other countries that have similar characteristics. For example, a big-budget Hollywood blockbuster would be matched to a similarly funded movie from another country. This ensures that any observed difference in popularity can be more confidently attributed to the country of origin, rather than other factors.

<div style="display: flex; align-items: flex-start">
    <div style="flex: 1; margin-right: 10px;">
		{% include plots/03_country_propensity_bar.html %}
	</div>
    <div style="flex: 1;">
        After performing propensity score matching, we obtain a balanced dataset with 6504 movies, half produced in the USA and half produced elsewhere. Then, we perform a t-test comparing the average popularity of movies produced in the U.S. against those produced elsewhere. Strikingly, we find an exptremely low p-value, meaning that the two groups have indeed different mean. This means that, even after controlling for factors like budget, runtime, and genre, being produced in the United States really does give movies an edge. The bar plot here on the side visually illustrates this difference.
    </div>
</div>

This finding suggests that Hollywood’s dominance isn’t just about having larger budgets or producing more movies. There is a real and measurable advantage for a movie in being produced in the United States of America.

# Genres
