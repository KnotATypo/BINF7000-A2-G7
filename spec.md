## Part 4: Group Project

### Problem C1

Investigate the predictive power of DNA methylation as compared with RNA-seq, in terms of classifying patient samples as either "Primary Tumor" or "Solid Tissue Normal". 

The primary question is: Which data type "performs" better? We will provide each group with a cancer dataset (there may be a few groups with similar datasets). 

You will need to train two machine learning models: 1 on DNA methylation data, and 1 on gene expression data (it can be the same model/architecture just trained on different data). Your report will investigate which of the two models performed better.

#### Each group will have 2 sets of data from a **specific tissue** with:
1. Gene expression data for samples along with a label of either "Solid Tissue Normal" or "Primary Tumor"
2. DNA methylation beta values for samples along with a label of either "Solid Tissue Normal" or "Primary Tumor"

#### A shared mystery dataset will also be available
3. A mystery **DNA methylation** dataset and a mystery **Gene Expression** dataset (for the final testing). In this dataset we don't say which tissue (or tissues) the samples come from so may be harder to classify the samples. Again the samples will have a label of either "Solid Tissue Normal" or "Primary Tumour". This dataset is used to assess how well your model generalises beyond your training and test splits in your data.

### As part of this experiment you will need to think about the following in your methodological decisions and discussion:
- What is the scientific problem? What are the challenges in this problem?
- What method will you use to classify the samples (we provide a Neural Network example in the week 5 notebook)? This will require a short justification and a description of the method. What are the advantages and disadvantages of your method over alternative options? If you choose NN based architectures over alternative ML models, what are the implications? Is your choice of architecture interpretable? Why, why not? Does it matter?
- How will you split your data for training and testing. Ensure you have a hold out test set, independant of your training data. (This is not the mystery dataset)
- What normalisation did you perform before putting the data through your model? Describe how you normalised each data type and why you normalised it in a certain way - plots would provide a sufficent justification here. Normalisation methods covered in week 6 were: standardising, min-max scaling, and log2 transformation
- How many features (i.e. genes or CpGs) is a sensible choice for each of your feature sets? What happens when you increase the number of genes or CpGs to your "performance"? Examples of feature selection could be: choosing X genes based on the literature, choosing the top X most variable genes, or the X genes with the largest log fold change. When considering the choice of X (e.g. number of genes or CpGs) think about the number of training examples you have.
- What are good metrics for "performance"? Is it "accuracy"? Or "sensitivity"? Or another metric? You will need to choose and justify this.
- How does each of your models perform on the mystery dataset? Why does it perform worse/better than on the dataset you used for training?
- What are the limitations of your experimental design and model? Do you expect your model to generalise well, and why? How would you improve the design of this experiment in the future?
- What difference in performance do you notice between the two data modalities? How do you relate this difference to your biological understanding of the problem/data?

### General tips for the report
- We really evaluate you based on your decision making and the justification of these decisions. This means the discussion is very important. This is where you will contextualise your experiment and show your understanding! Pay most attention to this section while answering some of the questions we suggest above.
- The performance of your model is not a major consideration for your final grade! We don't care if you get 100% for your chosen metrics. We are interested in the design of your experiment and the clarity and depth of the report.
- Be careful not to violate any major machine learning experimental design rules. I.e. don't train with your test data!
- Make sure you understand the purpose of the datasets we have provided (train,mystery) in terms of your experimental design.
- The previous sections give a good indication of the things we would like you to discuss but this is definitely not exhaustive. Additionally, it is not feasible to cover all the topics that we listed, so make sure you think about what topics are most relevant to your specific project.
- Treat the conclusion a bit like a very short abstract. Communicate what you did and the key findings.

### Dataset information

1) breast = samples from the breast cancer cohort from TCGA (BRCA)  
2) colon = samples from the colon cancer cohot from TCGA (COAD)  
3) kidney = samples from the kidney cancer cohort from TCGA (KIRC)  
4) liver = samples from the liver cancer cohort from TCGA (LIHC)  
5) lung = samples from the lung cancer cohort from TCGA (LUAD)  

The datasets labelled: dna-meth are the DNA methylation datasets and contain beta values for select CpG probes from the Illumina HumanMethylation450 BeadChip.
The datasets labelled: gene-expr are the gene expression datasets and contain RPKM values for each gene.


The columns of the dataset are the gene names followed by the entrez ID e.g. genename.entrezID (`AADAC.13`),  if the gene doesn't have a name it will be replaced by a dot (e.g. `..100130426` but you can still seach for the entrez id: e.g https://www.ncbi.nlm.nih.gov/gene/100130426). The first column of the dataset is the sample ID e.g. `TCGA.A3.3307.01` and the second column is the label e.g. `Primary Tumor`. The CpGs are labelled by their identifier which you can find information for in the provided annotation file: `CpG_hg19_annot.csv`.

Datasets were downloaded from: http://acgt.cs.tau.ac.il/multi_omic_benchmark/download.html  

Supplemental Papers:  
https://www.nature.com/articles/s41467-020-20430-7  
https://academic.oup.com/nar/article/46/20/10546/5123392  