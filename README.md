# Bellabeat Case Study

**Objective**: Analyze smart device usage (Fitbit data) to generate actionable marketing recommendations for Bellabeat’s Leaf product.

**Tools**:  
- R (`dplyr`, `ggplot2`, `kableExtra`, `lubridate`, `readr`)  
- Python (`pandas`, `sqlalchemy`, `psycopg2`)  
- SQL (PostgreSQL via pgAdmin4)  
- R Markdown, PowerPoint

**Approach**:
- Cleaned and transformed over 1 million data rows using PostgreSQL and Python scripts.
- Explored daily activity, heart rate, and sleep behaviors using R.
- Visualized key user patterns with `ggplot2` and summarized insights in a professional report and presentation.

**Key Insights**:
- Most users average fewer than 10,000 steps daily.
- Sleep duration is below the 8-hour recommendation and efficiency varies widely.
- Heart rate peaks in the morning, suggesting ideal moments for wellness nudges.
- Users can be segmented into three tiers (sedentary, moderate, active) for targeted marketing.

**Files**:
- [`R Markdown`](Bellabeat_Case_Study_Insights.Rmd): Full case study code and analysis.
- [`PDF`](Bellabeat_Case_Study_Insights.pdf): Knitted report for stakeholders.
- [`Presentation`](Bellabeat_Case_Study_Insights.pptx): Executive presentation.

**How to View**:  
- Open `.Rmd` in RStudio to explore the code.  
- Read the PDF or view the PowerPoint for summarized insights.

## Key Code Example
```r
daily_activity %>%
  group_by(Id) %>%
  summarise(avg_steps = mean(TotalSteps)) %>%
  ggplot(aes(x = avg_steps)) +
  geom_histogram(bins = 30, fill = "darkgreen", color = "black", alpha = 0.75) +
  geom_vline(xintercept = 10000, color = "red", linetype = "dashed") +
  annotate("text", x = 10250, y = 3.5, label = "Recommended 10,000 Steps", color = "red", size = 3.5, hjust = 0) +
  labs(title = "Distribution of Average Daily Steps per User", x = "Average Steps", y = "Count of Users") +
  theme_minimal()
```

## Key Visualization
![Average Daily Steps](avg_daily_steps.jpeg)
