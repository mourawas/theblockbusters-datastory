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

Initially, we plotted the variables to examine their distributions:

<figure class="center">
  <img src="./assets/img/density_subplots.png" alt = "Illustration of Kircher's Stenographic mirror" class = "center" width="300"> 
   <figcaption>
    Caption.
   </figcaption>
</figure>

<img src="" alt="Skewed Distributions">

As shown, the distributions for Revenue, ROI, Budget, and Number of Votes were skewed. To address this, we applied a logarithmic transformation. The resulting distributions are as follows:

<img src="_includes/images/log_transformed_density_subplots.png" alt="Normal Distributions">

To better understand the relationships between the factors we’re analyzing—number of votes, revenues, ROI, and budget—the first step was to create a scatter matrix. This gave us a visual overview of how these variables interact with each other. The scatter matrix revealed noticeable correlations between some variables, particularly revenues, number of votes, and budget. However, ROI stood out as being less consistently correlated with the others. To investigate further, we ran Pearson correlation tests to quantify these relationships and confirm their statistical significance.

Here’s what we found:

<div style="display: flex; justify-content: center; margin-top: -40px;">
    {% include plots/02_gg_pairs_plot.html %}
</div>

The analysis confirms some key intuitions. For example, the strong link between votes and revenues suggests that popularity plays a major role in a movie’s financial success. ROI, however, stands out as a different kind of metric. Its weaker correlations with votes and revenues reflect the fact that it’s more about efficiency than scale—it measures how much value was created relative to the budget, rather than how much money was made overall.

The negative correlation between ROI and budget is especially interesting. Smaller-budget films often achieve higher ROI percentages because they require less money to turn a profit. However, this doesn’t mean these films are more lucrative overall. High-budget movies, while less efficient in terms of ROI, tend to generate far larger absolute revenues and profits. This creates an intriguing dynamic: smaller films succeed by being efficient, while bigger productions succeed through scale.

Since we have much more reliable and complete information about popularity, measured as the logarithm of the number of votes, we will prioritize this metric to determine a movie's success. Popularity reflects audience engagement and the reach of a film, making it a practical and robust measure for our analysis. Additionally, its strong correlations with revenue and budget reinforce its suitability as a central indicator of success.


#  Closer Look at ROI and Budget
To explore the ROI further, it may be helpful to divide movies into two groups: low-budget and high-budget. By analyzing these categories separately, we can better understand how ROI behaves in each group. Initial findings suggest that low-budget films tend to achieve disproportionately high ROI percentages, while high-budget movies deliver larger profits overall but with lower efficiency. This makes sense—smaller productions have less at stake and fewer costs to recoup, while blockbuster films invest heavily in scale and marketing to drive massive revenues.

This division also raises interesting questions about production strategies and audience expectations. For instance, do certain genres perform better within specific budget ranges? Are there patterns in the types of films that succeed at different scales? Exploring these questions could reveal valuable insights into the complex interplay between budgets, revenues, and ROI.

By examining these dynamics in more detail, we can start to build a clearer picture of what drives success for movies of different types and sizes. This layered approach will help us better understand the broader patterns behind a movie’s financial and overall performance.

#### DISPLAY THE INTERACTIVE GRAPH HERE


--------------------------------------------------------------------------------------------------------------
#### UNDERSTAND WHERE TO INCLUDE:

Once transformed, we discovered a correlation of 0.67 between the number of votes and revenues. This indicates a significant linear relationship between these two variables and suggests a potential solution to the problem of missing revenue values in our dataset. The strong correlation implies that as the number of ratings increases, the revenue of a movie tends to rise proportionally.

PLOT SCATTER PLOT (+ REGRESSION LINE)

This finding aligns with intuition: the more ratings a movie receives, the greater its audience engagement and viewership, which directly contribute to its box office or streaming earnings. By analyzing these variables in their logarithmic forms, this relationship becomes even clearer and more mathematically robust, further supporting the validity of this approach.

Given this correlation, at first, we thought about using a linear regression model with the number of ratings as the predictor variable to estimate missing revenue values. This approach capitalizes on the strong relationship between the two variables, enabling us to recover incomplete data. By filling in the gaps in revenue data, we can ensure a more comprehensive and accurate analysis of the factors driving a movie’s financial and overall success. However, as the analysis shows, the forecast of the revenues is not necessary.
-------------------------------------------------------------------------------------------------------------------