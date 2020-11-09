---
img-grid:
  src: aws-logo.jpg
  alt: Amazon Web Services logo
img-header:
  src: infinityque.png
  alt: Architecture diagram of InfinityQue data pipeline
category: Data Warehouse
github-repo: jacobcallear/infinityque
website: https://infinityque0.wixsite.com/project
languages: Python, SQL, YAML
screenshots:
  - src: infinityque-plot.png
    alt: AWS QuickSight bar chart of the most popular drinks in October
    description: AWS QuickSight used to visualise data 
summary:
  Cloud database application that extracts, cleans, and transforms cafe
  transaction data for analysis and visualisation. Python Lambda functions
  extract and transform the data before loading it into a RedShift data
  warehouse. AWS QuickSight is then used to visualise the data.
---

### Architecture

<br>

<img class="img-responsive img-centered" src="/img/infinityque-architecture.png"
     alt="Flowchart of data pipeline architecture">
