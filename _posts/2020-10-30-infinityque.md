---
img-grid:
  src: aws-logo.jpg
  alt: Amazon Web Services logo
img-header:
  src: infinityque-architecture.png
  alt: Architecture diagram of InfinityQue data pipeline
category: Data Warehouse
github-repo: jacobcallear/infinityque
website: https://infinityque0.wixsite.com/project
languages: Python, SQL, YAML
screenshots:
  - src: infinityque-plot.png
    alt: AWS QuickSight bar chart of the most popular drinks in October
    description: AWS QuickSight used to visualise data
  - src: infinityque-grafana.png
    alt: Screenshot of Grafana dashboard showing product metrics
    description: Grafana dashboard with AWS CloudWatch used to track metrics
summary:
  Cloud database application that extracts, cleans, and transforms cafe
  transaction data for analysis and visualisation. Python Lambda functions
  extract and transform the data before loading it into a RedShift data
  warehouse. AWS QuickSight is then used to visualise the data.
---

## Code Samples

The python code below loads cleaned transaction data into the data warehouse

```python
with conn.cursor() as cursor:
    psycopg2.extras.execute_values(cursor, """
        INSERT INTO transactions_g3 VALUES %s;
    """, [(
        transaction['unique_id'],
        transaction['date'],
        transaction['time'],
        transaction['location'],
        transaction['first_name'],
        transaction['total'],
        transaction['payment_method'],
        transaction['date_time']
    ) for transaction in transaction_list])
    conn.commit()
    logging.info('Transactions written to database')
```

The YAML extract below defines the AWS permissions for the extract Lambda

```yaml
iamRoleStatements:
  - Effect: 'Allow'
    Action:
      - sqs:SendMessage
      - sqs:GetQueueUrl
      - sqs:GetQueueAttributes
    Resource: !GetAtt Group3SQSExtracttoTransform.Arn
```

## Contributors

- Jacob Callear
- Shameela Begum
- Hamza Bashir
- Chenyse Semper
- Andrei Ilici
- Jaspreet "Jazz" Singh
- Jawad Khan
