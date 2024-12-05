### Setup
Python Version: 3.11.3

Install python dependencies:
```bash
pip install -r requirements.txt
```


### Dataset Fetching
The dataset is already downloaded and extracted from Kaggle in the `bible_data` folder. The
dataset is available at [Kaggle](https://www.kaggle.com/oswinrh/bible).

If you want to download it you can run the `fetch_kaggle_dataset.ipynb` notebook to download and extract the dataset. 
You will need to replace your username and kaggle api key in the notebook. However all the below notebooks can run
without downloading the dataset as it is already included in the repo.

### Initial Dataset Training
To recreate the initial dataset training from jcharis and their GitHub repo here: [jcharis](https://github.com/Jcharis/Bible-NLP-and-ML-using-Python)
You can run the initial_classifier.ipynb notebook. This trains a very basic logistic regression classifier 
using only the King James Version of the Bible and it is a limited data set that is located in the `data/kjvdata.csv`

### Baseline Training and Move to Kaggle Dataset w/ Additional Translations
To train the baseline models which uses the kaggle dataset with additional translations you can run the notebook `kaggle_initial_classifier.ipynb`

### Final Model Training
To train the final models (RNN, CNN and RCNN) you can run the notebook `kaggle_final_classifier.ipynb` which will train and output 
the following:
- RNN Model
- CNN Model
- RCNN Model
- accuracy/loss data in JSON format
- accuracy/loss in PNG format for model type and task (author, book, translation)
- confusion matrix for model type and task (author, book, translation)
- print a classification report
- overall model accuracies in JSON format
- plot combined accurcy/loss png for each model type

**Note this does take awhile and you can reduce epochs and/or tasks to reduce time.

### Utility Notebooks
There are also utility notebooks to combine confusion matrices by running: `combine_confusion_matrices.ipynb` 
This will simply combine the confusion matrices for each model type and task (author, book, translation) into one confusion matrix.

### Early Experimental Notebooks
There are also early experimental notebooks that were used during testing in the `experimental_notebooks` folder. These
were not used in the final models but did help in learning / understanding different models. They can all be run as individual notebooks.

### Dataset Analysis
In order to run the dataset analysis you can run the notebook `dataset_analysis.ipynb` which will output the following:
- translation counts
- translation distribution
- book counts
- book distribution
- author counts
- author distribution
- verse length
- verse length distribution
- book proportions
- book class imbalance
- author proportions
- author class imbalance