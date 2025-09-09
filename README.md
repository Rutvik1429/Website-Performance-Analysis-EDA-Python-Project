# Website-Performance-Analysis-EDA-Python-Project
This project focuses on analyzing website performance data to uncover key insights through Exploratory Data Analysis (EDA). Using Python libraries such as NumPy, Pandas, Matplotlib, and Seaborn, the project demonstrates how to clean, process, and visualize data for better decision-making.
## ✅ Objective
The main goal of this project is to analyze and understand the performance of a website using Python. By leveraging key libraries like numpy, pandas, matplotlib, and seaborn, this analysis aims to explore user behavior, traffic patterns, and overall website efficiency. Through Exploratory Data Analysis (EDA), the project identifies trends, patterns, and anomalies to provide actionable insights that can improve user experience and optimize website functionality.

## 📂 Tools and Libraries Used
- **Numpy** – For numerical operations and handling large datasets efficiently.
- **Pandas** – For data manipulation, cleaning, and transformation.
- **Matplotlib** – For creating visualizations such as line charts, bar graphs, and histograms.
- **Seaborn** – For advanced statistical visualizations that highlight relationships between variables.
- **Exploratory Data Analysis (EDA)** – To uncover hidden patterns, understand distributions, and derive meaningful conclusions from raw data.

# Some Analysis
## What patterns or trends can you observe in website sessions and users over time.
```python
# Set figure size (width=10, height=5)
plt.figure(figsize=(10,5))

# Group data by DateHour and sum Sessions & Users, then plot on the same axis
df.groupby("DateHour")[["Sessions","Users"]].sum().plot(ax=plt.gca())

# Add title and axis labels
plt.title("Sessions & Used Over Time")
plt.xlabel("DateHour")
plt.ylabel("Count")

# Save the figure as PNG with very high resolution (2000 dpi)
plt.savefig("sessions and used over time.png", dpi=2000, bbox_inches="tight")

# Display the plot
plt.show()
```
![Sessions and used over time](https://github.com/Rutvik1429/Website-Performance-Analysis-EDA-Python-Project/blob/main/Visual%20plot/Sessions_And_Used_Over_Time.png)
### Insights for This visual
- **Daily Trend:** Both sessions and users show strong daily cycles, with high activity during peak hours and significant drops during late nights/early mornings.
- **Sessions > Users:** The sessions line is consistently above the users line, meaning users often initiate multiple sessions per day.
- **Traffic Spikes:** There are noticeable traffic surges (e.g., around mid-month), which could be linked to campaigns, promotions, or seasonal effects.
- **Consistency:** Despite fluctuations, the overall traffic pattern remains stable, showing steady engagement across the month.
- **User Engagement:** Since the gap between sessions and users is relatively constant, it suggests stable user behavior (returning users engaging multiple times).

## Which marketing channel brought the highest number of users to the website,and how can we use this insight to improve traffic from other sources?
```python
# Set figure size (width=5, height=4)
plt.figure(figsize=(5, 4))

# Create barplot showing total Users by channel group
# - data=df → using dataset df
# - x="channel group" → categories on x-axis
# - y="Users" → values on y-axis
# - estimator=np.sum → sum all Users for each channel
# - palette="viridis" → color style
sns.barplot(data=df, x="channel group", y="Users", estimator=np.sum, palette="viridis")

# Add title to the chart
plt.title("Total User By Channel")

# Rotate x-axis labels for better readability
plt.xticks(rotation=45)

# Save plot as a high-resolution PNG file
plt.savefig("total_user_by_channel.png", dpi=2000, bbox_inches="tight")

# Display the plot
plt.show()
```
![total user by channel](https://github.com/Rutvik1429/Website-Performance-Analysis-EDA-Python-Project/blob/main/Visual%20plot/Total_User_By_Channel.png)
### Insights for This visual
- Highest Channel: The chart shows that Organic Social brought the highest number of users (nearly 48,000).
- Other Strong Channels: Direct traffic (~30,000 users), Organic Search (~28,000 users), and Referral (~27,000 users) are also major contributors.
- Low Performing Channels: Email, Organic Video, and Unassigned channels contribute very little traffic compared to the top sources.
### How to impact This insight
**Leverage Strength of Organic Social**
Since Organic Social drives the highest traffic, continue investing in social media campaigns, influencer partnerships, and consistent posting to maintain and grow this channel.
**Boost Underperforming Channels**
Explore targeted email campaigns (personalized offers, newsletters) to improve the Email channel.
Enhance video marketing strategies (YouTube SEO, short-form videos, reels) to increase Organic Video performance.
**Optimize Search & Referral**
Strengthen SEO strategies (keyword optimization, content updates) to improve Organic Search further.
Build more partnerships & backlinks to grow Referral traffic.
**Diversify Traffic Sources**
Don’t rely too heavily on one channel. By improving lower-performing channels, you reduce risk and create a balanced acquisition strategy.
