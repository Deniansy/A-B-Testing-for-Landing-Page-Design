# A/B Testing for Landing Page Designs 🎨

Evaluating which landing page design — **Vibrant**, **Heat**, or **Cold** — drives the highest conversion rate for a bluetooth speaker e-commerce brand, and uncovering the customer behavior patterns behind it.

**Author:** [Deni Ansyah](https://www.linkedin.com/in/deni-ansyah) · [GitHub](https://github.com/Deniansy)

---

## 📋 Project Overview

Although the global bluetooth speaker market keeps growing, this company was struggling to convert visitors into sign-ups or purchases — out of 30,000 users, only **15.1%** converted.

This project runs an end-to-end A/B test across three landing page color themes to identify which one performs best, then dives deeper into demographic and behavioral factors (age, gender, marketing channel, traffic patterns) to turn the findings into actionable marketing recommendations.

## ❓ Business Questions

1. Which design is more effective in converting into sign-up or purchase, as well as improving customer engagement (duration and page views)?
2. Which channel contributes the most to the number of sessions and conversions?
3. When is the peak customer traffic on our website/app?
4. Which customer segments contribute the most to total sales and conversion rates?

## 🛠️ Tools Used

| Tool | Purpose |
|---|---|
| Google Colab (Python) | Data preprocessing, feature engineering, EDA, hypothesis testing |
| Power BI | Interactive dashboard & data visualization |
| Pandas, NumPy | Data manipulation |
| SciPy / Statsmodels | Statistical testing |

## 📊 Dataset Overview

Dataset downloaded from **[Kaggle](https://www.kaggle.com/datasets/sandeep1080/bassburst/data)** — website conversion data for bluetooth speaker sales, containing **30,000 user sessions** segmented by landing page variant, with user demographics, session engagement, purchase, and payment details.

| Column Name | Description |
|---|---|
| `user_id` | Unique identifier for each visitor |
| `session_id` | Unique identifier for each session or visit |
| `sign_in` | Indicates if the user logged in via email or used guest access |
| `name` | Name of the visitor (generated from multiple locales) |
| `demographic_age` | Age of the visitor (ranging from 14 to 80) |
| `demographic_age_group` | Age group of the visitor: "Teenage", "Adult", "Old" |
| `demographic_gender` | Gender of the visitor (Male, Female, Not Answered) |
| `email` | Email address of the user (if logged in via email) |
| `location` | The city where the visitor is located |
| `country` | Country corresponding to the location |
| `device_type` | Type of device used (Mobile, Desktop, Tablet) |
| `timestamp` | Session start time |
| `variant_group` | The landing page design variant the user saw (Vibrant, Cold, Heat) |
| `time_spent` | Total time (in minutes) the user spent on the landing page |
| `pages_visited` | Number of pages the user viewed during the session |
| `conversion_flag` | Binary flag (0/1) indicating whether the user converted (signed up or made a purchase) |
| `conversion_type` | Type of conversion achieved (Signup or Purchase) |
| `traffic_source` | Source of traffic (Organic, Paid, Social, Referral) |
| `product_purchased` | List of products purchased (if applicable) |
| `revenue` | Total revenue generated from the transaction (if purchase was made) |
| `payment_type` | Payment method used (Card or COD) |
| `card_type` | Card type if payment was made by card (Amex, Visa, Master) |
| `coupon_applied` | Whether a coupon was applied (Yes/No) |
| `bounce_flag` | Indicates if the session was a bounce (only one page visited) |

## 🧮 Statistical Approach

| Method | Purpose |
|---|---|
| Proportion Z-test (one-tailed, pairwise) | Compare the effects of landing page design on conversion rate; compare age group and gender on conversion rate; compare marketing channel on conversion rate and bounce rate |
| Kruskal-Wallis Test | Compare the effects of age group on average sales (non-normal distribution) |
| Mann-Whitney U Test | Compare the effects of gender on average sales (non-normal distribution) |
| Kolmogorov-Smirnov Test | Normality test prior to choosing parametric/non-parametric test |

Significance level (**alpha**) used across all tests: **5%**

## 📈 Key Results & Insights

### Landing Page Design vs Conversion Rate
| Variant | Conversion Rate |
|---|---|
| Vibrant | 12.13% |
| Heat | 15.17% |
| **Cold (winner)** | **18.08%** |

Cold significantly outperformed both Vibrant and Heat (p-value < alpha for all pairs). However, there was **no significant difference** in session duration or pages visited across the three designs.

### Age Group
- Adults (67.1% of users) had the **highest conversion rate** (15.50%).
- Teenagers (only 9% of users) generated the **highest average order value** ($32.49).
- Differences in conversion rate and average sales across age groups were **not statistically significant**.

### Gender
- Male and female users were split almost evenly (~45% each).
- Females had a slightly higher conversion rate (15.28% vs 14.82%).
- Males had a higher average sale value ($26.86 vs $25.45).
- Differences were **not statistically significant**.

### Marketing Channel
- Organic traffic dominated user acquisition (50.3% of sessions).
- **Paid channel** had the highest conversion rate (15.68%), significantly higher than **Social** (14.45%, p < 0.05).
- Referral traffic had the highest bounce rate (19.64%).

## ✍️ Recommendations

**Landing Page Design**
- Implement the **Cold** color theme as the default landing page design.
- Investigate other UI factors (button style, layout, font color) that could impact engagement (page views, session duration), and run a follow-up A/B test.

**Marketing Channel**
- Focus budget on Organic, Paid, and Referral channels instead of Social Media.
- Scale up the successful Paid channel campaign.
- Optimize SEO to strengthen the Organic channel.
- Re-evaluate Social Media targeting/creative to improve its conversion rate.

**Customer Demographics**
- Prioritize Adult customers, who make up the largest and best-converting segment.
- Increase Average Order Value (AOV) among Adults via product bundling and personalized recommendations based on purchase history.
- Encourage repeat purchases with a points/rewards program redeemable for discounts.
- Recommend high-margin products specifically to male customers, who show higher AOV.

## 🔗 Related Links

- 📄 [Presentation Slides (PDF)](https://drive.google.com/file/d/1uPpvwMSjwoAfHhOsuizigqRRgjM3KIX8/view?usp=sharing)
- 📊 [Full Power BI Dashboard] *(https://drive.google.com/file/d/1nJpKeB5ivlSNBOqkeDWYGcPFAiQL7BmA/view?usp=sharing)*
- 🔬 [Google Colab Notebook] *(https://colab.research.google.com/drive/1Ur6MR9FjstbnZhOIGmM6V2WKUajAjWpj?usp=sharing)*
