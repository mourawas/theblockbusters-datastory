# The Definition of Success

What makes a movie successful? Is it the glowing reviews from critics, the number of people who watch it, the box office revenue it generates, or how effectively it turns investment into profit? 

Success in the film industry isn’t one-dimensional; it’s a combination of factors that work together to create an impact. In this chapter, we focus on four key indicators of success: ratings, popularity, revenue, and the often-overlooked but crucial metric of Return on Investment (ROI). Together, these metrics provide a clearer picture of what makes a movie stand out and thrive in a competitive landscape.

<ul>
  <li><b>Ratings:</b> High ratings reflect audience approval, showcasing engaging stories, strong performances, or stunning visuals. However, ratings alone don’t tell the full story—some critically acclaimed films remain niche, while others with average scores achieve massive success.</li>
  <li><b>Popularity:</b> Measured by the number of ratings, popularity indicates how many people watched the movie and cared enough to respond. Even if a film doesn’t earn top reviews, attracting a large audience highlights its broad appeal and cultural impact.</li>
  <li><b>Revenue:</b> Whether from box office earnings or streaming platforms, is a clear measure of commercial success. However, revenue doesn’t account for production costs, which is where ROI comes in.</li>
  <li><b>ROI:</b> Measures how efficiently a movie turns its budget into profit. For example, an ROI of 300% means the film earned three times its cost. While ROI data can be incomplete, it remains essential for assessing financial success.</li>
</ul>

By unpacking these metrics, we hope to better understand the dynamics of what makes a movie successful. Whether it’s a critically acclaimed masterpiece, a box office juggernaut, or a cultural phenomenon watched by millions, each metric contributes to the bigger picture of cinematic success.

All success metric have been converted in logarithmic form before starting the analysis. This transformation was necessary because the distributions of votes, budget, revenue, and ROI were very skewed and difficult to work with. The plots here below shows the distribution of the metrics before the transformation.

<figure class="center">
  <img src="./assets/img/density_subplots.png" class = "center" width="1000"> 
</figure>

After applying the logarithmic transformation we obtain the following plots.

<figure class="center">
  <img src="./assets/img/log_transformed_density_subplots.png" class = "center" width="1000"> 
</figure>

To understand further the relationships between the factors we’re analyzing, the first step was to create a scatter matrix. This gives us a visual overview of how these variables interact with each other. 

<figure class="center">
  <img src="./assets/img/01GGpairs.png" class = "center" width="1000"> 
</figure>

The scatter matrix reveals noticeable correlations between some variables. In particular revenues, number of votes, and ratings seem to be highly correlated and likely deliver the same information about the movie. On the other hand, the ROI stood out for being less consistently correlated with the other metrics. 

Since we have much more reliable and complete information about popularity, that we define as the logarithm of the number of votes, we will use this metric to determine a movie's success. Popularity reflects audience engagement and the reach of a film, making it a practical and robust measure for our analysis. Additionally, its strong correlations with revenue and budget reinforce its suitability as a central indicator of success.


#  A small detour: the Return on Investment (ROI)

Since ROI stood out for not being correlated with other metrics, we explore this aspect a bit further, before continuing with our analysis. In particular we examine the ROI in the context of budget size.

Dividing movies into low-budget and high-budget categories reveals key differences in term of ROI. To visualize this, we plotted the ROI against the budget using different colors to distinguish between high-budget and low-budget movies.

<br>
<div style="display: flex; justify-content: center; margin-top: -40px;">
    {% include plots/02_ROI_highvslow_budget.html %}
</div>

Low-budget films often achieve higher ROI percentages due to lower costs, while high-budget movies generate larger overall profits despite lower efficiency. This reflects the tradeoff: smaller productions focus on efficiency, while blockbusters rely on scale and heavy investments to maximize revenue.

<figure class="center">
  <img src="./assets/img/9e3ek0.jpg" alt = "ROI Meme" class = "center" width="500"> 
</figure>