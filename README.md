
<img src="https://github.com/joaopbe/FakeNewsDetector/blob/master/Presentation/pp_title.png" alt="Fake News" width="500" align="middle" />


# Fake News - Cleaning Online Media with Machine Learning
*João Pedro Eira*

## Content
- [Project Description](#project-description)
- [Questions](#questions)
- [Dataset](#dataset)
- [Cleaning](#cleaning)
- [Analysis](#analysis)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [Links](#links)

## Project Description

This project aims to develop a Machine Learning algorithm to detect fake news in the English language.
Several classifiers are testes together with bag of words processing of the text.

## Questions

Given a news defined bu it´s title and text determine if the news is a real news article or fake news.

Fake news is one of the great plagues of the modern fully connected age. They are now back on the spotlight in the context of the COVID-19 crisis, as rumours spread even faster than the virus. To be able to effectively identify and eliminate fake news is paramount to any democracy.

To approach this issue using Machine Learning a Bag of Words approach is used, and the text is first vectorized. Then several classifiers are tested and tuned to find the optimal model.

## Dataset

The original data to train/test the models is obtained from two Kaggle datasets. You can find them [here](https://www.kaggle.com/snapcrack/all-the-news) and [here](https://www.kaggle.com/mrisdal/fake-news). Both datasets include the article text and title.

Additionaly, a small more recent data set of COVID 19 news was used to test the model performance with news from a different context and timeline of the original data. This data is included in the file 'corona_fake.csv' included in this repository.

## Cleaning
The data sets required some cleaning for missing entries. The process used is described in detail in the notebooks. Also, since the size was very unbalanced (150K entries versus 12K), the "true news" data set was sampled so that a balanced training set was used for the model.

## Analysis

The first step in the project is process the text - cleaning punctuation, tokenizing, stemming, lemmatization and stop word removing followed by vectorization and tf-idf transforming.

This was done with a combination of nltk and sklearn library implementations.

After that, six classifiers are tested, hypertuned and cross-validated - Naive-Bayes, Logistic Regression, SVM with Linear Kernel, Decision Tree, Random Forest and Gradient Boosting. Then they are evaulted on the test set - using Accuracy, Precision, Recall and F1-score metrics.

For each classifier 3 feature configurations were tested - only title of the article, only the text (full article) or both text and title used as features.

All models were tested using sklearn implementations of the models.

Results show that:

  - Using the full text of the article leads to better (6-8% depending on the model) results than using only the title
  - Using both text and title at the same time does not show sensible improvement, and, depending on the model, may even show worse results than using only the text
  - The best model overall is Logistic Regression using the text as a feature and a regularization parameter C=10, which produces an accuracy of 93.11% and an F1-Score of 0.93.

  - Tested on a different dataset (COVID-19 news) the model still shows an high accuracy - 85%.

## Conclusion

- Results show a very high accuracy using a very simple model - Logistic Regression. The model is relatively computer-processing inexpensive.
- The more rich text article produces significantly better results, meaning the model can infer more "meaning" from the full text than when using just the title.
- The model reveals robustness to a different data set.


## Future Work
- Test the model with a bigger and more rich recent dataset, filled with different news cycles. Analyse results and retrain acoordingly.
- Test new approaches - deep learning, LTSM,...
- Extend to Fake "audio news" and "video" - Get text from audio and video and use the models to infer fake/true news.
- Integrate with online platforms for automatic detection and elimination of fake contents.

## Links

[Repository](https://github.com/joaopbe/FakeNewsDetector)  
[Slides](https://github.com/joaopbe/FakeNewsDetector/blob/master/Presentation/Fake_News.pptx)  
