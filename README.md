# Craniometrics

## Classification of Crusade-era skulls using W.W Howell's Craniometric Data Set


It has long been accepted that certain bones in the skull are more or less prominent in different populations. Skull features are the result of both the evolution of populations to their environments and sexual selection. Craniometrics is the classification of skulls to a particular population based on the measurements of many different skull features.
W. W. Howell published three monographs on the data: Cranial Variation in Man (1973), Skull Shapes and the Map (1989), and Who's Who in Skulls (1995). This data is currently under the supervision of Dr. Benjamin Auerbach of the University of Tennessee--Knoxville.

### Procedure
These skulls will be the test sample for the model. Then, the machine learning model will be given thirteen skulls from the Caesarea Maritima archaeological site. The skulls are documented as likely either Frankish Crusader or Ayyubid Muslim. Burial types were noted in the archaeological reports. Skulls were reassembled and measured by Shannon McChesney (myself) in 2007.

The data is cleaned and preprocessed with null values being replaced.

Next, the training skulls were used to determine K for KNN. Unfortunately, this left us with an F1-score of just 68%. 

#### Classification with a Decision Tree
A decision tree was then created and important features plotted. The graph of important features determined that XCB (maximal cranial breadth) and RFA (radiofrontal angle) were the most important features in classifying each skull. The accuracy of this classifier was 96%.

#### Classification with Random Forest (and GridSearch)
Due to the large number of features, a random forest model was used as the next classification model. The random forest model proved less successfully than the decision tree model, until GridSearch was implemented. Accuracy with GridSearch and Random Forest increased to 99%. XCB (maximal cranial breadth) remain the most important feature in classification.

#### Classifying the Caesarea Maritima Skulls
Unfortunately, the skulls from the Caesarea Maritima were not measured as thoroughly as the Howells Dataset. Many features were  missing including the most important feature measurement, XCB. This greatly hindered our classification. Even after GridSearch was added to the random forest classification of our skulls, we were only able to achieve 87% accuracy. The two most prominent measurements included were AUB (biauricular breadth) and BNL (cranial base length).

### Results
By ridding ourselves of irrelevant groups, the classification of certain skulls are more easily accomplished. However, the only way we were able to achieve high accuracy rates for our models was to overfit them. This is in part due to the overlap in similarity between groups of peoples.

With the exception of highly isolated groups, there is far too much heterogeny due to human migration in the individual groups for the computer to accurately classify new samples. While this is a nuisance for our intended purpose, it shows two beneficial points: first, that there is very little difference between human beings around the world, and second, our ability to extrapolate that there is still enough biological variation within our species to prevent extreme bottle-necking (when the gene pool grows too similar to produce a healthy genetic line).

### Further Research
- Comparison against known Frankish and Abbuyyid skulls
- Addition of larger samples of each of the known groups to fine-tune training data
- Further measures taken (where possible) on test data
- Combine craniometric data with genomic data to reinforce phenotypic statistics

These suggestions and more will not only serve to help classify archaeological remains, but also help to identify victims of mass tragedies (natural disasters, terrorist attacks, etc.). ForDisc, created by the University of Tennesee--Knoxville, was considered inaccurate due to the limited number of ethnic groups represented. However, with the advancements of machine learning and programming capabilities as well as the ubiquity of DNA testing, another more refined program could be created.

### Sources
#### Howells Dataset
- Howells Database Website (Dr. Auerbach at UT-Knoxville): https://web.utk.edu/~auerbach/HOWL.htm
- Howells WW. 1973. Cranial Variation in Man. A Study by Multivariate Analysis of Patterns of Differences Among Recent Human Populations. Papers of the Peabody Museum of Archeology and Ethnology, vol. 67, pp. 259. Cambridge, Mass.: Peabody Museum.
- Howells WW. 1989. Skull Shapes and the Map. Craniometric Analyses in the Dispersion of Modern Homo. Papers of the Peabody Museum of Archaeology and Ethnology, vol. 79, pp. 189. Cambridge, Mass.: Peabody Museum.
- Howells WW. 1995. Who’s Who in Skulls. Ethnic Identification of Crania from Measurements. Papers of the Peabody Museum of Archaeology and Ethnology, vol. 82, pp. 108. Cambridge, Mass.: Peabody Museum.

#### Caesarea Maritima Craniometric Dataset
- McChesney S. 2012. Senior Research Project. Unpublished.