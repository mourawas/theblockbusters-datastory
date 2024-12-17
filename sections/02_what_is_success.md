# The Definition of Success

What makes a movie successful? Is it the glowing reviews from critics, the number of people who watch it, the box office revenue it generates, or how effectively it turns investment into profit? 

Success in the film industry isn’t one-dimensional; it’s a combination of factors that work together to create an impact. In this chapter, we focus on five key indicators of success: ratings, popularity, revenue, budget, and the often-overlooked but crucial metric of Return on Investment (ROI). Together, these metrics provide a clearer picture of what makes a movie stand out and thrive in a competitive landscape.

<ul>
  <li><b>Ratings:</b> High ratings reflect audience approval, showcasing engaging stories, strong performances, or stunning visuals. However, ratings alone don’t tell the full story—some critically acclaimed films remain niche, while others with average scores achieve massive success.</li>
  <li><b>Popularity:</b> Measured by the number of ratings, popularity indicates how many people watched the movie and cared enough to respond. Even if a film doesn’t earn top reviews, attracting a large audience highlights its broad appeal and cultural impact.</li>
  <li><b>Revenue:</b> Whether from box office earnings or streaming platforms, is a clear measure of commercial success. However, revenue doesn’t account for production costs, which is where ROI comes in.</li>
  <li><b>Budget:</b> The total cost required to produce a movie, including expenses for cast, crew, sets, effects, and marketing</li>
  <li><b>ROI:</b> Measures how efficiently a movie turns its budget into profit. For example, an ROI of 300% means the film earned three times its cost. While ROI data can be incomplete, it remains essential for assessing financial success.</li>
</ul>

By unpacking these metrics, we hope to better understand the dynamics of what makes a movie successful. Whether it’s a critically acclaimed masterpiece, a box office juggernaut, or a cultural phenomenon watched by millions, each metric contributes to the bigger picture of cinematic success.

Initially, we plotted the variables to examine their distributions:

<figure class="center">
  <img src="./assets/img/density_subplots.png" alt = "Illustration of Kircher's Stenographic mirror" class = "center" width="1000"> 
</figure>

As shown, the distributions for Revenue, ROI, Budget, and Number of Votes were skewed. To address this, we applied a logarithmic transformation. The resulting distributions are as follows:

<figure class="center">
  <img src="./assets/img/log_transformed_density_subplots.png" alt = "Illustration of Kircher's Stenographic mirror" class = "center" width="1000"> 
</figure>

To understand further the relationships between the factors we’re analyzing, the first step was to create a scatter matrix. This gave us a visual overview of how these variables interact with each other. 


#### DISPLAY GG-PAIRS HERE (Francesco)

The scatter matrix revealed noticeable correlations between some variables, particularly revenues, number of votes, budget and ratings. However, ROI stood out as being less consistently correlated with the others. 

Since we have much more reliable and complete information about popularity, measured as the logarithm of the number of votes, we will prioritize this metric to determine a movie's success. Popularity reflects audience engagement and the reach of a film, making it a practical and robust measure for our analysis. Additionally, its strong correlations with revenue and budget reinforce its suitability as a central indicator of success.


#  The Return on Investment (ROI)

ROI stood out as less consistently correlated with other metrics, to explore this further, it makes sense to examine ROI in the context of budget size.

Dividing movies into low-budget and high-budget categories reveals key differences in ROI. To visualize this, we plotted ROI using different colors to distinguish between high-budget and low-budget movies:

<br>
<div style="display: flex; justify-content: center; margin-top: -40px;">
    {% include plots/03_ROI_highvslow_bidget.html %}
</div>

Low-budget films often achieve higher ROI percentages due to lower costs and risks, while high-budget movies generate larger overall profits despite lower efficiency. This reflects the tradeoff: smaller productions focus on efficiency, while blockbusters rely on scale and heavy investments to maximize revenue.

This division also raises interesting questions about production strategies and audience expectations. For instance, do certain genres perform better within specific budget ranges? Are there patterns in the types of films that succeed at different scales? Exploring these questions could reveal valuable insights into the complex interplay between budgets, revenues, and ROI.

<figure class="center">
  <img src="./assets/img/roi_meme.png" alt = "ROI Meme" class = "center" width="500"> 
</figure>