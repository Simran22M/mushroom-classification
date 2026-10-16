# Mushroom Classification: Edible or Poisonous?

## Project Overview
This project builds a machine learning model that predicts whether a
mushroom is edible or poisonous from its physical features (odor, cap
shape, gill size, etc.). Identifying poisonous mushrooms correctly is
important for safety. I compared two models: Decision Tree and K-Nearest
Neighbors (KNN).

## Dataset
- UCI Mushroom Dataset: [(https://www.kaggle.com/datasets/uciml/mushroom-classification?resource=download)]
- 8,124 mushrooms, 22 features, 1 target (`class`: e = edible, p = poisonous)
- No missing values found

## Setup Instructions
1. Clone this repository:
   `git clone (https://github.com/Simran22M/mushroom-classification)`
2. Install the required libraries:
   `pip install pandas numpy matplotlib seaborn scikit-learn`
3. Open `mushroom_classification.ipynb` in Jupyter Notebook or Google Colab.
4. Make sure `mushrooms.csv` is in the same folder, then run all cells.

## Methodology
1. Loaded the data and checked for missing values
2. Separated features (X) and target (y), and one-hot encoded the features
3. Split into 80% training and 20% testing sets
4. Trained a Decision Tree and a KNN (k = 5) model
5. Evaluated with accuracy and confusion matrices

## Results
| Model         | Accuracy |   False Negatives |
| Decision Tree | 1.0      |                 0  |
| KNN (k=5)     | 1.0      |                 0   |

5-fold cross-validation mean: Decision Tree [0.996182796513831], KNN [0.9133194391815082]

## Conclusion
Both the Decision Tree and KNN achieved 100% accuracy on the test set with
zero false negatives, so neither was better in terms of accuracy. This is
because the mushroom dataset has strongly separable features such as odor.
5-fold cross-validation gave mean scores of 0.996182796513831 (Decision Tree)
and 0.9133194391815082 (KNN).

The Decision Tree is preferable overall because it is easy to interpret,
shows which features matter most (top feature: odor_n), and
was faster. KNN also performed perfectly but stores
all the training data and compares every new mushroom against it.

What I learned: how to check and prepare data, encode categorical
features, split data into train and test sets, build and compare two models,
and read a confusion matrix, where false negatives matter most for safety.
