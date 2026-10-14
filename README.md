# E-commerce Operations Analysis

**Exploring the factors associated with low customer ratings in Brazilian e-commerce**

## About the Project

A customer may leave a low rating because an order arrived late, the product did not meet their expectations, or the overall shopping experience was disappointing. But which of these factors are actually associated with lower ratings, and are some sellers or product categories more affected than others?

This project uses the Olist Brazilian E-Commerce dataset to investigate these questions. The analysis looks at customer reviews alongside order, delivery, product, payment, and seller data to understand where low ratings are more common.

The goal is to go beyond average review scores and find patterns that could help an e-commerce business understand its customers better and decide which parts of the shopping experience need closer attention.

**Project status:** In progress

## What I'm Investigating

### 1. Delivery and Customer Satisfaction

- Do orders delivered late receive lower ratings than orders delivered on time?
- Does the length of a delivery delay matter?
- Are some Brazilian states more affected by late deliveries and low ratings?
- Do sellers with more delivery delays also tend to receive lower ratings?

These questions can help identify whether delivery performance deserves attention when investigating customer dissatisfaction.

### 2. Products, Prices, and Payments

- Do product prices or freight costs differ between orders with high and low ratings?
- Which product categories receive low ratings more often?
- Is the amount of information provided on a product page, such as description length and number of photos, related to customer ratings?
- Do ratings differ between customers who pay in one installment and those who use installment payments?

The aim is to find out whether certain products, costs, or purchasing conditions are worth investigating more closely.

### 3. Seller Performance

- Which sellers have higher rates of low ratings?
- Do high-volume sellers have different rating patterns from sellers with fewer orders?
- Is there a relationship between a seller's delivery performance and customer ratings?

Seller comparisons need to account for the number of reviews available. A seller with only a handful of reviews should not automatically be considered worse than one with hundreds of reviews based on a small difference in their ratings.

### 4. Customer Behavior and Review Comments

- Do repeat customers rate their orders differently from customers who order only once?
- Are some customers consistently dissatisfied across multiple orders?
- What do customers mention most often in negative reviews?
- Which aspects of the shopping experience appear most often in positive reviews?

Review comments may help explain patterns that are not obvious from numerical ratings alone.

## How I'm Approaching the Analysis

### Data Audit

Before calculating any metrics, I am examining the structure and quality of the available tables. This includes checking missing values, duplicate records, key uniqueness, and possible inconsistencies in review data.

This step matters because joining tables incorrectly or counting the same review more than once can change the results of an analysis.

### Data Preparation

The dataset contains separate tables for customers, orders, order items, products, payments, sellers, and reviews. These tables need to be connected according to the question being investigated.

I will pay particular attention to table granularity and join keys, especially when an order contains multiple items or when review records are ambiguous. The aim is to keep the calculations consistent and avoid introducing duplicate records during joins.

### Metrics and Comparisons

The main metrics planned for the analysis include:

| Metric | What it measures |
|---|---|
| Average Review Score | Average customer rating |
| Low-Rating Rate | Share of reviews with a score of 1 or 2 |
| Late-Delivery Rate | Share of eligible delivered orders that arrived after the estimated delivery date |
| Delivery Delay (Days) | Difference between the actual and estimated delivery dates |
| Review Count | Number of reviews behind a comparison |
| Average Price and Freight Value | Typical item prices and freight costs |
| Orders per Customer | Number of orders placed by a customer |
| Seller-Level Metrics | Ratings and delivery performance by seller |

A score of 1 or 2 is the initial definition of a low rating for this project.

Depending on the question, I will compare groups, examine distributions, and look for differences across states, product categories, sellers, and customer segments. Comparisons will also account for sample size where necessary.

### From Findings to Recommendations

Once the analysis is complete, I will use the results to identify the patterns that matter most from a business perspective.

For example, if late deliveries are associated with lower ratings, the next question is whether the problem is concentrated in particular regions or sellers. If some product categories receive more low ratings, their review counts and product characteristics need to be examined before suggesting changes.

The recommendations will depend on the results. I will distinguish between patterns observed in the data and explanations that would require further investigation.

## Tools

- Python
- Pandas
- NumPy
- Jupyter Notebook
- Matplotlib and Seaborn for visualization

## Dataset

The project uses the [Brazilian E-Commerce Public Dataset by Olist on Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).

It contains information about orders, customers, sellers, products, payments, deliveries, and customer reviews from a Brazilian e-commerce marketplace.

The dataset makes it possible to examine different parts of the shopping experience together rather than looking at customer ratings in isolation.

## Repository Structure

```text
ecommerce-operations-analysis/
├── notebooks/
│   └── 01-data-audit.ipynb
└── README.md
```

The repository structure will be updated as more analysis notebooks are added.

## Current Progress

The project is currently focused on data quality and preparation. I have outlined the main business questions and the metrics needed to investigate them.

The next steps are to finish checking the data, prepare the tables required for each analysis, and begin comparing customer ratings across delivery, product, seller, and customer-related factors.

The findings and recommendations will be added once the analyses have been completed.

## Notes on Interpretation

This analysis looks for relationships between variables; it cannot establish causation on its own. Other factors may influence customer ratings, and comparisons based on small numbers of reviews can be misleading.

These limitations will be considered when interpreting the results.
