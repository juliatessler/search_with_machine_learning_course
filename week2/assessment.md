# Assessment
You can find the notebook with most of the results in `playground.ipynb`

## 1. For classifying product names to categories:
### a. What precision (P@1) were you able to achieve?
97.33% on pruned dataset.

### b. What fastText parameters did you use?

```
model = fasttext.train_supervised(input = '/workspace/datasets/fasttext/pruned_training_data.txt', 
                                  lr = 1, 
                                  epoch = 25)
```

### c. How did you transform the product names?
As suggested per the project instructions, 
* Remove all non-alphanumeric characters other than underscore (which we need for the labels!).
* Convert all letters to lowercase.

* Trim excess space characters so that tokens are separated by a single space.

### d. How did you prune infrequent category labels, and how did that affect your precision?
With the following functions:
```
def create_pruned_labeled_products(df, min_products = 500):
    labels = []
    pruned_labeled_products = []
    count_products = 0

    print('Mapping labels')
    for row in range(0, len(df)):
        label = df[0][row].split()[0]
        labels.append(label)
        # product = df[0][row].split()[:1]
    
    labels = pd.Series(labels)
    label_counts = labels.value_counts()
    keep_labels = label_counts[label_counts >= min_products].index.tolist()

    print('Found labels to keep!')

    for row in range(0, len(df)):
        if labels[row] in keep_labels:
            pruned_labeled_products.append(df[0][row])
        else:
            pass
    
    pruned_labeled_products = pd.DataFrame(pruned_labeled_products)
    pruned_labeled_products.to_csv('/workspace/datasets/fasttext/pruned_labeled_products.txt', header = None, index = None, mode = 'a')
    print('Saved pruned_labeled_products.txt')

    return pruned_labeled_products
```

It increased P@1 from 62.1% to 97.3%.

### e. How did you prune the category tree, and how did that affect your precision?
I didn't! :scream: Didn't realized this was a step described in the project instructions. Will do it soon.

## 2. For deriving synonyms from content:

### a. What were the results for your best model in the tokens used for evaluation?
Very similar to the model description.

### b. What fastText parameters did you use?
```
model = fasttext.train_unsupervised(model = 'skipgram',
                                    input = '/workspace/datasets/fasttext/normalized_titles.txt',
                                    epoch = 25,
                                    minCount = 20)
```

### c. How did you transform the product names?
Applied the same transformation as suggested before.

## 3. For integrating synonyms with search:

### a. How did you transform the product names (if different than previously)?
The same as previously.

### b. What threshold score did you use?
75%

### c. Were you able to find the additional results by matching synonyms?

## 4. For classifying reviews:
I didn't get to level 4, unfortunately :/

### a. What precision (P@1) were you able to achieve?

### b. What fastText parameters did you use?

### c. How did you transform the review content?

### d. What else did you try and learn?

