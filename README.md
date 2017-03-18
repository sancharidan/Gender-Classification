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
