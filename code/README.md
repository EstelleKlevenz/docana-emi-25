# History of a scattered analysis due to enormous sample size:

Please read to be able to follow:

## Step 1:

**File:** `preprocessing_EMI/PreprocessingEMI.ipynb` <br>
**Contains:** Looking into the dataset and choosing a subset, the preprocessing and cleaning of the posts, & calculation EMI scores of the post and the tldr.  
**Output:** tldr_cleaned_sample data set (too big to upload) and `tldr_cleaned.csv` with the EMI scores for post and tldr, `selection_emi_expect.pkl`

## Step 2 (keyword experiment):

**File:** `preprocessing_EMI/EMI_dict.ipynb`<br>
**Needs:** tldr_cleaned_sample<br>
**Contains:** Analysis of existing dict and creation of new, calculating EMI scores based on tldr_cleaned_sample and new dicts  
**Output:** `evidence_set_final.pkl`, `intuition_set_final.pkl`, tldr_cleaneds_sample_dict (too big to upload)

## Step 3 (BERT experiment):

**File:** `visualisation/AnalysisVisualisation_BERT.ipynb`<br>  
**Contains:** Calcualtion of BERT embeddings, taking the cleaned samples from tldr_cleaned_sample (only post and again subsample, because it took so long) and calculating the EMI scores.  
**Output:** `emi_bert.csv` and `emi_bert_estelle_sample.csv` with id and emi_bert; BERT embeddings are not stored in the remote repository due to their size

## Step 4 (separate visual analysis):

**File:** `visualisations/AnalysisVisualisation_base.ipynb`<br>
**Contains:** Wordclouds with coloring by EMI score, words with highest EMI scores & PCA of subreddit average vectors for the base version (It will not run without the corresponding word2vec model, which again is too big to be uploaded, but technically can be produced in the PreprocessingEMI.ipynb).  
**Output:** colorful fun to be found in the report

**File:** `visualisations/AnalysisVisualisation_dict.ipynb` <br>
**Contains:** same as for AnalysisVisualisation_base.ipynb but with values of model that is trained with own keyword lists<br>
**Output:** `tldr_emi_dict.csv` with the EMI scores & colorful fun to be found in the report

## Step 5 (comparisons):

**File:** `visualisations/EMI_visualisation.ipynb` <br>
**Contains:** merging all the EMI scores together via id, saving them as a .csv-file together & making nice visualisations of this.  
**Output:** nothing but colorful fun to be found in the report

## Also here:

**File:** `visualisations/PresentationGraphics.ipynb`<br>
**Needs:** `evidence_set_final.pkl`, `intuition_set_final.pkl`  
**Contains:** code for 2 wordclouds for the presentation slides  
**Output:** nothing but colorful fun to be found in the slides
