# Consumer360 — RFM Customer Segmentation

A retail analytics project I built to solve a real business problem — a company was treating all customers the same way. A person who spent £5000 was getting the same email as someone who spent £10. That makes 
no sense from a business perspective, so I built this.


## The Problem

Most e-commerce businesses blast the same marketing campaign to their entire customer base. This is inefficient and expensive. Some customers need to be rewarded, some need to be retained before they leave, and 
some are already gone. Without data, you cannot tell who is who.


## What I Built

A pipeline that takes raw transaction data, cleans it, scores every customer, puts them into meaningful groups, and displays everything in a dashboard that anyone in the business can understand and act on.


## How the Analysis Works

I used a technique called RFM scoring. Every customer gets three scores:

- Recency — when did they last buy something?
- Frequency — how many times have they bought?
- Monetary — how much have they spent in total?

Each score runs from 1 to 5. A customer scoring 5 on all three is your best customer. A customer scoring 1 on all three has probably already moved on.

Based on these scores every customer lands in one of six groups:

- Champion — buying recently, buying often, spending the most
- Loyal Customer — consistent buyers, just not the biggest spenders
- Recent User — just joined, need to be nurtured
- At Risk — used to buy regularly but have gone quiet
- Needs Attention — somewhere in the middle, could go either way
- Lost — have not bought in a long time, low frequency and spend


## What the Dashboard Shows

- How customers are distributed across all six segments
- Which countries are generating the most revenue
- A scatter plot of all customers plotted by their RFM scores
- Product combinations — what people tend to buy together

The scatter plot is the most useful visual. Champions cluster in one corner, lost customers in the opposite corner. You can immediately see where your customer base is concentrated.


## Market Basket Analysis

On top of the segmentation I ran association rule mining on the transaction data. This finds non-obvious patterns like customers who buy one specific product almost always buy another specific product 
in the same order. Useful for product placement and recommendations.


## Tech Used

- Python and Pandas for all the data work
- mlxtend for the market basket analysis
- Power BI for the dashboard
- Windows Task Scheduler to run the whole thing automatically every week


## Files

- rfm_analysis.ipynb — all the code, step by step with comments
- rfm_output.csv — the final segmented customer list
- basket_rules.csv — the product association rules
- Consumer360.pbix — the Power BI dashboard


## Dataset

The raw data file is too large to upload here. You can download it 
free from Kaggle:

https://www.kaggle.com/datasets/mashlyn/online-retail-ii-uci

Once downloaded, place it in the same folder as the notebook and 
run the cells in order.


## Results

- 500,000+ transactions processed and cleaned
- 5,878 customers scored and segmented
- Champion and At Risk customers clearly identified
- Product buying patterns discovered
- Entire pipeline automated to refresh every Sunday
