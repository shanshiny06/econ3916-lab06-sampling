# econ3916-lab06-sampling
# Sampling for Machine Learning — Train-Test Splits

## Objective
I studied how the way a sample is drawn, rather than how large it is, affects the accuracy of a model's evaluation and of a survey estimate.

## Methodology
- I explored the Titanic dataset, which has 891 passengers, with survival as the target variable.
- I split the data into training and test sets two ways, a naive random split and a stratified split, and checked that stratifying kept the survival rate the same in both halves.
- I found data leakage in a StandardScaler step and a SimpleImputer step, where each was fitted on the full dataset before splitting, and fixed it by fitting them on the training set only.
- I wrote a function, `split_by_share()`, that splits a table using a test share and a random seed, and checked its output against the lab's own split.
- I simulated the 1936 Literary Digest polling failure using a population of 10 million voters.
- I computed Meng's data defect correlation for the biased sample and compared a biased sample of [YOUR VALUE] responses with a random sample of 50,000.
- I ran 100 replications comparing the biased sample and the random sample to see how consistent the difference was.

## Key Findings
- Stratifying the train-test split kept the survival rate the same in the training and test sets, which the naive split did not guarantee.
- Fitting the scaler and imputer before splitting let information from the test set leak into training. Fitting them on the training set only removed that leak.
- My `split_by_share()` function matched the lab's own split.
- Sample design beats sample size. The biased sample of [YOUR VALUE] responses was less accurate than the random sample of 50,000, even though it was larger.
- A data defect correlation of [YOUR VALUE] produced an error of [YOUR VALUE] percentage points, and the 100 replications showed the same pattern each time.
