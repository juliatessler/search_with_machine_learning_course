# Lab notepad
*This is my personal notepad of things I tried and steps I took during the process. This is not my project assessment, but it will help me write it.*

## Level 1: Classifying Product Names to Categories
* To shuffle and split data, I used Python.

```
import pandas as pd

labeled_products = pd.read_table('/workspace/datasets/fasttext/shuffled_labeled_products.txt', header = None)

training_data = labeled_products.loc[0:9999]
training_data.to_csv('/workspace/datasets/fasttext/training_data.txt', header = None, index = None, sep = ' ', mode = 'a')

test_data = labeled_products.loc[10000:19999]
test_data.to_csv('/workspace/datasets/fasttext/test_data.txt', header = None, index = None, sep = ' ', mode = 'a')
```

* Without reading all the project instructions, I switched to full data and ran into issues, so I changed the learning rate of the models to be able to overcome those.

TODO: Process the name strings by implementing the transform_name() method in creatingContentTrainingData.py– as we saw in the tutorial, simple string manipulation, like a good analyzer, can make a big difference. You can implement the above transformations here, as well as  stemming (you can use the NLTK Snowball stemmer). Are you able to improve P@1?

