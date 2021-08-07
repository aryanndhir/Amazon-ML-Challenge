
# Amazon ML Challenge 2021

Dataset: https://s3-ap-southeast-1.amazonaws.com/he-public-data/dataset52a7b21.zip

## Product Browse Node Classification

Amazon catalog consists of billions of products that belong to thousands of browse nodes (each browse node represents a collection of items for sale). Browse nodes are used to help customer navigate through our website and classify products to product type groups. Hence, it is important to predict the node assignment at the time of listing of the product or when the browse node information is absent.

As part of this hackathon, you will use product metadata to classify products into browse nodes. You will have access to product title, description, bullet points etc. and labels for ~3MM products to train and test your submissions. Note that there is some noise in the data - real world data looks like this!!

## Data Description

### Full Train/Test dataset details:

- Key column – PRODUCT_ID
- Input features – TITLE, DESCRIPTION, BULLET_POINTS, BRAND
- Target column – BROWSE_NODE_ID
- Train dataset size – 2,903,024
- Number of classes in Train – 9,919
- Overall Test dataset size – 110,775

### Important Note:

In case you are using pandas to read the csv train and test datasets, use escapechar = "\\" and quoting = csv.QUOTE_NONE options with read_csv to avoid errors during import.

### Evaluation Criteria

This contest uses Accuracy as the evaluation metric to measure submissions quality. Since this is a multiclass classification problem, we are interested in subset accuracy: the set of labels predicted for a sample must exactly match the corresponding set of ground truth labels.

### Submission File

For each PRODUCT_ID in the test data set, you are required to provide a browse node id prediction. The submission file should be a csv and contain a header followed by pairs of PRODUCT_ID, BROWSE_NODE_ID.

### Approach

1. Used Label Encoder to create Label column

2. Replaced all the null values with an empty string

3. Dropped Bullet Points, Brand and Description columns

4. Created a Bar Graph to see the correlation amongst all the features

5. Removed punctuations from the data

6. Used TfidVectorizer on the Title Column

7. Used Logistic Regression as the model

8. Finally got an accuracy of 53.95
