# Boosting Showdown — XGBoost vs LightGBM vs CatBoost

A hands-on comparison of three gradient boosting algorithms on the 
Adult Census Income dataset (32K rows, 8 categorical features).

## Results

| Model    | Accuracy | F1 Score | AUC-ROC | Train Time |
|----------|----------|----------|---------|------------|
| XGBoost  | 0.8191   | 0.6895   | 0.9181  | 0.45s      |
| LightGBM | 0.8185   | 0.6885   | 0.9186  | 0.43s      |
| CatBoost | 0.8165   | 0.6905   | 0.9180  | 19.62s     |

## Key Insight

All three models achieved nearly identical AUC-ROC of 0.918.
The real differences were in training speed and preprocessing effort:

- XGBoost — requires manual label encoding, depth-wise tree growth
- LightGBM — fastest training, leaf-wise growth, bin-bucket categorical handling
- CatBoost — zero preprocessing needed, native ordered encoding, 
  best recall on minority class but slowest training time

## Dataset

Adult Census Income Dataset — UCI Machine Learning Repository  
Available on Kaggle: https://www.kaggle.com/datasets/uciml/adult-census-income

## Project Structure

boosting-showdown/
│── adult.csv
├── boosting_showdown_xgb_lgbm_catboost.ipynb
├── Notes.txt
└── README.md

## Libraries Used

- Python 3.x
- XGBoost
- LightGBM
- CatBoost
- Scikit-learn
- Pandas
- NumPy
- Matplotlib
- Seaborn

## When to Use Which

| Situation                        | Best Model |
|----------------------------------|------------|
| Heavy categorical data           | CatBoost   |
| Speed critical production system | LightGBM   |
| Need community support           | XGBoost    |
| Large dataset with GPU           | LightGBM   |
| Small dataset                    | CatBoost   |

## Author

Adesh Srivastava  
B.E. Information Technology — Saraswati College of Engineering, Mumbai  
GitHub: https://github.com/AdeshSrivastava-06  
LinkedIn: https://linkedin.com/in/adesh-srivastava-038a2037a
