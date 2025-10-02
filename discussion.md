## What is the scientific problem? What are the challenges in this problem?

---

## What method will you use to classify the samples (we provide a Neural Network example in the week 5 notebook)? This will require a short justification and a description of the method. What are the advantages and disadvantages of your method over alternative options? If you choose NN based architectures over alternative ML models, what are the implications? Is your choice of architecture interpretable? Why, why not? Does it matter?

The method chosen for classification is a decision tree. Decision trees are a type of supervised ML algorithm that
can be used for both classification and regression tasks. They work by splitting the data into subsets based on the
values of the input features. This algorithm was chosen because the results are very easily interpretable. The
decision tree can be visualised, and the rules used to make predictions can be easily understood. This interpretability
is important in the context of cancer classification, as it allows for insights into the biomarkers and features that
are most relevant and allows for biological interpretation.

A disadvantage of decision trees is that they are more sensitive to noise or changes in the data than other algorithms.
This is because of the usage of absolute thresholds to split the data unlike other algorithms like neural networks or
regression which use a continuous functions. Another disadvantage is that decision trees can be prone to overfitting.
However, this overfitting can be measured with a combination of metrics and be controlled to some extent with
regularisation techniques such as pruning, setting a maximum depth, or requiring a minimum number of samples at a leaf
node.

---

## How will you split your data for training and testing. Ensure you have a hold out test set, independant of your training data. (This is not the mystery dataset)

The data was split into training and testing sets using an 80/20 split, with 80% of the data used for training and 20%
for testing. The split was performed using stratified sampling to ensure that the proportion of "Primary Tumor" and
"Solid Tissue Normal" samples was maintained in both the training and testing sets.

No validation set was used, as the available data was limited and the initial results were promising, suggesting that
the model was not overfitting.

---

## What normalisation did you perform before putting the data through your model? Describe how you normalised each data type and why you normalised it in a certain way - plots would provide a sufficent justification here. Normalisation methods covered in week 6 were: standardising, min-max scaling, and log2 transformation

No normalisation was performed on the data before training the decision tree. This is because decision trees are not
sensitive to the scale of the input features.

---

## How many features (i.e. genes or CpGs) is a sensible choice for each of your feature sets? What happens when you increase the number of genes or CpGs to your "performance"? Examples of feature selection could be: choosing X genes based on the literature, choosing the top X most variable genes, or the X genes with the largest log fold change. When considering the choice of X (e.g. number of genes or CpGs) think about the number of training examples you have.

---

## What are good metrics for "performance"? Is it "accuracy"? Or "sensitivity"? Or another metric? You will need to choose and justify this.

A combination of accuracy and F1-score were used to evaluate the performance of the model. Accuracy allows for an
overall measure of how well the model is performing, while F1-score provides a more balanced measure that takes
into account both precision and recall. Ultimately, the F1-score was prioritised when evaluating the model's performance.

F1-score is less sensitive to class imbalance than accuracy, which is important in this case as the dataset has a
significant class imbalance of about 88% towards "Primary Tumor" samples.

---

## How does each of your models perform on the mystery dataset? Why does it perform worse/better than on the dataset you used for training?

---

## What are the limitations of your experimental design and model? Do you expect your model to generalise well, and why? How would you improve the design of this experiment in the future?

---

## What difference in performance do you notice between the two data modalities? How do you relate this difference to your biological understanding of the problem/data?

---