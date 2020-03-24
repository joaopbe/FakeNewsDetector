

# Fake News - Cleaning Online Media with Machine Learning
*João Pedro Eira*

## Content
- [Project Description](#project-description)
- [Hypotheses / Questions](#hypotheses-questions)
- [Dataset](#dataset)
- [Cleaning](#cleaning)
- [Analysis](#analysis)
- [Model Training and Evaluation](#model-training-and-evaluation)
- [Conclusion](#conclusion)
- [Future Work](#future-work)
- [Workflow](#workflow)
- [Organization](#organization)
- [Links](#links)

## Project Description

This project aims to develop a Machine Learning algorithm to detect fake news in the English language.
Several classifiers are testes together with bag of words processing of the text.

## Hypotheses / Questions

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

After that, six classifiers are tested hypertuned and cross-validated - Naive-Bayes, Logistic Regression, SVM with Linear Kernel, Decision Tree, Random Forest and Gradient Boosting. They are evaluated using Accuracy, Precision, Recall and F1-score metrics.


## Model Training and Evaluation
*Include this section only if you chose to include ML in your project.*
* Describe how you trained your model, the results you obtained, and how you evaluated those results.

## Conclusion
* Summarize your results. What do they mean?
* What can you say about your hypotheses?
* Interpret your findings in terms of the questions you try to answer.

## Future Work
Address any questions you were unable to answer, or any next steps or future extensions to your project.

## Workflow
Outline the workflow you used in your project. What were the steps?
How did you test the accuracy of your analysis and/or machine learning algorithm?

## Organization
How did you organize your work? Did you use any tools like a trello or kanban board?

What does your repository look like? Explain your folder and file structure.

## Links
Include links to your repository, slides and trello/kanban board. Feel free to include any other links associated with your project.


[Repository](https://github.com/)  
[Slides](https://slides.com/)  
[Trello](https://trello.com/en)  
