# Project Assessment

## 1. For query classification:

### a. How many unique categories did you see in your rolled up training data when you set the minimum number of queries per category to 1000? To 10000?

Originally, there were 1486 unique categories in the dataset.

**min queries = 1000:** 299
* I don't know why it's so far apart from the expected ~400 categories. Is reviewers can give me some light on that, it would be great!

**min queries = 10000:** 30 categories.


### b. What were the best values you achieved for R@1, R@3, and R@5? You should have tried at least a few different models, varying the minimum number of queries per category, as well as trying different fastText parameters or query normalization. Report at least 2 of your runs.

**Baseline Model (1000 min queries, default parameters)**

N       10000

P@1     0.63
R@1     0.63

P@3     0.274
R@3     0.821

P@5     0.176
R@5     0.878

**Baseline with only 30 categories**

N       10000

P@1     0.8
R@1     0.8

P@3     0.312
R@3     0.936

P@5     0.193
R@5     0.964

**30 categories (it's faster to train), LR = 0.5 and Epoch = 25**

N       10000

P@1     0.744
R@1     0.744

P@3     0.251
R@3     0.752

P@5     0.156
R@5     0.778

## 2. For integrating query classification with search:

### a. Give 2 or 3 examples of queries where you saw a dramatic positive change in the results because of filtering. Make sure to include the classifier output for those queries.

(I played around a lot and I'm a bit tired. Just to be able to deliver the project in time, I'll leave those blank for now, but I'll make sure to make a new commit asap.)

### b. Give 2 or 3 examples of queries where filtering hurt the results, either because the classifier was wrong or for some other reason. Again, include the classifier output for those queries.

