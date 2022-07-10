# Project Assessment

## 1. For query classification:
### a. How many unique categories did you see in your rolled up training data when you set the minimum number of queries per category to 1000? To 10000?
Originally, there were 1486 unique categories in the dataset.

**min queries = 1000:** 
* I don't know why it's so far apart from the expected ~400 categories. Is reviewers can give me some light on that, it would be great!

**min queries = 10000:** 


### b. What were the best values you achieved for R@1, R@3, and R@5? You should have tried at least a few different models, varying the minimum number of queries per category, as well as trying different fastText parameters or query normalization. Report at least 2 of your runs.

## 2. For integrating query classification with search:

### a. Give 2 or 3 examples of queries where you saw a dramatic positive change in the results because of filtering. Make sure to include the classifier output for those queries.

### b. Give 2 or 3 examples of queries where filtering hurt the results, either because the classifier was wrong or for some other reason. Again, include the classifier output for those queries.