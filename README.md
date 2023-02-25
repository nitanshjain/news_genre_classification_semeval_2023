# SemEval 2023 - Task 3 - "DETECTING THE GENRE, THE FRAMING, AND THE PERSUASION TECHNIQUES IN ONLINE NEWS IN A MULTI-LINGUAL SETUP"
## Team Name - MLModeler5
## Subtask 1 - News Genre Categorisation

Aim of Subtask 1 - Definition: given a news article, determine whether it is an opinion piece, aims at objective news reporting, or is a satire piece. This is a multi-class (single-label) task at article-level.

Training and Validation Languages Provided 
* English
* French
* Italian
* German
* Polish
* Russian

Testing Languages Provided
* English
* French
* Italian
* German
* Polish
* Russian
* Greek
* Georgian
* Spanish

This repository focuses on News Genre Categorisation of only the Articles in the English language
### Methodology

#### Metrics
Subtask 1 focused primarily on F1 Macro score and secondly on F1 Micro score.

#### Data Preprocessing
* Translated Non-English Training and Validation Dataset to English to increase the dataset. Translation was done using GoogleTranslator library.
* Merged the all the translated training and validation dataset not including the English validation Dataset and then performed under sampling.
* Further performed Text Augmentation using the "nlpaug" library to increase the dataset.
* Performed basic Data Preprocessing using spacy and nltk to remove punctuations and white space. Also performed Lemmatization and extracted POS and ER tags.

#### Model Building
* Initially implemented basic ML models like KNN, Logistice Regression, etc on word embeddings using tfidf and word2vec.
* Implemented CNN-LSTM on word embeddings using tfidf and word2vec.

Since we didn't achieve decent results using these models, we used BERT based architectures - RoBERTa and ALBERT.

* Implemented RoBERTa and ALBERT, converted data to RoBERTa or ALBERT based word embeddings to be used by the RoBERTa or ALBERT models respectively.

### Results
Achieved a ranking of 2 in English Subtask 1 Task 3 Semeval 2023. The results in the official submission were as follows : 
```
F1 Macro - 0.61632 & F1 Micro - 0.62963
```
Post official submissions, I changed the class weights to accurately represent the trainig data use and the results improved as follows : 
```
F1 Macro - 0.66077 & F1 Micro - 0.70370
```
### Relevant Links
[SemEval 2023 Task 3 Website](https://propaganda.math.unipd.it/semeval2023task3/index.html) \
[SemEval 2023 Task 3 Leaderboard Link](https://propaganda.math.unipd.it/semeval2023task3/leaderboard.php)


