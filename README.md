# Gender-Classification
Gender Classification based on text from a products catalog

Input Data Analysis

The gender classes were initially 11. 
['girls', 'None', 'kids', 'womens', 'boys', 'baby girls', 'mens', 'plus size', 'unisex', 'baby & toddler', 'baby boys']

Since ‘plus size’ is technically not gender, the examples with gender ‘plus size’ were incorporated into the ‘womens class’. The class distribution over the dataset is given as follows:
Class	Number of samples in given dataset
‘girls’	112

‘None’	2877

‘kids’	46

‘womens’	1932

‘boys’	63

‘baby girls’	21

‘mens’	938

‘unisex’	3690

‘baby & toddler’	185

‘baby boys’	14


As can be seen the distribution is highly skewed. While ‘unisex’ has 3690 samples, ‘baby boys’ has only 14 samples. The low number of training samples for ‘kids’, ‘boys’, ‘baby girls’ and ‘baby boys’ is insufficient to generate a good feature model for those classes. Hence, these four classes are removed from the training dataset. Also, ‘None’ class was removed since these are missing values and essentially can be considered as unlabeled data.

Pre-Processing:

1.	Training samples with missing values in ‘description’, ‘title’ and ‘category’ were not removed because that would lead to drastic decrease in number of training samples. Not removing the missing values gave better results on test set than removing some or all of them.
2.	Punctuations, numbers, and stopwords were removed from all text.
3.	‘description’ and ‘title’ were concatenated into a single field ‘description + title’ and the ‘wordcount’ was calculated on this concatenated field.
4.	Further the word count features were trimmed to consider only words which occur more than once.

Choice of Algorithm:

Features: category, sub_category, sub_sub_category, wordcount

Logistic Classifier: Logistic Classifier has been used to develop the model for gender classification. Graphlab Create was used to develop the model and evaluate the results. However, the classifier needs regularization to prevent overfitting. This is the case because in case of text or language processing the number of features is very large as compared to the number of training samples. There are two regularization parameters: L1 and L2 regularization parameters which are set very high for accurate classification results. In graphlab_create, logistic classifier produced best results.

Interpretation of Result:

The results on ‘baby toddler’, ‘women’ and ‘unisex’ are the best owing to the fact that they occupy the largest percentage of the training dataset. The ‘girls’ class doesn’t give very good classification results because there were very few training samples to train on. Hence, the results on the large number of test examples labeled ‘girls’ was not very good because the feature space for the ‘girls’ class isn’t very strong.
