# The Definition of Success

What makes a movie successful? Is it the glowing reviews from critics, the number of people who watch it, the box office revenue it generates, or how effectively it turns investment into profit? 

Success in the film industry isn’t one-dimensional; it’s a combination of factors that work together to create an impact. In this chapter, we focus on four key indicators of success: ratings, popularity, revenue, and the often-overlooked but crucial metric of Return on Investment (ROI). Together, these metrics provide a clearer picture of what makes a movie stand out and thrive in a competitive landscape.

Ratings are perhaps the most obvious measure of a film’s reception. High ratings reflect audience approval, suggesting that the movie delivered something memorable, whether it was an engaging story, strong acting, or stunning visuals. Conversely, low ratings indicate disappointment, but ratings alone don’t tell the full story. Many critically acclaimed films remain niche, while others with average ratings achieve massive commercial success.

Popularity adds another dimension to the analysis. The number of ratings a movie receives is a proxy for how many people have watched it and cared enough to leave feedback. A popular movie might not always earn rave reviews, but the fact that it attracts a large audience shows its cultural impact and broad appeal.

Revenue is a straightforward indicator of commercial success. A movie that generates significant box office earnings or streaming revenue reflects strong audience interest and effective marketing. However, revenue by itself doesn’t account for how much was spent to achieve those earnings. This is where Return on Investment (ROI) becomes critical.

ROI is a key metric for understanding the financial success of a movie. It’s calculated as the ratio of revenues to the budget and shows how effectively the film converted its investment into profit. For example, an ROI of 300% means the movie earned three times its production costs. ROI doesn’t just measure success in absolute terms—it highlights efficiency, showing which films created the most value relative to their cost. It’s especially important for filmmakers, producers, and investors who need to gauge the profitability of their projects.

That said, analyzing ROI comes with challenges. Data on revenues and budgets is often incomplete, which can make it difficult to calculate ROI for some movies. Despite these limitations, exploring the available data is still worthwhile because ROI offers such a valuable perspective on the relationship between investment and outcomes.

To better understand these three dimensions of success, we’ll take a closer look at their details. We will explore how ratings, popularity, revenue, and ROI are interconnected, looking for patterns or relationships that might offer deeper insights. Finally, we’ll address the challenge of filling in missing revenue data, ensuring that the analysis remains thorough and reliable.

By unpacking these metrics, we hope to better understand the dynamics of what makes a movie successful. Whether it’s a critically acclaimed masterpiece, a box office juggernaut, or a cultural phenomenon watched by millions, each metric contributes to the bigger picture of cinematic success.


# Data Preparation

The first step in our analysis was to transform the variables into their logarithmic forms. This was necessary because, when plotted, their distributions were highly skewed, making it difficult to draw meaningful insights.

Once transformed, we performed several tests and discovered a correlation of 0.67 between the number of votes and revenues. This indicates a significant linear relationship between these two variables and suggests a potential solution to the problem of missing revenue values in our dataset. The strong correlation implies that as the number of ratings increases, the revenue of a movie tends to rise proportionally.

This finding aligns with intuition: the more ratings a movie receives, the greater its audience engagement and viewership, which directly contribute to its box office or streaming earnings. By analyzing these variables in their logarithmic forms, this relationship becomes even clearer and more mathematically robust, further supporting the validity of this approach.

Given this correlation, we propose using a linear regression model with the number of ratings as the predictor variable to estimate missing revenue values. This approach capitalizes on the strong relationship between the two variables, enabling us to recover incomplete data. By filling in the gaps in revenue data, we can ensure a more comprehensive and accurate analysis of the factors driving a movie’s financial and overall success.


#  The Analysis

To better understand the relationships between the factors we’re analyzing—number of votes, revenues, ROI, and budget—the first step was to create a scatter matrix. This gave us a visual overview of how these variables interact with each other. The scatter matrix revealed noticeable correlations between some variables, particularly revenues, number of votes, and budget. However, ROI stood out as being less consistently correlated with the others. To investigate further, we ran Pearson correlation tests to quantify these relationships and confirm their statistical significance.

Here’s what we found:

- Number of votes and revenues: There was a strong positive linear relationship, with a Pearson correlation value of 0.67 and a p-value of 0.00. This result confirms that movies with more ratings tend to generate higher revenues, which makes sense—more ratings likely reflect higher viewership and engagement.

- Number of votes and ROI: The relationship was weaker but still statistically significant, with a Pearson correlation value of 0.32 and a p-value of 0.00. This suggests that while popular movies may achieve higher ROI in some cases, the connection isn’t as strong as it is with revenue.

- Revenues and ROI: There was a moderate to strong positive relationship, with a Pearson correlation value of 0.62 and a p-value of 0.00. This indicates that higher revenues are often associated with better ROI, though the relationship isn’t absolute.

- Revenues and budget: As expected, these two variables had a strong positive correlation, with a Pearson correlation value of 0.67 and a p-value of 0.00. Higher budgets tend to lead to higher revenues, reflecting the advantages of larger-scale productions.

- ROI and budget: Interestingly, this relationship was weak but negative, with a Pearson correlation value of -0.17 and a p-value of 0.00. This means that lower-budget films often achieve higher ROI percentages, likely because the initial investment is smaller.

- Number of votes and budget: There was a strong positive correlation here as well, with a Pearson correlation value of 0.62 and a p-value of 0.00, suggesting that higher-budget movies attract more viewers and thus receive more ratings.

##### MAYBE WE CAN DISPLAY THE CORRELATION RESULTS WITHIN A TABLE

# What The Results Tell Us
The analysis confirms some key intuitions. For example, the strong link between votes and revenues suggests that popularity plays a major role in a movie’s financial success. ROI, however, stands out as a different kind of metric. Its weaker correlations with votes and revenues reflect the fact that it’s more about efficiency than scale—it measures how much value was created relative to the budget, rather than how much money was made overall.

The negative correlation between ROI and budget is especially interesting. Smaller-budget films often achieve higher ROI percentages because they require less money to turn a profit. However, this doesn’t mean these films are more lucrative overall. High-budget movies, while less efficient in terms of ROI, tend to generate far larger absolute revenues and profits. This creates an intriguing dynamic: smaller films succeed by being efficient, while bigger productions succeed through scale.

# Focusing on Popularity

Since we have much more reliable and complete information about popularity, measured as the logarithm of the number of votes, we will prioritize this metric to determine a movie's success. Popularity reflects audience engagement and the reach of a film, making it a practical and robust measure for our analysis. Additionally, its strong correlations with revenue and budget reinforce its suitability as a central indicator of success.


#  Closer Look at ROI and Budget
To explore the ROI further, it may be helpful to divide movies into two groups: low-budget and high-budget. By analyzing these categories separately, we can better understand how ROI behaves in each group. Initial findings suggest that low-budget films tend to achieve disproportionately high ROI percentages, while high-budget movies deliver larger profits overall but with lower efficiency. This makes sense—smaller productions have less at stake and fewer costs to recoup, while blockbuster films invest heavily in scale and marketing to drive massive revenues.

This division also raises interesting questions about production strategies and audience expectations. For instance, do certain genres perform better within specific budget ranges? Are there patterns in the types of films that succeed at different scales? Exploring these questions could reveal valuable insights into the complex interplay between budgets, revenues, and ROI.

By examining these dynamics in more detail, we can start to build a clearer picture of what drives success for movies of different types and sizes. This layered approach will help us better understand the broader patterns behind a movie’s financial and overall performance.

#### DISPLAY THE INTERACTIVE GRAPH HERE



