# project4

## Jeopardy!: Categorizing Clues

**Created by Will Stith**  
**08/22/2020**

**Introduction**

This folder contains files comprising my fourth project for Metis. The project features natural language processing and unsupervised learning as tools for creating categories for clues from the TV trivia game show Jeopardy! The data was obtained from https://www.kaggle.com/tunguz/200000-jeopardy-questions. The main work for the project is found in a single Jupyter Notebook file, which contains code for cleaning the data and applying several different natural language processing techniques. A corpus was created from the dataset by combining each question-answer-category set into individual "documents". The final corpus contains just over 100,000 documents. Both term frequency-inverse document frequency (TF-IDF) and CountVectorizer were tried for tokenizing and vectorizing the corpus, and Latent Dirichlet Allocation (LDA) and non-negative matrix factorization (NMF) were both tried for topic modeling. TF-IDF and NMF were clearly superior with regards to producing a collection of mostly interpretable topics, or categories. The final model produced 25 topics into which each clue can be grouped based on greatest score on the document-topic matrix. In addition to the topic modeling, this project includes functions for a basic data application by which one can obtain the most "similar" questions to a given question, to theoretically be used to optimize practice on areas of deficient knowledge.

**Requirements**

Python 3.?
Necessary modules (listed below)

**Necessary modules**

- pickle
- pandas
- matplotlib
- numpy
- sklearn
- copy
- random
- re
- string
- nltk

In addition, nltk's preconstructed stopword list must be downloaded. This can be done by running the following line after importing nltk:

nltk.download('stopwords')

**Data**

The data was downloaded from Kaggle at https://www.kaggle.com/tunguz/200000-jeopardy-questions. The dataset was originally created by webscraping J! Archive, a fan-run website cataloguing every Jeopardy! match. Each row of the dataset includes a single question from the show, along with the category, correct answer, original airdate, dollar value on the show, show number, round (Jeopardy! or Double Jeopardy! or Final Jeopardy!). Some episodes are missing from the dataset, and a considerable portion of the clues are media-based (picture, video, or audio), referenced with a web link. These clues were excluded from this analysis.

**Contents**

*project4_jeopardy.ipynb* - contains all code used in this project, including data cleaning, trying out several vectorizers and topic models, and a final application for obtaining questions most similar to another.  
*project4_final_categories* - text file listing the 25 topics obtained in the final analysis, including topic labels and the top 20 terms associated with each topic.  

**Instructions**

Download data from Kaggle at https://www.kaggle.com/tunguz/200000-jeopardy-questions. Follow the instructions in the project4_jeopardy.ipynb notebook to clean data, preprocess it for modeling, and model it. The get_q function is a simple function used to obtain a random question from the dataset. I suggest repeating this until a question stumps you. When that happens, the get_closest_qs function can be used to generate a quiz of specified length based on questions most similar to the one that stumped you. This quiz consists of questions and their associated ID in the dataframe. In order to check answers, simply run the following line:  
jdf_qanda['answer'][<num>]
where <num> corresponds to the question ID.   Theoretically, this should help keep a user focused on learning topics similar to those they don't already know.

**Acknowledgements**

Thank you to all my Metis instructors and TAs for their support and guidance for this project and others. Additionally, I'd like to thank my fellow Metis students for contributing to a supportive, productive, and constructive learning environment. Special thanks to Bojan Tunguz for making the data available on Kaggle, as well as to the many fans responsible for the wonderful resource that is J! Archive and to Sony Pictures Television for allowing it to remain online. Finally, I would like to thank Roger Craig for developing and presenting on his own Jeopardy! training app, which served as an inspiration for many parts of this project.
    J! Archive - https://j-archive.com/
    Kaggle data download - https://www.kaggle.com/tunguz/200000-jeopardy-questions
