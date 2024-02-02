# Tweet Customer Service NLP
LSTM based sentiment analysis for customer service tweets. Initial sentiment for model training is based on VADER compound score.
- 3 different classes (positive/neutral/negative)
- Able to detect emojis (👿, 😊, etc)
- Based on 88171 tweets from various customer support (using stratified undersampling)
- Around 85% prediction accuracy

Obviously, VADER  is still better (if the tweets are in English), but LSTM can be trained in other languages as well without much effort.

## Example Predictions
The array is representing prediction confidence for each class (from left: positive, neutral, negative).
```
Input: Your customer service is awful
LSTM -> [0.00861 0.38315 0.60824] Negative
VADER -> Neutral 

Input: Your customer service is awful 👿
LSTM -> [0.00864 0.36702 0.62434] Negative
VADER -> Negative 

Input: Your customer service is ok
LSTM -> [0.04808 0.9392  0.01271] Neutral
VADER -> Neutral 

Input: Your customer service is good
LSTM -> [0.22569 0.65428 0.12003] Neutral
VADER -> Neutral 

Input: Your customer service is good 😊
LSTM -> [0.98203 0.0172  0.00077] Positive
VADER -> Positive 
```

## Source Dataset
[Customer Support on Twitter](https://www.kaggle.com/datasets/thoughtvector/customer-support-on-twitter) (Kaggle)