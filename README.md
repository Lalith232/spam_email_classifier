# Spam Classifier

A simple spam detector that classifies SMS/email text as **spam** or **ham** (not spam) using a Naive Bayes model.

## Files

- `spam.csv` - The dataset. Each row contains an email text and its label (`spam` or `ham`).
- `spam_classifier_py.ipynb` - Jupyter notebook that loads the data, trains the model, and evaluates it.

## How it works

1. Load the dataset and keep the `text` and `spam` columns.
2. Convert the labels to numbers (`spam` = 1, `ham` = 0).
3. Split the data into 80% training and 20% testing.
4. Convert the text into word counts with `CountVectorizer`.
5. Train a `MultinomialNB` (Naive Bayes) model.
6. Predict on the test set and print the accuracy and classification report.

## Results

On the test set (1,146 messages):

- **Accuracy:** about 98.8%
- **Spam precision / recall:** 0.98 / 0.97

## Requirements

- Python 3.8+
- pandas
- scikit-learn

Install them with:

```bash
pip install pandas scikit-learn
```

## How to run

### Option 1: Google Colab

The notebook was written for Google Colab. Upload `spam.csv` to the `sample_data` folder in Colab, then run the notebook.

### Option 2: Run locally

1. Download this repository, or clone it:
   ```bash
   git clone https://github.com/your-username/spam-classifier.git
   cd spam-classifier
   ```
2. Open `spam_classifier_py.ipynb` in Jupyter, or convert it to a Python script.
3. In the cell that loads the data, change this line:
   ```python
   df = pd.read_csv("/content/sample_data/spam.csv", encoding="latin-1")
   ```
   to:
   ```python
   df = pd.read_csv("spam.csv", encoding="latin-1")
   ```
4. Run all cells.

The `encoding="latin-1"` setting is needed because the file contains characters that the default UTF-8 encoding cannot read.
